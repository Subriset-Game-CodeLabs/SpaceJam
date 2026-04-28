# Unity ML-Agents Toolkit

The Unity Machine Learning Agents Toolkit (ML-Agents) is an open-source project that enables games and simulations to serve as environments for training intelligent agents using reinforcement learning, imitation learning, and other machine learning methods. It provides a comprehensive bridge between Unity game engine environments and PyTorch-based training algorithms, allowing developers to create intelligent NPCs, automate testing, and evaluate game design decisions through AI-driven simulation.

The toolkit consists of three main components: a Python training framework built on PyTorch that implements state-of-the-art algorithms (PPO, SAC, MA-POCA), a Unity C# SDK that integrates seamlessly into game projects, and a gRPC-based communication protocol that connects the two. This architecture enables multiple concurrent Unity instances to generate training experiences in parallel, supports multi-agent scenarios with both cooperative and competitive behaviors, and provides flexible observation types including vector data, visual inputs from cameras, and raycasting sensors.

## Training Agents with Python API

```python
from mlagents_envs.environment import UnityEnvironment
from mlagents_envs.base_env import ActionTuple
from mlagents_envs.side_channel.environment_parameters_channel import EnvironmentParametersChannel
import numpy as np

# Create environment connection
env = UnityEnvironment(
    file_name="./Build/MyGame.exe",  # Path to Unity executable, or None for Editor
    worker_id=0,                      # Unique ID for parallel environments
    base_port=5005,                   # Communication port
    seed=42,                          # Random seed
    no_graphics=True,                 # Headless mode for faster training
    timeout_wait=60                   # Connection timeout
)

# Register side channel for runtime parameter control
params_channel = EnvironmentParametersChannel()
env.register_side_channel(params_channel)

# Reset environment
env.reset()

# Get behavior names (each behavior represents a group of agents)
behavior_names = list(env.behavior_specs.keys())
behavior_name = behavior_names[0]

# Get behavior specification (observation/action space)
spec = env.behavior_specs[behavior_name]
print(f"Observation shapes: {[obs_spec.shape for obs_spec in spec.observation_specs]}")
print(f"Action spec: {spec.action_spec.continuous_size} continuous, "
      f"{spec.action_spec.discrete_branches} discrete")

# Training loop
for episode in range(1000):
    # Set environment parameters dynamically
    params_channel.set_float_parameter("difficulty", episode * 0.01)
    params_channel.set_float_parameter("gravity", 9.8)

    decision_steps, terminal_steps = env.get_steps(behavior_name)

    while len(decision_steps) > 0:
        # Access observations (list of numpy arrays)
        observations = decision_steps.obs
        rewards = decision_steps.reward          # Shape: (num_agents,)
        agent_ids = decision_steps.agent_id      # Shape: (num_agents,)

        # Check for action masking (discrete actions only)
        if decision_steps.action_mask is not None:
            action_masks = decision_steps.action_mask

        # Generate actions (random example)
        num_agents = len(decision_steps)
        continuous_actions = np.random.randn(
            num_agents,
            spec.action_spec.continuous_size
        ).astype(np.float32)

        discrete_actions = np.column_stack([
            np.random.randint(0, branch_size, size=(num_agents,))
            for branch_size in spec.action_spec.discrete_branches
        ])

        # Create action tuple
        actions = ActionTuple(
            continuous=continuous_actions,
            discrete=discrete_actions
        )

        # Send actions to environment
        env.set_actions(behavior_name, actions)

        # Step simulation
        env.step()

        # Get new observations
        decision_steps, terminal_steps = env.get_steps(behavior_name)

        # Process terminal agents
        if len(terminal_steps) > 0:
            final_rewards = terminal_steps.reward
            interrupted = terminal_steps.interrupted  # True if max_steps reached
            print(f"Episode ended: {len(terminal_steps)} agents, "
                  f"avg reward: {final_rewards.mean():.2f}")

# Cleanup
env.close()
```

## Command-Line Training with mlagents-learn

```bash
# Basic training with configuration file
mlagents-learn config/ppo/3DBall.yaml --run-id=first_training_run

# Training with Unity executable (built environment)
mlagents-learn config/ppo/3DBall.yaml \
    --run-id=training_run_001 \
    --env=./Build/MyGame.exe \
    --num-envs=4 \
    --no-graphics

# Resume training from checkpoint
mlagents-learn config/ppo/3DBall.yaml \
    --run-id=training_run_001 \
    --resume

# Force overwrite existing run
mlagents-learn config/ppo/3DBall.yaml \
    --run-id=training_run_001 \
    --force

# Training with custom parameters
mlagents-learn config/ppo/3DBall.yaml \
    --run-id=high_performance \
    --env=./Build/MyGame.exe \
    --num-envs=16 \
    --no-graphics \
    --seed=123 \
    --width=84 \
    --height=84 \
    --quality-level=0 \
    --time-scale=20

# Inference only (no training)
mlagents-learn config/ppo/3DBall.yaml \
    --run-id=inference_test \
    --inference \
    --env=./Build/MyGame.exe
```

## Training Configuration File (YAML)

```yaml
behaviors:
  3DBall:  # Behavior name (must match BehaviorParameters.BehaviorName in Unity)
    trainer_type: ppo  # Options: ppo, sac, poca

    hyperparameters:
      batch_size: 64              # Samples per gradient descent step
      buffer_size: 12000          # Total experience buffer size
      learning_rate: 0.0003       # Initial learning rate
      beta: 0.001                 # Entropy regularization coefficient
      epsilon: 0.2                # PPO clipping parameter
      lambd: 0.99                 # GAE lambda for advantage estimation
      num_epoch: 3                # Number of passes through experience buffer
      learning_rate_schedule: linear  # Options: linear, constant

    network_settings:
      normalize: true             # Normalize vector observations
      hidden_units: 128           # Neurons per hidden layer
      num_layers: 2               # Number of hidden layers
      vis_encode_type: simple     # Options: simple, nature_cnn, resnet, match3
      memory:                     # Optional LSTM memory
        memory_size: 128          # Memory vector size
        sequence_length: 64       # Training sequence length

    reward_signals:
      extrinsic:                  # Environment rewards
        gamma: 0.99               # Discount factor
        strength: 1.0             # Reward scaling
      curiosity:                  # Optional intrinsic motivation
        gamma: 0.99
        strength: 0.01
        encoding_size: 256

    keep_checkpoints: 5           # Number of checkpoints to keep
    max_steps: 500000             # Total training steps
    time_horizon: 1000            # Steps before value estimate bootstrapping
    summary_freq: 12000           # Tensorboard logging frequency
    checkpoint_interval: 50000    # Model save frequency

# Multi-agent example with different behaviors
  Seeker:
    trainer_type: ppo
    hyperparameters:
      batch_size: 128
      buffer_size: 2048
      learning_rate: 0.0003
    network_settings:
      hidden_units: 256
      num_layers: 2
    reward_signals:
      extrinsic:
        gamma: 0.995
        strength: 1.0
    max_steps: 1000000

  Hider:
    trainer_type: ppo
    hyperparameters:
      batch_size: 128
      buffer_size: 2048
      learning_rate: 0.0003
    network_settings:
      hidden_units: 256
      num_layers: 2
    reward_signals:
      extrinsic:
        gamma: 0.995
        strength: 1.0
    max_steps: 1000000

# SAC (Soft Actor-Critic) for continuous control
  RobotArm:
    trainer_type: sac
    hyperparameters:
      batch_size: 128
      buffer_size: 50000
      learning_rate: 0.0003
      tau: 0.005                  # Target network update rate
      init_entcoef: 1.0           # Initial entropy coefficient
    network_settings:
      hidden_units: 256
      num_layers: 2
    reward_signals:
      extrinsic:
        gamma: 0.99
        strength: 1.0
    max_steps: 2000000

# MA-POCA for cooperative multi-agent
  CoopTeam:
    trainer_type: poca
    hyperparameters:
      batch_size: 1024
      buffer_size: 20000
      learning_rate: 0.0003
    network_settings:
      hidden_units: 256
      num_layers: 2
    reward_signals:
      extrinsic:
        gamma: 0.99
        strength: 1.0
    max_steps: 5000000
```

## Creating Unity Agent (C#)

```csharp
using UnityEngine;
using Unity.MLAgents;
using Unity.MLAgents.Actuators;
using Unity.MLAgents.Sensors;

public class Ball3DAgent : Agent
{
    public GameObject ball;
    public bool useVecObs = true;

    private Rigidbody ballRb;
    private EnvironmentParameters resetParams;

    // Called once when agent is first enabled
    public override void Initialize()
    {
        ballRb = ball.GetComponent<Rigidbody>();
        resetParams = Academy.Instance.EnvironmentParameters;
    }

    // Collect vector observations (called before each decision)
    public override void CollectObservations(VectorSensor sensor)
    {
        if (useVecObs)
        {
            // Add 8 observations total
            sensor.AddObservation(transform.rotation.z);                    // 1 float
            sensor.AddObservation(transform.rotation.x);                    // 1 float
            sensor.AddObservation(ball.transform.position - transform.position);  // 3 floats (Vector3)
            sensor.AddObservation(ballRb.linearVelocity);                  // 3 floats (Vector3)
        }
    }

    // Execute actions received from policy
    public override void OnActionReceived(ActionBuffers actionBuffers)
    {
        // Extract continuous actions (size: 2)
        float actionZ = 2f * Mathf.Clamp(actionBuffers.ContinuousActions[0], -1f, 1f);
        float actionX = 2f * Mathf.Clamp(actionBuffers.ContinuousActions[1], -1f, 1f);

        // Apply rotation based on actions
        if ((transform.rotation.z < 0.25f && actionZ > 0f) ||
            (transform.rotation.z > -0.25f && actionZ < 0f))
        {
            transform.Rotate(new Vector3(0, 0, 1), actionZ);
        }

        if ((transform.rotation.x < 0.25f && actionX > 0f) ||
            (transform.rotation.x > -0.25f && actionX < 0f))
        {
            transform.Rotate(new Vector3(1, 0, 0), actionX);
        }

        // Check failure conditions
        if ((ball.transform.position.y - transform.position.y) < -2f ||
            Mathf.Abs(ball.transform.position.x - transform.position.x) > 3f ||
            Mathf.Abs(ball.transform.position.z - transform.position.z) > 3f)
        {
            SetReward(-1f);
            EndEpisode();
        }
        else
        {
            SetReward(0.1f);  // Small reward for keeping ball balanced
        }
    }

    // Reset environment at episode start
    public override void OnEpisodeBegin()
    {
        // Reset platform rotation
        transform.rotation = Quaternion.identity;
        transform.Rotate(new Vector3(1, 0, 0), Random.Range(-10f, 10f));
        transform.Rotate(new Vector3(0, 0, 1), Random.Range(-10f, 10f));

        // Reset ball physics and position
        ballRb.linearVelocity = Vector3.zero;
        ball.transform.position = new Vector3(
            Random.Range(-1.5f, 1.5f),
            4f,
            Random.Range(-1.5f, 1.5f)
        ) + transform.position;

        // Get runtime parameters from Python
        float mass = resetParams.GetWithDefault("mass", 1.0f);
        float scale = resetParams.GetWithDefault("scale", 1.0f);
        ballRb.mass = mass;
        ball.transform.localScale = new Vector3(scale, scale, scale);
    }

    // Manual control for testing (keyboard input)
    public override void Heuristic(in ActionBuffers actionsOut)
    {
        var continuousActionsOut = actionsOut.ContinuousActions;
        continuousActionsOut[0] = -Input.GetAxis("Horizontal");
        continuousActionsOut[1] = Input.GetAxis("Vertical");
    }
}
```

## Advanced Agent with Discrete Actions and Action Masking

```csharp
using UnityEngine;
using Unity.MLAgents;
using Unity.MLAgents.Actuators;
using Unity.MLAgents.Sensors;

public class GridWorldAgent : Agent
{
    public Transform target;
    private Vector3[] moveDirections = new Vector3[]
    {
        Vector3.forward,   // Action 0: Move forward
        Vector3.back,      // Action 1: Move backward
        Vector3.left,      // Action 2: Move left
        Vector3.right,     // Action 3: Move right
        Vector3.zero       // Action 4: Stay in place
    };

    public override void CollectObservations(VectorSensor sensor)
    {
        // Agent position (3 floats)
        sensor.AddObservation(transform.localPosition);

        // Target position (3 floats)
        sensor.AddObservation(target.localPosition);

        // Distance to target (1 float)
        sensor.AddObservation(Vector3.Distance(transform.localPosition, target.localPosition));
    }

    public override void OnActionReceived(ActionBuffers actionBuffers)
    {
        // Get discrete action (single branch with 5 actions)
        int action = actionBuffers.DiscreteActions[0];

        // Move agent
        Vector3 movement = moveDirections[action];
        transform.localPosition += movement * Time.deltaTime * 5f;

        // Reward shaping
        float distanceToTarget = Vector3.Distance(transform.localPosition, target.localPosition);

        // Small penalty for each step
        AddReward(-0.001f);

        // Large reward for reaching target
        if (distanceToTarget < 1.4f)
        {
            SetReward(1.0f);
            EndEpisode();
        }

        // Penalty for going out of bounds
        if (transform.localPosition.y < 0)
        {
            SetReward(-1.0f);
            EndEpisode();
        }
    }

    // Prevent invalid actions (action masking)
    public override void WriteDiscreteActionMask(IDiscreteActionMask actionMask)
    {
        // Disable forward movement if at boundary
        if (transform.localPosition.z > 19f)
        {
            actionMask.SetActionEnabled(0, 0, false);  // Branch 0, Action 0 disabled
        }

        // Disable backward movement if at boundary
        if (transform.localPosition.z < 1f)
        {
            actionMask.SetActionEnabled(0, 1, false);
        }

        // Disable left movement if at boundary
        if (transform.localPosition.x < 1f)
        {
            actionMask.SetActionEnabled(0, 2, false);
        }

        // Disable right movement if at boundary
        if (transform.localPosition.x > 19f)
        {
            actionMask.SetActionEnabled(0, 3, false);
        }
    }

    public override void OnEpisodeBegin()
    {
        // Randomize agent position
        transform.localPosition = new Vector3(
            Random.Range(1f, 19f),
            0.5f,
            Random.Range(1f, 19f)
        );

        // Randomize target position
        target.localPosition = new Vector3(
            Random.Range(1f, 19f),
            0.5f,
            Random.Range(1f, 19f)
        );
    }

    public override void Heuristic(in ActionBuffers actionsOut)
    {
        var discreteActionsOut = actionsOut.DiscreteActions;

        if (Input.GetKey(KeyCode.W)) discreteActionsOut[0] = 0;      // Forward
        else if (Input.GetKey(KeyCode.S)) discreteActionsOut[0] = 1; // Backward
        else if (Input.GetKey(KeyCode.A)) discreteActionsOut[0] = 2; // Left
        else if (Input.GetKey(KeyCode.D)) discreteActionsOut[0] = 3; // Right
        else discreteActionsOut[0] = 4;                              // Stay
    }
}
```

## Unity Inspector Configuration

```csharp
// Attach these components to your Agent GameObject:

// 1. BehaviorParameters Component:
//    - Behavior Name: "3DBall" (must match YAML config)
//    - Vector Observation Space Size: 8
//    - Stacked Vectors: 1
//    - Actions:
//      * Continuous Actions: 2
//      * Discrete Branches: (leave empty)
//    - Model: (drag trained .onnx model here for inference)
//    - Inference Device: CPU or GPU
//    - Behavior Type: Default (or HeuristicOnly for manual control)

// 2. DecisionRequester Component:
//    - Decision Period: 5 (request decision every 5 FixedUpdate calls)
//    - Take Actions Between Decisions: true

// 3. Agent Script (your custom class)

// 4. Optional Sensor Components:
//    - CameraSensorComponent (for visual observations)
//    - RayPerceptionSensorComponent3D (for raycasting)
```

## Multi-Agent Cooperative Training with MA-POCA

```csharp
using UnityEngine;
using Unity.MLAgents;
using Unity.MLAgents.Actuators;
using Unity.MLAgents.Sensors;

public class CooperativeAgent : Agent
{
    public Transform sharedGoal;
    private SimpleMultiAgentGroup agentGroup;

    public override void Initialize()
    {
        // Create multi-agent group
        agentGroup = new SimpleMultiAgentGroup();

        // Find all agents in team and add to group
        var allAgents = FindObjectsByType<CooperativeAgent>(FindObjectsSortMode.None);
        foreach (var agent in allAgents)
        {
            if (agent.sharedGoal == this.sharedGoal)  // Same team
            {
                agentGroup.RegisterAgent(agent);
            }
        }
    }

    public override void CollectObservations(VectorSensor sensor)
    {
        sensor.AddObservation(transform.localPosition);
        sensor.AddObservation(sharedGoal.localPosition);
    }

    public override void OnActionReceived(ActionBuffers actionBuffers)
    {
        float moveX = actionBuffers.ContinuousActions[0];
        float moveZ = actionBuffers.ContinuousActions[1];

        transform.localPosition += new Vector3(moveX, 0, moveZ) * Time.deltaTime * 3f;

        // Check if any agent reached goal
        float distanceToGoal = Vector3.Distance(transform.localPosition, sharedGoal.localPosition);
        if (distanceToGoal < 1.5f)
        {
            // Reward entire group
            agentGroup.AddGroupReward(1.0f);
            agentGroup.EndGroupEpisode();
        }
    }

    public override void OnEpisodeBegin()
    {
        transform.localPosition = new Vector3(
            Random.Range(-10f, 10f),
            0.5f,
            Random.Range(-10f, 10f)
        );
    }
}
```

## Camera Sensor for Visual Observations

```csharp
using UnityEngine;
using Unity.MLAgents;
using Unity.MLAgents.Sensors;

public class VisualAgent : Agent
{
    // No CollectObservations needed - camera provides observations

    public override void OnActionReceived(ActionBuffers actionBuffers)
    {
        float rotation = actionBuffers.ContinuousActions[0];
        float movement = actionBuffers.ContinuousActions[1];

        transform.Rotate(0, rotation * 100f * Time.deltaTime, 0);
        transform.position += transform.forward * movement * 5f * Time.deltaTime;
    }

    // In Inspector, add CameraSensorComponent:
    // - Camera: (assign camera)
    // - Width: 84, Height: 84
    // - Grayscale: true (for faster training)
    // - Compression Type: PNG
}
```

## Ray Perception Sensor

```csharp
using UnityEngine;
using Unity.MLAgents;
using Unity.MLAgents.Sensors;

public class RaycastAgent : Agent
{
    // Add RayPerceptionSensorComponent3D in Inspector:
    // - Detectable Tags: ["wall", "target", "obstacle"]
    // - Rays Per Direction: 3
    // - Max Ray Degrees: 70
    // - Sphere Cast Radius: 0.5
    // - Ray Length: 20
    // - Ray Layer Mask: Default
    // - Observation Stacks: 1

    public override void OnActionReceived(ActionBuffers actionBuffers)
    {
        float rotation = actionBuffers.ContinuousActions[0];
        float movement = actionBuffers.ContinuousActions[1];

        transform.Rotate(0, rotation * 150f * Time.deltaTime, 0);

        Rigidbody rb = GetComponent<Rigidbody>();
        rb.AddForce(transform.forward * movement * 10f);
    }
}
```

## Imitation Learning Configuration

```yaml
behaviors:
  ExpertAgent:
    trainer_type: ppo

    # Behavioral cloning settings
    behavioral_cloning:
      demo_path: demos/ExpertDemos.demo  # Path to recorded demonstrations
      steps: 100000                       # BC pretraining steps
      strength: 0.5                       # BC loss weight
      batch_size: 512
      num_epoch: 3
      samples_per_update: 0               # 0 = use all demo samples

    # GAIL (Generative Adversarial Imitation Learning)
    reward_signals:
      gail:
        gamma: 0.99
        strength: 1.0
        demo_path: demos/ExpertDemos.demo
        encoding_size: 128
        learning_rate: 0.0003
        use_actions: false                # Learn from observations only

    hyperparameters:
      batch_size: 1024
      buffer_size: 10240
      learning_rate: 0.0003

    max_steps: 500000
```

## Recording Demonstrations in Unity

```csharp
using UnityEngine;
using Unity.MLAgents;
using Unity.MLAgents.Demonstrations;

public class DemoRecordingAgent : Agent
{
    // Add DemonstrationRecorder component in Inspector:
    // - Record: true
    // - Num Steps To Record: 1000
    // - Demonstration Directory: "demos/"
    // - Demonstration Name: "ExpertDemos"

    // Set BehaviorType to HeuristicOnly
    // Play the scene and control agent manually
    // Demonstration file will be saved automatically

    public override void Heuristic(in ActionBuffers actionsOut)
    {
        var continuousActionsOut = actionsOut.ContinuousActions;
        continuousActionsOut[0] = Input.GetAxis("Horizontal");
        continuousActionsOut[1] = Input.GetAxis("Vertical");
    }

    public override void OnActionReceived(ActionBuffers actionBuffers)
    {
        // Implementation
    }
}
```

## Curriculum Learning with Environment Parameters

```python
# Python side - dynamically adjust difficulty
from mlagents_envs.environment import UnityEnvironment
from mlagents_envs.side_channel.environment_parameters_channel import EnvironmentParametersChannel

env = UnityEnvironment(file_name="./Game.exe")
params_channel = EnvironmentParametersChannel()
env.register_side_channel(params_channel)

# Curriculum stages
for lesson in range(10):
    print(f"Starting lesson {lesson}")

    # Gradually increase difficulty
    params_channel.set_float_parameter("spawn_rate", 0.5 + lesson * 0.1)
    params_channel.set_float_parameter("enemy_speed", 1.0 + lesson * 0.2)
    params_channel.set_float_parameter("num_obstacles", 5 + lesson * 2)

    # Train for N episodes at this difficulty
    for episode in range(100):
        env.reset()
        # Training loop...

env.close()
```

```csharp
// Unity side - read parameters
using UnityEngine;
using Unity.MLAgents;

public class CurriculumAgent : Agent
{
    private EnvironmentParameters envParams;

    public override void Initialize()
    {
        envParams = Academy.Instance.EnvironmentParameters;
    }

    public override void OnEpisodeBegin()
    {
        // Read curriculum parameters from Python
        float spawnRate = envParams.GetWithDefault("spawn_rate", 0.5f);
        float enemySpeed = envParams.GetWithDefault("enemy_speed", 1.0f);
        int numObstacles = (int)envParams.GetWithDefault("num_obstacles", 5.0f);

        // Adjust environment based on curriculum
        ConfigureEnvironment(spawnRate, enemySpeed, numObstacles);
    }

    private void ConfigureEnvironment(float spawnRate, float speed, int obstacles)
    {
        // Implement environment configuration
    }
}
```

## Gym Wrapper for External Training Frameworks

```python
from mlagents_envs.environment import UnityEnvironment
from mlagents_envs.envs.unity_gym_env import UnityToGymWrapper
import gym

# Create Unity environment
unity_env = UnityEnvironment(file_name="./Game.exe")

# Wrap as OpenAI Gym environment
gym_env = UnityToGymWrapper(
    unity_env=unity_env,
    allow_multiple_obs=True,    # Combine multiple observation types
    flatten_branched=True,      # Flatten multi-discrete actions
    uint8_visual=True           # Use uint8 for visual observations
)

# Now use with any Gym-compatible framework (Stable-Baselines3, RLlib, etc.)
obs = gym_env.reset()
print(f"Observation space: {gym_env.observation_space}")
print(f"Action space: {gym_env.action_space}")

for step in range(1000):
    action = gym_env.action_space.sample()
    obs, reward, done, info = gym_env.step(action)

    if done:
        obs = gym_env.reset()

gym_env.close()
```

## Self-Play Configuration

```yaml
behaviors:
  SelfPlayAgent:
    trainer_type: ppo

    # Self-play settings
    self_play:
      save_steps: 20000           # Save opponent snapshot every N steps
      team_change: 100000         # Swap teams every N steps
      swap_steps: 10000           # How often to train against old policies
      window: 5                   # Number of past policies to train against
      play_against_latest_model_ratio: 0.5  # 50% against latest, 50% against older
      initial_elo: 1200.0         # Starting ELO rating

    hyperparameters:
      batch_size: 1024
      buffer_size: 20000
      learning_rate: 0.0003

    network_settings:
      hidden_units: 256
      num_layers: 2

    reward_signals:
      extrinsic:
        gamma: 0.995
        strength: 1.0

    max_steps: 10000000
```

## Custom Side Channel Communication

```python
# Python custom side channel
from mlagents_envs.side_channel.side_channel import SideChannel, IncomingMessage, OutgoingMessage
import uuid

class CustomSideChannel(SideChannel):
    def __init__(self):
        super().__init__(uuid.UUID("621f0a70-4f87-11ea-a6bf-784f4387d1f7"))

    def on_message_received(self, msg: IncomingMessage) -> None:
        # Receive data from Unity
        data = msg.read_float32()
        print(f"Received from Unity: {data}")

    def send_string(self, text: str) -> None:
        # Send data to Unity
        msg = OutgoingMessage()
        msg.write_string(text)
        super().queue_message_to_send(msg)

# Usage
from mlagents_envs.environment import UnityEnvironment

env = UnityEnvironment()
custom_channel = CustomSideChannel()
env.register_side_channel(custom_channel)

custom_channel.send_string("Hello Unity!")
env.reset()
```

```csharp
// Unity custom side channel
using UnityEngine;
using Unity.MLAgents;
using Unity.MLAgents.SideChannels;

public class CustomSideChannel : SideChannel
{
    public CustomSideChannel()
    {
        ChannelId = new System.Guid("621f0a70-4f87-11ea-a6bf-784f4387d1f7");
    }

    protected override void OnMessageReceived(IncomingMessage msg)
    {
        // Receive data from Python
        string text = msg.ReadString();
        Debug.Log($"Received from Python: {text}");
    }

    public void SendFloat(float value)
    {
        // Send data to Python
        using (var msgOut = new OutgoingMessage())
        {
            msgOut.WriteFloat32(value);
            QueueMessageToSend(msgOut);
        }
    }
}

// Register in Academy
public class CustomAcademy : MonoBehaviour
{
    private CustomSideChannel customChannel;

    void Awake()
    {
        customChannel = new CustomSideChannel();
        SideChannelManager.RegisterSideChannel(customChannel);
    }

    void OnDestroy()
    {
        if (customChannel != null)
        {
            SideChannelManager.UnregisterSideChannel(customChannel);
        }
    }
}
```

The Unity ML-Agents Toolkit serves as a comprehensive solution for training intelligent agents across diverse applications. Primary use cases include developing adaptive NPC behaviors in games where enemies learn player strategies and adjust difficulty dynamically, automated testing systems that discover edge cases and balance issues faster than manual QA, and procedural content evaluation where agents playtest levels to assess quality and difficulty curves. Researchers leverage the toolkit for multi-agent coordination experiments, studying emergent behaviors in competitive and cooperative scenarios with up to hundreds of simultaneous agents.

Integration patterns typically follow a development lifecycle where prototypes begin with heuristic policies for manual testing, transition to reinforcement learning with curriculum training that gradually increases complexity, incorporate imitation learning from expert demonstrations to bootstrap training, and conclude with deployed inference using exported ONNX models running on Unity's Sentis inference engine. The architecture supports both Editor-based development for rapid iteration and headless training on cloud infrastructure with Docker containers running multiple parallel environments. Cross-platform trained models deploy seamlessly to mobile, console, desktop, and WebGL targets without retraining, while the modular sensor/actuator system allows mixing visual observations from cameras, vector data from game state, and raycasting sensors within single agents that control character movement, animation triggers, and strategic decision-making through hybrid continuous-discrete action spaces.
