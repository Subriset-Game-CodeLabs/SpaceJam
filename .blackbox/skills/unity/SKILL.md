### Example cURL Request to Start Server

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-start-specific

This example demonstrates how to use cURL to send a GET request to the server start endpoint. Ensure you replace YOUR_AUTH_CREDENTIALS with your actual authentication token.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/server/<serverid>/start' \
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Manual Event Bid Setup Example

Source: https://docs.unity.com/en-us/grow/offerwall/user-acquisition/dashboard/add-a-multi-rewards-ad-set

This example illustrates the default bid setup where a specific publisher app ('MyTapjoy') has a higher bid ($10) than the general default bid ($5).

```text
Default bids apply to publisher apps not included in your list. The following example, **Default** is set to $5, and **MyTapjoy** to $10. This setup means that if a user completes your events after encountering them in the **MyTapjoy** , you pay $10. For all other publisher apps not on the list, you pay $5.
```

--------------------------------

### Example Server Start Response

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-start-by-criteria

A successful response indicates the server start action was initiated. The response includes the action performed and details about the server that was started.

```json
{
    "action": "start",
    "success": true,
    "server": {
        "serverid": <serverid>
    }
}
```

--------------------------------

### Sample Unity License Server Setup Output (Windows)

Source: https://docs.unity.com/en-us/licensing-server/migrating

Example output from the Unity License Server setup command on Windows, showing a migration process that requires confirmation.

```bash
> .\Unity.Licensing.Server.exe setup
- - - -
Welcome to Unity Licensing Server setup command line interface.
This setup will help you configure your license server 
and generate server registration request file.
- - - -

Upgrading from 1.10.0 to 1.11.0...

This migration can take more than a few minutes. Are you sure you want to run it now? [y/N] y

Proceeding with migration... 
Backup installed version 1.10.0...Done
Scripts to run: 1.11.0
Executing 1.11.0...Done
Stamping version 1.11.0...Done
Successfully migrated from 1.10.0 to 1.11.0
Enter the server name (e.g. LicenseServer):

```

--------------------------------

### Unity Licensing Server Setup Welcome Message and Server Name Prompt

Source: https://docs.unity.com/en-us/licensing-server/server-setup-cfg-v2

This is an example of the initial output and prompt during the Unity Licensing Server setup, asking for the server name.

```bash
Welcome to Unity Licensing Server setup command line interface.
This setup will help you configure your license server 
and generate server registration request file.

Enter the server name (e.g. LicenseServer):  [DESKTOP] TestServer
```

--------------------------------

### Unity Licensing Server Example Output

Source: https://docs.unity.com/en-us/licensing-server/quick-start-web

Example output when the Unity Licensing Server starts successfully on Linux or Windows. It indicates the server version and the URL to access its status.

```bash
Server Version: 1.6.0.19b28b6
Successfully started the licensing server: http://10.211.55.4:8080/v1/admin/status
Press Ctrl+C to shut down...
```

--------------------------------

### Full Banner Ad Implementation Example

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/react/banner-integration

Example demonstrating the creation and loading of a banner ad with standard size, including necessary imports and listener setup.

```javascript
import {
  LevelPlayBannerAdView,
  LevelPlayAdSize,
  type LevelPlayBannerAdViewMethods,
  type LevelPlayBannerAdViewListener,
  type LevelPlayAdInfo,
  type LevelPlayAdError,
} from 'unity-levelplay-mediation'

// Start of some component ...
const bannerAdViewRef = useRef<LevelPlayBannerAdViewMethods>(null);
const adSize = LevelPlayAdSize.BANNER
const listener: LevelPlayBannerAdViewListener = {
    onAdLoaded: (adInfo: LevelPlayAdInfo) => {
        // Implement your logic here
    },
    onAdLoadFailed: (error: LevelPlayAdError) => {
        // Implement your logic here
    },
    onAdDisplayed: (adInfo: LevelPlayAdInfo) => {
        // Implement your logic here
    },
    onAdDisplayFailed: (adInfo: LevelPlayAdInfo, error: LevelPlayAdError) => {
        // Implement your logic here
    },
    onAdClicked: (adInfo: LevelPlayAdInfo) => {
        // Implement your logic here
    },
    onAdExpanded: (adInfo: LevelPlayAdInfo) => {
        // Implement your logic here
    },
    onAdCollapsed: (adInfo: LevelPlayAdInfo) => {
        // Implement your logic here
    },
    onAdLeftApplication: (adInfo: LevelPlayAdInfo) => {
        // Implement your logic here
    },
};
return (
    <LevelPlayBannerAdView 
        ref={bannerAdViewRef}
        adUnitId={'YOUR_AD_UNIT_ID'}
        adSize={adSize}
        placementName={'YOUR_PLACEMENT'}
        listener={listener}
        onLayout={(_) => bannerAdViewRef.current?.loadAd()}
        style={{width: adSize.width, height: adSize.height}} // Get actual banner layout size
      />
);
  
// End of component ... 
```

--------------------------------

### Example cURL Request to Start Server

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-start-by-criteria

Use this cURL command to initiate a request to start a game server. Ensure you replace placeholder values with your actual credentials and IDs. Authentication is required.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/server/start?accountserviceid=<accountserviceid>&gameid=<gameid>&locationid=1&country_code=<country_code>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Example openwith.conf file

Source: https://docs.unity.com/en-us/unity-version-control/config-files/openwith-conf

An example configuration for the `openwith.conf` file, demonstrating how to add Notepad++ to the 'Open with' menu.

```conf
[Notepad|CtrlI] "C:\Program Files (x86)\Notepad++\notepad++.exe" @file
```

--------------------------------

### Get Placements Response Example

Source: https://docs.unity.com/en-us/grow/levelplay/platform/api/placements

This JSON structure represents the response when retrieving placement setup information. It includes details like ad unit type, placement name, ID, ad delivery status, and optional capping and pacing configurations.

```json
[
    {
        "name": "Home_Screen",
        "id": 12,
        "adUnit": "rewardedVideo",
        "itemName": "Coins",
        "rewardAmount": 3,
        "adDelivery": 1,
        "capping": {
            "enabled": 1,
            "cappingLimit": 3,
            "cappingInterval": "h"
        },
        "pacing": {
            "enabled": 1,
            "pacingMinutes": 12.5
        },
        "abVersion": "A"
    }
]
```

--------------------------------

### Initialize All Services Example

Source: https://docs.unity.com/en-us/services/services-core-api

Initializes all services at once, using the Environments initialization extension. This example should be placed in a MonoBehaviour script.

```csharp
using System;
using Unity.Services.Core;
using Unity.Services.Core.Environments;
using UnityEngine;

public class InitializeUGS : MonoBehaviour {
    
    public string environment = "production";

    async void Start() {
        try {
            var options = new InitializationOptions()
                .SetEnvironmentName(environment);

            await UnityServices.InitializeAsync(options);
        }
        catch (Exception exception) {
            // An error occurred during initialization.
        }
    }
}
```

--------------------------------

### Unity Licensing Server Network Interface Selection Prompt

Source: https://docs.unity.com/en-us/licensing-server/server-setup-cfg-v2

Example prompt during Unity Licensing Server setup for selecting the network interface index.

```bash
List of available network interfaces on this host
- [1] en0 (8C:85:90:CA:72:DC) 192.168.0.51
- [2] gpd0 (02:50:41:00:01:01) 10.1.4   2228
Enter the index number of the network interface which server will operate on:
```

--------------------------------

### Example Output of Unity Licensing Server Service Creation

Source: https://docs.unity.com/en-us/licensing-server/server-setup-svc

This is an example of the output you might see after successfully creating the Unity Licensing Server service on Linux. It confirms the service creation, enabling, and starting.

```text
- - - -
Welcome to Unity Licensing Server create service command line interface.
This command line interface will assist you in creating the Unity.Licensing.Server service.
- - - -

Creating service for user 'adminuser' ...
Setting permissions on service file ... Done
Enabling service to start automatically after (re)boot ... Done
Starting service ... Done
unity.licensing.server.service has been successfully created and running.

```

--------------------------------

### Get Next Page of Servers (Paging Example)

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-list-v3

This example demonstrates how to fetch the subsequent page of servers, sorted by name in descending order. It utilizes `last_id` and `last_val` for pagination.

```bash
curl --location --request GET  'https://api.multiplay.co.uk/cfp/v3/servers?/cfp/v3/servers?sort_by=name&sort_dir=desc&last_id=30&last_val=svrname'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Get Command Help Information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/repository

For comprehensive help and examples related to a specific repository command, use the --help flag. This provides detailed explanations and usage scenarios.

```bash
cm repository <command> --help
```

--------------------------------

### Image Install Queue Response (Mirror Jobs)

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-install-queue

This is an example JSON response for a queued image install job that is mirrored. It includes details about the job's status and progress.

```json
{
    "versionmirrorid": <versionmirrorid>,
    "jobcreated": <jobcreated>,
    "joberror": <joberror>,
    "jobeta": <jobeta>,
    "jobfailed": <jobfailed>,
    "jobprogress": <jobprogress>,
    "jobstart": <jobstart>,
    "jobstateid": <jobstateid>,
    "jobstatename": <jobstatename>,
    "jobupdated": <jobupdated>
}
```

--------------------------------

### Run Unity Licensing Server Setup (Linux)

Source: https://docs.unity.com/en-us/licensing-server/quick-start-web

Execute the setup command for the Unity Licensing Server on Linux. This command initiates the configuration process for the server.

```bash
sudo -H ./Unity.Licensing.Server setup
```

--------------------------------

### Get ironSource Instances Request URL Example

Source: https://docs.unity.com/en-us/grow/is-ads/monetization/apis/ironsource-instances-api

Example of a request URL for fetching ironSource instances, including the application key.

```text
https://platform.ironsrc.com/ads/instances/v1/142401ac1/
```

--------------------------------

### Install Proxy Server on OpenSUSE

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Install the Unity Version Control proxy server using zypper.

```bash
sudo zypper install plasticscm-proxy-server
```

--------------------------------

### Unity Start Method for Cloud Code Call

Source: https://docs.unity.com/en-us/cloud-code/modules/how-to-guides/run-modules/unity-runtime

Example of how to call the `CallMethod` from the `Start()` method in a Unity script to initiate the Cloud Code interaction when the game begins.

```csharp
public void Start()
{
    CallMethod();
}
```

--------------------------------

### Setup Virtual Environment (Linux)

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/pixyzui/setup

Use these commands in the command line to set up a virtual environment, activate it, and install requirements for Pixyz UI development on Linux.

```bash
python -m venv .venv
source ./.venv/Scripts/activate
pip install -r .\requirements.txt
```

--------------------------------

### List All Users Example

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/listusers

Example command to list all users on a specified server.

```bash
cm lu localhost:8084
```

--------------------------------

### Remote Config Documentation Example

Source: https://docs.unity.com/en-us/services/release-notes

An improved example demonstrating how to fetch and apply configuration in Remote Config, as found in the documentation and `ExampleSample.cs`.

```csharp
Improved example for fetching and applying configuration in [Remote Config Documentation](https://docs.unity.com/Packages/com.unity.remote-config@latest/index.html?subfolder=/manual/CodeIntegration.html) and in `ExampleSample.cs`.
```

--------------------------------

### Setup Virtual Environment (Windows)

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/pixyzui/setup

Use these commands in the command line to set up a virtual environment, activate it, and install requirements for Pixyz UI development on Windows.

```bash
python -m venv .venv
.\.venv\Scripts\activate
pip install -r .\requirements.txt
```

--------------------------------

### Run Unity Licensing Server Setup (Windows)

Source: https://docs.unity.com/en-us/licensing-server/quick-start-web

Execute the setup command for the Unity Licensing Server on Windows. Requires elevated privileges. This command initiates the configuration process for the server.

```powershell
.\Unity.Licensing.Server.exe setup
```

--------------------------------

### Install Complete Edition on OpenSUSE

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Install the complete Unity Version Control package using zypper.

```bash
sudo zypper install plasticscm-complete
```

--------------------------------

### Queue Image Install Job

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-install-queue

Use this GET request to queue an image install job. Ensure your request includes the account service ID and mirroring status.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/imageinstall/<jobid>/queue?accountserviceid=<accountserviceid>&mirroring=<mirroring>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Run Interactive UVCS Client Configuration

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/configureclient

Execute the 'cm configure' command without any arguments to start an interactive session for configuring the UVCS client. This is useful for guiding users through the setup process.

```bash
cm configure
```

--------------------------------

### Full Banner Ad Implementation Example in Dart

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/flutter/banner-integration

Example demonstrating the creation and loading of a banner ad with standard banner size. Includes widget setup and listener implementations.

```dart
  // Start of the widget...
  final _bannerKey = GlobalKey<LevelPlayBannerAdViewState>();
  final adSize = LevelPlayAdSize.BANNER;
  @override
  Widget build(BuildContext context) {
    return SizedBox(
      width: adSize.width.toDouble(), // Get actual banner layout width size
      height: adSize.height.toDouble(), // Get actual banner layout height size
      child: LevelPlayBannerAdView(
        key: _bannerKey,
        adUnitId: 'YOUR_AD_UNIT_ID',
        adSize: adSize,
        listener: this,
        placementName: 'YOUR_PLACEMENT',
        onPlatformViewCreated: () {
	// In this implementation we call loadAd on the key,
            // it is also possible to store the LevelPlayBannerAdView widget
            // in a variable and call loadAd on it as described above in the docs.
          _bannerKey.currentState?.loadAd(); 
        },
      ),
    );
  }
  @override
  void onAdClicked(LevelPlayAdInfo adInfo) {
    // Implement your logic here...
  }
  @override
  void onAdCollapsed(LevelPlayAdInfo adInfo) {
    // Implement your logic here...
  }
  @override
  void onAdDisplayFailed(LevelPlayAdInfo adInfo, LevelPlayAdError error) {
    // Implement your logic here...
  }
  @override
  void onAdDisplayed(LevelPlayAdInfo adInfo) {
    // Implement your logic here...
  }
  @override
  void onAdExpanded(LevelPlayAdInfo adInfo) {
    // Implement your logic here...
  }
  @override
  void onAdLeftApplication(LevelPlayAdInfo adInfo) {
    // Implement your logic here...
  }
  @override
  void onAdLoadFailed(LevelPlayAdError error) {
    // Implement your logic here...
  }
  @override
  void onAdLoaded(LevelPlayAdInfo adInfo) {
    // Implement your logic here...
  }
  // End of widget...
```

--------------------------------

### Install Unity Version Control Complete Installation on Debian

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Installs the complete package for Unity Version Control on Debian, providing both server and client tools for on-premises setups.

```bash
sudo apt-get install plasticscm-complete
```

--------------------------------

### Get Incomplete Image Install Jobs

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-install-status

Use this GET request to retrieve all incomplete image installation jobs associated with a specific account service ID. Ensure your request headers contain credentials with access to the provided ASID.

```json
{
  "installs": [
    {
      "jobid": <jobid>,
      "jobcreated": <jobcreated>,
      "joberror": <joberror>,
      "jobeta": <jobeta>,
      "jobfailed": <jobfailed>,
      "jobprogress": <jobprogress>,
      "jobstart": <jobstart>,
      "jobstateid": <jobstateid>,
      "jobstatename": <jobstatename>,
      "jobupdated": <jobupdated>,
      "mirroring": <mirroring>,
      "restart": <restart>,
      "location": <location>,
      "machine": <machine>,
      "imagepath": <imagepath>,
      "install_at": <install_at>,
      "mirror": <mirror_name>,
      "target_imageversionid": <target_imageversionid>,
      "restart": <restart>
    }
  ]
}
```

--------------------------------

### Example GET Request for Revenue Data

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/custom-adapters-reporting-api

ironSource will send requests to your endpoint a few times a day, with each call for a specific account and date. This is an example of the GET request format.

```http
GET https://www.CustomNetworkEndPoint.com?date=2021-09-01\&&apiKey=value1\&&myUser=value2
```

--------------------------------

### External Tools Configuration Examples

Source: https://docs.unity.com/en-us/unity-version-control/config-files/externaltools-conf

Illustrates how to configure external tools for different object types and applications. These examples show how to specify paths, environment variables, and arguments with placeholders.

```conf
item | Open with sublime | C:\Program Files\Sublime Text 3\subl.exe | "@object"
```

```conf
label:changeset:branch | Create new code review... | /usr/bin/createcodereview | "@object@@repository" @wkpath
```

```conf
item | Preview with PhotoScape | %PHOTOSCAPE_PATH% | "@object"
```

--------------------------------

### Configure SSL Server (Old Method)

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

This example shows the previous, multi-step process for configuring an SSL server address and port using the command line client.

```text
Configure the Unity VCS server address/port:
Unity VCS server address [localhost]: version-control.unity-hq.domain
Unity VCS server port [8087]: 8087
Use encryption (SSL)? [y/N]: y
Unity VCS SSL server port [8088]: 9095
```

--------------------------------

### Example GET Request for Image Diff Status

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-diff-status

An example using `curl` to make a GET request to the Image Diff Status API. Ensure you include your authorization credentials and the required `accountserviceid`.

```bash
curl -X GET \
    -H "Authorization: Basic <CLANFORGE_CREDENTIALS>" \
    https://api.multiplay.co.uk/cfp/v1/imagediff/1234/status?accountserviceid=5678&diff_info=1
```

--------------------------------

### Set Unity Editor Install Path

Source: https://docs.unity.com/en-us/hub/hub-cli

Specify the directory where Unity Editors should be installed. If no option is provided, it defaults to getting the current install path.

```shell
/Applications/Unity\ Hub.app/Contents/MacOS/Unity\ Hub -- --headless install-path
-s /Applications/Unity/Hub/Editor/
```

```shell
C:\Program Files\Unity Hub>"Unity Hub.exe" -- --headless install-path
-s /Applications/Unity/Hub/Editor/
```

```shell
~/Applications/Unity\ Hub.AppImage --headless install-path
-s /Applications/Unity/Hub/Editor/
```

--------------------------------

### Configure SSL Server (New Method)

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

This example demonstrates the streamlined, single-step process for configuring an SSL server address and port using the command line client.

```text
Enter server address: ssl://version-control.unity-hq.domain:9095
```

--------------------------------

### Start Unity Licensing Server Service on Windows

Source: https://docs.unity.com/en-us/licensing-server/server-setup-svc

Run this command to start the Unity Licensing Server service. Use this after stopping the service or if it has stopped unexpectedly.

```bash
sc.exe start Unity.Licensing.Server
```

--------------------------------

### GET /server/start

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-start-by-criteria

Starts the first inactive game server identified by the criteria passed through the parameters.

```APIDOC
## GET /server/start

### Description
Starts the first inactive game server identified by the criteria passed through the parameters.

### Method
GET

### Endpoint
https://api.multiplay.co.uk/cfp/v1/server/start

### Parameters
#### Query Parameters
- **accountserviceid** (string) - Required - Account service ID to filter servers for
- **gameid** (string) - Required - Game ID to filter servers for
- **country_code** (string) - Optional - Optional country code to filter servers for, lookup available in the [server countries](/clanforge/api/endpoints/server-countries.md) endpoint
- **locationid** (integer) - Optional - Optional location ID to filter servers for

### Request Example
```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/server/start?accountserviceid=<accountserviceid>&gameid=<gameid>&locationid=1&country_code=<country_code>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

### Response
#### Success Response (200)
- **action** (string) - Action performed on the server. Will be 'start' for this endpoint
- **success** (boolean) - Boolean indicating whether the action was successful
- **server** (object) - Server object containing information about the server
  - **serverid** (integer) - ID of the server

#### Response Example
```json
{
    "action": "start",
    "success": true,
    "server": {
        "serverid": <serverid>
    }
}
```
```

--------------------------------

### Image Install Queue Response (Machine Jobs)

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-install-queue

This is an example JSON response for a queued image install job for machines. It provides similar status and progress information as mirror jobs.

```json
{
    "machinejobid": <machinejobid>,
    "installs_squashed": <installs_squashed>,
    "jobcreated": <jobcreated>,
    "joberror": <joberror>,
    "jobeta": <jobeta>,
    "jobfailed": <jobfailed>,
    "jobprogress": <jobprogress>,
    "jobstart": <jobstart>,
    "jobstateid": <jobstateid>,
    "jobstatename": <jobstatename>,
    "jobupdated": <jobupdated>
}
```

--------------------------------

### Unity Licensing Server Setup Completion Output

Source: https://docs.unity.com/en-us/licensing-server/server-setup-cfg-v2

Sample output indicating successful completion of the Unity Licensing Server setup, including generated files.

```bash
Generating signing key... Done

Generating server configuration ...Done
Generating services configuration ...Done
Reloading configuration... Done
Generating server registration request file... Done
Setting up file permissions... Done

- - - -
Setup Completed!
- - - -

<Note>
  Server Registration Request
</Note>
Please go to Unity ID portal -> Organizations -> [Organization Name] -> 
Subscriptions & Services -> [Floating Subscription] -> Configure License 
Server, upload server-registration-request.xml, and follow the 
instructions to receive a compressed license archive file.

File to upload:
/home/adminuser/server-registration-request.xml

<Note>
  Services Configuration File
</Note>
Generated services-config.json file must be copied to the following location
on all end user computer in order to enable floating licensing:
  - Windows: %PROGRAMDATA%\Unity\config\
  - MacOS:  /Library/Application Support/Unity/config/
  - Linux:  /usr/share/unity3d/config/

File to copy:
/home/adminuser/services-config.json

WARNING: Please make sure to backup the following directory as it contains
essential data for operating the licensing server:
  ... [Path varies by server version and operating system]
```

--------------------------------

### Start the UVCS proxy service

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/configure/use-proxy-server

Starts the UVCS proxy service after it has been installed. This command is used to manage the background service.

```bash
plasticd proxy --start
```

--------------------------------

### Example Launch Parameters

Source: https://docs.unity.com/en-us/multiplay-hosting/concepts/launch-parameters

Use launch parameters to pass essential information to your game server upon startup. Enclose each parameter in double dollar signs ($$).

```plaintext
-port $$port$$ -queryport $$query_port$$ -log $$log_dir$$
```

--------------------------------

### Install PubMatic Adapter and SDK

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/ios/networks/guides/pubmatic

Execute this command in your terminal after updating your Podfile to install the necessary adapter and SDK components.

```sh
pod install --repo-update
```

--------------------------------

### Get Default Bid and Setup Goal

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/country-group-api

Retrieves the default bid and setup goal values for Country groups within a campaign.

```APIDOC
## GET /advertisers/v4/CountryGroup/:campaignId/default

### Description
Use this API in order to get the default values for Country groups.

### Method
GET

### Endpoint
/advertisers/v4/CountryGroup/:campaignId/default

### Parameters
#### Path Parameters
- **campaignId** (string) - Required - The ID of the campaign.

### Response
#### Success Response (200)
- **setupGoal** (number) - The default setup goal value.
- **bid** (number) - The default bid value.
```

--------------------------------

### Unattended Plastic SCM Installation

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

Launch Plastic SCM installers in unattended mode using the following command. This configures the Plastic Server with default values and starts it if no previous installation is detected.

```bash
PlasticSCM-10.0.16.5710-windows-installer.exe --mode unattended --unattendedmodeui none --disable-components ideintegrations,eclipse,mylyn,intellij12 --enable-components server
```

--------------------------------

### Install vpctl Tool (Interactive Mode)

Source: https://docs.unity.com/en-us/cloud/virtual-private-cloud/on-premises/installation/prerequisites

Run the install script for the vpctl tool and enter registry credentials when prompted. This script automatically detects your OS and architecture.

```bash
./install-vpctl.sh 0.8.0
```

```bash
[install-vpctl] Logging in to uccmpprivatecloud.azurecr.io (interactive)...
[install-vpctl] Please enter your registry credentials:
Username: <your-username>
Password: <your-password>
```

--------------------------------

### Get Version

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_coreinterface

Retrieves the Pixyz product version. No specific setup is required.

```csharp
[HandleProcessCorruptedStateExceptions]
public string GetVersion()
```

--------------------------------

### Install Specific Cocoapods Version

Source: https://docs.unity.com/en-us/build-automation/check-build-results/troubleshoot-build-failures/error-migrating-xcode

Use this pre-build script to install a specific version of Cocoapods, ensuring consistency between local development and build automation environments. This example installs version 1.12.0.

```bash
gem install cocoapods -v 1.12.0
echo "current cocoapods version: "
gem which cocoapods
```

--------------------------------

### Attribute Array Example

Source: https://docs.unity.com/en-us/grow/exchange/bid-responses

Example of an attribute array for creative description. Refer to the OpenRTB API guide for a complete list of supported values.

```json
"attr": [1, 13]
```

--------------------------------

### Initialize Pixyz SDK and Get Version

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/installation/csharp

This script initializes the Pixyz API, retrieves and prints the SDK version, and includes logic to configure a license server if no license is found. Ensure you have the necessary Pixyz NuGet packages installed.

```csharp
using UnityEngine.Pixyz.API;

// init Pixyz
PiXYZAPI api = PiXYZAPI.Initialize();

// print Pixyz version
Console.WriteLine(api.Core.GetVersion());

// if no license is found, try to configure a license server
if (!api.Core.CheckLicense())
{
    api.Core.ConfigureLicenseServer("company-server-hostname", 27000, true);
}

// use api.IO.ImportScene to import a file and enjoy :)
```

--------------------------------

### GET /api/cad/getLineCurveDefinition

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/cad_functions

Retrieves the start and end points of a line curve.

```APIDOC
## GET /api/cad/getLineCurveDefinition

### Description
Get all parameters contain in the lineCurve.

### Method
GET

### Endpoint
/api/cad/getLineCurveDefinition

### Parameters
#### Query Parameters
- **lineCurve** (LineCurve) - Required - The lineCurve.

### Response
#### Success Response (200)
- **startPoint** (geom.Point3) - The starting point of the line curve.
- **endPoint** (geom.Point3) - The ending point of the line curve.

#### Response Example
{
  "startPoint": {"x": 0, "y": 0, "z": 0},
  "endPoint": {"x": 1, "y": 1, "z": 1}
}
```

--------------------------------

### Example GET Request to Save Server Configuration

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-save

Use this curl command to send a GET request to save a server's configuration. Replace placeholders like <serverid>, <profileid>, <active>, <name>, and YOUR_AUTH_CREDENTIALS with your actual values.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/server/<serverid>/save?profileid=<profileid>&active=<active>&name=<name>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Initialize Pixyz Session

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/pxz_functions

Start a new Pixyz session. This is mandatory before using any SDK features. It acquires the previously installed license. Optional parameters include productName, validationKey, optionalTokenList, and license file path.

```python
pxz.initialize(productName=None, validationKey=None, optionalTokenList=None, license=None)
```

--------------------------------

### Install Cloud Edition on OpenSUSE

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Install the Unity Version Control Cloud Edition using zypper.

```bash
sudo zypper install plasticscm-cloud
```

--------------------------------

### Example Access Token for Unmute

Source: https://docs.unity.com/en-us/vivox-core/server-to-server-api-reference/control-active-channels-api/unmute-user-in-channel

An example of an access token generated with the specified parameters for unmuting a user. Refer to the Access Token Developer Guide for more information.

```plaintext
e30.eyJ2eGkiOjMsInN1YiI6InNpcDouYmxpbmRtZWxvbi1BcHBOYW1lLWRldi5qZXJreS5AbXQxcy52aXZveC5jb20iLCJmIjoic2lwOmJsaW5kbWVsb24tQXBwTmFtZS1kZXYtQWRtaW5AbXQxcy52aXZveC5jb20iLCJpc3MiOiJibGluZG1lbG9uLUFwcE5hbWUtZGV2IiwidnhhIjoibXV0ZSIsInQiOiJzaXA6Y29uZmN0bC1nLWJsaW5kbWVsb24tQXBwTmFtZS1kZXYudGhlLWNoYW5uZWxAbXQxcy52aXZveC5jb20iLCJleHAiOjE2MDAzNDk0MDB9.ufa-NQxsObktQbVrBqvK27epuNrixNhMjRS7EmcpB-E
```

--------------------------------

### Full Integration Example (C#)

Source: https://docs.unity.com/en-us/cloud-code/scripts/how-to-guides/run-scripts/unity-runtime

A complete C# script demonstrating how to initialize Unity Services, authenticate, and call a Cloud Code script.

```APIDOC
## Full Integration Example

### Description
This example demonstrates how to integrate Cloud Code with Authentication in a Unity project. It initializes services, signs in anonymously, and calls a 'RollDice' Cloud Code script with a 'diceSides' parameter.

### Method
N/A (This is a client-side script example)

### Endpoint
N/A

### Parameters
N/A

### Request Example
(See C# code for example of calling the script)

### Response
#### Success Response (200)
- **Roll** (int) - The result of the dice roll.
- **Sides** (int) - The number of sides on the dice.

#### Response Example
```json
{
  "Roll": 3,
  "Sides": 6
}
```

### C# Code Example
```csharp
using System.Collections.Generic;
using UnityEngine;
using Unity.Services.Authentication;
using Unity.Services.CloudCode;
using Unity.Services.Core;

public class RollDiceExample : MonoBehaviour
{
    // ResultType structure is the serialized response from the RollDice script in Cloud Code
    private class ResultType
    {
        public int Roll;
        public int Sides;
    }

    // Call this method to roll the dice (use a button)
    public async void CallMethod()
    {
        await UnityServices.InitializeAsync();
        // Sign in anonymously into the Authentication service
        if (!AuthenticationService.Instance.IsSignedIn) await AuthenticationService.Instance.SignInAnonymouslyAsync();

        // Call out to the Roll Dice script in Cloud Code
        var response = await CloudCodeService.Instance.CallEndpointAsync<ResultType>("RollDice", new Dictionary<string, object>( ) { { "diceSides", 6 } });

        // Log the response of the script in console
        Debug.Log($"You rolled {response.Roll} / {response.Sides}");
    }

    public void Start()
    {
        CallMethod();
    }
}
```
```

--------------------------------

### View Help for Shelveset Apply

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

Access the help documentation for the 'cm partial shelveset apply' command to see more examples and options.

```console
cm partial shelveset apply --help
```

--------------------------------

### Reporting API v4 Request Example

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/reporting-api-v4

This is an example of a GET request to the Reporting API v4. It specifies breakdowns, metrics, date ranges, and country filters.

```http
https://api.ironsrc.com/advertisers/v4/reports?breakdowns=day,campaign,country,deviceType&metrics=impressions,clicks,completions,spend&format=csv&count=100&startDate=2018-03-14&endDate=2018-04-07&country=US,CA,GB,FR&order=day&direction=desc
```

--------------------------------

### Get Current License Information

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/core_functions

Retrieves information about the currently installed license.

```APIDOC
## getCurrentLicenseInfos

### Description
Get information on current installed license.

### Method
Not specified (function call shown)

### Endpoint
Not applicable (function call)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```python
core.getCurrentLicenseInfos()
```

### Response
#### Success Response (200)
- **licenseInfos** (LicenseInfos) - Description not specified.

#### Response Example
None
```

--------------------------------

### Get CLI Version

Source: https://docs.unity.com/en-us/ccd/cli

Displays the currently installed version of the UGS CLI.

```bash
$ ucd --version
```

--------------------------------

### Get Current License Information

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_coreinterface

Retrieves information about the currently installed license.

```csharp
[HandleProcessCorruptedStateExceptions]
public LicenseInfos GetCurrentLicenseInfos()
```

--------------------------------

### Get Unity Version Control CLI client path

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/location

Use this command to find the installation path of the 'cm' executable. It relies on environment variables and returns the first installation found in your PATH.

```bash
cm location
```

--------------------------------

### IP Address Example

Source: https://docs.unity.com/en-us/grow/acquire/partner-integration/custom/postback-request

Include the user's IP address to identify the source of the post-install event.

```text
ip=123.456.78.90
```

--------------------------------

### Example Service Status Output on Windows

Source: https://docs.unity.com/en-us/licensing-server/server-setup-svc

This is an example of the output you might see when checking the status of the Unity.Licensing.Server service, indicating it is running.

```bash
SERVICE_NAME: Unity.Licensing.Server
        TYPE               : 10  WIN32_OWN_PROCESS
        STATE              : 4  RUNNING
                                   (STOPPABLE, NOT_PAUSABLE, ACCEPTS_SHUTDOWN)
        WIN32_EXIT_CODE    : 0  (0x0)
        SERVICE_EXIT_CODE  : 0  (0x0)
        CHECKPOINT         : 0x0
        WAIT_HINT          : 0x0
```

--------------------------------

### Example server.json for an Allocated Server

Source: https://docs.unity.com/en-us/multiplay-hosting/concepts/server-json

This is an example of the server.json file when a server is allocated, showing the allocation ID.

```plaintext
{
	"ipv6": "::1",
	"port": "9000",
	"allocatedUUID": "1a04a1ac-a31a-11ed-a5e3-00155d4f1a62",
	"serverID": "12345",
	"machineID": "6789",
	"fleetID": "c0a3e2a1-6955-415c-b1d4-af9199833e6a",
	"regionID": "f15a6c27-de2a-4848-abc3-9579fbfd2259",
	"regionName": "North America",
	"queryPort": "9010",
	"ip": "127.0.0.1",
	"queryType": "sqp",
	"serverLogDir": "/mnt/unity/logs/"
}
```

--------------------------------

### Create Render Audio Start Request

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/group__devices

Allocates and initializes a vx_req_aux_render_audio_start_t object. Use this to begin rendering audio.

```c
VIVOXSDK_DLLEXPORT int vx_req_aux_render_audio_start_create(
    vx_req_aux_render_audio_start_t ** req
)
```

--------------------------------

### Get Image Version Status Request

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-version-status

Example cURL request to get the status of an image version. Ensure to replace placeholders with your actual values and include authorization.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/imageversion/<imageversionid>/status?accountserviceid=<accountserviceid>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### ReadyServerForPlayers Method

Source: https://docs.unity.com/en-us/multiplay-hosting-unreal/sdk-api/multiplay-game-server-subsystem

Marks the server as ready for players. Invoke this when the server is prepared to accept connections. Requires success and failure delegates.

```cpp
UFUNCTION(BlueprintCallable, Category="Multiplay | GameServer")
void ReadyServerForPlayers(FReadyServerSuccessDelegate OnSuccess, FReadyServerFailureDelegate OnFailure)
```

--------------------------------

### Run SDKSampleApp and Sign in as Bob

Source: https://docs.unity.com/en-us/vivox-core/text-chat-guide/sdksampleapp/log-in-as-bob

Execute the SDKSampleApp with specific arguments to connect and log in as the user 'Bob'. This demonstrates the connection and login process.

```plaintext
[SDKSampleApp]: conn
* Connecting to http://mt1s.www.vivox.com/api2 with connector handle http://mt1s.www.vivox.com/api2...
* Issuing req_connector_create with cookie=1
* Request req_connector_create with cookie=1 completed.
[SDKSampleApp]: login -u .xyzzy.bob.
* Logging .xyzzy.bob. in with connector handle http://mt1s.www.vivox.com/api2 and account handle .xyzzy.bob.
* Issuing req_account_anonymous_login with cookie=2
* evt_account_login_state_change: .xyzzy.bob. login_state_logging_in
* Request req_account_anonymous_login with cookie=2 completed.
* evt_account_login_state_change: .xyzzy.bob. login_state_logged_in
```

--------------------------------

### Example lock.conf file with global and repository-specific rules

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/configure/exclusive-checkouts

A comprehensive example of a `lock.conf` file. It includes global rules for audio, video, and image formats, and repository-specific rules for the 'doom3src' repository, including exclusions for certain branches.

```text
rep: * br:/main
# Audio and video formats
*.mkv
*.mp3
*.mp4
*.ogg
*.wav
*.wave

# Image formats
*.bmp
*.jpg
*.jpeg
*.png
*.gif
*.eps
*.exif
*.icns
*.ico
*.psd
*.ai
*.svg
*.pcx

rep: doom3src br:/main excluded_branches: /main/experiment /main/experiments/* */art-concept */art-concepts/*
**/sys/*.xlib
*.def

```

--------------------------------

### Example: Configure Blob Storage and MinSize in Plastic SCM

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

An example configuration for the 'db.conf' file showing how to set the base path for blob storage and the minimum size threshold for storing revision chunks.

```xml
<BlobStorage>
   <BasePath>C:\\PlasticSCM\\server\\db_storage</BasePath>
   <MinSize>1000</MinSize>
</BlobStorage>
```

--------------------------------

### Invoke Unity Hub URL from Windows

Source: https://docs.unity.com/en-us/hub/deeplinking-support

Use the 'start' command in Windows to activate Unity Hub and display the 'Create New Project' interface.

```shell
start "" unityhub://editor/project/new
```

--------------------------------

### List schedule configurations with pagination

Source: https://docs.unity.com/en-us/cloud-code/triggers/tutorials/schedule-events/rest-api

Use query parameters like 'limit' to paginate through schedule configurations. This example retrieves the first two configurations. Replace placeholders with your actual project and environment IDs, and include encoded service account credentials.

```bash
curl 'https://services.api.unity.com/scheduler/v1/projects/<PROJECT_ID>/environments/<ENVIRONMENT_ID>/configs?limit=2' \
--header 'Authorization: Basic <SERVICE_ACCOUNT_CREDENTIALS_ENCODED>'
```

--------------------------------

### Get ironSource Instances Response Example

Source: https://docs.unity.com/en-us/grow/is-ads/monetization/apis/ironsource-instances-api

Example JSON response when retrieving ironSource ad instances. It includes details like instance ID, name, ad unit type, and pricing information.

```json
[
  {
    	"instanceId": 0,
    	"instanceName": "Default",
    	"adUnit": "rewardedVideo",
    	"isLive": false,
    	"isOptimized": true,
    	"isInTestMode": false
  },
  {
    	"instanceId": 123456,
    	"instanceName": "instance1",
    	"adUnit": "rewardedVideo",
    	"isLive": true,
    	"isOptimized": false,
      "isInTestMode": false,
    	
    	"globalPricing": 10,
    	"countriesPricing": [
	{
		"country": "US",
		"eCPM": 20
	},
	{
		"country": "CN",
		"eCPM": 20
	},	{
		"country": "AU",
		"eCPM": 30
	}
]
  }
]
```

--------------------------------

### Get Default Bid and Setup Goal API Response

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/country-group-api

This JSON response provides the current default bid and setup goal values for a campaign's country group.

```json
{
    "setupGoal" : 4,
    "bid" : 2
}
```

--------------------------------

### Create Unity Hub sources.list.d Directory

Source: https://docs.unity.com/en-us/hub/install-hub-linux

Manually create the '/etc/apt/sources.list.d' directory and an empty 'unityhub.list' file if they do not exist to resolve 'No such file or directory' errors.

```shell
sudo mkdir /etc/apt/sources.list.d
sudo touch /etc/apt/sources.list.d/unityhub.list
```

--------------------------------

### Example UVCS Server and Repository Configuration

Source: https://docs.unity.com/en-us/unity-version-control/vcs-plugins/teamcity-plugin

Illustrates example values for UVCS server and repository configuration parameters within the TeamCity Kotlin DSL.

```text
"organization@cloud"
"Awesome Project"
```

--------------------------------

### GET /cfp/v1/imageinstall/status

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-install-status

Retrieves a list of all incomplete image install jobs for a specified account service ID.

```APIDOC
## GET /cfp/v1/imageinstall/status

### Description
Get all incomplete image install jobs under the provided `<accountserviceid>`.

### Method
GET

### Endpoint
/cfp/v1/imageinstall/status

### Parameters
#### Query Parameters
- **accountserviceid** (string) - Required - The account service ID (ASID) associated with the specified resource. The credentials in the request header must have access to the ASID to perform the request.

### Response
#### Success Response (200)
- **installs** (array) - A list of incomplete image install jobs.
  - **jobid** (integer) - The ID of the job.
  - **jobcreated** (string) - The timestamp when the job was created.
  - **joberror** (string) - Any error message associated with the job.
  - **jobeta** (string) - Estimated time of arrival for the job.
  - **jobfailed** (boolean) - Indicates if the job has failed.
  - **jobprogress** (integer) - The progress of the job in percentage.
  - **jobstart** (string) - The timestamp when the job started.
  - **jobstateid** (integer) - The ID of the job's current state.
  - **jobstatename** (string) - The name of the job's current state.
  - **jobupdated** (string) - The timestamp when the job was last updated.
  - **mirroring** (boolean) - Indicates if mirroring is enabled for the job.
  - **restart** (boolean) - Indicates if the job is set to restart.
  - **location** (string) - The location where the job is running.
  - **machine** (string) - The machine associated with the job.
  - **imagepath** (string) - The path to the image being installed.
  - **install_at** (string) - The timestamp when the installation is scheduled.
  - **mirror** (string) - The name of the mirror being used.
  - **target_imageversionid** (string) - The ID of the target image version.

#### Response Example
```json
{
  "installs": [
    {
      "jobid": <jobid>,
      "jobcreated": <jobcreated>,
      "joberror": <joberror>,
      "jobeta": <jobeta>,
      "jobfailed": <jobfailed>,
      "jobprogress": <jobprogress>,
      "jobstart": <jobstart>,
      "jobstateid": <jobstateid>,
      "jobstatename": <jobstatename>,
      "jobupdated": <jobupdated>,
      "mirroring": <mirroring>,
      "restart": <restart>,
      "location": <location>,
      "machine": <machine>,
      "imagepath": <imagepath>,
      "install_at": <install_at>,
      "mirror": <mirror_name>,
      "target_imageversionid": <target_imageversionid>,
      "restart": <restart>
    }
  ]
}
```
```

--------------------------------

### Example LDAP User Filter Override

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/webadmin/authentication-config

An example of an LDAP user filter override for setups lacking the UID attribute. This filter uses a combination of sAMAccountName and cn attributes.

```text
|(sAMAccountName={user})(cn={user}))
```

--------------------------------

### Kotlin Example

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/rewarded-ads-integration

Example of how to use the getReward API in Kotlin to retrieve and log reward details.

```APIDOC
## Kotlin getReward Example

### Description
This example demonstrates how to retrieve reward information using the `getReward` method in Kotlin. It logs the amount and name of the reward.

### Code
```kotlin
/** 
 * Retrieves the reward associated with the ad. 
 * Use this method to obtain the reward configured for the ad unit or placement. The 
 * placement-specific reward takes precedence over the ad unit reward when a valid placement name 
 * is provided. 
 * @param placement The placement name to retrieve the reward for, or `null` to use the ad unit's reward. 
 * @return A [LevelPlayReward] object. Returns an empty reward on failures (`name: ""` and `amount: 0`). 
 */ 
@JvmOverloads 
fun getReward(placement: String? = null): LevelPlayReward { 
    val reward = mRewardedAd.getReward(placement)
    Log.d("LevelPlay", "Amount: ${reward.amount}, Name: ${reward.name}")
    return reward
}
```
```

--------------------------------

### Start Server Query Handler

Source: https://docs.unity.com/en-us/multiplay-hosting/sdk/game-server-sdk-for-unity

Use the `StartServerQueryHandlerAsync` method to connect to the game server’s SQP implementation with the provided parameters. This allows Multiplay Hosting to query server status.

```APIDOC
## Start server query handler

Use the `StartServerQueryHandlerAsync` method to connect to the game server’s SQP implementation with the provided parameters.

### Parameters
#### Request Body
- **maxPlayers** (ushort) - Required - The maximum number of players on the server.
- **serverName** (string) - Required - The name for the server.
- **gameType** (string) - Required - The name or identifier of the game type the server is running.
- **buildId** (string) - Required - The version of the game.
- **map** (string) - Required - The map or world the server is running for the game.
- **port** (ushort) - Required - The port number of the game server that the game client can use to connect.

Multiplay Hosting uses the `StartServerQueryHandlerAsync` parameters to initialize the server query handler. After you initialize the server query handler, you can use the `IServerCheckManager` instance provided by this call to update the values at any time. You must call `UpdateServerCheck()` for the changes to take effect. Call `UpdateServerCheck()` when game server variables change. Refer to [SQP](../concepts/sqp) for more information.

> **Tip:**
> You should call `UpdateServerCheck()` often enough to ensure you send up-to-date data back to Multiplay Hosting when the query request happens every 60 seconds.
> One of the best ways to do so is to call it in the `Update` loop. But you can also call it when specific game events occur, such as a player joining, a player leaving, or a game match starting.

> **Note:**
> The `currentPlayers` field always starts at 0. You must update this value each time a player connects to (or disconnects from) the game server.

The following example shows how to start the server query handler.

```cs
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using Unity.Services.Multiplay;

/// <summary>
/// An example of how to use SQP from the server using the Multiplay SDK.
/// The ServerQueryHandler reports the given information to the Multiplay Service.
/// </summary>
public class Example_ServerQueryHandler : MonoBehaviour
{
	private const ushort k_DefaultMaxPlayers = 10;
	private const string k_DefaultServerName = "MyServerExample";
	private const string k_DefaultGameType = "MyGameType";
	private const string k_DefaultBuildId = "MyBuildId";
	private const string k_DefaultMap = "MyMap";

	public ushort currentPlayers;

	private IServerQueryHandler m_ServerQueryHandler;

	await private async void Start()
	{
		m_ServerQueryHandler = await MultiplayService.Instance.StartServerQueryHandlerAsync(k_DefaultMaxPlayers, k_DefaultServerName, k_DefaultGameType, k_DefaultBuildId, k_DefaultMap);
	}

	private void Update()
	{
		m_ServerQueryHandler.UpdateServerCheck();
	}

	public void ChangeQueryResponseValues(ushort maxPlayers, string serverName, string gameType, string buildId)
	{
		m_ServerQueryHandler.MaxPlayers = maxPlayers;
		m_ServerQueryHandler.ServerName = serverName;
		m_ServerQueryHandler.GameType = gameType;
		m_ServerQueryHandler.BuildId = buildId;
	}

	public void PlayerCountChanged(ushort newPlayerCount)
	{
		m_ServerQueryHandler.CurrentPlayers = newPlayerCount;
	}
}
```
```

--------------------------------

### Example Callback URL Structure

Source: https://docs.unity.com/en-us/grow/ads/mediation/s2s-redeem-callbacks

This is an example of a complete callback URL with all parameters.

```text
https://developer.example.com/award.php?productid=1234&amp;sid=1234567890&amp;oid=0987654321&amp;hmac=106ed4300f91145aff6378a355fced73
```

--------------------------------

### Get Segment Curve Definition

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/cad_functions

Retrieves the start and end points of a segment curve.

```APIDOC
## GET /api/cad/getSegmentCurveDefinition

### Description
Retrieves the start and end points of a segment curve.

### Method
GET

### Endpoint
/api/cad/getSegmentCurveDefinition

### Parameters
#### Query Parameters
- **segmentCurve** (SegmentCurve) - Required - The segment curve to query.

### Response
#### Success Response (200)
- **startPoint** (geom.Point3) - The first point of the segment curve.
- **endPoint** (geom.Point3) - The second point of the segment curve.

#### Response Example
```json
{
  "startPoint": {
    "x": 0.0,
    "y": 0.0,
    "z": 0.0
  },
  "endPoint": {
    "x": 1.0,
    "y": 1.0,
    "z": 1.0
  }
}
```
```

--------------------------------

### Handle Purchases and Initialization

Source: https://docs.unity.com/en-us/iap/purchases

Sets up listeners for purchase events and connects to the store. Fetches previous purchases upon initialization.

```csharp
// Handle restore on initialization
private async void Start()
{
    // Setup, e.g. add listeners to your StoreController...
    m_StoreController.OnPurchasePending += OnPurchasePending;
    m_StoreController.OnPurchasesFetched += OnPurchasesFetched;
    await m_StoreController.Connect();

    // Fetch previous purchases (includes confirmed orders)
    m_StoreController.FetchPurchases();
}
```

```csharp
// Handle new purchases and pending transactions
private void OnPurchasePending(PendingOrder order)
{
    ProcessPurchase(order);
}
```

```csharp
// Handle fetched purchases (includes previously confirmed orders)
private void OnPurchasesFetched(Orders orders)
{
    foreach (var confirmedOrder in orders.ConfirmedOrders)
    {
        if (confirmedOrder.CartOrdered.Items().FirstOrDefault()?.Product.definition.type != ProductType.Consumable)
        {
            // Mark non-consumable and subscription products as entitled on fetch, as they only need to be granted once
            MarkAsEntitled(confirmedOrder.CartOrdered.Items().FirstOrDefault().Product);
        }
    }
}
```

```csharp
// Your ProcessPurchase logic
private void ProcessPurchase(PendingOrder order)
{
    foreach (var product in order.CartOrdered.Items())
    {
        // Grant product
        GrantProduct(product);
    }
    // Confirm the order to finalize the transaction
    m_StoreController.ConfirmPurchase(order);
}
```

--------------------------------

### Start Plastic Server for Client Configuration

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/saml-auth-microsoft

Initiate the Plastic server in console mode using `plasticd --console` before configuring the client.

```bash
.\plasticd --console
```

--------------------------------

### Get Product Name

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_coreinterface

Retrieves the Pixyz product name. No specific setup is required.

```csharp
[HandleProcessCorruptedStateExceptions]
public string GetProductName()
```

--------------------------------

### Full Rewarded Ads Implementation Example

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/unity/rewarded-ad-integration-package

A comprehensive example demonstrating the creation, loading, showing, and event handling for rewarded ads. This includes subscribing to various ad lifecycle events.

```csharp
public class RewardedAdSample {
    private LevelPlayRewardedAd RewardedAd;
    void CreateRewardedAd() {
        // Create RewardedAd instance
        RewardedAd = new LevelPlayRewardedAd("RewardedAdUnitId");

        // Subscribe RewardedAd events
        RewardedAd.OnAdLoaded += RewardedOnAdLoadedEvent;
        RewardedAd.OnAdLoadFailed += RewardedOnAdLoadFailedEvent;
        RewardedAd.OnAdDisplayed += RewardedOnAdDisplayedEvent;
        RewardedAd.OnAdDisplayFailed += RewardedOnAdDisplayFailedEvent;
        RewardedAd.OnAdClicked += RewardedOnAdClickedEvent;
        RewardedAd.OnAdClosed += RewardedOnAdClosedEvent;
        RewardedAd.OnAdRewarded += RewardedOnAdRewardedEvent;
        RewardedAd.OnAdInfoChanged += RewardedOnAdInfoChangedEvent;
    }
    void LoadRewardedAd() {
        // Load or reload RewardedAd
        RewardedAd.LoadAd();
    }
    void ShowRewardedAd() {
        // Show RewardedAd, check if the ad is ready before showing
        if (RewardedAd.IsAdReady()) {
            RewardedAd.ShowAd();
        }
    }
    // Implement RewardedAd events
    void RewardedOnAdLoadedEvent(LevelPlayAdInfo adInfo) { }
    void RewardedOnAdLoadFailedEvent(LevelPlayAdError error) { }
    void RewardedOnAdClickedEvent(LevelPlayAdInfo adInfo) { }
    void RewardedOnAdDisplayedEvent(LevelPlayAdInfo adInfo) { }
    void RewardedOnAdDisplayFailedEvent(LevelPlayAdInfo adInfo, LevelPlayAdError error) { }
    void RewardedOnAdClosedEvent(LevelPlayAdInfo adInfo) { }
    void RewardedOnAdRewardedEvent(LevelPlayAdInfo adInfo, LevelPlayReward adReward) { }
    void RewardedOnAdInfoChangedEvent(LevelPlayAdInfo adInfo) { }
}
```

--------------------------------

### Get Workspace Name, Type, and Dynamic Status

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/getworkspacefrompath

Example using the shorthand `gwp` command to get the workspace name, type, and dynamic status from the current directory, formatted as a string.

```text
cm gwp . --format="Name: {wkname} | Type: {type}, {dynamic}"
```

--------------------------------

### Example cURL Request to Restart Server

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-restart

This cURL command demonstrates how to make a GET request to restart a server. Ensure you replace `<serverid>` and `YOUR_AUTH_CREDENTIALS` with your specific values.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/server/<serverid>/restart' \
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Java Example

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/rewarded-ads-integration

Example of how to use the getReward API in Java to retrieve reward data and check the amount.

```APIDOC
## Java getReward Example

### Description
This example shows how to call the `getReward` method in Java and then check if the reward amount is greater than 0 before proceeding with reward logic.

### Code
```java
LevelPlayReward reward = mRewardedAd.getReward("bonus_level");
if (reward.getAmount() > 0) {
    // Grant reward logic
}
```
```

--------------------------------

### Get Comprehensive Command Help - UVCS CLI

Source: https://docs.unity.com/en-us/unity-version-control/cli/help

For detailed help, including examples, for a specific command, use the `--help` flag. Replace `<command>` with the command you need assistance with.

```bash
cm <command> --help
```

--------------------------------

### Example cURL Request to Reserve Server

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/reserve

Use this cURL command to make a GET request to reserve a game server. Ensure you replace `<machineid>`, `<serverid>`, and `YOUR_AUTH_CREDENTIALS` with your specific values.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/machine/<machineid>/reserve_server?serverid=<serverid>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
--header 'Content-Type: application/x-www-form-urlencoded'
```

--------------------------------

### Example commandline configuration variable

Source: https://docs.unity.com/en-us/clanforge/legacy/configuration-variables

A string of the launch parameters passed to the game server or application on launch.

```text
-config path/to/server.json
```

--------------------------------

### Get Pixyz Website URL

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_coreinterface

Retrieves the Pixyz website URL. No specific setup is required.

```csharp
[HandleProcessCorruptedStateExceptions]
public string GetPixyzWebsiteURL()
```

--------------------------------

### Install Unity Editors

Source: https://docs.unity.com/en-us/hub/hub-cli

Installs a new Unity Editor version from the releases list or archive using the `install` command.

```APIDOC
## POST /api/editors/install

### Description
Installs a new Unity Editor version.

### Method
POST

### Endpoint
/api/editors/install

### Parameters
#### Query Parameters
- **version** (string) - Required - The Editor version to install.
- **changeset** (string) - Optional - The changeset of the Editor. This information might be required if the version isn't in the release list.
- **module** (string) - Optional - The module ID. Accepts multiple module IDs.
- **childModules** (boolean) - Optional - Ensures any child modules of the specified `--module` are also downloaded.
- **architecture** (string) - Optional - macOS only: Use this argument to explicitly choose between the Apple Silicon or Intel version of the Editor. Defaults to Intel, `x86_64`.

### Request Example
```json
{
  "version": "2022.1.1f1",
  "changeset": "9b001d489a54",
  "module": "android",
  "childModules": true,
  "architecture": "arm64"
}
```

### Response
#### Success Response (200)
- **message** (string) - Indicates successful installation.

#### Response Example
```json
{
  "message": "Unity Editor installed successfully."
}
```
```

--------------------------------

### Install License

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_coreinterface

Installs a new license using a provided file path. Supports both .bin and .lic file types. The 'user' parameter determines if the license is installed for the current user only or for all users, with a specific post-installation step required for all-user installations.

```csharp
[HandleProcessCorruptedStateExceptions]
public void InstallLicense(string licensePath, bool user = false)
```

--------------------------------

### SKAN CV Reporting API Request Example

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/skan-reporting-api

Example GET request to retrieve SKAN CV data. Includes parameters for date range, breakdowns, bundle ID, and campaign ID.

```http
https://api.ironsrc.com/advertisers/v4/reports/skan/cv?breakdowns=day,campaign,title&startDate=2021-11-10&endDate=2021-11-10&bundleId=com.abcd.game&campaignId=1234567
```

--------------------------------

### Display Help for Unity Version Control CLI Support

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/support

Run this command to see the general usage of the support command.

```bash
cm support
```

--------------------------------

### Set up Red Hat / CentOS Repository

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Downloads and installs the Unity Version Control stable repository configuration file for Red Hat and CentOS systems.

```bash
sudo wget https://www.plasticscm.com/plasticrepo/stable/redhat/plasticscm-stable.repo \
  -O /etc/yum.repos.d/plasticscm-stable.repo
```

--------------------------------

### Paginate Labels with Limit and Offset

Source: https://docs.unity.com/en-us/unity-version-control/cli/cm-find/cm-find-syntax

Use 'limit' to specify the number of results and 'offset' to define the starting point. This example displays ten labels, starting from the twenty-first, owned by the current user.

```text
cm find label "where owner='me'" limit 10 offset 20
```

--------------------------------

### Deploy Configuration With Source Control

Source: https://docs.unity.com/en-us/services/service-environments

Leverage source control with `ugs deploy` for easier tracking and automation of deployments. This example demonstrates deploying from a local configuration folder after checking out specific branches or tags.

```bash
git checkout origin/stable
ugs deploy ugs_config_folder
#rollback
git checkout tags/last-release -b stable
ugs deploy ugs_config_folder
```

--------------------------------

### Install Modules for Unity Editor

Source: https://docs.unity.com/en-us/hub/hub-cli

Downloads and installs a module to an installed Unity Editor using the `install-modules` command.

```APIDOC
## POST /api/editors/install-modules

### Description
Downloads and installs a module to an installed Unity Editor.

### Method
POST

### Endpoint
/api/editors/install-modules

### Parameters
#### Query Parameters
- **version** (string) - Required - Specifies the version of the installed Editor to add the module to.
- **module** (string) - Required - Specifies the module ID. You can add more than one module at a time.
- **childModules** (boolean) - Optional - Ensures any child modules of the specified `--module` are also downloaded.

### Request Example
```json
{
  "version": "6000.3.7f1",
  "module": "android",
  "childModules": true
}
```

### Response
#### Success Response (200)
- **message** (string) - Indicates successful module installation.

#### Response Example
```json
{
  "message": "Module installed successfully."
}
```
```

--------------------------------

### P4Sync Example Command

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

An example of the 'cm sync' command for P4Sync, demonstrating how to connect to a Perforce server and specify branch folders.

```console
cm sync plastic-repo p4multibranch p4server:1666 --mainbranch=//depot/main --branchesfolder=//depot --user=user --pwd=mypwd
```

--------------------------------

### Get Instances Request URL

Source: https://docs.unity.com/en-us/grow/levelplay/platform/api/instances-api-v4

Example URL for retrieving a list of all application instances using the v3 API. Ensure you replace 'aa2209b1d' with your actual application key.

```http
https://platform.ironsrc.com/partners/publisher/instances/v3?appKey=aa2209b1d
```

--------------------------------

### Initialize Manifest File

Source: https://docs.unity.com/en-us/cloud/virtual-private-cloud/on-premises/installation/deployment

Create a new `manifest.yaml` file for your deployment configuration. This command initiates the process, and you will be prompted for various deployment details.

```sh
vpctl manifest init
```

--------------------------------

### SKAN Reporting API Request Example

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/skan-reporting-api

Example of a GET request to the SKAN Reporting API. Includes parameters for campaign IDs, country, breakdowns, metrics, count, date range, and sort direction.

```http
https://api.ironsrc.com/advertisers/v4/reports/skan?campaignId=1234567,7654321&country=US,CA&breakdowns=country,day&metrics=impressions, installs,spend&count=100&startDate=2021-04-14&endDate=2021-04-23&direction=desc
```

--------------------------------

### Configure Private Cloud from Code

Source: https://docs.unity.com/en-us/cloud/asset-manager/python-sdk/virtual-private-cloud

Use this method before calling initialize to set up the SDK for Virtual Private Cloud integration. Provide the FQDN, OIDC config URL, and path prefix.

```python
integration_creation = unity_cloud.set_private_cloud(fully_qualified_domain_name="my-fqdn",
                                                     openid_config_url="my-oidc-config-url",
                                                     path_prefix="my-path-prefix")
```

--------------------------------

### Example Request to Get Locations

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/locations-list

This `curl` command demonstrates how to request scalable locations, including authentication and the required account service ID.

```bash
curl --location -g 'https://api.multiplay.co.uk/cfp/v1/server/locations?accountserviceid=<accountserviceid>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Initialize and Sign in Anonymously

Source: https://docs.unity.com/en-us/authentication/uas-native-sdk

Set up the AuthenticationClient with environment and project IDs, then sign in anonymously. The callback handles the sign-in response.

```cpp
    unity::uaslib::AuthenticationClient client;
    client.SetEnvironmentName(UNITY_ENVIRONMENT_NAME);
    client.SetProjectId(UNITY_PROJECT_ID);

    Unity::Authentication::AuthenticationSignInCallback cb;
    cb = [](const unity::uaslib::AuthenticationSignInResponse &response) {
        std::cout << "Authentication Sign In Response:\n";
        std::cout << "Token: " << response.Token << "\n";
        std::cout << "PlayerId: " << response.PlayerId << "\n";
        std::cout << "ExpiresIn: " << response.ExpiresIn << "\n";
    };

    client.SignInAnonymously(cb);
```

--------------------------------

### Render Audio Start

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/deprecated

Starts rendering audio from a specified path. This function is for debug use only.

```APIDOC
## POST /api/aux/render_audio_start

### Description
Starts rendering audio from a specified path. This function is for debug use only.

### Method
POST

### Endpoint
/api/aux/render_audio_start

### Parameters
#### Request Body
- **path** (string) - Required - The path to the audio file to render.
```

--------------------------------

### Get Assets Response Example

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/assets-api

Example JSON response when retrieving assets. Includes asset details such as id, type, titleId, orientation, source, and duration. Also includes totalResultsCount and requestId for pagination.

```json
{
	"assets": [{
		"id": 200305,
		"type": "video",
		"titleId": 501567,
		"orientation": "all",
		"source": "none",
		"duration": 30
	}, {
		"id": 200304,
		"type": "image",
		"titleId": 501567,
		"orientation": "all",
		"source": "none",
		"duration": null
	}, {
		"id": 200303,
		"type": "html_iec",
		"titleId": 501567,
		"orientation": "all",
		"source": "playworks",
		"duration": null
	}, {
		"id": 200302,
		"type": "video",
		"titleId": 501567,
		"orientation": "all",
		"source": "none",
		"duration": 17
	}, {
		"id": 200301,
		"type": "html",
		"titleId": 501567,
		"orientation": "portrait",
		"source": "none",
		"duration": null
	}, {
		"id": 200300,
		"type": "html_iec",
		"titleId": 501567,
		"orientation": "portrait",
		"source": "none",
		"duration": null
	}],
	"totalResultsCount": 6,
	"requestId": "MjA1MzUzLjIwMDMwMy40LjM1OTY="
}
```

--------------------------------

### Full Request Example for Updating Country Group

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/country-group-api

This JSON example demonstrates how to update an existing country group, specifying country-level bid and setup goal values. Note that 'bid' can be set to 'default'.

```json
{
  "countries": [
    {"Country": "AT", "bid": "default", "setupGoal" : 12}
  ]
}
```

--------------------------------

### Pre-export Method Example

Source: https://docs.unity.com/en-us/build-automation/build-automation-integrations/use-build-automations-build-manifest-during-runtime

Example of a pre-export method that uses BuildManifestObject to update PlayerSettings.

```csharp
using UnityEngine;
using UnityEditor;
using System;

public class CloudBuildHelper : MonoBehaviour
{
    #if UNITY_CLOUD_BUILD
        public static void PreExport(UnityEngine.CloudBuild.BuildManifestObject manifest)
        {
            // Example: Update bundleVersion in PlayerSettings based on buildNumber from manifest
            PlayerSettings.bundleVersion = string.Format("1.0.{0}", manifest.GetValue<int>("buildNumber"));
        }
    #endif
}
```

--------------------------------

### Get Default SDK Configuration

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Retrieves the default configuration for the Vivox SDK. This can be used as a starting point for custom configurations passed to vx_initialize3.

```c
int vx_get_default_config3(vx_sdk_config_t *config, size_t config_size);
```

--------------------------------

### Manage Plastic Proxy Service on Windows

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

Use plasticd proxy subcommands to install, start, stop, restart, check status, and uninstall the Plastic Proxy service on Windows.

```bash
plasticd proxy --installservice
```

```bash
plasticd proxy --start
```

```bash
plasticd proxy --stop
```

```bash
plasticd proxy --restart
```

```bash
plasticd proxy --status
```

```bash
plasticd proxy --uninstallservice
```

--------------------------------

### List All Repositories

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/repository-list

Lists all available repositories on the server. No additional arguments are required.

```bash
cm repository
```

--------------------------------

### Get Custom Version Tag

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_coreinterface

Retrieves the Pixyz custom version tag. No specific setup is required.

```csharp
[HandleProcessCorruptedStateExceptions]
public string GetCustomVersionTag()
```

--------------------------------

### Initialize Vivox SDK with Configuration

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Initializes the Vivox SDK with a custom configuration. Use vx_get_default_config3 to obtain a default configuration structure.

```c
int vx_initialize3(vx_sdk_config_t *config, size_t config_size);
```

--------------------------------

### Start Pixyz UI from Batch File (Windows)

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/pixyzui/setup

Navigate to the Pixyz UI folder and execute this batch file to automatically set up the virtual environment and launch Pixyz UI.

```bash
cd PixyzUI
./PixyzUI.bat
```

--------------------------------

### Unattended Plastic SCM Installation

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

Run the Plastic SCM installer in unattended mode with the '--mode unattended' and '--unattendedmodeui none' flags. This example shows how to update the system environment PATH variable.

```bash
PlasticSCM-8.0.16.3621-windows-installer.exe --mode unattended --unattendedmodeui none
```

--------------------------------

### Example Request to Get Fleet Profile Switch Status

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/fleet-profile-switch-status

Use this `curl` command to make a GET request to the fleet profile switch status endpoint. Ensure you replace `<fleetID>` and `YOUR_AUTH_CREDENTIALS` with your specific values.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v2/fleet/<fleetID>/switchprofile' \
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS' \
--header 'Content-Type: application/json'
```

--------------------------------

### Create Capture Audio Start Request

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/group__devices

Allocates and initializes a vx_req_aux_capture_audio_start_t object. Use this to begin capturing audio.

```c
VIVOXSDK_DLLEXPORT int vx_req_aux_capture_audio_start_create(
    vx_req_aux_capture_audio_start_t ** req
)
```

--------------------------------

### Get Current License Information

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/core_functions

Retrieve information about the currently installed license. This function returns a LicenseInfos object.

```python
core.getCurrentLicenseInfos() -> core.LicenseInfos
```

--------------------------------

### Example Module Project Structure with DTOs

Source: https://docs.unity.com/en-us/cloud-code/modules/how-to-guides/initialize-modules/dto

Illustrates the typical output directory structure after building a module that includes DTOs, showing where to find the generated DLLs.

```text
├─ Main.csproj
    └─ bin
        └─ Debug
            └─ Release
                └─ net6.0
                    └─ linux-x64
                        └─ publish
                            └─ Main.dll
                            └─ Main.pdb
                            └─ DTOs.dll
                            └─ DTOs.pdb
                            ...

```

--------------------------------

### Install vpctl Tool (Custom Directory)

Source: https://docs.unity.com/en-us/cloud/virtual-private-cloud/on-premises/installation/prerequisites

Optionally specify a custom installation directory for the vpctl tool by providing it as the second argument to the install script. Defaults to /usr/local/bin.

```bash
./install-vpctl.sh 0.8.0 /opt/bin
```

--------------------------------

### Initialize Unity Services and Vivox SDK

Source: https://docs.unity.com/en-us/vivox-core/access-token-guide/authentication-package-tokens

This C# code snippet demonstrates the setup for initializing Unity Services, signing in anonymously, and then initializing the Vivox SDK. Ensure the Unity Authentication package is included in your project.

```csharp
using Unity.Services.Authentication;

public class VoiceManager : MonoBehaviour
{
    async void Start()
    {
        await UnityServices.InitializeAsync();
        await AuthenticationService.Instance.SignInAnonymouslyAsync();
        await VivoxService.Instance.InitializeAsync();
    }
}
```

--------------------------------

### Get Part Occurrences

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/scene_functions

Recursively finds all occurrences that contain a specific part component. Can start from a specified occurrence.

```python
scene.getPartOccurrences(fromOcc=None) -> scene.OccurrenceList
```

--------------------------------

### Example cURL Request for Image Update Status

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-update-status

This example demonstrates how to make a GET request to the image update status endpoint using cURL. Ensure you replace placeholders with your actual values and include your authorization credentials.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/imageupdate/<updateid>/status?accountserviceid=<accountserviceid>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Create a Repository with Name

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/repository-create

Use this command to create a new repository with a specified name on the default server.

```bash
cm repository MyRep
```

--------------------------------

### Delay Network Connection Start as Host

Source: https://docs.unity.com/en-us/mps-sdk/manage-session-network-connection

This example shows how to delay the network connection in a host session until all players have joined. It uses the Session API and event handlers to manage the connection lifecycle.

```csharp
async Task StartSessionAsHost()
{
    var options = new SessionOptions { MaxPlayers = 4 }; // note the omitted `With<X>Network() call.

    var session = await MultiplayerService.Instance.CreateSessionAsync(options);
    session.PlayerJoined += OnPlayerJoined;
    session.Network.StartFailed += OnNetworkStartFailed;
    session.Network.StateChanged += OnNetworkStateChanged;

    Debug.Log($
```

--------------------------------

### Command-line Checkout Example

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

This command-line example demonstrates checking out a file through symlinks. It highlights a previous issue where symlinks with '.' and '..' elements in their target paths caused commands to fail, and shows the expected behavior after the fix.

```bash
$ cm co links/linkedfile.txt
```

```bash
The element '/wk/links/../content/file.tx^' is either a private file or it is already checked out in the current workspace.
```

--------------------------------

### Get a transformation

Source: https://docs.unity.com/en-us/cloud/asset-manager/python-sdk/manage-transformations

Retrieves a previously started transformation by providing dataset and transformation IDs. Works for transformations that are completed or in progress.

```python
    transformation = unity_cloud.assets.get_transformation(
        org_id = "012345678912",
        project_id = "1234abcd-ab12-cd34-ef56-123456abcdef",
        asset_id = "0123456789abcdefghijklmn",
        asset_version = "1234abcd-ab12-cd34-ef56-123456abcdef",
        dataset_id = "1234abcd-12ab-34cd-56ef-123456abcdef",
        workflow_id = "012345678912"
    )
```

--------------------------------

### Example API Request URL for User Ad Revenue v3

Source: https://docs.unity.com/en-us/grow/is-ads/monetization/apis/impression-level-revenue-server-side

Construct a GET request URL with required parameters to fetch user ad revenue data. Ensure 'appKey', 'date', and 'reportType' are correctly set.

```text
https://platform.ironsrc.com/partners/userAdRevenue/v3?appKey=12345678&date=2018-12-15&reportType=1
```

--------------------------------

### Sign in as Alice using login -u

Source: https://docs.unity.com/en-us/vivox-core/text-chat-guide/sdksampleapp/log-in-as-alice

Use the 'login -u' command to sign in as the example user 'Alice'. The -help option displays available command options.

```plaintext
[SDKSampleApp]: conn
* Connecting to http://mt1s.www.vivox.com/api2 with connector handle http://mt1s.www.vivox.com/api2...
* Issuing req_connector_create with cookie=1
* Request req_connector_create with cookie=1 completed.
[SDKSampleApp]: login -u .xyzzy.alice.
* Logging .xyzzy.alice. in with connector handle http://mt1s.www.vivox.com/api2 and account handle .xyzzy.alice.
* Issuing req_account_anonymous_login with cookie=2
* evt_account_login_state_change: .xyzzy.alice. login_state_logging_in
* Request req_account_anonymous_login with cookie=2 completed.
* evt_account_login_state_change: .xyzzy.alice. login_state_logged_in
```

--------------------------------

### GET /placements/v1

Source: https://docs.unity.com/en-us/grow/levelplay/platform/api/placements

Provides placement setup information. You must authenticate each API request by using Bearer API authentication.

```APIDOC
## GET /placements/v1

### Description
Provides placement setup information.

### Method
GET

### Endpoint
https://platform.ironsrc.com/partners/publisher/placements/v1/

### Parameters
#### Query Parameters
- **appKey** (string) - Required - Application unique identifier

### Response
#### Success Response (200)
- **adUnit** (string) - ad-unit name: rewardedVideo interstitial banner
- **name** (string) - placement unique name
- **id** (integer) - Placement unique identifier
- **adDelivery** (integer) - 1 if placement ad delivery is on, otherwise 0
- **itemName** (string) - Reward name (max 30 chars) (Required for rewardedVideo only)
- **rewardAmount** (integer) - Amount of items to gift for a single ad view (max 2000000000) (Required for rewardedVideo only)
- **capping.enabled** (integer) - 1 to enable capping, otherwise 0
- **capping.limit** (integer) - Maximum number of ads delivered per capping interval (max 1000)
- **capping.interval** (string) - capping interval: d - days h - hours
- **pacing.enabled** (integer) - 1 to enable pacing, otherwise 0
- **pacing.minutes** (float) - Minimum gap in minutes between ad delivery (max 1000)

#### Response Example
```json
[
    {
        "name": "Home_Screen",
        "id": 12,
        "adUnit": "rewardedVideo",
        "itemName": "Coins",
        "rewardAmount": 3,
        "adDelivery": 1,
        "capping": {
            "enabled": 1,
            "cappingLimit": 3,
            "cappingInterval": "h"
        },
        "pacing": {
            "enabled": 1,
            "pacingMinutes": 12.5
        },
        "abVersion": "A"
    }
]
```
```

--------------------------------

### Install Unity Version Control Proxy Server on Fedora

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Installs the proxy server component for Unity Version Control on Fedora using dnf.

```bash
sudo dnf install plasticscm-proxy-server
```

--------------------------------

### Example GameExe configuration variable

Source: https://docs.unity.com/en-us/clanforge/legacy/configuration-variables

The name of the primary executable for the game server.

```text
server-linux
```

--------------------------------

### Create and Check-in Symlinks on Windows

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

Demonstrates how to create symbolic links on Windows using `mklink` and then add and check them in using Unity DevOps Version Control commands.

```console
C:\wkspaces\sokoban> mklink /D Scripts Assets\Scripts
C:\wkspaces\sokoban> cm add Scripts
The selected items are about to be added. Please wait ...
Item c:\wkspaces\sokoban\Scripts was correctly added
C:\wkspaces\sokoban> cm ci --symlink Scripts
The selected items are about to be checked in. Please wait ...
- Checkin finished 26 bytes/26 bytes [################################] 100 %
```

```console
C:\wkspaces\sokoban> cm co --symlink Scripts
The selected items are about to be checked out. Please wait ...
Item c:\wkspaces\sokoban\Scripts was correctly checked out
```

```console
C:\wkspaces\sokoban> cm undo --symlink Scripts
c:\wkspaces\sokoban\Scripts unchecked out correctly
```

--------------------------------

### GET /reports/cost

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/cost-api

Retrieves campaign cost and installs based on the requested breakdowns and filters. The data can be retrieved in JSON or CSV format.

```APIDOC
## GET /reports/cost

### Description
Retrieves campaign cost and installs based on the requested breakdowns and filters. The data can be retrieved in JSON or CSV format.

### Method
GET

### Endpoint
https://api.ironsrc.com/advertisers/v4/reports/cost

### Parameters
#### Query Parameters
- **startDate** (Date. String in the format: YYYY-MM-DD) - Required - Start date for the report.
- **endDate** (Date. String in the format: YYYY-MM-DD) - Required - End date for the report.
- **metrics** (Comma-separated list of strings) - Required - A list of metrics to be included in the response. The default is none. Values: impressions, clicks, installs, billable_spend, ecpi.
- **breakdowns** (Comma-separated list of strings) - Optional - A list of breakdowns by which the response data is returned. The default is none. Values: day, campaign, title, os, country.
- **format** (String) - Optional - The format of the response. The default is JSON. Values: json,csv.
- **count** (Integer) - Optional - The number of records to return in the response. The default is 10000 and the maximum is 250000.
- **campaignId** (Comma-separated list of integers) - Optional - List of campaign IDs to filter.
- **bundleId** (Comma-separated list of strings) - Optional - List of bundle IDs to filter.
- **country** (Comma-separated list of strings by ISO 3166-2) - Optional - List of countries to filter. Values: Comma-separated list of strings by ISO 3166-2.
- **os** (String) - Optional - Present data for this operating system only. Values: ios, android.
- **order** (String) - Optional - Order the results by breakdown / metric. Values: impressions, installs, billable spend day, campaign, title, os, country.
- **direction** (String) - Optional - Order by direction. Default is asc. Values: asc, desc.

### Request Example
https://api.ironsrc.com/advertisers/v4/reports/cost?campaignId=1234567\&startDate=2023-03-10\&endDate=2023-03-11\&breakdowns=day,campaign,title\&metrics=impressions,clicks,installs,billable_spend,ecpi

### Response
#### Success Response (200)
- **data** (Array) - Array of cost and install data based on the specified parameters.
- **totalCount** (Integer) - Total number of records returned.

#### Response Example
```json
{
  "data": [
    {
      "date": "2023-03-10",
      "campaign_name": "Example Campaign",
      "bundle_id": "com.example.app",
      "impressions": 10000,
      "clicks": 500,
      "installs": 50,
      "billable_spend": 100.50,
      "ecpi": 2.01
    }
  ],
  "totalCount": 1
}
```
```

--------------------------------

### Get Unity Project ID - C++

Source: https://docs.unity.com/en-us/authentication-unreal/sdk-api/authentication/authentication-blueprint-api

Retrieves the unique identifier for the current Unity project. Returns a GUID representing the project.

```cpp
UFUNCTION(BlueprintPure, Category = "Unity Gaming Services | Authentication")
FGuid GetUnityProjectId() const
```

--------------------------------

### Start Plastic SCM Service (Linux - init.d)

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/start-stop-restart-server

Command to start the Plastic SCM service using the init.d script on Linux.

```text
/etc/init.d/plasticsd start
```

--------------------------------

### Authenticate with Server Parameters

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

Example of authenticating against a server using command-line parameters for username and password, even without a valid client.conf file. This ensures authentication works correctly with specific server configurations.

```text
cm repo list --username=sergio --password="t0p_secret!" --workingmode=LDAPWorkingMode --server="my-organization@cloud"
```

--------------------------------

### Get Workspace Name with Custom Format

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/getworkspacefrompath

Example of retrieving only the workspace name using the `--format` option with a specific string.

```text
cm getworkspacefrompath c:\myworkspace\code\file1.cpp --format="Workspace name: {wkname}"
```

--------------------------------

### Example GET Request for Game Versions

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/game-version-list

This cURL command demonstrates how to request a list of game versions, including optional filters for game ID, game version ID, and game version identifier. Ensure you replace placeholders with your actual credentials and IDs.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/gameversion/list?accountserviceid=<accountserviceid>&gameid=<gameid>&gameversionid=<gameversionid>&gameversion_identifier=<gameversion_identifier>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Get Custom Version Tag

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/core_functions

Retrieves the custom version tag for the Pixyz installation. This function returns a string representing the custom tag.

```python
core.getCustomVersionTag() -> core.String
```

--------------------------------

### Workspace Configuration Example

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

Illustrates a typical workspace configuration with controlled and private files before a move operation.

```text
/fileA.txt - CONTROLLED
/fileB.txt - CONTROLLED
/fileC.txt - CONTROLLED
/fileD.txt - PRIVATE
```

--------------------------------

### Example Trigger Filter Configuration

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

This example shows how to configure a trigger filter for repositories. Previously, appending '*' was necessary for filters to work correctly with repositories.

```text
cm trigger create before-checkin MyTrigger c:\tmp\mytrigger.bat --filter="rep:repo2,*"
```

```text
cm trigger create before-checkin MyTrigger c:\tmp\mytrigger.bat --filter="rep:repo2"
```

--------------------------------

### Filter with Wildcards

Source: https://docs.unity.com/en-us/unity-version-control/triggers/concepts/filters

Utilize wildcards in filters to match multiple repositories, objects, or paths. For example, `br*` matches any string starting with 'br'.

```bash
--filter="STATUS,br*"
```

```bash
--filter="rep:test*"
```

--------------------------------

### Initialize Web Offerwall SDK

Source: https://docs.unity.com/en-us/grow/offerwall/web/advanced/installation-and-authentication

Initialize the SDK with your application's details after adding the main SDK snippet. Replace placeholders with your actual SDK key, user ID, and placement name.

```html
<script>
  Tapjoy('init', {
    sdkKey: '<SDK_KEY>',
    publisherUserId: '<USER_ID>',
    eventName: '<PLACEMENT_NAME>', // default is '#WebOfferwall'
  });
</script>
```

--------------------------------

### View Purge History

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/purge-history

Shows the ID and status for all purges ever registered in the server. No specific setup is required beyond having the CLI installed.

```bash
cm purge history
```

--------------------------------

### Example Schedule Configuration (Combined)

Source: https://docs.unity.com/en-us/cloud-code/triggers/tutorials/schedule-events/cli

A sample JSON configuration file demonstrating both recurring and one-time schedule types. This file can be deployed to activate the defined schedules.

```json
{
  "$schema": "https://ugs-config-schemas.unity3d.com/v1/schedules.schema.json",
  "Configs": {
    "Schedule1": {
      "EventName": "EventType1",
      "Type": "recurring",
      "Schedule": "0 * * * *",
      "PayloadVersion": 1,
      "Payload": "{}"
    },
    "Schedule2": {
      "EventName": "EventType2",
      "Type": "one-time",
      "Schedule": "2024-03-03T13:06:32.311+00:00",
      "PayloadVersion": 1,
      "Payload": "{ \"message\": \"Hello, world!\"}"
    }
  }
}
```

--------------------------------

### Install Specific Unity Hub Beta Version on Ubuntu

Source: https://docs.unity.com/en-us/hub/install-hub-linux

Installs a specific beta version of Unity Hub. Replace `<version>` with the desired version string, e.g., `3.4.1-beta.1`.

```shell
sudo apt update
sudo apt install unityhub=<version>
```

--------------------------------

### Implementation Example: Launch Test Suite on Success Callback

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/integration-test-suite

Launch the test suite within the onInitializationComplete callback of the InitializationListener after the LevelPlay SDK has successfully initialized.

```java
LevelPlay.init(this, appKey,new InitializationListener){
   
    @Override
    public void onInitializationComplete() {
        // LevelPlay SDK is initialized 
    
       //Launch test suite
       LevelPlay.launchTestSuite(this);
}

```

--------------------------------

### Get Object Specification Help

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/objectspec

Use this command to get general information on how to build object specifications.

```bash
cm objectspec
```

--------------------------------

### Install Eclipse Plug-in

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Commands to install the Unity Version Control plug-in for Eclipse. Ensure you replace `$ECLIPSE_ROOT` with your Eclipse installation directory.

```bash
rm -f $ECLIPSE_ROOT/plugins/com.codicesoftware.*.jar
cp /opt/plasticscm5/client/eclipse_plugin/com.codicesoftware.*.jar $ECLIPSE_ROOT/plugins
$ECLIPSE_ROOT/eclipse -clean
```

--------------------------------

### Verify vpctl Installation

Source: https://docs.unity.com/en-us/cloud/virtual-private-cloud/on-premises/installation/prerequisites

After installation, run this command to confirm that the vpctl tool is accessible and functioning correctly.

```bash
vpctl version
```

--------------------------------

### Example A/B Testing Result JSON

Source: https://docs.unity.com/en-us/matchmaker/ab-testing

This is an example of the JSON output for A/B testing results. It indicates whether A/B testing is active, the variant ID, and the pool IDs involved. A null result may indicate issues with SDK installation or configuration.

```json
{
  "isAbTesting": true,
  "variantId": "aaaaaaaa-cdf2-4752-bae1-52ecc90d38c6:Variant 1",
  "poolId": "bbbbbbbb-722f-40f2-87f4-28ec307b7d0c",
  "basePoolId": "cccccccc-39a0-42ca-a15e-77544d7ffe41"
}
```

--------------------------------

### Example File Path Rules for Compression

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

Illustrates different types of rules that can be specified in 'compression.conf' to match file paths for compression configuration.

```text
1. /dir/foo.png
2. foo.png
3. .png
4. /**/foo*.???
```

--------------------------------

### Render Audio Start

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/group__devices

Starts audio rendering for a specified sound file on a selected device, with looping capability.

```APIDOC
## Render Audio Start

### Description
Ensures that a specific selected render device is functioning properly by playing a sound file.

### Method
POST (Assumed, as it starts a process)

### Endpoint
/api/aux/render/audio/start

### Parameters
#### Request Body
- **sound_file_path** (string) - Required - Path to a local monaural .wav or .au sound file.
- **loop** (integer) - Optional - Set to 1 to loop the sound file continuously. Defaults to 0.

### Request Example
```json
{
  "sound_file_path": "/path/to/sound.wav",
  "loop": 1
}
```

### Response
#### Success Response (200)
- **status** (string) - Indicates success or failure.

#### Response Example
```json
{
  "status": "success"
}
```
```

--------------------------------

### Check-in Operation Example - Gluon

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

This example demonstrates a scenario where a check-in operation might fail due to the order of operations when moving an item and deleting its parent directory. The fix ensures correct handling.

```text
* move /src/lib/foo.c -> /foo.c
* rm   /src/lib
* cm checkin
```

--------------------------------

### Example cURL Request for Image Diff Retry

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-diff-retry

This example demonstrates how to use cURL to send a GET request to retry an image difference analysis job. Ensure you replace placeholders with your actual diff ID, account service ID, and authorization credentials.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/imagediff/<diffid>/retry?accountserviceid=<accountserviceid>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Launch GUI Diffs with Program Arguments

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

Examples of using command-line arguments to launch Plastic SCM GUI diffs for branches and changesets on Windows.

```text
plastic.exe --diffbranch=br:/main@myrepo@myserver:8087
```

```text
plastic.exe --diffchangeset=cs:2@myrepo@myserver:8087
```

```text
plastic.exe --diffchangesetsrc=cs:0@myrepo@myserver:8087 --diffchangesetdst=cs:2@myrepo@myserver:8087
```

--------------------------------

### View Help for Unity Licensing Server CLI (Windows)

Source: https://docs.unity.com/en-us/licensing-server/server-setup

Display all available command parameters for the Unity Licensing Server CLI on Windows. This is useful for understanding the full syntax of each command.

```bash
.\Unity.Licensing.Server.exe --help
```

--------------------------------

### Manage Plastic Proxy Service

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

Commands to install, start, stop, and uninstall the Plastic proxy service. Ensure you are in the correct directory when executing these commands.

```console
C:\PlasticSCM\server> plasticd proxy --installservice
Installing service Plastic Proxy...
Service Plastic Proxy has been successfully installed.
Creating EventLog source Plastic Proxy in log Application...
Service correctly installed
```

```console
C:\PlasticSCM\server> plasticd proxy --start
Server started
```

```console
C:\PlasticSCM\server> plasticd proxy --stop
Server stopped
```

```console
C:\PlasticSCM\server> plasticd proxy --uninstallservice
Removing EventLog source Plastic Proxy.
Service Plastic Proxy is being removed from the system...
Service Plastic Proxy was successfully removed from the system.
Service correctly uninstalled
```

--------------------------------

### Example Server Status Output

Source: https://docs.unity.com/en-us/licensing-server/server-admin

This is an example of the output you can expect when running the `status` command. It details the health of various components like HTTP configuration, licenses, licensing configuration, plugins, and database.

```bash
Server Version: 2.0.0+e81737f
Healthy
HttpConfig: Healthy
HTTP config is healthy
  [OK] Kestrel: Found config section Kestrel
  [OK] Kestrel:Endpoints:HTTP:Url: Found valid config Kestrel:Endpoints:HTTP:Url: http://10.192.192.255:80
ServerLicense: Healthy
Server license and delegation are valid
  [OK] ServerLicense::Context::FirstPhysicalAddress: 48:2a:e3:87:3b:19
  [OK] ServerLicense::Context::Platform: Win32NT
  [OK] ServerLicense::Context::ProcessorCount: 12
  [OK] ServerLicense::Context::MachineName: LAPTOP-2Q28U8QB
  [OK] ServerLicense::ContextCount: Found 4 out of 4 context values
  [OK] ServerLicense::EntitlementGroup::test-licenseServer_3573567292644_1: ... has valid server entitlements
  [OK] ServerLicense::EntitlementGroupCount: Found 1 valid server license(s)
  [OK] ServerLicense::Delegation::test-licenseServer-delegation-20200925_145658.xml: Found valid server delegation: <absolute_path>
  [OK] ServerLicense::DelegationsCount: Found 1 valid server delegations
LicensingConfig: Healthy
Licensing configuration is healthy
  [OK] licensing:licenseSigningCertLoading: Successfully loaded license signing key
  [OK] SyntaxValidation: Configuration syntax is valid
  [WARNING] licensing:defaultToolset: The defaultToolset configuration is invalid or not set. Valid toolsets are: ...
  [OK] licensing: Found config section licensing
  [OK] LicenseAclConfigValidation: License access control list configuration is valid
Plugins: Healthy
Plugins
  [OK] PluginAssemblies: 0
  [OK] RegisteredPlugins: 0
Database: Healthy
Connection state for Microsoft.Data.Sqlite.SqliteConnection is Open. Database is writable. Sufficient disk space available.
  [OK] FloatingDbStatus: Connection state for Microsoft.Data.Sqlite.SqliteConnection is Open. Database is writable. Sufficient disk space available.
  [OK] HistoricalDbStatus: Connection state for Microsoft.Data.Sqlite.SqliteConnection is Open. Database is writable. Sufficient disk space available.
```

--------------------------------

### Example ConfigPath configuration variable

Source: https://docs.unity.com/en-us/clanforge/legacy/configuration-variables

The path to the directory that has the configuration files for the game server.

```text
123456/cfg
```

--------------------------------

### Get Filtered Occurrences

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/scene_functions

Recursively finds all occurrences that satisfy a given filter expression. An optional starting occurrence can be provided to limit the search scope.

```python
scene.getFilteredOccurrences(filter, fromOcc=None) -> scene.OccurrenceList
```

--------------------------------

### Get Tessellation Infos

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/scene_sceneinterface

Fetches tessellation information for the scene, optionally starting from a specified root. This method includes exception handling for corrupted states.

```csharp
[HandleProcessCorruptedStateExceptions]
public GetTessellationInfosReturn GetTessellationInfos(uint root = 0)
```

--------------------------------

### Create Repository using 'mk' keyword

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/repository-create

Use the 'mk' keyword as an alias for 'create' to create a new repository.

```bash
cm repo mk list
```

--------------------------------

### Create Repository using 'create' keyword

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/repository-create

Use the 'create' keyword with the repository command to explicitly create a new repository.

```bash
cm repo create Rep01
```

--------------------------------

### Get Attributes for a Specific Object ID

Source: https://docs.unity.com/en-us/unity-version-control/cli/cm-find/find-attributes

Once you have the object ID, use this command to list all attributes associated with it. The example shows how to retrieve the 'status' attribute.

```bash
cm find attributes "where srcobj = 3" --nototal
objid:3@repid:2@repserver:localhost:8087 -- status --> PASSED
```

--------------------------------

### Example Reporting Request

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/ios/custom-adapters-reporting-api

ironSource will send GET requests to your reporting endpoint with date, apiKey, and user parameters. Ensure your endpoint is structured to receive these.

```http
GET https://www.CustomNetworkEndPoint.com?date=2021-09-01\&apiKey=value1\&myUser=value2
```

--------------------------------

### Initialize and Handle Apple Sign-In in Unity

Source: https://docs.unity.com/en-us/authentication/platform-signin/apple

This script demonstrates how to initialize the Apple Auth Manager and handle the sign-in process, including retrieving the ID token. Ensure you have the necessary external dependencies and have configured your project's Bundle ID in Unity Services.

```csharp
using System.Text;
using UnityEngine;

// External dependencies
using AppleAuth;
using AppleAuth.Enums;
using AppleAuth.Interfaces;
using AppleAuth.Native;

public class AppleExampleScript : MonoBehaviour
{
    IAppleAuthManager m_AppleAuthManager;
    public string Token { get; private set; }
    public string Error { get; private set; }

    public void Initialize()
    {
        var deserializer = new PayloadDeserializer();
        m_AppleAuthManager = new AppleAuthManager(deserializer);
    }

   public void Update()
   {
      if (m_AppleAuthManager != null)
      {
         m_AppleAuthManager.Update();
      }
   }

    public void LoginToApple()
    {
        // Initialize the Apple Auth Manager
        if (m_AppleAuthManager == null)
        {
            Initialize();
        }

        // Set the login arguments
        var loginArgs = new AppleAuthLoginArgs(LoginOptions.IncludeEmail | LoginOptions.IncludeFullName);

        // Perform the login
        m_AppleAuthManager.LoginWithAppleId(
            loginArgs,
            credential =>
            {
                var appleIDCredential = credential as IAppleIDCredential;
                if (appleIDCredential != null)
                {
                    var idToken = Encoding.UTF8.GetString(
                        appleIDCredential.IdentityToken,
                        0,
                        appleIDCredential.IdentityToken.Length);
                    Debug.Log("Sign-in with Apple successfully done. IDToken: " + idToken);
                    Token = idToken;
                }
                else
                {
                    Debug.Log("Sign-in with Apple error. Message: appleIDCredential is null");
                    Error = "Retrieving Apple Id Token failed.";
                }
            },
            error =>
            {
                Debug.Log("Sign-in with Apple error. Message: " + error);
                Error = "Retrieving Apple Id Token failed.";
            }
        );
    }
}
```

--------------------------------

### Example server.json for an Unallocated Server

Source: https://docs.unity.com/en-us/multiplay-hosting/concepts/server-json

This is an example of the server.json file when a server is unallocated, showing an empty allocation ID.

```plaintext
{
	"ipv6": "::1",
	"port": "9000",
	"allocatedUUID": "",
	"serverID": "12345",
	"machineID": "6789",
	"fleetID": "c0a3e2a1-6955-415c-b1d4-af9199833e6a",
	"regionID": "f15a6c27-de2a-4848-abc3-9579fbfd2259",
	"regionName": "North America",
	"queryPort": "9010",
	"ip": "127.0.0.1",
	"queryType": "sqp",
	"serverLogDir": "/mnt/unity/logs/"
}
```

--------------------------------

### Install License

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/core_functions

Adds a new license using either an activation .bin file or a .lic file. For .lic files, setting 'user' to false installs it for all users and requires running 'PiXYZFinishInstall' utility once.

```python
core.installLicense(licensePath, user=False)
```

--------------------------------

### Get Occurrences with Component

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/scene_functions

Recursively searches for and returns all occurrences that contain a component of a specified type. An optional starting occurrence can be provided to limit the search scope.

```python
scene.getOccurrencesWithComponent(componentType, fromOcc=None) -> scene.OccurrenceList
```

--------------------------------

### Example Console Output

Source: https://docs.unity.com/en-us/grow/offerwall/ios/introduction/manual-integration

This is an example of the console log output you can expect after a successful Tapjoy connection.

```swift
2020-01-29 16:01:55.422 Storyteller Roller[25869:1433019] [TJLog level: 4] Connect success with type:0
```

--------------------------------

### Initialize WebLicenseInfoList with Size

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_weblicenseinfolist

Constructs a WebLicenseInfoList with a specified size.

```csharp
public WebLicenseInfoList(int size)
```

--------------------------------

### Get Filtered Occurrences

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/scene_sceneinterface

Recursively retrieves all occurrences that validate a given filter expression. Accepts the filter expression string and an optional starting occurrence ID.

```csharp
[HandleProcessCorruptedStateExceptions]
public OccurrenceList GetFilteredOccurrences(string filter, uint fromOcc = 0)
```

--------------------------------

### List Users in Group Example

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/listusers

Example command to list users belonging to the 'Administrators' group on a specific organization's server.

```bash
cm listusers codice@cloud --group=Administrators
```

--------------------------------

### Install Pods

Source: https://docs.unity.com/en-us/grow/ads/ios-sdk/install-sdk

Run this command in your terminal after updating your Podfile to install the Unity Ads SDK.

```bash
pod install
```

--------------------------------

### Start Game Server

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-start-specific

Starts the game server identified by `<serverid>`. If the game server is already started, this endpoint has no effect.

```APIDOC
## GET /websites/unity_en-us/server/<serverid>/start

### Description
Starts the game server identified by `<serverid>`. If the game server is already started, this endpoint has no effect.

### Method
GET

### Endpoint
https://api.multiplay.co.uk/cfp/v1/server/<serverid>/start

### Parameters
#### Path Parameters
- **serverid** (string) - Required - The ID of the server to start

### Response
#### Success Response (200)
- **action** (string) - Action performed on the server. Will be 'start' for this endpoint
- **success** (boolean) - Boolean indicating whether the action was successful
- **server** (object) - Server object containing information about the server
  - **serverid** (integer) - ID of the server

### Request Example
```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/server/<serverid>/start' \
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

### Response Example
```json
{
    "action": "start",
    "success": true,
    "server": {
        "serverid": <serverid>
    }
}
```
```

--------------------------------

### Initialize Unity Services and Sign In

Source: https://docs.unity.com/en-us/cloud-save/tutorials/cloud-code

Initializes Unity Services and signs the user in anonymously to the Authentication service. Ensure Unity Services are initialized before proceeding.

```csharp
public class Test : MonoBehaviour
{
    public async void Awake()
    {
        await UnityServices.InitializeAsync();
        // Sign in anonymously into the Authentication service
        if (!AuthenticationService.Instance.IsSignedIn) await AuthenticationService.Instance.SignInAnonymouslyAsync();

        try
        {
            var module = new CloudSaveModuleBindings(CloudCodeService.Instance);
            await module.ManageDataAccessClasses();
        } catch (CloudCodeException exception)
        {
            Debug.LogException(exception);
        }

    }
}
```

--------------------------------

### GitServer Configuration File Example

Source: https://docs.unity.com/en-us/unity-version-control/gitserver/configure-gitserver

This is an example of the gitserver.conf file, showing configurations for TCP port, HTTP port, storage directory, mapping interval, and specific repositories to export.

```conf
# port configuration
tcp.port=9418
http.port=80
# mapping storage - the mappings between GitHub and UVCS objects
# the default path is automatically generated by the server
storage.baseDirectory=e:\gitserver\mappings
# mapping interval - how often GitServer looks for new changes
# on the UVCS side to make them available to GitHub
# By default, it is 5 minutes (300 seconds)
mapping.interval=300
# repositories to be exported. By default, all repositories 
# will be available on GitServer unless a list is specified here
export.repo=code
export.repo=quake
export.repo=robotcode
```

--------------------------------

### Display GameUI Help

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

Use command-line arguments like '--help', '-h', '--?', or '-?' to display GameUI help information.

```bash
    * '--help'
    * '-h'
    * '--?'
    * '-?'
```

```bash
    $> gameui.exe --help
```

--------------------------------

### Pagination Request Example URL - Initial Bulk Size

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/assets-api

Example URL for the initial request to set the number of results per page using the `resultsBulkSize` parameter. This is recommended for performance.

```http
https://api.ironsrc.com/advertisers/v2/assets?resultsBulkSize=2
```

--------------------------------

### Local branchexplorer.conf Example

Source: https://docs.unity.com/en-us/unity-version-control/config-files/branch-explorer-global

Example of a local `branchexplorer.conf` file. This configuration includes user-specific display and filter settings that are merged with global settings.

```conf
[Default]
display.attributes.visible=true
display.changestats.visible=true
display.extension.visible=true
display.navigator.visible=false
display.options.branch_level_filter=-1
display.options.changeset_color=1
display.options.dag_mergelinks=false
display.options.draw_branches=true
display.options.draw_crossbranch_changeset_links=true
display.options.draw_labels=true
display.options.draw_merge_links=true
display.options.draw_only_relevant_changesets=false
display.options.draw_taskinfo=true
display.options.end_date=0
display.options.end_date_enablement=false
display.options.full_branch_names=true
display.options.layout_mode=0
display.options.show_parent_to_child_arrows=false
display.options.start_date=636136983268496003
display.options.visible=false
display.properties.legend=false
display.properties.visible=true
display.properties.zoom=0,9999999
filters.conditional.numrules=1
filters.conditional.rule0.branches_query=
filters.conditional.rule0.color=0,128,192
filters.conditional.rule0.description=Unresolved branches
filters.conditional.rule0.enabled=true
filters.conditional.rule0.related.branches=None
filters.conditional.rule0.type=non_integrated_branches
filters.conditional.visible=true
```

--------------------------------

### Basic fast-import example

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/fastimport

Imports the contents exported in the 'repo.fast-export' file into 'mynewrepo' repository on server 'atenea:8084'.

```bash
cm fast-import mynewrepo@atenea:8084 repo.fast-export
```

--------------------------------

### Multiplay Configuration Example (YAML)

Source: https://docs.unity.com/en-us/multiplay-hosting/sdk/game-server-sdk-for-unity

An example of a Multiplay configuration file in YAML format. This file defines builds, build configurations, and fleets for your game servers. Ensure to replace placeholder values with your specific details.

```yaml
version: 1.0
builds:
  my build: # replace with the name for your build
    executableName: Build.x86_64 # the name of your build executable
    buildPath: Builds/Multiplay # the location of the build files
buildConfigurations:
  my build configuration: # replace with the name for your build configuration
    build: my build # replace with the name for your build
    queryType: sqp # sqp or a2s, delete if you do not have logs to query
    binaryPath: Build.x86_64 # the name of your build executable
    commandLine: -port $$port$$ -queryport $$query_port$$ -log $$log_dir$$/Engine.log # launch parameters for your server
    variables: {}
    cores: 1 # number of cores per server
    speedMhz: 750 # launch parameters for your server
    memoryMiB: 800 # launch parameters for your server
fleets:
  my fleet: # replace with the name for your fleet
    buildConfigurations:
      - my build configuration # replace with the names of your build configuration
    regions:
      North America: # North America, Europe, Asia, South America, Australia
        minAvailable: 0 # minimum number of servers running in the region
        maxServers: 1 # maximum number of servers running in the region

```

--------------------------------

### Install Unity Editor on Windows

Source: https://docs.unity.com/en-us/hub/hub-cli

Use this command to install a specific Unity Editor version and changeset on Windows. Ensure Unity Hub is installed in the default location.

```shell
C:\Program Files\Unity Hub>"Unity Hub.exe" -- --headless install --version 6000.3.7f1 --changeset 9b001d489a54
```

--------------------------------

### Get Top Scores from Leaderboard Version - C#

Source: https://docs.unity.com/en-us/leaderboards/tutorials/unity-sdk/get-score-version

Fetches the top 10 scores from a specified leaderboard version. No special setup is required beyond having the LeaderboardsService instance.

```csharp
public async void GetVersionScores(string leaderboardId, string versionId)
{
    var scoresResponse = await LeaderboardsService.Instance
        .GetVersionScoresAsync(leaderboardId, versionId);
    Debug.Log(JsonConvert.SerializeObject(scoresResponse));
}
```

--------------------------------

### Install Unity Version Control Complete on Fedora

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Installs the complete package of Unity Version Control on Fedora using dnf.

```bash
sudo dnf install plasticscm-complete
```

--------------------------------

### On Audio Unit Started Callback

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/structvx__sdk__config

Callback function executed when an audio processing unit starts.

```APIDOC
## variable pf_on_audio_unit_started

### Description
Called when an audio processing unit is started in the audio processing thread.

No blocking operations should occur on this callback.
```

--------------------------------

### Create a New User with umtool

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/webadmin/authentication-config

Use this command to create a new user in Plastic SCM. Replace `%serverinstalldir%` with your server installation directory.

```bash
%serverinstalldir%/plasticd umtool cu maria
```

--------------------------------

### Get Packed Subtree in C#

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/scene_sceneinterface

Returns a packed representation of the entire scene tree, starting from a specified root and with configurable depth and visibility settings. This method is marked with HandleProcessCorruptedStateExceptions.

```csharp
[HandleProcessCorruptedStateExceptions]
public PackedTree GetSubTree(uint root = 0, VisibilityMode visibilityMode = VisibilityMode.Hide, int depth = -1)
```

--------------------------------

### Create workspace with 'rep:' prefix

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

The `cm wk mk` subcommand now correctly handles repository creation when using the 'rep:' prefix, even without a server address specified.

```console
> cm wk mk Project ./Project rep:project@thecompany@cloud # This works.
> cm wk mk Project ./Project rep:project # This fails silently.
> cm wk mk Project ./Project project # This works even so.
[console]

Now the second command works as you would expect.
```

--------------------------------

### Get Revolution Surface Definition

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/cad_functions

Retrieves the parameters of a revolution surface. Use this function to extract the generatrix curve, axis origin and direction, and the start and end angles of the surface.

```python
cad.getRevolutionSurfaceDefinition(revolutionSurface) -> cad.Curve, geom.Point3, geom.Point3, core.Double, core.Double
```

--------------------------------

### Create Viewer and Take Screenshot in C#

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/viewer

This C# snippet demonstrates how to create a viewer, add a GPU scene, fit the camera, configure viewer properties for edges and lines, and capture a screenshot. Ensure to clean up by destroying the viewer and GPU scene.

```C#
uint viewer = pxz.View.CreateViewer(resolution, resolution);
uint gpuScene = pxz.View.CreateGPUScene(occurrence, showEdges);
pxz.View.AddGPUScene(gpuScene, viewer);
pxz.View.FitCamera(direction, type, fov, viewer, new OccurrenceList(new uint[] { occurrence }));
pxz.View.SetViewerProperty("ShowEdges", showEdges ? "True" : "False", viewer);
pxz.View.SetViewerProperty("ShowLines", showLines ? "True" : "False", viewer);
pxz.View.TakeScreenshot(path, viewer);
pxz.View.DestroyViewer(viewer);
pxz.View.DestroyGPUScene(gpuScene);
```

--------------------------------

### Get Random Channel URI

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Generates a random ephemeral channel ID for a specific realm with a given prefix. The prefix should start with 'confctl-g-', 'confctl-e-', or 'confctl-d-' for different channel types. The returned ID must be deallocated using `vx_free()`.

```APIDOC
## vx_get_random_channel_uri

### Description
Get a random ephemeral channel ID with the given prefix for the specific realm.

### Method
Not Applicable (C function)

### Endpoint
Not Applicable

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
None

### Response
#### Success Response
- **char *** - A pointer to the generated random channel URI. This must be deallocated with `vx_free()`.

#### Response Example
None

### Notes
- The prefix should start with one of the following options:
  - `confctl-g-` for general non-positional channels
  - `confctl-e-` for echo channels
  - `confctl-d-` for positional channels
```

--------------------------------

### Initialize Unity Ads and Load Banner Ads (Objective-C)

Source: https://docs.unity.com/en-us/grow/ads/ios-sdk/banner-ads

This snippet demonstrates initializing the Unity Ads SDK and setting up banner views for top and bottom screen placement. Ensure you have the Unity Ads SDK integrated and the placement ID configured.

```objective-c
@interface ViewController () <UADSBannerViewDelegate>

// This is the Ad Unit or Placement that will display banner ads:
@property (strong) NSString* placementId;
// This banner view object will be placed at the top of the screen:
@property (strong, nonatomic) UADSBannerView *topBannerView;
// This banner view object will be placed at the bottom of the screen:
@property (strong, nonatomic) UADSBannerView *bottomBannerView;

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    self.placementId = @"banner";
    [UnityAds initialize: @"1234567" testMode: YES initializationDelegate: self];
}

// Example method for creating and loading the top banner view object:
- (void)loadTopBanner{
    // Instantiate a banner view object with the Ad Unit ID and size:
    self.topBannerView = [[UADSBannerView alloc] initWithPlacementId: _placementId size: CGSizeMake(320, 50)];
    // Set the banner delegate for event callbacks:
    self.topBannerView.delegate = self;
    // Add the banner view object to the view hierarchy:
    [self addBannerViewToTopView:self.topBannerView];
    // Load ad content to the banner view object:
    [_topBannerView load];
}

// Example method for creating and loading the bottom banner view object:
- (void)loadBottomBanner{
    self.bottomBannerView = [[UADSBannerView alloc] initWithPlacementId: _placementId size: CGSizeMake(320, 50)];
    self.bottomBannerView.delegate = self;
    [self addBannerViewToBottomView:self.bottomBannerView];
    [_bottomBannerView load];
}

// Example method for discarding the top banner view object (for example, if there's no fill):
- (void)unLoadTopBanner{
    // Remove the banner view object from the view hierarchy:
    [self.topBannerView removeFromSuperview];
    // Set it to nil:
    _topBannerView = nil;
}

// Example method for discarding the bottom banner view object:
- (void)unLoadBottomBanner{
    [self.bottomBannerView removeFromSuperview];
    _bottomBannerView = nil;
}


// Example method for placing the top banner view object:
- (void)addBannerViewToTopView:(UIView *)bannerView {
    bannerView.translatesAutoresizingMaskIntoConstraints = NO;
    [self.view addSubview:bannerView];
    [self.view addConstraints:@[
        [NSLayoutConstraint constraintWithItem:bannerView
                                    attribute:NSLayoutAttributeTop
                                    relatedBy:NSLayoutRelationEqual
                                        toItem:self.topLayoutGuide
                                    attribute:NSLayoutAttributeBottom
                                    multiplier:1
                                      constant:0],
        [NSLayoutConstraint constraintWithItem:bannerView
                                    attribute:NSLayoutAttributeCenterX
                                    relatedBy:NSLayoutRelationEqual
                                        toItem:self.view
                                    attribute:NSLayoutAttributeCenterX
                                    multiplier:1
                                      constant:0]
    ]];
}

// Example method for placing the bottom banner view object:
- (void)addBannerViewToBottomView: (UIView *)bannerView {
    bannerView.translatesAutoresizingMaskIntoConstraints = NO;
    [self.view addSubview:bannerView];
    [self.view addConstraints:@[
        [NSLayoutConstraint constraintWithItem:bannerView
                                    attribute:NSLayoutAttributeBottom
                                    relatedBy:NSLayoutRelationEqual
                                        toItem:self.bottomLayoutGuide
                                    attribute:NSLayoutAttributeTop
                                    multiplier:1
                                      constant:0],
        [NSLayoutConstraint constraintWithItem:bannerView
                                    attribute:NSLayoutAttributeCenterX
                                    relatedBy:NSLayoutRelationEqual
                                        toItem:self.view
                                    attribute:NSLayoutAttributeCenterX
                                    multiplier:1
                                      constant:0]
    ]];
}

// Implement the delegate methods:
#pragma mark : UADSBannerViewDelegate

- (void)bannerViewDidLoad:(UADSBannerView *)bannerView {
    // Called when the banner view object finishes loading an ad.
    NSLog(@"Banner loaded for Ad Unit or Placement: %@", bannerView.placementId);
}

- (void)bannerViewDidClick:(UADSBannerView *)bannerView {
    // Called when the banner is clicked.

```

--------------------------------

### Example cURL Request for Server Locations

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-locations

Use this cURL command to make a GET request to the server locations endpoint. Ensure you replace <accountserviceid> and YOUR_AUTH_CREDENTIALS with your actual values.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/server/locations?accountserviceid=<accountserviceid> \
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Pagination Example

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/creative-api

Example of how to paginate through creative assets using the requestId and pageNumber.

```APIDOC
### Pagination

To retrieve subsequent pages of creatives, use the `requestId` from the previous response and the `pageNumber` parameter.

### Endpoint Example
```
https://api.ironsrc.com/advertisers/v2/creatives?requestId=MjE2MDkzLjUwMTEwMC4yLjE5&pageNumber=2
```

Increment the `pageNumber` parameter to fetch the next pages.
```

--------------------------------

### Check Ad Readiness and Placement Cap (Java)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/migrate-interstitial-ad-unit-api

Before showing an ad, verify that it is ready and that the specified placement is not capped to prevent show failures. This is recommended for a smoother user experience.

```java
if (mInterstitialAd.isAdReady() && !LevelPlayInterstitialAd.isPlacementCapped(placementName)) {
    mInterstitialAd.showAd(this, placementName);
}
```

--------------------------------

### Example cURL Request for Image Options

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-options

Use this cURL command to make a GET request to the image options endpoint. Ensure you replace placeholders with your actual credentials and IDs.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/image/options?accountserviceid=<accountserviceid>&gameid=<gameid>&imageid=<imageid>&gameversion_identifier=<GameVersionIdentifier>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Initiate Channel Join Request

Source: https://docs.unity.com/en-us/vivox-unity/developer-guide/channels/initiate-channel-join

This example demonstrates how to initiate a channel join request with text and audio capabilities. Ensure you have a signed-in ILoginSession and bind to ChannelJoined and ChannelLeft events for feedback.

```csharp
using System;
using System.ComponentModel;
using UnityEngine;
using Unity.Services.Vivox;

class JoinChannelExample : MonoBehaviour
{
    // For this example, _loginSession is a signed in ILoginSession.
    . .
    void OnLoggedIn()
    {
        //These events can be bound anywhere, but keeping them within the lifecycle of an active LoginSession is typically best
        VivoxService.Instance.ChannelJoined += OnChannelJoined
        VivoxService.Instance.ChannelLeft += OnChannelLeft
    }

    void OnChannelJoined(string channelName)
    {
        //Perform actions to react to joining the specific channel with name channelName
        //UI switches, participant UI setup, etc
    }

    void OnChannelLeft(string channelName)
    {
        //Perform cleanup to react to leaving a specific channel with name channelName
    }

    async void JoinChannelAsync(string channelName)
    {
        //Join channel with name channelName and capability for text and audio transmission
        VivoxService.Instance.JoinGroupChannelAsync(channelName, ChatCapability.TextAndAudio);
    }
    . .
}
```

--------------------------------

### Get Server Allocations Request

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-allocations

Example cURL request to retrieve details for specific server allocations. Include your authorization credentials and the fleet ID along with one or more allocation UUIDs.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/server/allocations?fleetid=<fleetid>&uuid=<uuid>&uuid=<uuid>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Get Help for Partial Shelveset Commands

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/partial-shelveset

Run these commands to get detailed usage information for specific partial shelveset commands.

```bash
cm partial shelveset <command> --usage
```

```bash
cm partial shelveset <command> --help
```

--------------------------------

### Create Licensing Server Service on Linux

Source: https://docs.unity.com/en-us/licensing-server/quick-start-web

Execute this command in the Linux Terminal to create and start the Unity licensing server as a service. This requires superuser privileges.

```bash
sudo -H ./Unity.Licensing.Server create-service
```

--------------------------------

### Get Reward API

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/ios/rewarded-ads-integration

Retrieves the reward name and amount for a specific placement or the default ad unit. This API call is instantaneous as reward data is retrieved during initial SDK setup.

```APIDOC
## GET /reward

### Description
Retrieves the reward name and amount for a specific placement or the default ad unit. There are no other parameters to use.

### Method
GET

### Endpoint
/reward

### Parameters
#### Query Parameters
- **placementName** (String) - Optional - The unique identifier for the placement as defined in the LevelPlay dashboard. Pass `nil` to retrieve the default reward for the ad unit.

### Response
#### Success Response (200)
- **LPMReward** (Object) - An object containing the reward details.
  - **name** (String) - The name of the reward.
  - **amount** (int) - The amount of the reward.

#### Response Example
```json
{
  "name": "Gold Coins",
  "amount": 50
}
```

### Objective-C Example
```objectivec
/** 
 * Retrieves the reward associated with the ad. 
 * Use this method to obtain the reward configured for the ad unit or placement. The 
 * placement-specific reward takes precedence over the ad unit reward when a valid placement name 
 * is provided. 
 * @param placement The placement name to retrieve the reward for, or `nil` to use the ad unit's reward. 
 * @return A `LPMReward` object. Returns an empty reward on failures (`name: ""` and `amount: 0`). 
 */ 
LPMReward *reward = [self.rewardedAd getRewardWithPlacementName:@"main_menu"];
NSLog(@"Reward: %ld %@", (long)reward.amount, reward.name);
```

### Swift Example
```swift
/** 
 * Retrieves the reward associated with the ad. 
 * Use this method to obtain the reward configured for the ad unit or placement. The 
 * placement-specific reward takes precedence over the ad unit reward when a valid placement name 
 * is provided. 
 * @param placementName The placement name to retrieve the reward for, or `nil` to use the ad unit's reward. 
 * @return A `LPMReward` object. Returns an empty reward on failures (`name: ""` and `amount: 0`). 
 */ 
let reward = self.rewardedAd.getReward(placementName: "main_menu")
print("Watch to get \(reward.amount) \(reward.name)")
```
```

--------------------------------

### Global branchexplorer.conf Example

Source: https://docs.unity.com/en-us/unity-version-control/config-files/branch-explorer-global

Example of a global `branchexplorer.conf` file. This configuration defines conditional filter rules that apply to all repositories.

```conf
[Default]
filters.conditional.numrules=1
filters.conditional.rule0.branches_query=attribute = 'status' and attrvalue = 'RESOLVED'
filters.conditional.rule0.description=Unresolved branches
filters.conditional.rule0.enabled=true
filters.conditional.rule0.related.branches=None
filters.conditional.rule0.type=exclusion_rule
```

--------------------------------

### Initialize Vivox SDK with Unity Services

Source: https://docs.unity.com/en-us/vivox-unity/vivox-unity-first-steps

Initializes Unity Services, signs in anonymously, and then initializes the Vivox SDK. Ensure Unity Services and Authentication are set up before calling this.

```csharp
using System;
using UnityEngine;
using Unity.Services.Authentication;
using Unity.Services.Core;
using Unity.Services.Vivox;

async void InitializeAsync()
{
    await UnityServices.InitializeAsync();
    await AuthenticationService.Instance.SignInAnonymouslyAsync();

    await VivoxService.Instance.InitializeAsync();
}
```

--------------------------------

### Full Banner Ad Implementation Example - Unity

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/unity/migrate-banner-ad-unit-api

Example demonstrating the creation, subscription to events, loading, showing, hiding, and destroying of a banner ad using the LevelPlay SDK.

```csharp
public class BannerAdSample {
  private LevelPlayBannerAd bannerAd;
  void CreateBannerAd() {
    // Create banner instance
    bannerAd = new LevelPlayBannerAd("bannerAdUnitId");
    // Subscribe BannerAd events
    bannerAd.OnAdLoaded += BannerOnAdLoadedEvent;
    bannerAd.OnAdLoadFailed += BannerOnAdLoadFailedEvent;
    bannerAd.OnAdDisplayed += BannerOnAdDisplayedEvent;
    bannerAd.OnAdDisplayFailed += BannerOnAdDisplayFailedEvent;
    bannerAd.OnAdClicked += BannerOnAdClickedEvent;
    bannerAd.OnAdCollapsed += BannerOnAdCollapsedEvent;
    bannerAd.OnAdLeftApplication += BannerOnAdLeftApplicationEvent;
    bannerAd.OnAdExpanded += BannerOnAdExpandedEvent;
  }
  void LoadBannerAd() {
    // Load the banner ad
    bannerAd.LoadAd();
  }
  void ShowBannerAd() {
    // Show the banner ad, call this method only if you turned off the auto show when you created this banner instance.
    bannerAd.ShowAd();
  }
  void HideBannerAd() {
    // Hide banner
    bannerAd.HideAd();
  }
  void DestroyBannerAd() {
    // Destroy banner
    bannerAd.DestroyAd();
  }
  // Implement BannerAd Events
  void BannerOnAdLoadedEvent(LevelPlayAdInfo adInfo) {}
  void BannerOnAdLoadFailedEvent(LevelPlayAdError error) {}
  void BannerOnAdClickedEvent(LevelPlayAdInfo adInfo) {}
  void BannerOnAdDisplayedEvent(LevelPlayAdInfo adInfo) {}
  void BannerOnAdDisplayFailedEvent(LevelPlayAdInfo adInfo, LevelPlayAdError error) {}
  void BannerOnAdCollapsedEvent(LevelPlayAdInfo adInfo) {}
  void BannerOnAdLeftApplicationEvent(LevelPlayAdInfo adInfo) {}
  void BannerOnAdExpandedEvent(LevelPlayAdInfo adInfo) {}
}
```

--------------------------------

### Check Ad Readiness and Placement Cap (Kotlin)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/migrate-interstitial-ad-unit-api

Before showing an ad, verify that it is ready and that the specified placement is not capped to prevent show failures. This is recommended for a smoother user experience.

```kotlin
if (mInterstitialAd.isAdReady() && !LevelPlayInterstitialAd.isPlacementCapped(placementName)) {
    mInterstitialAd.showAd(this, placementName)
}
```

--------------------------------

### Find Labels with Pagination and Sorting

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/10

Use the 'cm find' command with 'limit' and 'offset' to paginate results. This example retrieves labels owned by the current user, starting from the 21st and showing 10 results.

```console
$ cm find label "where owner='me' limit 10 offset 20"
```

--------------------------------

### Show pending branch merges for a file

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/branch-showmerges

Use this command to see branches involved in the pending merge of a specific file. No special setup is required beyond having the Unity Version Control CLI installed.

```bash
cm branch showmerges file.txt
```

--------------------------------

### Initialize Network SDK (Swift)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/flutter/build-custom-adapter-ios

Implement the init method in your Swift adapter to initialize the network SDK. Use the delegate to report initialization success or failure.

```swift
public override func `init` (_ adData: ISAdData, delegate: ISNetworkInitializationDelegate) {
   ...
   // handle errors
   if (error-handling) {
      delegate.onInitDidFailWithErrorCode(ISAdapterErrors.missingParams.rawValue, errorMessage: "Fail to init SDK")
      return
   }
   // init success
   delegate.onInitDidSucceed()
   return        
}
```

--------------------------------

### Configuration via CLI Commands and Options

Source: https://docs.unity.com/en-us/ccd/cli

Details on configuring the CLI using direct commands for environment, project ID, bucket name, and using command options.

```APIDOC
#### Use CLI Commands for configuration

The CLI also supports direct configuration through commands. Here are some examples to set the active environment, project-id and bucket-name:

```powershell
ugs env use <environment-name>
ugs config set project-id <project-id>
ugs config set bucket-name <bucket-name>
```

#### Use Option with a command

The CLI supports specifying a bucket for any ccd command using the option `-b`.

```powershell
ugs ccd entries list -b <bucket-name>
```
```

--------------------------------

### UnityAds - initialize

Source: https://docs.unity.com/en-us/grow/ads/android-sdk/android-api

Initializes the ads service with specified Game ID, test mode status, and initialization listener.

```APIDOC
## initialize

### Description
Initializes the ads service, with a specified [Game ID](/grow/dashboard/get-started/project/settings.md#game-ids), [test mode](/grow/ads/optimization/test-ads-integration.md) status, and initialization listener.

### Method
Java

### Endpoint
UnityAds.initialize

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```java
initialize(final Context context, final String gameId, final boolean testMode, final IUnityAdsInitializationListener initializationListener)
```

### Response
#### Success Response (200)
None

#### Response Example
None

### Error Handling
None
```

--------------------------------

### Construct Access Token for Unmuting

Source: https://docs.unity.com/en-us/vivox-unreal/server-to-server-api-reference/control-active-channels-api/unmute-all-users-in-channel

This example shows how to construct an access token with specific parameters for muting actions. Ensure you have a valid Vivox access token and refer to the Access Token Developer Guide for details.

```plaintext
e30.eyJ2eGkiOjEsImYiOiJzaXA6YmxpbmRtZWxvbi1BcHBOYW1lLWRldi1BZG1pbkBtdDFzLnZpdm94LmNvbSIsImlzcyI6ImJsaW5kbWVsb24tQXBwTmFtZS1kZXYiLCJ2eGEiOiJtdXRlIiwidCI6InNpcDpjb25mY3RsLWctYmxpbmRtZWxvbi1BcHBOYW1lLWRldi50aGUtaWNoYW5uZWxAbXQxcy52aXZveC5jb20iLCJleHAiOjE2MDAzNDk0MDB9.KIk1eaT7dUv-eLhcpZg4SJbEJoHIePzlLmULg2YuCIQ
```

--------------------------------

### Get Label Command Help

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/label

Run this command to get comprehensive help for a specific label command.

```bash
cm label <command> --help
```

--------------------------------

### Initialize Vivox SDK

Source: https://docs.unity.com/en-us/vivox-core/developer-guide/client-sdk-basics/initialize-sdk

Call `vx_initialize3()` on application startup to initialize the Vivox SDK. Ensure you handle potential errors during default configuration retrieval and initialization.

```cpp
#include"Vxc.h"
#include"VxcErrors.h"
. . .
vx_sdk_config_t defaultConfig;
int status = vx_get_default_config3(&defaultConfig, sizeof (defaultConfig));

if (status != VxErrorSuccess)
{
    printf("vx_sdk_get_default_config3() returned %d: %s\n", status,
    vx_get_error_string(status));
    return;
}

status = vx_initialize3(&defaultConfig, sizeof (defaultConfig));

if (status != VxErrorSuccess)
{
    printf ("vx_initialize3() returned %d : %s\n", status, vx_get_error_string(status));
    return;
}
// Vivox Client SDK is now initialized

```

--------------------------------

### Get Assets Request Example

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/assets-api

Use this URL to retrieve a list of assets. You can filter by type, titleId, ids, and status. Pagination parameters like requestId, pageNumber, and resultsBulkSize are available for managing large datasets.

```http
https://api.ironsrc.com/advertisers/v2/assets?
```

--------------------------------

### Set up Ubuntu Repository

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Add Unity Version Control's stable repository to access the latest long-term support releases on Ubuntu. Ensure apt-transport-https is installed and the GPG key is added securely.

```bash
sudo apt-get update
sudo apt-get install -y apt-transport-https
wget -qO - https://www.plasticscm.com/plasticrepo/stable/ubuntu/Release.key |
  gpg --dearmor | sudo tee /usr/share/keyrings/plasticscm-stable.gpg > /dev/null
echo "deb [signed-by=/usr/share/keyrings/plasticscm-stable.gpg] \
  https://www.plasticscm.com/plasticrepo/stable/ubuntu ./" | 
  sudo tee /etc/apt/sources.list.d/plasticscm-stable.list
sudo apt-get update
```

--------------------------------

### Implement Score Aggregation in Cloud Code

Source: https://docs.unity.com/en-us/cloud-code/modules/use-cases/community-goal

Use the injected IScoreAggregator to increment player scores within a Cloud Code function. This example also includes a one-time setup function for Cloud Save data.

```csharp
using System.Threading.Tasks;
using Unity.Services.CloudCode.Apis;
using Unity.Services.CloudCode.Core;
using Unity.Services.CloudSave.Model;

namespace CommunityGoal;

public class MyModule
{
    [CloudCodeFunction("AddScore")]
    public async Task AddScore(IExecutionContext ctx, IScoreAggregator scoreAggregator, int score)
    {
        await scoreAggregator.Increment(ctx, score);
    }


    // This is a setup function for initializing the Cloud Save data. Only call it once.
    // Don't include this in a live version!
    [CloudCodeFunction("InitializeCloudSave")]
    public async Task InitializeCloudSave(IExecutionContext ctx, IGameApiClient apiClient)
    {
        await apiClient.CloudSaveData.SetCustomItemAsync(
            ctx, ctx.ServiceToken, ctx.ProjectId, "global", new SetItemBody("event_score", 0));
    }
}
```

--------------------------------

### Submodule Definition Example

Source: https://docs.unity.com/en-us/unity-version-control/gitserver/gitserver-submodules

This is an example of how a Git submodule is defined in the configuration, specifying its path and URL.

```text
[submodule "mduem"]
        path = mduem
        url = git://github.com/user/mduem
```

--------------------------------

### Install Timestamp Parameter

Source: https://docs.unity.com/en-us/grow/acquire/partner-integration/custom/send-postbacks

You must include the install timestamp parameter in your secondary postback URL.

```APIDOC
## Install Timestamp

### Description
Include the original install timestamp in Unix format.

### Parameters
#### Query Parameters
- **install_ts** (integer) - Required - The original install timestamp in Unix time (seconds or milliseconds). Milliseconds are recommended.

### Example
- `install_ts=1466637800175`
```

--------------------------------

### Get Command Help Information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/attribute

Run this command to get comprehensive help information for a specific attribute command.

```bash
cm attribute <command> --help
```

--------------------------------

### Get Campaign Country Groups Response Example

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/country-group-api

This JSON structure represents the response when retrieving a list of all country configurations for a specific campaign. The 'budget' field is included only if the campaign budget type is set to 'By Country'.

```json
{
    "campaignId": 8405744,
    "CountryGroups": [
        {
            "id": 16854,
            "name": "12345",
            "budget": 700,
            "countries": [
                {
                    "Country": "AT",
                    "bid": 6,
                    "setupGoal": "default"
                },
                {
                    "Country": "AU",
                    "bid": "default",
                    "setupGoal": "default"
                },
                {
                    "Country": "CA",
                    "bid": "default",
                    "setupGoal": "default"
                },
                {
                    "Country": "CH",
                    "bid": "default",
                    "setupGoal": "default"
                },
                {
                    "Country": "CN",
                    "bid": "default",
                    "setupGoal": "default"
                },
                {
                    "Country": "DE",
                    "bid": "default",
                    "setupGoal": "default"
                },
                {
                    "Country": "DK",
                    "bid": "default",
                    "setupGoal": "default"
                },
                {
                    "Country": "FR",
                    "bid": "default",
                    "setupGoal": "default"
                },
                {
                    "Country": "GB",
                    "bid": "default",
                    "setupGoal": "default"
                },
                {
                    "Country": "IL",
                    "bid": 11,
                    "setupGoal": 4
                },
                {
                    "Country": "JP",
                    "bid": "default",
                    "setupGoal": "default"
                },
                {
                    "Country": "NO",
                    "bid": "default",
                    "setupGoal": "default"
                },
                {
                    "Country": "NZ",
                    "bid": "default",
                    "setupGoal": "default"
                },
                {
                    "Country": "SE",
                    "bid": "default",
                    "setupGoal": "default"
                },
                {
                    "Country": "US",
                    "bid": 7,
                    "setupGoal": 3
                }
            ]
        }
    ]
}
```

--------------------------------

### Start Multiplayer Session on Allocated Server

Source: https://docs.unity.com/en-us/mps-sdk/game-server-hosting-support

This code sample demonstrates how to start a multiplayer session on a server allocated by a hosting provider. It requires version 2.1 or later of the Multiplayer Services package. Ensure service account credentials are removed from client builds.

```csharp
#if UNITY_SERVER
// The setup logic can be called when the hosting provider signals that the server is ready
public async Task SetupServer()
 {
     try
     {
         // Enter logic for retrieving the match id from the hosting provider sdk and any additional setup
         var matchId = "MATCH_ID";
         // Initialize unity services
         await UnityServices.InitializeAsync();
         // Sign in with a service account - Ensure this information gets stripped from client builds
         await ServerAuthenticationService.Instance.SignInWithServiceAccountAsync("KEY", "SECRET");
         // Adapt session options to your game needs 
         var sessionOptions = new SessionOptions() { MaxPlayers = 2 };
         // Create the match session
         IServerSession session = await MultiplayerServerService.Instance.CreateMatchSessionAsync(matchId, sessionOptions);
         // Hook to any relevant session lifecycle events and integrate hosting provider signals and application quit accordingly
         session.Deleted += () => Application.Quit();
         // Add optional logic for the hosting provider player readiness
     }
     catch (Exception e)
     {
         Debug.LogException(e);
         Application.Quit();
     }
 }
#endif
```

--------------------------------

### Create PlasticFS Shortcut for Startup

Source: https://docs.unity.com/en-us/unity-version-control/enable-dynamic-workspaces

Create a shortcut to the plasticfs.exe file in the shell:startup directory to ensure PlasticFS starts automatically when you log in.

```bash
shell:startup
```

--------------------------------

### UP (User Password) Authentication Example

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/push

Example of providing authentication data for UPWorkingMode. The --authdata format is specific to the mode, and can be simplified using --user and --password.

```bash
(--authmode=UPWorkingMode) --authdata=dave:fPBea2rPsQaagEW3pKNveA==
```

--------------------------------

### Get Help from CLI

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/version-control-cli

Access the command-line documentation for help. You can get general help or specific help for a command by appending '--help'.

```text
cm help
```

--------------------------------

### vx_req_aux_render_audio_start_create

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/group__devices

Allocates and initializes a vx_req_aux_render_audio_start object.

```APIDOC
## vx_req_aux_render_audio_start_create

### Description
Allocate and initialize a [vx_req_aux_render_audio_start](./structvx_req_aux_render_audio_start) object.

### Method
N/A (This is a function signature, not an API endpoint)

### Endpoint
N/A

### Parameters
#### Path Parameters
N/A

#### Query Parameters
N/A

#### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
N/A

#### Response Example
N/A
```

--------------------------------

### Install Unity Editor with Modules on Windows

Source: https://docs.unity.com/en-us/hub/hub-cli

Installs a new Unity Editor version along with specified modules on Windows using the Unity Hub CLI.

```shell
"C:\Program Files\Unity Hub\Unity Hub.exe" - --headless install --version 6000.3.7f1 --module android android-sdk-ndk-tools android-open-jdk
```

--------------------------------

### Control Plastic SCM Service via Command Line (Linux)

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/start-stop-restart-server

Use this command to start, stop, restart, or check the status of the Plastic SCM service on Linux systems. The script can be found in /etc/init.d/ or the server installation directory.

```text
plasticsd {start | stop | restart | status}
```

--------------------------------

### Set up Fedora Repository

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Adds the Unity Version Control stable repository for Fedora systems using dnf config-manager.

```bash
sudo dnf config-manager --add-repo \
  https://www.plasticscm.com/plasticrepo/stable/fedora/plasticscm-stable.repo
```

--------------------------------

### Full Implementation Example of Interstitial Ads

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/unity/migrate-interstitial-ad-unit-api

A comprehensive example demonstrating the integration of Interstitial Ads in a Unity application.

```APIDOC
## Full Implementation Example of Interstitial Ads

```csharp
public class InterstitialAdSample {
    private LevelPlayInterstitialAd interstitialAd;
    void CreateInterstitialAd() {
        // Create InterstitialAd instance
        interstitialAd = new LevelPlayInterstitialAd("interstitialAdUnitId");

        // Subscribe InterstitialAd events
        interstitialAd.OnAdLoaded += InterstitialOnAdLoadedEvent;
        interstitialAd.OnAdLoadFailed += InterstitialOnAdLoadFailedEvent;
        interstitialAd.OnAdDisplayed += InterstitialOnAdDisplayedEvent;
        interstitialAd.OnAdDisplayFailed += InterstitialOnAdDisplayFailedEvent;
        interstitialAd.OnAdClicked += InterstitialOnAdClickedEvent;
        interstitialAd.OnAdClosed += InterstitialOnAdClosedEvent;
        interstitialAd.OnAdInfoChanged += InterstitialOnAdInfoChangedEvent;
    }
    void LoadInterstitialAd() {
        // Load or reload InterstitialAd
        interstitialAd.LoadAd();
    }
    void ShowInterstitialAd() {
        // Show InterstitialAd, check if the ad is ready before showing
        if (interstitialAd.IsAdReady()) {
            interstitialAd.ShowAd();
        }
    }
    void DestroyInterstitialAd() {
        // Destroy InterstitialAd
        interstitialAd.DestroyAd();
    }
    // Implement InterstitialAd events
    void InterstitialOnAdLoadedEvent(LevelPlayAdInfo adInfo) { }
    void InterstitialOnAdLoadFailedEvent(LevelPlayAdError error) { }
    void InterstitialOnAdClickedEvent(LevelPlayAdInfo adInfo) { }
    void InterstitialOnAdDisplayedEvent(LevelPlayAdInfo adInfo) { }
    void InterstitialOnAdDisplayFailedEvent(LevelPlayAdInfo adInfo, LevelPlayAdError error) { }
    void InterstitialOnAdClosedEvent(LevelPlayAdInfo adInfo) { }
    void InterstitialOnAdInfoChangedEvent(LevelPlayAdInfo adInfo) { }
}
```
```

--------------------------------

### Access Publisher Setup Parameters

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/build-custom-adapter

Access publisher setup parameters (app-level and instance-level keys) at runtime using the AdData object. These values are defined by the publisher on the ironSource platform.

```java
// Get Publisher setup parameters
final String appLevelParam1 = adData.getString(<YourAppLevelParam1>);
final String instanceLevelParam1 = adData.getString(<YourInstanceLevelParam1>);
final String instanceLevelParam2 = adData.getString(<YourInstanceLevelParam2>);
```

--------------------------------

### Begin Login with Presence

Source: https://docs.unity.com/en-us/vivox-unreal/reference-manual/unreal/class_i_login_session

Initiates the sign-in process for a login session, including presence management. Requires server URI, access token, subscription mode, and sets of presence subscriptions. An optional delegate can be provided for completion callbacks.

```cpp
virtual VivoxCoreError BeginLogin(
    const FString & server,
    const FString & accessToken,
    SubscriptionMode subscriptionMode,
    const TSet< AccountId > & presenceSubscriptions,
    const TSet< AccountId > & blockedPresenceSubscriptions,
    const TSet< AccountId > & allowedPresenceSubscriptions,
    FOnBeginLoginCompletedDelegate theDelegate =FOnBeginLoginCompletedDelegate()
) =0
```

--------------------------------

### Example Active Service Status on Linux

Source: https://docs.unity.com/en-us/licensing-server/server-setup-svc

This is an example of the output from the status verification command on Linux, confirming the service is active and running.

```bash
Active: active (running) since Fri 2020-02-14 16:44:59 EST; 2s ago
```

--------------------------------

### Example CTA Icon Code in VAST

Source: https://docs.unity.com/en-us/grow/exchange/video-ads

This XML snippet demonstrates how to nest a custom icon within a VAST tag for display alongside the 'Install Now' button. Ensure the icon is a StaticResource with a PNG, JPG, or JPEG extension and is sized at 25x25 pixels.

```xml
<Icons>
	<Icon width="25" height="25">
	<StaticResource creativeType="image/png">
		<![CDATA[ https://Unity.com/DSP/square_icon_name ]]> 
	</StaticResource>
	</Icon>
</Icons>
```

--------------------------------

### Example server.json structure

Source: https://docs.unity.com/en-us/clanforge/legacy/configuration-variables

This JSON structure shows how Clanforge populates a server.json file using configuration variables.

```json
{
	"allocationUUID": "434af841-586d-4403-939b-db19f77611a6",
	"serverID": "12345",
	"queryType": "sqp",
	"queryPort": "9010",
	"port": "9000",
	"serverLogDirectory": "12345/logs/"
}
```

--------------------------------

### Get command help information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/purge

Run this command to get comprehensive help information for a specific purge command.

```bash
cm purge <command> --help
```

--------------------------------

### Increment Player Currency Balance with Config Hash - Cloud Code JS

Source: https://docs.unity.com/en-us/economy/config-caching

This Cloud Code example demonstrates how to retrieve the player's configuration to get the `configAssignmentHash`. This hash is then used when calling `incrementPlayerCurrencyBalance` to ensure the currency is synced with the latest configuration.

```javascript
const { CurrenciesApi, ConfigurationApi } = require("@unity-services/economy-2.4");

module.exports = async ({ params, context, logger }) => {
  const currenciesApi = new CurrenciesApi({ accessToken: context.accessToken });
  const configApi = new ConfigurationApi({ accessToken: context.accessToken });
  const currencyId = "COIN";

  try {
    // Retrieve the player config to get the configAssignmentHash.
    // This is needed to ensure the currency is synced
    var config = await configApi.getPlayerConfiguration({
      playerId: context.playerId,
      projectId: context.projectId,
    });

    const result = await currenciesApi.incrementPlayerCurrencyBalance({
      currencyId,
      playerId: context.playerId,
      projectId: context.projectId,
      configAssignmentHash: config.data.metadata.configAssignmentHash,
      currencyModifyBalanceRequest: { amount: 10 },
    });

    return result.data;
  } catch (err) {
    logger.error("Failed to increment currency for player", { "error.message": err.message });
    return;
  }
};
```

--------------------------------

### Initialize WebLicenseInfoList with Array

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_weblicenseinfolist

Constructs a WebLicenseInfoList using an array of WebLicenseInfo objects.

```csharp
public WebLicenseInfoList(WebLicenseInfo[] tab)
```

--------------------------------

### Create Viewer and Take Screenshot in Python

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/viewer

Use this Python snippet to create a viewer, add a GPU scene, fit the camera, set viewer properties for edges and lines, and take a screenshot. Remember to destroy the viewer and GPU scene when finished.

```Python
direction = geom.Point3(0, 0, -1) # front
viewer = view.createViewer(resolution, resolution)
gpu_scene = view.createGPUScene(occurrence, show_edges)
view.addGPUScene(gpu_scene, viewer)
view.fitCamera(direction, type, fov, viewer, [occurrence])
if show_edges:
    view.setViewerProperty("ShowEdges", "True", viewer)
if show_lines:
    view.setViewerProperty("ShowLines", "False", viewer)
view.takeScreenshot(path, viewer)
view.destroyViewer(viewer)
view.destroyGPUScene(gpu_scene)
```

--------------------------------

### Allocate Relay Server and Get Join Code with DTLS

Source: https://docs.unity.com/en-us/relay/enable-dtls-encryption

This function allocates a Relay server, requests a join code, and configures the connection type as DTLS. Ensure you are using Unity Editor versions 2020.3 (starting at 2020.3.34), 2022.1, or above for secure DTLS connections.

```csharp
public static async Task<(string ipv4address, ushort port, byte[] allocationIdBytes, byte[] connectionData, byte[] key, string joinCode)> AllocateRelayServerAndGetJoinCode(int maxConnections, string region = null)
{
    Allocation allocation;
    string createJoinCode;
    try
    {
        allocation = await RelayService.Instance.CreateAllocationAsync(maxConnections, region);
    }
    catch (Exception e)
    {
        Debug.LogError($"Relay create allocation request failed {e.Message}");
        throw;
    }

    Debug.Log($"server connection data: {allocation.ConnectionData[0]} {allocation.ConnectionData[1]}");
    Debug.Log($"server allocation ID: {allocation.AllocationId}");

    try
    {
        createJoinCode = await RelayService.Instance.GetJoinCodeAsync(allocation.AllocationId);
    }
    catch
    {
        Debug.LogError("Relay create join code request failed");
        throw;
    }

    var dtlsEndpoint = allocation.ServerEndpoints.First(e => e.ConnectionType == "dtls");
    return (dtlsEndpoint.Host, (ushort)dtlsEndpoint.Port, allocation.AllocationIdBytes, allocation.ConnectionData, allocation.Key, createJoinCode);
}
```

--------------------------------

### Field Mapping Example

Source: https://docs.unity.com/en-us/unity-version-control/vcs-plugins/issue-tracking/jira/configure-jira

An example demonstrating how to map JIRA fields to display project key, description, and issue creator.

```APIDOC
### Field mapping example

For example, the following is a valid example for the following configuration:
  * Displays the project key in the description.
  * Displays the JIRA description as the title.
  * Displays the issue creator as the owner.

```
issue.Fields.Project.Name->Description|issue.Fields.Reporter.Name->Owner|issue.Fields.Description->Title
```
```

--------------------------------

### Initialize Google Play Games Login

Source: https://docs.unity.com/en-us/authentication/platform-signin/google

Configure and initialize the Google Play Games platform for login. This setup requests an ID token, which is essential for authenticating players with external services. Ensure the Google Play Games plugin for Unity v10.14 or later is installed.

```cs
void InitializePlayGamesLogin()
{
    var config = new PlayGamesClientConfiguration.Builder()
        // Requests an ID token be generated.
        // This OAuth token can be used to
        // identify the player to other services such as Firebase.
        .RequestIdToken()
        .Build();

    PlayGamesPlatform.InitializeInstance(config);
    PlayGamesPlatform.DebugLogEnabled = true;
    PlayGamesPlatform.Activate();
}
```

--------------------------------

### Authenticate Cloud Save API with Service Token using Axios

Source: https://docs.unity.com/en-us/cloud-code/scripts/how-to-guides/token-support

This example shows how to authenticate with the Cloud Save API using a service token passed as a bearer token in the Authorization header via Axios. It records a new value and then retrieves all data for a player. Ensure the axios library is installed.

```javascript
const axios = require("axios-0.21");

module.exports = async ({ params, context, logger }) => {
  const config = {
    headers: {
      'Content-Type': 'application/json',
      // Authenticate as Cloud Code using the serviceToken from the context object
      Authorization: `Bearer ${context.serviceToken}`
    }
  };

  let result;
  try {
    const cloudSaveUrl = `https://cloud-save.services.api.unity.com/v1/data/projects/${context.projectId}/players/${params.playerId}/items`
    const payload = {
      key : "test",
      value: "test"
    };

    await axios.post(cloudSaveUrl, payload, config);
    result = await axios.get(cloudSaveUrl, config);

    return result.data;
  } catch (err) {
    logger.error("Failed to call out to Cloud Save", {"error.message": err.message});
    throw err;
  }
};

```

--------------------------------

### List modules with pagination

Source: https://docs.unity.com/en-us/cloud-code/modules/how-to-guides/write-modules/rest-api

Use the 'limit' query parameter to paginate through your deployed modules. This example retrieves the first two modules. Adjust the limit as needed.

```bash
curl 'https://services.api.unity.com/cloud-code/v1/projects/<PROJECT_ID>/environments/<ENVIRONMENT_ID>/modules?limit=2'
--header 'Authorization: Basic <SERVICE_ACCOUNT_CREDENTIALS_ENCODED>'
```

--------------------------------

### Install and Use NVM Version

Source: https://docs.unity.com/en-us/build-automation/advanced-build-configuration/run-custom-scripts-during-the-build-process

Installs a specific NVM version and sets it as the current version for the build environment. Outputs the Node version used.

```bash
. ~/.profile
nvm install 16.13.0
nvm use 16.13.0
node -v
exit 0
```

--------------------------------

### Update Operation Progress Example

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

This text example shows the format of the progress message for the 'update' operation in the command line client, indicating downloaded data, files to download, and operations to apply.

```text
'Updated 2.8MB of 580MB (2 of 156 files to download / 45 of 202 operations to apply'
```

--------------------------------

### List All Repositories

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/repository

Execute this command to display a list of all available repositories managed by Unity Version Control.

```bash
cm repository list
```

--------------------------------

### GET /ads/instances/v1

Source: https://docs.unity.com/en-us/grow/is-ads/monetization/apis/ironsource-instances-api

Get a list of your application's ironSource traditional instances. Bidding instances are supported on GET method only.

```APIDOC
## GET /ads/instances/v1

### Description
Get a list of your application's ironSource traditional instances.

### Method
GET

### Endpoint
https://platform.ironsrc.com/ads/instances/v1

### Parameters
#### Query Parameters
- **appKey** (String) - Required - application key (as seen on the platform)

### Request Example URL
https://platform.ironsrc.com/ads/instances/v1/142401ac1/

### Response
#### Success Response (200)
- **instanceId** (Integer) - Unique instance ID generated by ironSource Ads
- **instanceName** (String) - The instance name
- **adUnit** (String) - rewardedVideo, interstitial, banner, or native
- **isLive** (Boolean) - Boolean value if the instance is live or not
- **isBidder** (Boolean) - the instance a bidder instance (true or false)
- **isOptimized** (Boolean) - Optional - Boolean value if the instance has optimized pricing
- **isInTestMode** (Boolean) - Campaigns are delivering to your app but not generating revenue
- **globalPricing** (Float) - Optional - the value of the global CPM pricing
- **countriesPricing** (Array) - Optional - list of countries and their eCPM value
  - **country** (String) - Country code which is defined by a 2 letter country code, as per ISO 3166-1 Alpha-2
  - **eCPM** (Integer) - The eCPM value for the specific country

#### Response Example
```json
[
  {
    	"instanceId": 0,
    	"instanceName": "Default",
    	"adUnit": "rewardedVideo",
    	"isLive": false,
    	"isOptimized": true,
    	"isInTestMode": false
  },
  {
    	"instanceId": 123456,
    	"instanceName": "instance1",
    	"adUnit": "rewardedVideo",
    	"isLive": true,
    	"isOptimized": false,
      "isInTestMode": false,
    	
    	"globalPricing": 10,
    	"countriesPricing": [
	{
		"country": "US",
		"eCPM": 20
	},
	{
		"country": "CN",
		"eCPM": 20
	},	{
		"country": "AU",
		"eCPM": 30
	}
]
  }
]
```
```

--------------------------------

### Example Field Mapping Configuration

Source: https://docs.unity.com/en-us/unity-version-control/vcs-plugins/issue-tracking/jira/configure-jira

Provides an example of how to configure field mappings in the 'jira.conf' file, linking JIRA fields to UVCS properties like 'Id', 'Owner', 'Status', 'Title', and 'Description'.

```text
from->to
```

--------------------------------

### Install Unity Version Control Cloud Edition on Fedora

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Installs the Cloud Edition of Unity Version Control on Fedora using dnf.

```bash
sudo dnf install plasticscm-cloud
```

--------------------------------

### Install xdg-utils for Plastic SCM Links

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

On Debian and Ubuntu systems, if `xdg-mime` is not installed, Plastic SCM GUI installation will not fail but custom links may not be recognized. Install `xdg-utils` to ensure proper recognition.

```bash
xdg-mime default /usr/applications/plasticx.desktop x-scheme-handler/plastic
```

--------------------------------

### ProductViewDefinitionList Constructors

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/scene_productviewdefinitionlist

Provides information on how to instantiate ProductViewDefinitionList.

```APIDOC
## ProductViewDefinitionList(ProductViewDefinition[])

### Description
Initializes a new instance of the ProductViewDefinitionList class with a specified array of ProductViewDefinition objects.

### Method
Constructor

### Parameters
#### Path Parameters
- **tab** (ProductViewDefinition[]) - Required - An array of ProductViewDefinition objects.

### ProductViewDefinitionList(int)

### Description
Initializes a new instance of the ProductViewDefinitionList class with a specified size.

### Method
Constructor

### Parameters
#### Path Parameters
- **size** (int) - Required - The size of the ProductViewDefinitionList.
```

--------------------------------

### Get Command Help Information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/trigger

Run this command to get comprehensive help information for a specific trigger command.

```bash
cm trigger <command> --help
```

--------------------------------

### Initialize ProductViewDefinitionList with Array

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/scene_productviewdefinitionlist

Constructor for ProductViewDefinitionList that accepts an array of ProductViewDefinition objects.

```csharp
public ProductViewDefinitionList(ProductViewDefinition[] tab)
```

--------------------------------

### Install the UVCS proxy service

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/configure/use-proxy-server

Installs the UVCS proxy as a Windows service. This allows the proxy to run in the background.

```bash
plasticd proxy --installservice
```

--------------------------------

### Find Changeset by GUID

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/show-find-objects

Locate a specific changeset using its Global Unique Identifier (GUID). The GUID must be in the correct hexadecimal format.

```bash
cm find changeset "where guid = '1b30674f-14cc-4fd7-962b-676c8a6f5cb6'"
```

--------------------------------

### Install PowerShell Autocompletion

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

Install command autocompletion for PowerShell by running the 'cm autocomplete install' command. Restart PowerShell for changes to take effect.

```powershell
> cm autocomplete install
C:\Users\sergi\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1 modified.
You need to restart PowerShell for changes to take effect.
```

--------------------------------

### List Repositories Command

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

Example of running the 'cm repo list' command. This command is used to list repositories and its output is logged by the server, indicating successful allow list loading.

```console
cm repo list
```

--------------------------------

### UVCS Plugin Installation Path for TeamCity

Source: https://docs.unity.com/en-us/unity-version-control/vcs-plugins/teamcity-plugin

Locate the UVCS plugin zip file for TeamCity installation. This path is specific to the UVCS installation directory.

```text
<UVCS installation directory>/client/plugins/teamcity/com.codicesoftware.plugins.teamcity.PlasticSCM.zip
```

--------------------------------

### View Help for Unity Licensing Server CLI (Linux)

Source: https://docs.unity.com/en-us/licensing-server/server-setup

Display all available command parameters for the Unity Licensing Server CLI on Linux. This is useful for understanding the full syntax of each command.

```bash
./Unity.Licensing.Server --help
```

--------------------------------

### Plastic SCM Plugin for Wwise Installation Path

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

To integrate Plastic SCM with Wwise, copy the plugin DLL to the specified SourceControl directory within your Wwise installation. Ensure you replace `<Wwise install directory>` with your actual Wwise installation path.

```text
<Wwise install directory>/Authoring/x64/Release/bin/SourceControl
```

--------------------------------

### SKAdNetwork Postback Example

Source: https://docs.unity.com/en-us/grow/acquire/privacy/skadnetwork/postback-integration

This example illustrates an HTTP POST request for an MMP registered with a specific endpoint. It includes various parameters related to app attribution and conversion values.

```text
POST /skadnetwork-postback HTTP/1.1
Host: mmp.example.com
Content-Type: application/json
Content-Length: 577

{
  "ip": "198.51.100.1",
  "version": "4.0",
  "app-id": 1234567890,
  "campaign-id": 23,
  "source-identifier": "2a3b",
  "coarse-conversion-value": "medium",
  "postback-sequence-index": 0,
  "ad-network-campaign-id": "546b9257365399e0031572bd",
  "ad-network-campaign-name": "Summer Launch Campaign",
  "ad-network-id": "1232",
  "ad-network-source-app-id": "com.unity.source.app",
  "source-app-id": 987654321,
  "transaction-id": "abcd1234-ef56-7890-gh12-ijkl3456mnop",
  "fidelity-type": 1,
  "attribution-signature": "MEYCIQDW...snip...i7XjFg==",
  "redownload": false,
  "conversion-value": 5,
  "timestamp": "1596525944"
}
```

--------------------------------

### HTTP GET Request API

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Synchronously download the contents of a URL using the GET method.

```APIDOC
## GET /api/http

### Description
Synchronously download the contents of the specified URL with the GET method.

### Method
GET

### Endpoint
/api/http

### Parameters
#### Query Parameters
- **url** (const char *) - Required - The URL to download.

### Response
#### Success Response (200)
- **response_code** (unsigned int) - The HTTP response code.
- **content** (char **) - A pointer to a buffer containing the downloaded content.
- **content_len** (size_t *) - A pointer to the size of the content buffer.
- **content_type** (char **) - A pointer to a buffer containing the content type.
- **content_type_len** (size_t *) - A pointer to the size of the content type buffer.

#### Response Example
```json
{
  "response_code": 200,
  "content": "<html><body>Hello World</body></html>",
  "content_type": "text/html"
}
```
```

--------------------------------

### Initialize ProductViewDefinitionList with Size

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/scene_productviewdefinitionlist

Constructor for ProductViewDefinitionList that initializes with a specified size.

```csharp
public ProductViewDefinitionList(int size)
```

--------------------------------

### Example Successful License Acquisition Output

Source: https://docs.unity.com/en-us/licensing-server/client-config

This is an example of the console output when a floating license is successfully acquired. It includes a token identifier and expiration date.

```bash
Trying to acquire floating license from: 10.1.34.126 ...
License lease Created with token e8b1afba-895d-4c54-aa50-5eadcc4d95a7.
Expires: July 12, 2019 6:47:57 PM
```

--------------------------------

### Install react-native-tracking-transparency

Source: https://docs.unity.com/en-us/grow/offerwall/react-native/introduction/quickstart

Install the react-native-tracking-transparency package using Yarn.

```javascript
yarn add react-native-tracking-transparency
```

--------------------------------

### Initialize Vivox SDK with Local Token Generation

Source: https://docs.unity.com/en-us/vivox-core/access-token-guide/developer-portal-token-generation

Use this setup for local testing purposes only. It requires caching the secret key on the client and should not be used outside of development.

```csharp
public class VoiceManager : MonoBehaviour
{
    async void Start()
    {
        InitializationOptions options = new InitializationOptions().SetVivoxCredentials(server, domain, issuer, secretKey);
        await UnityServices.InitializeAsync(options);
        await VivoxService.Instance.InitializeAsync();
    }
}
```

--------------------------------

### GET /server/locations

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-locations

Get a list of game server locations.

```APIDOC
## GET /server/locations

### Description
Get a list of game server locations.

### Method
GET

### Endpoint
https://api.multiplay.co.uk/cfp/v1/server/locations

### Parameters
#### Query Parameters
- **accountserviceid** (string) - Required - The account service ID (ASID) associated with the specified resource. The credentials in the request header must have access to the ASID to perform the request.

### Request Example
```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/server/locations?accountserviceid=<accountserviceid> \
--header "Authorization: Basic YOUR_AUTH_CREDENTIALS"' 
```

### Response
#### Success Response (200)
- **locations** (array) - List of location objects containing the name and ID of the server location.
  ### Locations object
  - **locationid** (string) - ID of the location of this server
  - **name** (string) - Name of the location

#### Response Example
```json
{
    "locations": [
        {
            "locationid": "<locationid>",
            "name": "<name>"
        },
        ...
    ]
}
```
```

--------------------------------

### Install Unity Version Control Proxy Server on Red Hat / CentOS

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Installs the proxy server component for Unity Version Control on Red Hat or CentOS using yum.

```bash
sudo yum install plasticscm-proxy-server
```

--------------------------------

### Get Material Pattern

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/material_functions

Gets the MaterialPattern name of the material.

```APIDOC
## GET /websites/unity_en-us/getMaterialPattern

### Description
Gets the MaterialPattern name of the material.

### Method
GET

### Endpoint
/websites/unity_en-us/getMaterialPattern

### Parameters
#### Query Parameters
- **material** (Material) - Required - The material to find the pattern.

### Response
#### Success Response (200)
- **pattern** (String) - The pattern of the material.

### Response Example
```json
{
  "pattern": "Standard"
}
```
```

--------------------------------

### Creating Repositories in Different Organizations

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/6

Demonstrates how to create repositories within different organizations on the server using the 'cm mkrep' command.

```bash
cm mkrep repo00@org1@localhost:8087
```

```bash
cm mkrep repo00@org2@localhost:8087
```

```bash
cm mkrep repo00@org3@localhost:8087
```

--------------------------------

### Example Tapjoy Connect Success Log

Source: https://docs.unity.com/en-us/grow/offerwall/ios/introduction/quickstart

This is an example of the console output you can expect upon a successful Tapjoy connection.

```Swift
        2020-01-29 16:01:55.422 App Name[25869:1433019] [TJLog level: 4] Connect success with type:0
```

--------------------------------

### Install Unity Editor on macOS

Source: https://docs.unity.com/en-us/hub/hub-cli

Use this command to install a specific Unity Editor version and changeset on macOS. Ensure Unity Hub is installed in the default location.

```shell
/Applications/Unity\ Hub.app/Contents/MacOS/Unity\ Hub -- --headless install --version 6000.3.7f1 --changeset 9b001d489a54
```

--------------------------------

### Initialize Unity IAP and Event Listeners

Source: https://docs.unity.com/en-us/iap/set-up-in-app-purchasing

This C# code demonstrates how to initialize the Unity IAP package, define products, get the StoreController, attach event listeners for store events, and connect to the app store. It includes callbacks for product and purchase fetching, as well as store disconnection.

```csharp
using System.Collections.Generic;
using UnityEngine.Purchasing;

public class MyIAPManager
{
    private StoreController m_StoreController;
    public MyIAPManager()
    {
        // Define products
        var catalogProvider = new CatalogProvider();
        catalogProvider.AddProduct("100_gold_coins", ProductType.Consumable,
            new StoreSpecificIds()
            {
                {"100_gold_coins_google", GooglePlay.Name},
                {"100_gold_coins_mac", MacAppStore.Name}
            });

        // Get StoreController
        m_StoreController = UnityIAPServices.StoreController();

        // Add event listeners
        m_StoreController.OnStoreDisconnected += OnStoreDisconnected;

        m_StoreController.OnProductsFetched += OnProductsFetched;
        m_StoreController.OnProductsFetchFailed += OnProductsFetchFailed;

        m_StoreController.OnPurchasesFetched += OnPurchasesFetched;
        m_StoreController.OnPurchasesFetchFailed += OnPurchasesFetchFailed;

        // Connect to store
        m_StoreController.Connect().ContinueWith(_ =>
        {
            // Fetch products from store
            catalogProvider.FetchProducts(
                list => m_StoreController.FetchProducts(list)
                );
        });
    }

    /// <summary>
    /// Invoked when connection is lost to the current store, or on a Connect() failure.
    /// </summary>
    /// <param name="failure">Information regarding the failure.</param>
    private void OnStoreDisconnected(StoreConnectionFailureDescription failure)
    {
    }

    /// <summary>
    /// Invoked with products that are successfully fetched.
    /// </summary>
    /// <param name="products">Products successfully returned from the app store.</param>
    private void OnProductsFetched(List<Product> products)
    {
        // Fetch purchases for successfully retrieved products
        m_StoreController.FetchPurchases();
    }

    /// <summary>
    /// Invoked when an attempt to fetch products has failed or when a subset of products failed to be fetched.
    /// </summary>
    /// <param name="failure">Information regarding the failure.</param>
    private void OnProductsFetchFailed(ProductFetchFailed failure)
    {
    }

    /// <summary>
    /// Invoked when previous purchases are fetched.
    /// </summary>
    /// <param name="orders">All active pending, completed, and deferred orders for previously fetched products.</param>
    private void OnPurchasesFetched(Orders orders)
    {
    }

    /// <summary>
    /// Invoked when an attempt to fetch previous purchases has failed.
    /// </summary>
    /// <param name="failure">Information regarding the failure.</param>
    private void OnPurchasesFetchFailed(PurchasesFetchFailureDescription failure)
    {
    }

    /// <summary>
    /// Invoked when a purchase needs to be processed and fulfilled.
    /// </summary>
    /// <param name="order">The order awaiting fulfillment.</param>
    private void OnPurchasePending(PendingOrder order)
    {
    }
}
```

--------------------------------

### Format cm find branch output with GUID

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/10

Use the `--format={guid}` option with `cm find branch` to display the branch GUID. This was previously unsupported.

```bash
cm find branch --format={guid}
```

--------------------------------

### Start Local API Server

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/api

Starts the API server listening on port 9090 for local connections only. Press Enter to stop the server.

```bash
cm api
```

--------------------------------

### List All Workspaces

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/workspace-list

Use this command to list all available workspaces. No additional setup is required.

```bash
cm workspace | wk [list | ls] [--format=<str_format>]
```

```bash
cm wk
```

--------------------------------

### Get StylizedLine Array

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/polygonal_stylizedlinelist

Gets the underlying array of StylizedLine objects.

```csharp
public StylizedLine[] list
```

--------------------------------

### Create Workspace with Simplified Command-Line Syntax

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

Use this simplified syntax to create a workspace, inferring the name and path from the repository spec. An advanced option allows specifying a different server.

```bash
$ cm wk mk project ./project rep:project@mydefaultserver
```

```bash
$ cm wk mk project
```

```bash
$ cm wk mk project@myorg@cloud
```

--------------------------------

### Capture Audio Start

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/deprecated

Starts capturing audio. This function is deprecated.

```APIDOC
## POST /api/aux/capture_audio_start

### Description
Starts capturing audio. This function is deprecated and should not be used.

### Method
POST

### Endpoint
/api/aux/capture_audio_start

### Parameters
#### Request Body
- **duration** (integer) - Optional - The duration in seconds for which to capture audio. If not specified, audio capture continues until stopped.
```

--------------------------------

### Set Cube to Non-Interactive on Play Start

Source: https://docs.unity.com/en-us/unity-studio/develop/logic/examples/control-gameobject-interactivity

This logic sets a Cube variable to non-interactive when the application starts. It requires a 'Cube_Interactive' boolean variable and a 'Play Starts' event listener.

```Logic Editor
When
  Play Starts
Set variable value
  Cube_Interactive = false
```

--------------------------------

### Example of Writing an Environment Variable

Source: https://docs.unity.com/en-us/build-automation/advanced-build-configuration/run-custom-scripts-during-the-build-process

Sets a sample environment variable in the pre-build script and writes it to the DEVOPS_ENV file.

```bash
echo "TEST_ENV=Sample environment variable" >> $DEVOPS_ENV
```

--------------------------------

### Example Ignore Rules

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

Illustrates ignore rules for excluding directories and specific files. The example shows how exclusion rules now only affect direct children of ignored directories, improving performance.

```text
/Library
/cfg
!/cfg/keys_default.cfg
```

--------------------------------

### Display changelist status example

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/10

Example output of 'cm status --changelists' showing controlled files and their status within different changelists.

```text
Changed
    Status         Size       Last Modified    Path
    Checked-out    5 bytes    1 hour ago       file1.txt

Changed
    Status         Size       Last Modified    Path
    Checked-out    7 bytes    1 hour ago       file2.txt
```

--------------------------------

### Simple Merge Example

Source: https://docs.unity.com/en-us/unity-version-control/triggers/concepts/detailed-trigger-reference

A concrete example illustrating a simple merge operation, showing a combination of file conflicts and operations to apply.

```text
CHANGE_DELETE [SRC] C "/src/foo.c" cs:12 (base cs:7) - [DST] D "/src/foo.c" cs:7
FILE_CONFLICT [SRC] C "/src /bar.c" cs:12 (base cs:7) - [DST] C "/src /bar.c" cs:8 (base cs:7)
M "/doc/readme.txt" -> "/readme.txt" cs:7
D "/doc" cs:7
```

--------------------------------

### Initialize Vivox SDK with Developer Portal Credentials

Source: https://docs.unity.com/en-us/vivox-unity/v16-upgrade-guide

Use this snippet for initialization with legacy Vivox Developer Portal credentials. Provide server, domain, issuer, and key. Remember to remove the signing key before release.

```csharp
async void InitializeAsync()
{
    InitializationOptions options = new InitalizationOptions();
    // _key can be excluded from SetVivoxCredentials if an implementation of IVivoxTokenProvider has been provided to the SDK.
    options.SetVivoxCredentials(_server, _domain, _issuer, _key);
    await UnityServices.InitializeAsync(options);
    await VivoxService.Instance.InitializeAsync();
}
```

--------------------------------

### Server Start Endpoint URL

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-start-by-criteria

The base URL for the server start endpoint.

```plaintext
https://api.multiplay.co.uk/cfp/v1/server/start
```

--------------------------------

### Run the Support Bundle Command

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/support

Execute the support bundle command to gather necessary information for troubleshooting.

```bash
cm support bundle
```

--------------------------------

### StartupModule

Source: https://docs.unity.com/en-us/vivox-unreal/reference-manual/unreal/class_f_vivox_core_module

Called on Modules startup. Implements the IModuleInterface.

```APIDOC
## StartupModule

### Description
Called on Modules startup. Implements the IModuleInterface.

### Method
void

### Endpoint
N/A

### Parameters
None

### Request Example
```cpp
void StartupModule() override
```

### Response
N/A
```

--------------------------------

### Apple Bundle Identifier Example

Source: https://docs.unity.com/en-us/grow/exchange/bid-responses

Example of an Apple App Store identifier.

```string
"1198634425"
```

--------------------------------

### Create a New Server Connection Profile

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/profile

Execute 'cm profile create' to initiate the process of setting up a new server connection profile.

```bash
cm profile create
```

--------------------------------

### Unity Licensing Server Setup - Admin IP Allowlist Configuration

Source: https://docs.unity.com/en-us/licensing-server/server-setup-cfg-v1

Prompts for configuring the Admin IP allowlist during Unity Licensing Server setup, including adding default and additional IP addresses.

```bash
Add default addresses to the Admin IP allowlist (127.0.0.1, ::1, 192.168.0.51)? [Y/n]
List of current allow-listed admin IP addresses:
- 127.0.0.1
- ::1
- 192.168.0.51
Add an additional admin IP address to the allow list? [y/N] y
Enter admin IP address (Press Enter to skip):
```

--------------------------------

### Install Unity Modules on Windows

Source: https://docs.unity.com/en-us/hub/hub-cli

Use this command to install specific Unity modules for a given Editor version on Windows via the command line.

```shell
C:\Program Files\Unity Hub>"Unity Hub.exe" -- --headless install-modules --version 6000.3.7f1 -m ios android
```

--------------------------------

### Install Stable Unity Hub on Debian

Source: https://docs.unity.com/en-us/hub/install-hub-linux

Use these commands to disable the beta repository and install the stable version of Unity Hub on Debian-based systems.

```shell
sudo mv /etc/apt/sources.list.d/unityhub-beta.list /etc/apt/sources.list.d/unityhub-beta.list.bak
sudo apt update
sudo apt install unityhub
```

```shell
sudo apt install unityhub=3.x.x
```

--------------------------------

### Set/Get Install Path

Source: https://docs.unity.com/en-us/hub/hub-cli

Configure or retrieve the directory where Unity Editors are installed on your system.

```APIDOC
## POST /install-path

### Description
Sets or gets the path where Unity Editors are installed.

### Method
POST

### Endpoint
--headless install-path

### Parameters
#### Query Parameters
- **set** (string) - Optional - Alias: -s - Sets the Editor install path to the given path.
- **get** (boolean) - Optional - Alias: -g - Displays the current Editor install path.

> **Note:** If no option is selected, it defaults to the `get` command.

### Request Example
```shell
/Applications/Unity\ Hub.app/Contents/MacOS/Unity\ Hub -- --headless install-path -s /Applications/Unity/Hub/Editor/
```

### Response
#### Success Response (200)
- **path** (string) - The current or newly set Editor install path.
```

--------------------------------

### Install vpctl Tool (Non-interactive Mode)

Source: https://docs.unity.com/en-us/cloud/virtual-private-cloud/on-premises/installation/prerequisites

For automated environments, set the ORAS_USERNAME and ORAS_PASSWORD environment variables before running the install script. This avoids interactive prompts.

```bash
export ORAS_USERNAME="<your-username>"
export ORAS_PASSWORD="<your-password>"

./install-vpctl.sh 0.8.0
```

--------------------------------

### Implement Ad Quality Initialization Callbacks

Source: https://docs.unity.com/en-us/grow/ad-quality/additional-configuration

Implement callback methods for successful and failed Ad Quality SDK initialization. These should be in a separate class where the SDK is initialized.

```csharp
public class AdQualityInit : ISAdQualityInitCallback { 
    public void adQualitySdkInitSuccess() { 
        Debug.Log("adQualitySdkInitSuccess"); 
    } 
 
    public void adQualitySdkInitFailed(ISAdQualityInitError adQualitySdkInitError, string errorMessage) { 
        Debug.Log($"adQualitySdkInitFailed: {adQualitySdkInitError}, message: {errorMessage}");
    }
}

public class AdQualityDemo : MonoBehaviour { 
    void Awake() { 
        AdQualityInit initCallbacks = new AdQualityInit(); 
        ISAdQualityConfig adQualityConfig = new ISAdQualityConfig { 
            AdQualityInitCallback = initCallbacks 
        };
 
        IronSourceAdQuality.Initialize(appKey, adQualityConfig); 
    } 
}
```

--------------------------------

### GET /server/{serverid}/status

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-status

Get the status of the game server identified by `<serverid>`.

```APIDOC
## GET /server/{serverid}/status

### Description
Get the status of the game server identified by `<serverid>`.

### Method
GET

### Endpoint
https://api.multiplay.co.uk/cfp/v1/server/<serverid>/status

### Parameters
#### Path Parameters
- **serverid** (string) - Required - The game server ID of the game server to retrieve the status of.

#### Query Parameters
- **query_info** (boolean) - Optional - Allows you to request query information about the game server in addition to the status. If set to `true`, the response includes query information and status. If set to `false` or excluded, the response includes the game server status.

### Response
#### Success Response (200)
- **active** (integer) - Number representing activity state, expect `0` for stopped, `1` for started and `>=2` for restarting.
- **allocated_uuid** (string) - UUID of the allocation this server is currently on or empty string if none.
- **admin_locked** (integer) - Number representing lock state, 1 indicates the server is undergoing maintenance or in a state that's currently unsuitable for a game session.
- **country_code** (string) - Two letter country code, country lookup available in the [server countries](/clanforge/api/endpoints/server-countries.md) endpoint.
- **game_port** (integer) - Port the game server is available on.
- **ip** (string) - IP address the game server is available on.
- **locationid** (string) - ID of the location the game server is in.
- **machineid** (integer) - ID of the machine the game server is on.
- **name** (string) - Name of the game server, this is usually autogenerated at creation time.
- **profileid** (integer) - ID of the profile this server is currently on.
- **query_port** (string) - Port the game server should be providing query information on via a query protocol such as SQP.
- **serverid** (integer) - ID of the server.
- **query_info** (object) - Query object containing additional server info if query_info is set on the request.

### Query object
All fields on the query service are returned directly from the game server's query service at the time of the request. The game must support query for this to function.
- **players** (integer) - Current number of players on the server.
- **max_players** (integer) - Current maximum match players.
- **map** (string) - Current map name.
- **status** (string) - Current status.
- **name** (string) - Current name.

#### Response Example
```json
{
  "active": 1,
  "allocated_uuid": "some-uuid",
  "admin_locked": 0,
  "country_code": "US",
  "game_port": 27015,
  "ip": "192.168.1.100",
  "locationid": "123",
  "machineid": 456,
  "name": "MyGameServer",
  "profileid": 789,
  "query_port": "27016",
  "serverid": 1011,
  "query_info": {
    "players": 10,
    "max_players": 20,
    "map": "Dust2",
    "status": "live",
    "name": "MyGameServer"
  }
}
```
```

--------------------------------

### Create and Load Banner Ad (Kotlin)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/banner-integration

This Kotlin code demonstrates how to create and load a banner ad. It includes setting up the ad configuration, creating the banner view, adding it to a container, and handling various ad lifecycle events through a listener. Ensure context and container are correctly set up.

```kotlin
public fun createAndLoadBanner() {
   // Create ad configuration - optional
   val adSize = LevelPlayAdSize.BANNER
   val adConfig = LevelPlayBannerAdView.Config.Builder()
   .setAdSize(adSize)
   .setPlacementName("placementName")
   .build()
   // Create the banner view and set the ad unit id
   val levelPlayBanner = LevelPlayBannerAdView(context, "adUnitId", adConfig)

   // Add the banner view to the container
   val adContainer = findViewById<ViewGroup>(R.id.adContainer)
   adContainer.addView(levelPlayBanner)
   levelPlayBanner.setBannerListener(object: LevelPlayBannerAdViewListener {
   override fun onAdLoaded(adInfo: LevelPlayAdInfo) {
      // Ad was loaded successfully 
   }
   override fun onAdLoadFailed(error: LevelPlayAdError) {
      // Ad load failed
   }
   override fun onAdDisplayed(adInfo: LevelPlayAdInfo) {
      // Ad was displayed and visible on screen
   }
   override fun onAdDisplayFailed(adInfo: LevelPlayAdInfo, error: LevelPlayAdError) {
      // Ad failed to be displayed on screen
   }
   override fun onAdClicked(adInfo: LevelPlayAdInfo) {
      // Ad was clicked
   }
   override fun onAdExpanded(adInfo: LevelPlayAdInfo) {
      // Ad is opened on full screen
   }
   override fun onAdCollapsed(adInfo: LevelPlayAdInfo) {
      // Ad is restored to its original size
   }
   override fun onAdLeftApplication(adInfo: LevelPlayAdInfo) {
      // User pressed on the ad and was navigated out of the app 
   }
   })

   // Load the banner ad
   levelPlayBanner.loadAd()

   // Get width and height for the container
   val width = adSize.getWidth()
   val height = adSize.getHeight()
   }
```

--------------------------------

### Get Material Main Color

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/material_functions

Gets the main color on any material pattern type.

```APIDOC
## GET /websites/unity_en-us/getMaterialMainColor

### Description
Get the main color on any material pattern type.

### Method
GET

### Endpoint
/websites/unity_en-us/getMaterialMainColor

### Parameters
#### Query Parameters
- **material** (Material) - Required - The material.

### Response
#### Success Response (200)
- **color** (ColorAlpha) - The main color.

### Response Example
```json
{
  "color": {
    "r": 1.0,
    "g": 0.0,
    "b": 0.0,
    "a": 1.0
  }
}
```
```

--------------------------------

### Start Buffer Capture Response

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_responses_8h

Details the response structure for starting buffer capture.

```APIDOC
## POST /api/aux/start_buffer_capture

### Description
This endpoint handles the response for starting buffer capture.

### Method
POST

### Endpoint
/api/aux/start_buffer_capture

### Response
#### Success Response (200)
- **vx_resp_aux_start_buffer_capture_t** (struct) - The response structure for starting buffer capture.
```

--------------------------------

### Initialize Network SDK (Swift)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/react/build-custom-adapter-ios

Implement the init method in your base adapter to initialize the network SDK. Ensure you call the initialization callbacks for success and failure, passing relevant error codes and messages.

```swift
public override func `init` (_ adData: ISAdData, delegate: ISNetworkInitializationDelegate) {
   ... 
   // handle errors 
   if (error-handling) {
      delegate.onInitDidFailWithErrorCode(ISAdapterErrors.missingParams.rawValue, errorMessage: "Fail to init SDK")
      return
   }
   // init success 
   delegate.onInitDidSucceed()
   return        
}

```

--------------------------------

### Install Pixyz Python SDK with pip

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/installation/python

Use this command to install the Pixyz Python SDK with all dependencies. Ensure you have Python 3.1 or newer.

```bash
pip install pxz --extra-index-url https://unity3ddist.jfrog.io/artifactory/api/pypi/pixyz-pypi-prod-local/simple
```

--------------------------------

### Full Rewarded Ad Implementation Example

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/react/rewarded-ads-integration

A complete example demonstrating the integration of Rewarded Ads using the LevelPlayRewardedAd class. It includes setting up listeners for various ad lifecycle events and loading the ad.

```javascript
import {
    LevelPlayRewardedAd,
    type LevelPlayRewardedAdListener,
    type LevelPlayAdInfo,
    type LevelPlayAdError,
    type LevelPlayReward
} from 'unity-levelplay-mediation'

const [rewardedAd, setRewardedAd] = useState<LevelPlayRewardedAd>(new LevelPlayRewardedAd('YOUR_AD_UNIT_ID'))
const listener: LevelPlayRewardedAdListener = {
    onAdLoaded: (adInfo: LevelPlayAdInfo) => {
        // Implement your logic here, for example showing the ad
        rewardedAd.showAd()
    },
    onAdLoadFailed: (error: LevelPlayAdError) => {
        // Implement your logic here...
    },
    onAdInfoChanged: (adInfo: LevelPlayAdInfo) => {
        // Implement your logic here...
    },
    onAdDisplayed: (adInfo: LevelPlayAdInfo) => {
        // Implement your logic here...
    },
    onAdDisplayFailed: (error: LevelPlayAdError, adInfo: LevelPlayAdInfo) => {
        // Implement your logic here...
    },
    onAdClicked: (adInfo: LevelPlayAdInfo) => {
        // Implement your logic here...
    },
    onAdClosed: (adInfo: LevelPlayAdInfo) => {
        // Implement your logic here...
    },
    onAdRewarded: (reward: LevelPlayReward, adInfo: LevelPlayAdInfo) => {
        // Implement your logic here...
    }
};
useEffect(() => {
    rewardedAd.setListener(listener)
    rewardedAd.loadAd()
}, []);
// Rest of component ...
// End of component ...
```

--------------------------------

### Progress Step Start Callbacks

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_coreinterface

Manage callbacks for progress step start events.

```APIDOC
## AddProgressStepStartCallback

### Description
Registers a callback function to be invoked when a progress step starts.

### Method
`public uint AddProgressStepStartCallback(CoreInterface.ProgressStepStartDelegate callback, IntPtr userData)`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
None

### Response
#### Success Response (200)
- **uint** - An identifier for the registered callback.

#### Response Example
None

## RemoveProgressStepStartCallback

### Description
Removes a previously registered progress step start callback.

### Method
`public void RemoveProgressStepStartCallback(uint id)`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
None

### Response
#### Success Response (200)
None

#### Response Example
None
```

--------------------------------

### Initialize Offerwall SDK

Source: https://docs.unity.com/en-us/grow/offerwall/web/advanced/api-reference

Call this method before showing any offerwall content. It initializes the SDK and can preload content by default. Options include SDK key, user ID, privacy settings, and callbacks.

```javascript
Tapjoy('init', options);
```

--------------------------------

### Google Bundle Identifier Example

Source: https://docs.unity.com/en-us/grow/exchange/bid-responses

Example of a Google Play Store bundle identifier.

```json
"bundle": "com.unityexample.game"
```

--------------------------------

### Set Placement Entry Point (Swift)

Source: https://docs.unity.com/en-us/grow/offerwall/ios/introduction/update-guide

Configure the entry point for a placement before requesting content. Use preset values like TJEntryPoint.mainMenu.

```Swift
let placement = TJPlacement(name: "myPlacement", delegate: nil)
placement?.entryPoint = TJEntryPoint.mainMenu
placement?.requestContent() 

// Values available
TJEntryPoint.unknown
TJEntryPoint.other
TJEntryPoint.mainMenu
TJEntryPoint.hud
TJEntryPoint.exit
TJEntryPoint.fail
TJEntryPoint.complete
TJEntryPoint.inbox
TJEntryPoint.initialisation
TJEntryPoint.store
```

--------------------------------

### SKAdNetwork Signature Example

Source: https://docs.unity.com/en-us/grow/exchange/ios14-support

Example of the SKAdNetwork signature, as specified by Apple, used for attribution.

```json
"signature": "MEQCIEQlmZRNfYzK…"
```

--------------------------------

### Install Stable Unity Hub on Rel/CentOS

Source: https://docs.unity.com/en-us/hub/install-hub-linux

Use these commands to disable the beta repository and install the stable version of Unity Hub on Red Hat-based systems.

```shell
sudo mv /etc/yum.repos.d/unityhub_beta.repo /etc/yum.repos.d/unityhub_beta.repo.bak
sudo yum check-updates
sudo yum install unityhub
```

```shell
sudo yum list unityhub
sudo yum install unityhub-<version info>
```

--------------------------------

### Install Unity Version Control Complete on Red Hat / CentOS

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Installs the complete package of Unity Version Control on Red Hat or CentOS using yum.

```bash
sudo yum install plasticscm-complete
```

--------------------------------

### vx_req_aux_capture_audio_start_create

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/group__devices

Allocates and initializes a vx_req_aux_capture_audio_start object.

```APIDOC
## vx_req_aux_capture_audio_start_create

### Description
Allocate and initialize a [vx_req_aux_capture_audio_start](./structvx_req_aux_capture_audio_start) object.

### Method
N/A (This is a function signature, not an API endpoint)

### Endpoint
N/A

### Parameters
#### Path Parameters
N/A

#### Query Parameters
N/A

#### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
N/A

#### Response Example
N/A
```

--------------------------------

### Example QueryRequest Packet

Source: https://docs.unity.com/en-us/clanforge/legacy/sqp

This is an example of a `QueryRequest` packet, showing the byte-level representation of the data.

```plaintext
[0x00000000] 0x01 '\x1' unsigned char
[0x00000001] 0x80 '€' unsigned char
[0x00000002] 0x31 '1' unsigned char
[0x00000003] 0xbe '¾' unsigned char
[0x00000004] 0x18 '\x18' unsigned char
[0x00000005] 0x00 '\0' unsigned char
[0x00000006] 0x01 '\x1' unsigned char
[0x00000007] 0x01 '\x1' unsigned char
```

--------------------------------

### Get Configuration Details

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/getconfig

Use this command to retrieve configuration information. Specify arguments to get specific details like read-only status of protected files or the client config path.

```bash
cm getconfig [setfileasreadonly] [location] [extensionworkingmode] [extensionprefix] [defaultrepserver]
```

```bash
cm getconfig setfileasreadonly
```

--------------------------------

### Launch Test Suite on Initialization Complete

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/adobe/integration-test-suite

This example shows how to launch the test suite automatically upon successful initialization of the LevelPlay SDK by listening for the InitializationComplete event.

```actionscript
IronSource.instance.addEventListener("InitializationComplete", InitializationComplete);
private function InitializationComplete(event:Event):void {
//InitializationComplete
//Launch test suite
IronSource.instance.launchTestSuite();
}
```

--------------------------------

### Install Unity Editor with Modules on Linux

Source: https://docs.unity.com/en-us/hub/hub-cli

Installs a new Unity Editor version along with specified modules on Linux using the Unity Hub CLI.

```shell
~/Applications/Unity\ Hub.AppImage --headless install --version 6000.3.7f1 --module android android-sdk-ndk-tools android-open-jdk
```

--------------------------------

### Install CM Command Completion

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/autocomplete

Installs 'cm' command completion for your current shell environment.

```bash
cm autocomplete install
```

--------------------------------

### List Builds using Unity Services Gateway

Source: https://docs.unity.com/en-us/multiplay-hosting/concepts/authentication

Example of using basic authentication with a pre-encoded KeyID and Secret key to list builds via the Unity Services Gateway. Ensure you replace `<projectID>` and `<environmentID>` with your specific values.

```bash
curl -X GET 'https://services.api.unity.com/multiplay/builds/v1/projects/<projectID>/environments/<environmentID>/builds \
--header 'Authorization: Basic OTI1MGY1NzgtOWZmMS00Yjc1LWFmY2MtN2VjYTFlOTRkYjU2OjVkN2YxYTY2LWYyOWQtNDVjOC1hNmFhLWE4NDI0MmFhODA1Zg=='
```

--------------------------------

### Combined Filters Example

Source: https://docs.unity.com/en-us/unity-version-control/config-files/branch-explorer-global

Example of the resulting configuration when global and local `branchexplorer.conf` files are combined. This shows the effective filter rules applied by the GUI.

```conf
filters.conditional.numrules=2
filters.conditional.rule0.branches_query=attribute = 'status' and attrvalue = 'RESOLVED'
filters.conditional.rule0.description=Unresolved branches
filters.conditional.rule0.enabled=true
filters.conditional.rule0.related.branches=None
filters.conditional.rule0.type=exclusion_rule
filters.conditional.rule1.branches_query=
filters.conditional.rule1.color=0,128,192
filters.conditional.rule1.description=Unresolved branches
filters.conditional.rule1.enabled=true
filters.conditional.rule1.related.branches=None
filters.conditional.rule1.type=non_integrated_branches
```

--------------------------------

### CLI Command with Shelf Support

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/7

Example of using the 'cm statt' command with shelf support. Ensure the core and Windows GUI also support shelves for full functionality.

```console
$ cm statt att:status@quake@localhost:6060 sh:6@quake@localhost:6060 New
```

--------------------------------

### UnityAds - initialize

Source: https://docs.unity.com/en-us/grow/ads/ios-sdk/ios-api

Initializes the ads service with a specified Game ID, test mode status, and initialization delegate.

```APIDOC
## POST /initialize

### Description
Initializes the ads service, with a specified Game ID, [test mode](/grow/ads/optimization/test-ads-integration.md) status, and initialization delegate.

### Method
POST

### Endpoint
/initialize

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **gameId** (string) - Required - The platform-specific Unity game identifier for your project, found on the [Unity Ads Monetization dashboard](https://cloud.unity.com/monetization).
- **testMode** (boolean) - Required - Use Test mode to test your integration without serving live ads. Use `true` to initialize in test mode.
- **initializationDelegate** (id<UnityAdsInitializationDelegate>) - Optional - Enables the SDK with [`UnityAdsInitializationDelegate`](#unityadsinitializationdelegate) callbacks (versions 3.7.0 and later).

### Request Example
```json
{
  "gameId": "YOUR_GAME_ID",
  "testMode": true,
  "initializationDelegate": null
}
```

### Response
#### Success Response (200)
- **status** (string) - Indicates the initialization status.

#### Response Example
```json
{
  "status": "initialized_successfully"
}
```
```

--------------------------------

### QStat CLI Basic Syntax

Source: https://docs.unity.com/en-us/clanforge/legacy/qstat

Use this syntax to query game servers for statistics. Specify options, configuration files, output files, server details, and raw output delimiters as needed.

```bash
qstat [options ...] [-f file] [-of|-af output-file] [-server-option host[:port]] [-raw delimiter] [-default server-type] host[:port[-port_max]]
```

--------------------------------

### Unity SDK Callback: Audio Unit Started

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_types_8h

Callback function pointer invoked when an audio unit starts. Provides session group and initial target URI.

```cpp
typedef void (*pf_on_audio_unit_started_t)(void *callback_handle, const char *session_group_handle, const char *initial_target_uri);
```

--------------------------------

### Sign Up with Username and Password

Source: https://docs.unity.com/en-us/authentication/platform-signin/username-password

Use this method to create a new player account with username and password credentials. Ensure the username meets length and character requirements, and the password meets complexity rules.

```csharp
async Task SignUpWithUsernamePasswordAsync(string username, string password)
{
    try
    {
        await AuthenticationService.Instance.SignUpWithUsernamePasswordAsync(username, password);
        Debug.Log("SignUp is successful.");
    }
    catch (AuthenticationException ex)
    {
        // Compare error code to AuthenticationErrorCodes
        // Notify the player with the proper error message
        Debug.LogException(ex);
    }
    catch (RequestFailedException ex)
    {
        // Compare error code to CommonErrorCodes
        // Notify the player with the proper error message
        Debug.LogException(ex);
    }
}
```

--------------------------------

### Launch Desktop Client Wizard (Windows)

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/version-control-cli

Use this command on Windows to launch the Unity Version Control Desktop Client wizard for configuration.

```text
plastic --configure
```

--------------------------------

### Launch Test Suite on Initialization Completion

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/unity/migrate-from-unity-ads-to-levelplay

Subscribe to the SDK initialization completion event and launch the test suite within the callback.

```csharp
LevelPlayEvents.onSdkInitializationCompletedEvent += SdkInitializationInitializationCompletedEvent;

private void SdkInitializationCompletedEvent(){
    ...
    //Launch test suite
    LevelPlay.LaunchTestSuite();
}
```

--------------------------------

### SKAdNetwork Timestamp Example

Source: https://docs.unity.com/en-us/grow/exchange/ios14-support

Example of a Unix timestamp in milliseconds used for generating SKAdNetwork signatures.

```json
"timestamp": "1225091839"
```

--------------------------------

### Example of cm mktrigger with Repository and File Filter

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

This example shows how to use 'cm mktrigger' with both a repository filter and a file extension filter. The trigger will only execute for '.cs' files in the 'default' repository on the specified server.

```text
cm mktrigger before-checkin "check-files"
    "/path/to/script" --filter=rep:default|*.cs
    --server=blackmore:8087
```

--------------------------------

### Update Default Bid and Setup Goal

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/country-group-api

Updates the default bid and setup goal for campaigns.

```APIDOC
## PUT /advertisers/v4/CountryGroup/:campaignId/default

### Description
Use this API to update default bids and goals for your campaigns.

### Method
PUT

### Endpoint
/advertisers/v4/CountryGroup/:campaignId/default

### Parameters
#### Path Parameters
- **campaignId** (string) - Required - The ID of the campaign.

#### Request Body
- **setupGoal** (number) - Optional - The default setupGoal to set.
- **bid** (number) - Optional - The default bid to set.

### Request Example
```json
{
    "setupGoal" : 4,
    "bid" : 2
}
```

### Response
#### Success Response (200)
- **success** (boolean) - Indicates if the operation was successful.
```

--------------------------------

### Create Licensing Server Service on Windows

Source: https://docs.unity.com/en-us/licensing-server/quick-start-web

Run this command in an elevated PowerShell to create and start the Unity licensing server as a Windows service. Ensure the user running the service has the 'Log on as a service' right.

```powershell
.\Unity.Licensing.Server.exe create-service
```

--------------------------------

### Sign in or Create Player with Google

Source: https://docs.unity.com/en-us/authentication/platform-signin/google

Use this method to sign in an existing player or create a new one using Google credentials. It handles both successful sign-in and potential authentication or request errors.

```csharp
async Task SignInWithGoogleAsync(string idToken)
{
    try
    {
        await AuthenticationService.Instance.SignInWithGoogleAsync(idToken);
        Debug.Log("SignIn is successful.");
    }
    catch (AuthenticationException ex)
    {
        // Compare error code to AuthenticationErrorCodes
        // Notify the player with the proper error message
        Debug.LogException(ex);
    }
    catch (RequestFailedException ex)
    {
        // Compare error code to CommonErrorCodes
        // Notify the player with the proper error message
        Debug.LogException(ex);
    }
}
```

--------------------------------

### Example Replica Progress Output

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/10

This is an example of the output that might be seen during a replica operation, which has since been fixed. It includes progress indicators and metadata fetching status.

```text
$cm clone codice@skullcito.codicefactory.com:9095 codice@localhost:6060 --authmode=LDAPWorkingMode --user=pablo --password=supersecret
Destination repository 'codice@localhost:6060' already exists and it's empty.
[#####.........................................................]
- Total active users:     {0}                             (8217)path is already used. Please unload the item (from the configuration view) and retry the operation.                             (0)
Fetching metadata               [###############...............]
Pushing metadata                [..............................]
Introducing data                [..............................]
```

--------------------------------

### Example: Set Big File Threshold to 3MB

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/6

An example of setting the big file size threshold to 3 megabytes in the mergetool.conf file.

```ini
big_file_size=3145728
```

--------------------------------

### Example log_dir configuration variable

Source: https://docs.unity.com/en-us/clanforge/legacy/configuration-variables

The directory in which a game server should send log files.

```text
logs
```

--------------------------------

### Cloaked Exception Rules Example

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/6

Example demonstrating cloaked exception rules within an xlinked directory. The rule '*.jpg' should now correctly apply to xlinked content.

```text
* *.jpg
```

```text
/
/src
/src/foo.c
/theme (xlink)
/theme/app.ico
/theme/logo.jpg
```

--------------------------------

### Field Mapping Example

Source: https://docs.unity.com/en-us/unity-version-control/vcs-plugins/issue-tracking/jira/configure-jira

An example configuration for field mapping that displays the project key in the description, the JIRA description as the title, and the issue creator as the owner.

```text
issue.Fields.Project.Name->Description|issue.Fields.Reporter.Name->Owner|issue.Fields.Description->Title
```

--------------------------------

### Create self-signed certificate on Windows

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/ssl/ssl-certificates

Use `makecert` to generate .pvk and .cer files, then `pvk2pfx` to combine them into a .pfx file. Ensure filenames match the UVCS server hostname to avoid warnings.

```bash
makecert -n "CN=TARDIS" -r -a sha1 -sky exchange -sv Tardis.pvk Tardis.cer
```

```bash
pvk2pfx -pvk "Tardis.pvk" -spc "Tardis.cer" -pfx "Tardis.pfx" -pi <password>
```

--------------------------------

### Get the underlying MeshDefinition array

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/polygonal_meshdefinitionlist

Access the 'list' field to get the raw array of MeshDefinition objects.

```csharp
public MeshDefinition[] list
```

--------------------------------

### StartupModule Implementation

Source: https://docs.unity.com/en-us/vivox-unreal/reference-manual/unreal/class_f_vivox_core_module

Called when the module starts up. This is part of the IModuleInterface implementation for initializing the Vivox module.

```cpp
void StartupModule() override

```

--------------------------------

### Example Failing Case for p4 sync

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

This example shows the 'p4 changelist' output that illustrates a failing case for the p4 sync operation on case-insensitive depots where moved files were not detected correctly.

```text
... depotFile //MyStream/Src/foo.c
... headAction move/delete
... depotFile //mystream/src/foo.c
... headAction move/add
```

--------------------------------

### Create a repository using the CLI

Source: https://docs.unity.com/en-us/unity-version-control/workflow/create-repository

Use the `cm repository create` command to create a new repository. Replace `rep_name` with the desired name for your repository.

```text
cm repository create rep_name
```

--------------------------------

### Audio Unit Started Callback

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_types_8h

Callback function type called when an audio processing unit starts.

```APIDOC
## pf_on_audio_unit_started_t

### Description
Called when an audio processing unit is started in the audio processing thread.

### Callback Signature
`void (*pf_on_audio_unit_started_t)(void *callback_handle, const char *session_group_handle, const char *initial_target_uri)`
```

--------------------------------

### Example 'after chattvalue' trigger data

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

An example of the data provided to an 'after chattvalue' trigger when it fires.

```text
lb:BL145 attribute:"RELEASED" oldvalue:"FALSE" newvalue:"TRUE"
```

--------------------------------

### Plastic SCM Command-Line Performance Benchmarks

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

Compares the performance of loading the client.conf file before and after optimizations for .NET 2 and .NET 4 environments. The 'After' times indicate improved performance.

```text
- .NET 2:
    Before ->  78 ms.
    After  -> 265 ms.

    - .NET 4:
        Before ->  63 ms.
        After  -> 156 ms.
```

--------------------------------

### Example 'before chattvalue' trigger data

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

An example of the data provided to a 'before chattvalue' trigger when it fires.

```text
br:/main/task985 attribute:"STATUS" value:"OK"
```

--------------------------------

### Initialize Vivox SDK

Source: https://docs.unity.com/en-us/vivox-core/quickstart-guide/initializing-vivox

Initialize the Vivox SDK by obtaining the default configuration and calling vx_initialize3. Ensure to check the response codes for success.

```c++
#include"Vxc.h"
#include"VxcErrors.h"

vx_sdk_config_t defaultConfig;
int status = vx_get_default_config3(&defaultConfig, size of (defaultConfig));

if (status != VxErrorSuccess) {
    printf("vx_sdk_get_default_config3() returned %d: %s\n", status,
    vx_get_error_string(status));
    return;
}
config.pf_sdk_message_callback = &sOnResponseOrEventFromSdk;
status = vx_initialize3(&defaultConfig, size of (defaultConfig));

if (status != VxErrorSuccess) {
    printf("vx_initialize3() returned %d : %s\n", status, vx_get_error_string(status));
    return;
}
// Vivox Client SDK is now initialized
```

--------------------------------

### Example Unity ignore file

Source: https://docs.unity.com/en-us/unity-version-control/ignore-files

This is an example of an ignore file configuration that works with a Unity project. It includes common directories, build artifacts, SCM-related files, and generated project files.

```conf
#Common directories
Library
library
Temp
temp
Obj
obj
Build
build
Builds
builds
UserSettings
usersettings
MemoryCaptures
memorycaptures
Logs
logs
**/Assets/AssetStoreTools
**/assets/assetstoretools
**/Assets/AddressableAssetsData/*/*.bin*
**/assets/addressableassetsdata/*/*.bin*
**/Assets/StreamingAssets/aa.meta
**/assets/streamingassets/*/aa/*
.collabignore

# Builds
*.apk
*.unitypackage

#Plastic SCM related
/ignore.conf
*.private
*.private.meta
^*.private.[0-9]+$
^*.private.[0-9]+.meta$

# Gradle cache directory
.gradle

# Autogenerated project files
/Assets/Plugins/Editor/JetBrains*
/assets/Plugins/Editor/JetBrains*
.vs
ExportedObj
.consulo
*.csproj
*.unityproj
*.sln
*.suo
*.tmp
*.user
*.userprefs
*.pidb
*.booproj
*.svd
*.pdb
*.mdb
*.opendb
*.VC.db

# Unity3D generated meta files
*.pidb.meta
*.pdb.meta
*.mdb.meta

# Unity3D Generated File On Crash Reports
sysinfo.txt

# Crashlytics generated file
crashlytics-build.properties

#Mac
.DS_Store*
Thumbs.db
Desktop.ini
```

--------------------------------

### Install Unity Modules on Linux

Source: https://docs.unity.com/en-us/hub/hub-cli

Use this command to install specific Unity modules for a given Editor version on Linux via the command line.

```shell
~/Applications/Unity\ Hub.AppImage --headless install-modules --version 6000.3.7f1 -m ios android
```

--------------------------------

### List available environments

Source: https://docs.unity.com/en-us/ccd/cli-walkthrough

Run this command to see a list of environments available for your project.

```powershell
$ ugs env list
```

--------------------------------

### Creative Width Example

Source: https://docs.unity.com/en-us/grow/exchange/bid-responses

Example of creative width in device-independent pixels (DIPS). Required for banner ads.

```json
"w": 320
```

--------------------------------

### Initialization API

Source: https://docs.unity.com/en-us/grow/offerwall/web/advanced/api-reference

Initializes the SDK and must be called before showing offerwall content. It supports various options for configuration.

```APIDOC
## Tapjoy('init', options)

### Description
Initializes the SDK. This call must be made before displaying any offerwall content. By default, offerwall content is preloaded.

### Method
JavaScript Function Call

### Endpoint
N/A

### Parameters
#### Request Body
- **options** (object) - Required - Configuration options for initialization.
  - **sdkKey** (string) - Required - Application SDK key.
  - **publisherUserId** (string) - Optional - Publisher User ID used to reward users. Defaults to '-'.
  - **ageRestrictedUser** (boolean) - Optional - Indicates if the user is age-restricted. Defaults to `false`. Refer to [User Privacy](./user-privacy) for value descriptions.
  - **gdprConsentGiven** (boolean) - Optional - Indicates if GDPR consent has been given. Defaults to `false`. Refer to [User Privacy](./user-privacy) for value descriptions.
  - **userSubjectToGdpr** (boolean) - Optional - Indicates if the user is subject to GDPR. Defaults to `false`. Refer to [User Privacy](./user-privacy) for value descriptions.
  - **usPrivacy** (string) - Optional - US privacy string. Defaults to '1---'. Refer to [User Privacy](./user-privacy) for value descriptions.
  - **eventName** (string) - Optional - Placement name. Defaults to '#WebOfferwall'.
  - **preload** (boolean) - Optional - Whether to preload offerwall content. Defaults to `false`.
  - **callback** (function) - Optional - Callback function executed when initialization is complete. Defaults to `() => {}`.
  - **userTags** (array) - Optional - An array of user tags for targeting. For example: `['TAG1', 'TAG2']`. Refer to [User Tags](/grow/offerwall/monetization/dashboard/targeting.md).

### Request Example
```javascript
Tapjoy('init', {
  sdkKey: 'YOUR_SDK_KEY',
  publisherUserId: 'user123',
  preload: true,
  callback: (initialized) => {
    console.log('SDK Initialized:', initialized);
  }
});
```

### Response
N/A (Initialization is asynchronous and signaled via callback)
```

--------------------------------

### Full Interstitial Ad Implementation Example

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/unity/interstitial-integration

This comprehensive example demonstrates the creation, loading, and showing of interstitial ads, along with event subscriptions for various ad lifecycle callbacks. Ensure you replace 'interstitialAdUnitId' with your actual ad unit ID.

```csharp
public class InterstitialAdSample {
    private LevelPlayInterstitialAd interstitialAd;
    void CreateInterstitialAd() {
	      //Create InterstitialAd instance
        interstitialAd= new LevelPlayInterstitialAd("interstitialAdUnitId");

        //Subscribe InterstitialAd events
        interstitialAd.OnAdLoaded += InterstitialOnAdLoadedEvent;
        interstitialAd.OnAdLoadFailed += InterstitialOnAdLoadFailedEvent;
        interstitialAd.OnAdDisplayed += InterstitialOnAdDisplayedEvent;
        interstitialAd.OnAdDisplayFailed += InterstitialOnAdDisplayFailedEvent;
        interstitialAd.OnAdClicked += InterstitialOnAdClickedEvent;
        interstitialAd.OnAdClosed += InterstitialOnAdClosedEvent;
        interstitialAd.OnAdInfoChanged += InterstitialOnAdInfoChangedEvent;
    }
    void LoadInterstitialAd() {
        //Load or reload InterstitialAd 	
        interstitialAd.LoadAd();
    }
    void ShowInterstitialAd() {
	       //Show InterstitialAd, check if the ad is ready before showing
        if (interstitialAd.IsAdReady()) {
   		      interstitialAd.ShowAd();
        }
    }
  
    //Implement InterstitialAd events
    void InterstitialOnAdLoadedEvent(LevelPlayAdInfo adInfo) { }
    void InterstitialOnAdLoadFailedEvent(LevelPlayAdError ironSourceError) { }
    void InterstitialOnAdClickedEvent(LevelPlayAdInfo adInfo) { }
    void InterstitialOnAdDisplayedEvent(LevelPlayAdInfo adInfo) { }
    void InterstitialOnAdDisplayFailedEvent(LevelPlayAdInfo adInfo, LevelPlayAdError error) { }
    void InterstitialOnAdClosedEvent(LevelPlayAdInfo adInfo) { }
    void InterstitialOnAdInfoChangedEvent(LevelPlayAdInfo adInfo) { }
}
```

--------------------------------

### Creative Height Example

Source: https://docs.unity.com/en-us/grow/exchange/bid-responses

Example of creative height in device-independent pixels (DIPS). Required for banner ads.

```json
"h": 568
```

--------------------------------

### Handle Incoming Changes During Check-in

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

This example illustrates the command line client's behavior during a 'cm ci --update' operation, showing validation, processing of conflicts, and file uploads.

```text
> cm ci -c "go in" --update
The selected items are about to be checked in. Please wait...
/ Validating checkin data
Processing directory conflicts
Processing directory operations
Merging file 1 of 1: README.txt
Validating checkin data
Uploading file data
Confirming checkin operation
Modified README.txt
Modified ConsoleApp\AssemblyInfo.cs
Created changeset cs:1150@br:/main@quake@localhost:6060 (mount:'/')

```

--------------------------------

### Initialize LevelPlay SDK (Java)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/sdk-integration

Initialize the LevelPlay SDK using the provided app key and an optional user ID. Implement listeners to handle initialization success or failure.

```java
LevelPlayInitRequest initRequest = new LevelPlayInitRequest.Builder(appKey)
        .withUserId("UserID")
        .build();

LevelPlayInitListener initListener = new LevelPlayInitListener() {
    @Override
    public void onInitFailed(@NonNull LevelPlayInitError error) {
        //Recommended to initialize again 
    }
    @Override
    public void onInitSuccess(LevelPlayConfiguration configuration) {
        //Create ad objects and load ads 
    }
};
LevelPlay.init(context, initRequest, initListener);
```

--------------------------------

### Example Response for Locations

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/locations-list

This is an example of the JSON response structure you can expect when successfully retrieving location data.

```json
{
    "name": <name>,
    "locationid": <locationid>,
}
```

--------------------------------

### Start Analytics Data Collection (Unity 6.1 and earlier)

Source: https://docs.unity.com/en-us/analytics/get-started/get-started

Call this method after initializing the SDK and confirming player consent to begin collecting data. Data collection must be explicitly started each session.

```csharp
AnalyticsService.Instance.StartDataCollection();
```

--------------------------------

### BeginStartAudioInjection

Source: https://docs.unity.com/en-us/vivox-unreal/reference-manual/unreal/class_i_login_session

Starts broadcasting audio from a file to all connected ChannelSessions.

```APIDOC
## BeginStartAudioInjection

### Description
Start broadcasting audio from a file to all connected ChannelSessions.

### Method
Not specified (virtual function in C++)

### Endpoint
Not applicable (function call)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
* **filePath** (FString) - The full pathname for the .wav file to play (this must be single channel, 16-bit PCM).
* **theDelegate** (FOnBeginStartAudioInjectionCompletedDelegate) - A delegate to call when this operation completes.

### Request Example
```cpp
virtual VivoxCoreError BeginStartAudioInjection(
    const FString & filePath,
    FOnBeginStartAudioInjectionCompletedDelegate theDelegate =FOnBeginStartAudioInjectionCompletedDelegate()
) =0
```

### Response
#### Success Response (0)
Indicates success.

#### Error Response
* **VxErrorInvalidState** - If not in an audio-connected ChannelSession.

#### Response Example
Return value of type VivoxCoreError.

### Remark
Injected audio is treated like a second microphone that you are speaking into. Muting or disconnecting your input device does not stop others from hearing the file audio. Muting yourself in a channel, stopping transmission to a channel, or disconnecting the channel AudioState does stop others from hearing the file audio.
```

--------------------------------

### List All Profiles

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/profile-list

Lists all configured profiles using the default output format. No special setup is required.

```bash
cm profile
```

--------------------------------

### Install Specific Unity Version on Fedora

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Installs a specific version of Unity Version Control components on Fedora. Replace version numbers as needed.

```bash
sudo dnf install \
  plasticscm-complete-11.0.16.7608-1.1 \
  plasticscm-server-complete-11.0.16.7608-1.1 \
  plasticscm-client-complete-11.0.16.7608-1.1 \
  plasticscm-client-core-11.0.16.7608-2.1 \
  plasticscm-client-gui-11.0.16.7608-1.1 \
  plasticscm-theme-11.0.16.7608-2.1 \
  plasticscm-server-core-11.0.16.7608-2.1
```

--------------------------------

### Merge Conflict Scenario Setup

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

Defines the initial structure and branch setup for reproducing a specific merge conflict scenario involving Xlinks.

```text
/game (xlink)
/game/src
/game/src/foo.c
/game/src/bar.c
```

--------------------------------

### Account Safe Voice Get Consent

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_requests_8h

Functions for creating and managing requests to get safe voice consent.

```APIDOC
## Account Safe Voice Get Consent API

### Description
Retrieves the current consent status for safe voice features for a given account.

### Method
CREATE

### Endpoint
N/A (Function call)

### Parameters
#### Request Body
- **req** (vx_req_account_safe_voice_get_consent_t **) - Output parameter for the request structure.

### Request Example
```c
vx_req_account_safe_voice_get_consent_t *req;
int result = vx_req_account_safe_voice_get_consent_create(&req);
```

### Response
#### Success Response (0)
- **req** (vx_req_account_safe_voice_get_consent_t **) - Pointer to the created request structure.

#### Response Example
```c
// Success is indicated by a return value of 0.
```
```

--------------------------------

### Example Image Update Response

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-update

This is an example of a successful response when updating a game image. It includes details about the image's status and metadata.

```json
{
    "image": {
        "active": <active>,
        "created_at": <created_at>,
        "updated_at": <updated_at>,
        "updated_by": <updated_by>,
        "latestversionid": <latestversionid>,
        "imageid": <imageid>,
        "path": <path>,
        "created_by": <created_by>,
        "gameversionid": <gameversionid>
    }
}
```

--------------------------------

### Send Friend Request Example

Source: https://docs.unity.com/en-us/friends/concepts/relationships

This example demonstrates sending a friend request. It may result in a FRIEND_REQUEST or a FRIEND relationship depending on the existing state.

```csharp
SendFriendRequestAsync
```

--------------------------------

### InstallLicense

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_coreinterface

Adds a new license to the system using either an activation .bin file or a .lic file.

```APIDOC
## InstallLicense

### Description
Add a new license. You can use either an activation .bin file from the website or a .lic file.

### Method
Not specified (likely a method within a class)

### Endpoint
Not specified

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
- **licensePath** (string) - Required - License file path (.bin or .lic).
- **user** (bool) - Optional - Decide if the .lic license is installed only for this user or for all users. If false, Pixyz must be configured by running 'PiXYZFinishInstall' utility first (only once).

### Request Example
```csharp
InstallLicense("path/to/your/license.bin");
InstallLicense("path/to/your/license.lic", true);
```

### Response
#### Success Response (200)
None (void return type)

#### Response Example
None
```

--------------------------------

### Get Command Usage Information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/trigger

Run this command to get detailed usage information for a specific trigger command.

```bash
cm trigger <command> --usage
```

--------------------------------

### ParallelStart

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_coreinterface

Starts a new parallel session with optional progression and naming.

```APIDOC
## ParallelStart

### Description
Starts a new parallel session.

### Method
POST

### Endpoint
/websites/unity_en-us/ParallelStart

### Parameters
#### Query Parameters
- **progression** (bool) - Optional - Enable progression for the parallel session.
- **name** (string) - Optional - Name of the parallel session.
- **jobCount** (int) - Optional - Count of parallel jobs if known (for progression).

### Response
#### Success Response (200)
- **return_value** (IntPtr) - Handle to the new parallel session.
```

--------------------------------

### Initialize Tapjoy SDK and Handle Callbacks

Source: https://docs.unity.com/en-us/grow/offerwall/ios/placements/offerwall-migration-guide

Initialize the Offerwall SDK using your TJ_SDK_KEY. Implement the `tjcConnectSuccess` and `tjcConnectFail` callbacks to handle initialization status. No further Offerwall SDK calls should be made until a success callback is received.

```objective-c
[Tapjoy connect:@"TJ_SDK_KEY"];
    
- (void)tjcConnectSuccess:(NSNotification *)notifyObj 
{
    NSLog(@"Tapjoy connect succeeded");
}

- (void)tjcConnectFail:(NSNotification *)notifyObj 
{
    NSLog(@"Tapjoy connect failed");
}
```

--------------------------------

### Get command usage information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/purge

Run this command to get detailed usage information for a specific purge command.

```bash
cm purge <command> --usage
```

--------------------------------

### Load Native Ad and Initialize View (Swift)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/ios/native-ads-integration

Initiate the native ad loading process and create an instance of NativeAdView in Swift. Store references to manage the ad and view lifecycle.

```swift
levelPlayNativeAd.load()
let levelPlayNativeAdView = NativeAdView()
```

--------------------------------

### Initiate Vivox Sign-in Process

Source: https://docs.unity.com/en-us/vivox-unreal/developer-guide/vivox-unreal-sdk-basics/sign-in-to-game

Use ILoginSession::BeginLogin to sign users in to Vivox. This method requires an access token and a delegate callback for completion.

```plaintext
/* . . . */
AccountId Account = AccountId(kDefaultIssuer, "example_user", kDefaultDomain);
ILoginSession &MyLoginSession(MyVoiceClient->GetLoginSession(Account));
bool IsLoggedIn = false;
// Setup the delegate to execute when login completes
ILoginSession::FOnBeginLoginCompletedDelegate OnBeginLoginCompleted;
OnBeginLoginCompleted.BindLambda([this, &IsLoggedIn, &MyLoginSession](VivoxCoreError Error)
{
    if (VxErrorSuccess == Error)
    {
        IsLoggedIn = true;
        // This bool is only illustrative. The user is now logged in.
    }
});
// Request the user to login to Vivox
MyLoginSession.BeginLogin(kDefaultServer, MyLoginSession.GetLoginToken(kDefaultKey, kDefaultExpiration), OnBeginLoginCompleted);
/* . . . */
```

--------------------------------

### Get command help information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/remove

Run this command to get comprehensive help information for a specific remove command.

```bash
cm remove <command> --help
```

--------------------------------

### Install Unity Editor on Linux

Source: https://docs.unity.com/en-us/hub/hub-cli

Use this command to install a specific Unity Editor version and changeset on Linux. Ensure the Unity Hub AppImage is executable.

```shell
~/Applications/Unity\ Hub.AppImage --headless install --version 6000.3.7f1 --changeset 9b001d489a54
```

--------------------------------

### Get command usage information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/remove

Run this command to get detailed usage information for a specific remove command.

```bash
cm remove <command> --usage
```

--------------------------------

### Get Label Command Usage

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/label

Run this command to get detailed usage information for a specific label command.

```bash
cm label <command> --usage
```

--------------------------------

### Example Message with Update Notification

Source: https://docs.unity.com/en-us/services/solutions/in-game-mailbox

This JSON shows a message intended to inform players about an upcoming update, including a humorous note about sample availability. This example corresponds to the 'MESSAGE_006' key.

```text
{
"title": "New update coming soon",
"content": "Our next update will be
released soon and will require a client
update from the App Store or Google Play
Store. No, that's a joke. Our samples
are only available on Github for now ;)",
"attachment": "",
"expiration": "0.00:03:00.00"
}
```

--------------------------------

### Start the UVCS proxy server

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/configure/use-proxy-server

Run this command in the terminal to start the UVCS proxy server. Ensure the plasticd executable is in your system's PATH.

```bash
plasticd proxy
```

--------------------------------

### Initialize LevelPlay SDK and Launch Test Suite

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/react/integration-test-suite

Pass an init listener to LevelPlay.init and call launchTestSuite in onInitSuccess. Ensure the LevelPlay SDK is initialized before launching the test suite.

```javascript
import {
  LevelPlay,
  LevelPlayInitRequest,
  type LevelPlayInitListener,
} from 'unity-levelplay-mediation'

const initListener: LevelPlayInitListener = {
  onInitFailed: (error) => {
    // Handle init failure
  },
  onInitSuccess: () => {
    LevelPlay.launchTestSuite()
  },
}

const initRequest = LevelPlayInitRequest.builder('YOUR_APP_KEY').build()
LevelPlay.init(initRequest, initListener)
```

--------------------------------

### JSON Response Example for Instances

Source: https://docs.unity.com/en-us/grow/levelplay/platform/api/instances-api-v4

This is an example of the JSON response received after creating or managing ad instances, showing details for rewarded video and interstitial ad types.

```json
{
  "rewardedVideo": {
    "AdColony": [
      {
        "id": 6701121,
        "zoneId": "102030",
        "name": "adcolony_rv",
        "status": "active",
        "rate": 10,
        "abVersion": "N/A"
      }
    ]
  },
  "interstitial": {
    "ironSource": [
      {
        "id": 0,
        "name": "Default",
        "status": "active",
        "abVersion": "N/A"
      },
      {
        "id": 6701117,
        "name": "low_interstitial",
        "status": "active",
        "abVersion": "N/A",
        "pricing": [
          {
            "eCPM": 3,
            "Countries": [
              "FR",
              "DE"
            ]
          }
        ]
      },
      {
        "id": 6701119,
        "name": "high_interstitial",
        "status": "active",
        "abVersion": "N/A",
        "pricing": [
          {
            "eCPM": 20,
            "Countries": [
              "IL",
              "US"
            ]
          }
        ]
      }
    ],
    "ironSourceBidding": [
      {
        "id": 2948695,
        "name": "",
        "status": "inactive",
        "abVersion": "N/A"
      }
    ]
  }
}
```

--------------------------------

### Example UVCS Branch and Branch Specification

Source: https://docs.unity.com/en-us/unity-version-control/vcs-plugins/teamcity-plugin

Shows example values for the default branch and branch specification parameters in TeamCity Kotlin DSL for UVCS.

```text
"/main"
+:/main/*
```

--------------------------------

### Get Command Usage Information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/attribute

Run this command to get detailed usage information for a specific attribute command.

```bash
cm attribute <command> --usage
```

--------------------------------

### core.parallelStart

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/core_functions

Starts a new parallel session with optional configuration for progression, name, and job count.

```APIDOC
## core.parallelStart

### Description
Starts a new parallel session.

### Method
Not specified (function call in Python)

### Endpoint
Not applicable (local function)

### Parameters
#### Query Parameters
- **progression** (Boolean) - Optional - Enable progression for the parallel session.
- **name** (String) - Optional - Name of the parallel session.
- **jobCount** (Int) - Optional - Count of parallel jobs if known (for progression).

### Request Example
```python
core.parallelStart(progression=False, name="Parallel session", jobCount=-1)
```

### Response
#### Success Response (200)
- **session** (ParallelSession) - Represents the created parallel session.

#### Response Example
```python
# Example response object structure
# core.ParallelSession(...)
```
```

--------------------------------

### Example query_type configuration variable

Source: https://docs.unity.com/en-us/clanforge/legacy/configuration-variables

The query protocol supported by the game server.

```text
sqp
```

--------------------------------

### Initialize IAP with StoreController in Unity

Source: https://docs.unity.com/en-us/iap/upgrade-to-iap-v5

This C# code demonstrates the new asynchronous initialization process for Unity In-App Purchasing v5 using StoreController. It shows how to connect to the store, set up event handlers for product and purchase fetching, and initiate the fetching of products.

```csharp
StoreController m_StoreController;
  
async void InitializeIAP()
{
    m_StoreController = UnityIAPServices.StoreController();

    m_StoreController.OnPurchasePending += OnPurchasePending;

    await m_StoreController.Connect();

    m_StoreController.OnProductsFetched += OnProductsFetched;
    m_StoreController.OnPurchasesFetched += OnPurchasesFetched;

    var initialProductsToFetch = new List<ProductDefinition>
    {
        new(goldProductId, ProductType.Consumable),
        new(diamondProductId, ProductType.Consumable)
    };

    m_StoreController.FetchProducts(initialProductsToFetch);
}
void OnProductsFetched(List<Product> products)
{
    // Handle fetched products
    m_StoreController.FetchPurchases();
}
void OnPurchasesFetched(Orders orders) {
   // Process purchases, e.g. check for entitlements from completed orders
}
```

--------------------------------

### GET /fleet/{fleetID}/switchprofile

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/fleet-profile-switch-status

Get the status of a profile switch triggered by the Fleet Profile Switch endpoint.

```APIDOC
## GET /fleet/<fleetID>/switchprofile

### Description
Get the status of a profile switch triggered by the Fleet Profile Switch endpoint.

### Method
GET

### Endpoint
https://api.multiplay.co.uk/cfp/v2/fleet/<fleetID>/switchprofile

### Parameters
#### Path Parameters
- **fleetID** (string) - Required - Fleet ID to check the current switch status of that fleet's profile.

### Request Example
```curl
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v2/fleet/<fleetID>/switchprofile' \
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS' \
--header 'Content-Type: application/json'
```

### Response
#### Success Response (200)
- **ServersPending** (number) - Number of servers still to be processed.
- **ServersProcessed** (number) - Number of servers that have been processed.
- **ProfileID** (number) - The ID of the profile.
- **State** (string) - The current state of the switch. The following possible values can be set: `pending`, `processing`, `complete`, `not requested`.
- **Deadline** (string) - The time of the deadline if set if a timeout was set in the switch profile request. The format is `2019-02-28T12:34:03.58Z` UTC.

#### Response Example
```json
{
    "ServersPending": <ServersPending>,
    "ServersProcessed": <ServersProcessed>,
    "ProfileID": <ProfileID>,
    "Deadline": <Deadline>,
    "State": <State>
}
```
```

--------------------------------

### Initialize SDK and Launch Test Suite (Swift)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/ios/integration-test-suite

Initialize the LevelPlay SDK with the provided request builder and then launch the test suite upon successful initialization. Handle any initialization errors appropriately.

```swift
LevelPlay.setMetaDataWithKey("is_test_suite", value: "enable")
let requestBuilder = LPMInitRequestBuilder(appKey: "appKey")
    .withUserId("UserId") // optional

let initRequest = requestBuilder.build()
LevelPlay.initWith(initRequest) { [weak self] config, error in
  guard let self = self else { return }
  if let error = error {
      // Handle error
  } else {
      LevelPlay.launchTestSuite(self)
  }
}
```

--------------------------------

### Start Audio Injection

Source: https://docs.unity.com/en-us/vivox-unity/speech-to-text/stt-audio-injection

Starts audio injection into a channel. The injected audio is only played into channels you are currently transmitting into.

```APIDOC
## IVivoxService.StartAudioInjection

### Description
Use this method to start audio injection inside a channel. Injected audio is played only into the channels you're transmitting into.

### Method
POST (or equivalent for SDK method call)

### Endpoint
N/A (SDK Method)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **audioFilePath** (string) - Required - The full pathname for the .wav file for audio injection. The file must be single channel, 16-bit PCM, with the same sample rate as the negotiated audio codec.

### Request Example
```csharp
VivoxService.Instance.StartAudioInjection("/path/to/your/audio.wav");
```

### Response
#### Success Response (200)
Indicates the audio injection process has started.

#### Response Example
None (SDK method, typically returns void or a success status)
```

--------------------------------

### Start API Server with Remote Connections

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/api

Starts the API server listening on port 9090 and allows any incoming connection, including remote ones. Press Enter to stop the server.

```bash
cm api -r
```

--------------------------------

### Example Response for Server Reservation

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/reserve

This is an example of a successful response when reserving a game server. The `success` field indicates the status, and the `allocation` object contains details about the reserved server.

```json
{
    "success": <status>,
    "messages": [],
    "allocation": {
        "profileid": <profileid>,
        "uuid": <uuid>,
        "regions": <regions>,
        "created": <created>,
        "requested": <requested>,
        "fulfilled": <fufilled>,
        "serverid": <serverid>,
        "fleetid": <fleetid>,
        "regionid": <regionid>,
        "machineid": <machineid>,
        "ip": <ip>,
        "game_port": <port>
    }
}
```

--------------------------------

### Text-to-Speech Injection Started Event

Source: https://docs.unity.com/en-us/vivox-core/developer-guide/text-to-speech/tts-events

This event is raised when a text-to-speech message has finished preparing for playback and is starting to play.

```APIDOC
## vx_evt_tts_injection_started

### Description
Raised when a TTS message has finished preparing for playback and is starting to play.

### Parameters
#### Event Parameters
- **num_consumers** (integer) - The number of active sessions (for `tts_dest_remote_transmission`) or local playback players (for `tts_dest_local_playback`) that the TTS message is injected into.
- **utterance_id** (string) - The unique identifier of the TTS message or utterance. This is the same identifier as the one that is returned to you when calling `vx_tts_speak`.
- **utterance_duration** (float) - The duration of the utterance in seconds.
- **tts_destination** (enum) - The destination into which the TTS message is injected.
```

--------------------------------

### List triggers with pagination (first page)

Source: https://docs.unity.com/en-us/cloud-code/triggers/tutorials/define-triggers/rest-api

Fetch the first set of trigger configurations using the `limit` query parameter. This is useful for paginating through a large number of triggers. Replace placeholders with your project and environment IDs.

```bash
curl 'https://services.api.unity.com/triggers/v1/projects/<PROJECT_ID>/environments/<ENVIRONMENT_ID>/configs?limit=2' \
--header 'Authorization: Basic <SERVICE_ACCOUNT_CREDENTIALS_ENCODED>'
```

--------------------------------

### Install Unity Version Control Cloud Edition on Red Hat / CentOS

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Installs the Cloud Edition of Unity Version Control on Red Hat or CentOS using yum.

```bash
sudo yum install plasticscm-cloud
```

--------------------------------

### Deploy Configuration Without Source Control

Source: https://docs.unity.com/en-us/services/service-environments

Use the `ugs deploy` command to promote configurations between environments. This example shows a workflow for backing up production and deploying staging configurations, including a rollback option.

```bash
mkdir backup_prod
mkdir staging_conf
ugs fetch backup_prod --reconcile -s <specify the services here>
ugs fetch staging_conf --reconcile -s <specify the services here>
ugs deploy staging_conf -e production # promotion
#rollback
ugs deploy backup_prod -e production
```

--------------------------------

### Example: Rename Attribute 'status' to 'state'

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/attribute-rename

This example demonstrates renaming an existing attribute named 'status' to 'state'.

```bash
cm attribute rename att:status state
```

--------------------------------

### Example Standard Input for Checkin Trigger

Source: https://docs.unity.com/en-us/unity-version-control/triggers/concepts/detailed-trigger-reference

This example demonstrates the standard input provided to a checkin trigger when a file is changed. It lists the status, path, type, branch, changeset ID, repository, and server for the modified items.

```text
CH "/" DIR#br:/main/scm001;changeset:61@@rep:doom3src@@repserver:HERMES:8087
CH "/search" DIR#br:/main/scm001;changeset:61@@rep:doom3src@@repserver:HERMES:8087
CH "/search/search.h" FILE#br:/main/scm001;changeset:61@@rep:doom3src@@repserver:HERMES:8087
```

--------------------------------

### Display license information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/licenseinfo

Use this command to view general license information. No setup is required.

```bash
cm licenseinfo
```

--------------------------------

### Full Interstitial Ad Implementation Example (C#)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/unity/migrate-interstitial-ad-unit-api

A comprehensive C# example demonstrating the creation, loading, showing, and event handling for interstitial ads using the LevelPlay SDK. Ensure you subscribe to all relevant events for proper ad lifecycle management.

```csharp
public class InterstitialAdSample {
    private LevelPlayInterstitialAd interstitialAd;
    void CreateInterstitialAd() {
        // Create InterstitialAd instance
        interstitialAd = new LevelPlayInterstitialAd("interstitialAdUnitId");

        // Subscribe InterstitialAd events
        interstitialAd.OnAdLoaded += InterstitialOnAdLoadedEvent;
        interstitialAd.OnAdLoadFailed += InterstitialOnAdLoadFailedEvent;
        interstitialAd.OnAdDisplayed += InterstitialOnAdDisplayedEvent;
        interstitialAd.OnAdDisplayFailed += InterstitialOnAdDisplayFailedEvent;
        interstitialAd.OnAdClicked += InterstitialOnAdClickedEvent;
        interstitialAd.OnAdClosed += InterstitialOnAdClosedEvent;
        interstitialAd.OnAdInfoChanged += InterstitialOnAdInfoChangedEvent;
    }
    void LoadInterstitialAd() {
        // Load or reload InterstitialAd
        interstitialAd.LoadAd();
    }
    void ShowInterstitialAd() {
        // Show InterstitialAd, check if the ad is ready before showing
        if (interstitialAd.IsAdReady()) {
            interstitialAd.ShowAd();
        }
    }
    void DestroyInterstitialAd() {
        // Destroy InterstitialAd
        interstitialAd.DestroyAd();
    }
    // Implement InterstitialAd events
    void InterstitialOnAdLoadedEvent(LevelPlayAdInfo adInfo) { }
    void InterstitialOnAdLoadFailedEvent(LevelPlayAdError error) { }
    void InterstitialOnAdClickedEvent(LevelPlayAdInfo adInfo) { }
    void InterstitialOnAdDisplayedEvent(LevelPlayAdInfo adInfo) { }
    void InterstitialOnAdDisplayFailedEvent(LevelPlayAdInfo adInfo, LevelPlayAdError error) { }
    void InterstitialOnAdClosedEvent(LevelPlayAdInfo adInfo) { }
    void InterstitialOnAdInfoChangedEvent(LevelPlayAdInfo adInfo) { }
}
```

--------------------------------

### Example Server Allocation Request

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-allocate

Use this cURL command to queue a server allocation request. Ensure you replace placeholder values with your actual IDs and credentials.

```bash
curl --location --request POST 'https://api.multiplay.co.uk/cfp/v1/server/allocate?regionid=<regionid>&profileid=<profileid>&uuid=<uuid>&fleetid=<fleetid>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### CPU Monitor Start Eater

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Starts CPU eater threads on Android to keep CPU frequency at maximum for accurate load measurements.

```APIDOC
## vx_cpumonitor_start_eater

### Description
Starts the requested number of tight loop threads with the requested priority. This function is intended for Android platform only to prevent CPU frequency scaling and ensure accurate CPU load measurements.

### Method
Not applicable (C function)

### Endpoint
Not applicable (C function)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```c
VIVOXSDK_DLLEXPORT int vx_cpumonitor_start_eater(
    int nthreads,
    int priority
);
```

### Response
#### Success Response (0)
Returns 0 on success.

#### Response Example
```
0
```

### Notes
- Android platform only. Does nothing on other platforms.
- High CPU usage may cause overheating and system throttling.
- Recommended priority value is 0.
```

--------------------------------

### Ignore Configuration Example

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

This configuration demonstrates how 'ignored' items and their children are handled, specifically when an exception is made for a subdirectory.

```text
/src
!/src/bin
```

--------------------------------

### SQP Challenge Response Packet Example

Source: https://docs.unity.com/en-us/clanforge/legacy/sqp

This is an example of a ChallengeResponse packet in the SQP protocol. It contains only a header and no payload.

```plaintext
[0x00000000] 0x00 '\0' unsigned char
[0x00000001] 0x80 '€' unsigned char
[0x00000002] 0x90 '•' unsigned char
[0x00000003] 0x23 '#' unsigned char
[0x00000004] 0x48 'H' unsigned char
```

--------------------------------

### SQP Challenge Request Packet Example

Source: https://docs.unity.com/en-us/clanforge/legacy/sqp

This is an example of a ChallengeRequest packet in the SQP protocol. It contains only a header and no payload.

```plaintext
[0x00000000] 0x00 '\0' unsigned char
[0x00000001] 0x00 '\0' unsigned char
[0x00000002] 0x00 '\0' unsigned char
[0x00000003] 0x00 '\0' unsigned char
[0x00000004] 0x00 '\0' unsigned char
```

--------------------------------

### JSON Request Example for Creating Instances

Source: https://docs.unity.com/en-us/grow/is-ads/monetization/apis/ironsource-instances-api

Provides an example of the JSON payload for creating or updating multiple ad instances. It includes instance name, ad unit, live status, optimization settings, global pricing, and country-specific pricing.

```json
[
  {
    	"instanceName": "instance1",
    	"adUnit": "rewardedVideo",
    	"isLive": false
  },
  {
    	"instanceName": "instance2",
    	"adUnit": "interstitial",
    	"isLive": true,
    	"isOptimized": false,
    	"globalPricing": 10,
    	"countriesPricing": [
	{
		"country": "US",
		"eCPM": 20
	},
	{
		"country": "CN",
		"eCPM": 20
	},	{
		"country": "AU",
		"eCPM": 30
	}
]
  }
]
```

--------------------------------

### Cloud Code Script Parameters Example

Source: https://docs.unity.com/en-us/services/solutions/command-batching

This example demonstrates the structure for parameters used in a Cloud Code script, specifically for processing command batching at the end of a game. Ensure the 'commands' array contains valid command keys.

```javascript
{
"commands": [
"COMMANDBATCH_DEFEAT_RED_ENEMY",
"COMMANDBATCH_OPEN_CHEST",
"COMMANDBATCH_ACHIEVE_BONUS_GOAL",
"COMMANDBATCH_DEFEAT_BLUE_ENEMY",
"COMMANDBATCH_OPEN_CHEST",
"COMMANDBATCH_ACHIEVE_BONUS_GOAL",
"COMMANDBATCH_GAME_OVER"
]
}
```

--------------------------------

### Specify Log and File Directories

Source: https://docs.unity.com/en-us/multiplay-hosting/guides/troubleshooting

Use these configuration variables in launch parameters to direct server logs and files to the correct locations for Multiplay Hosting.

```plaintext
-logFile $$log_dir$$/Engine.log -dataPath $$files_dir$$
```

--------------------------------

### Install Specific Version of Unity Version Control on Debian

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Installs a specific version of Unity Version Control components on Debian. Replace '11.0.16.7608' with the desired version number. Note that older versions might not be available via package installation.

```bash
sudo apt-get install \
  plasticscm-complete=11.0.16.7608 \
  plasticscm-server-complete=11.0.16.7608 \
  plasticscm-client-complete=11.0.16.7608 \
  plasticscm-client-core=11.0.16.7608 \
  plasticscm-client-gui=11.0.16.7608 \
  plasticscm-theme=11.0.16.7608 \
  plasticscm-server-core=11.0.16.7608
```

--------------------------------

### Maven SCM Example Connection String

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

An example of a complete scm connection string for the Plastic SCM Maven SCM plugin, specifying a branch and repository server.

```text
"scm:plasticscm:br:/main/Rel1.1@thirdpartytools@blackpearl:8087"
```

--------------------------------

### Device Hardware Version Example

Source: https://docs.unity.com/en-us/grow/exchange/bid-requests

Indicates the hardware version of the device.

```json
"hwv": "samsung SM-J200H"
```

--------------------------------

### Install Tapjoy React Native SDK via Yarn

Source: https://docs.unity.com/en-us/grow/offerwall/react-native/introduction/quickstart

Install the Tapjoy React Native SDK using Yarn.

```zsh
yarn add tapjoy-react-native-sdk
```

--------------------------------

### Pattern hierarchy example for file types

Source: https://docs.unity.com/en-us/unity-version-control/config-files/filter-pattern-values

Demonstrates pattern precedence in `filetypes.conf`. Path rules take precedence over name rules, so `/src/main/bootstrap/compile.exe` is binary, while other `compile.exe` files are text.

```text
compile.exe:txt
/src/main/bootstrap/compile.exe:bin
```

--------------------------------

### Example: Label Changeset External Tool

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/10

An example configuration for an external tool that labels a selected changeset. This creates a menu item 'Label changeset' under 'External Tools'.

```text
changeset | Label changeset | "C:/Program Files/PlasticSCM5/client/cm.exe" | label create lb:MyLabel cs:@object
```

--------------------------------

### Install Tapjoy React Native SDK via npm

Source: https://docs.unity.com/en-us/grow/offerwall/react-native/introduction/quickstart

Install the Tapjoy React Native SDK using npm.

```zsh
npm install tapjoy-react-native-sdk
```

--------------------------------

### Run SDKSampleApp with Multitenant Mode

Source: https://docs.unity.com/en-us/vivox-core/text-chat-guide/sdksampleapp/run-sdksampleapp

Use this command to run the SDKSampleApp. Replace 'xyzzy' and 'collosal' with your actual issuer and key. The '-m' option enables multitenant mode, prefixing generated names with the issuer.

```plaintext
SDKSampleApp --server=https://mt1s.www.vivox.com/api2 --realm=mt1s.vivox.com --issuer=xyzzy --key=collosal -m
[SDKSampleApp]: connect
* Connecting to http://mt1s.www.vivox.com/api2 with connector handle http://mt1s.www.vivox.com/api2...
* Issuing req_connector_create with cookie=1
* Request req_connector_create with cookie=1 completed.
[SDKSampleApp]: login
* Logging .xyzzy.sa_c78d1595. in with connector handle http://mt1s.www.vivox.com/api2 and account handle .xyzzy.sa_c78d1595.
* Issuing req_account_anonymous_login with cookie=2
* evt_account_login_state_change: .xyzzy.sa_c78d1595. login_state_logging_in
* Request req_account_anonymous_login with cookie=2 completed.
* evt_account_login_state_change: .xyzzy.sa_c78d1595. login_state_logged_in
```

--------------------------------

### Create a New Repository

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/repository

Use this command to create a new repository. You can use the shorthand 'newrepo' or the full 'create' command followed by the desired repository name.

```bash
cm repository newrepo
```

```bash
cm repository create newrepo
```

--------------------------------

### Get Log File Path

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/group__diagnostics

Gets the SDK log file path. This function is deprecated as file logging is not supported.

```APIDOC
## function vx_get_log_file_path

### Description
**Deprecated**: File logging is not supported. Get the SDK log file path.

### Returns
- char * - The path to the SDK log file.
```

--------------------------------

### Example Response URL for User Ad Revenue v3

Source: https://docs.unity.com/en-us/grow/is-ads/monetization/apis/impression-level-revenue-server-side

This is an example of a response URL that provides a link to download the requested user ad revenue report. The link is typically valid for one hour.

```text
https://user-ad-revenue.s3.amazonaws.com/data/bi databases/uar/tables/network/report version%3Dv1/publisher id%3D138101/application id%3D100411/day%3D2018-07-13/000000.gz?AWSAccessKeyId=AKIAILCCGIXP5G2XNXBA&Expires=1532524582&Signature=1U%2FbrLmb%2F7TwXXdoHtb%2F%2FQjrmz0%3D
```

--------------------------------

### Set up Cloud Code Dependencies in C#

Source: https://docs.unity.com/en-us/cloud-code/modules/use-cases/quest-system

This C# class implements ICloudCodeSetup to register services like IQuestService, IGameApiClient, and IPushClient as singletons with the dependency injection container.

```csharp
using Microsoft.Extensions.DependencyInjection;
using Unity.Services.CloudCode.Apis;
using Unity.Services.CloudCode.Core;

namespace QuestSystem;

public class CloudCodeSetup : ICloudCodeSetup
{
    public void Setup(ICloudCodeConfig config)
    {
        config.Dependencies.AddSingleton<IQuestService, QuestService>();
        config.Dependencies.AddSingleton<IGameApiClient>(GameApiClient.Create());
        config.Dependencies.AddSingleton<IPushClient>(PushClient.Create());
    }
}
```

--------------------------------

### Get Status of Multiple Files

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/getstatus

Use this command to get the status of specific files. Ensure files are listed with spaces.

```bash
cm getstatus file1.txt file2.txt
```

--------------------------------

### Start Host with Relay Allocation

Source: https://docs.unity.com/en-us/relay/relay-and-ngo

This function creates a Relay allocation, requests a join code, and starts the host. It requires the maximum number of connections and the connection type (udp, dtls, or wss). Ensure Unity Services are initialized and the player is signed in.

```csharp
public async Task<string> StartHostWithRelay(int maxConnections, string connectionType)
{
    await UnityServices.InitializeAsync();
    if (!AuthenticationService.Instance.IsSignedIn)
    {
        await AuthenticationService.Instance.SignInAnonymouslyAsync();
    }
    var allocation = await RelayService.Instance.CreateAllocationAsync(maxConnections);
    NetworkManager.Singleton.GetComponent<UnityTransport>().SetRelayServerData(AllocationUtils.ToRelayServerData(allocation, connectionType));
    var joinCode = await RelayService.Instance.GetJoinCodeAsync(allocation.AllocationId);
    return NetworkManager.Singleton.StartHost() ? joinCode : null;
}
```

--------------------------------

### Get Command Usage Information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/admin

Append --usage to any admin command to get specific usage details for that command.

```bash
cm admin <command> --usage
```

--------------------------------

### Fetch and Compare Configurations

Source: https://docs.unity.com/en-us/services/service-environments

Use the `ugs fetch` command to retrieve configurations from different environments and compare them, for example, using `kdiff3`. This is useful for diffing environments and preparing for rollbacks.

```bash
ugs fetch ./staging-configs --environment-name staging --reconcile -s <services>
ugs fetch ./prod-configs --environment-name production --reconcile -s <services>
kdiff3 ./staging-configs ./prod-configs
```

--------------------------------

### POST /websites/unity_en-us/image_version

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-create-version

Creates a new image version for a game server. This endpoint allows for detailed control over the installation process, including differential or full installs, server restarts, and handling of active game sessions.

```APIDOC
## POST /websites/unity_en-us/image_version

### Description
Creates a new image version for a game server. This endpoint allows for detailed control over the installation process, including differential or full installs, server restarts, and handling of active game sessions.

### Method
POST

### Endpoint
/websites/unity_en-us/image_version

### Parameters
#### Query Parameters
- **diffid** (string) - Required - The ID of a completed image difference analysis.
- **restart** (boolean) - Required - Specifies whether to restart all affected game servers after the update is complete. `1` to restart, `0` or omitted to not restart.
- **accountserviceid** (string) - Required - The account service ID (ASID) associated with the specified resource.
- **full** (boolean) - Optional - A boolean value that specifies whether to create a full image install (`1`) instead of a partial image install (`0` or omitted).
- **game_build** (string) - Optional - Identifies the game's internal build. If provided, the `<version>` field of the Clanforge Game Version value will be set to this value upon successful completion.
- **force** (boolean) - Optional - A boolean value that specifies whether to force the image version creation even if there are active allocations. `1` to force, `0` or omitted to not force.
```

--------------------------------

### Add Unity Hub Beta Repository on Ubuntu

Source: https://docs.unity.com/en-us/hub/install-hub-linux

Adds the Unity Hub beta repository to your system's sources list. Use this to install beta versions of Unity Hub.

```shell
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/unityhub.gpg] https://hub.unity3d.com/linux/repos/deb unstable main" | sudo tee /etc/apt/sources.list.d/unityhub-beta.list
```

--------------------------------

### Get Server Port - C++

Source: https://docs.unity.com/en-us/multiplay-hosting-unreal/sdk-api/multiplay-server-query-handler-subsystem

Gets the SQP port that the server is listening on. The returned value is a constant reference to an int32.

```cpp
UFUNCTION(BlueprintGetter, Category="Multiplay | ServerQuery")
const int32& GetPort() const
```

--------------------------------

### Example: Grant Specific Group Permissions to Repositories

Source: https://docs.unity.com/en-us/unity-version-control/security-scenarios

Provides concrete examples of granting full access to specific repositories for different groups. These commands ensure that users in 'Core_group' can only access the 'Core' repository, and similarly for 'Art_group' and 'Doc_group'.

```text
cm acl -group=Core_group -allowed=+all rep:Core@example_uvcs_server@cloud
```

```text
cm acl -group=Art_group -allowed=+all rep:Art@example_uvcs_server@cloud
```

```text
cm acl -group=Doc_group -allowed=+all rep:Doc@example_uvcs_server@cloud
```

--------------------------------

### Configuration via Environment Variables

Source: https://docs.unity.com/en-us/ccd/cli

Instructions for setting up UGS CLI configuration using environment variables on Unix-based systems and Windows.

```APIDOC
### Configuration

Environment setup for the UGS CLI is simple. You can use environment variables, CLI commands, or sometimes options within commands for configuration. You can use the following information to get started.

#### Use environment variables

Environment variables allow you to configure the CLI without having to enter details every time you run a command.
Open your terminal and run these commands to set your environment variables:

##### For Unix-based Systems (Linux, macOS)

```bash
export UGS_CLI_SERVICE_KEY_ID="your_key_id"
export UGS_CLI_SERVICE_SECRET_KEY="your_secret_key"
export UGS_CLI_ENVIRONMENT_NAME="your_environment_name"
export UGS_CLI_ENVIRONMENT_ID="your_environment_id"
export UGS_CLI_BUCKET_NAME="your_bucket_name"
export UGS_CLI_PROJECT_ID="your_project_id"
```

##### For Windows

```powershell
For Windows users, open Command Prompt and enter:
set UGS_CLI_SERVICE_KEY_ID=your_key_id
set UGS_CLI_SERVICE_SECRET_KEY=your_secret_key
set UGS_CLI_ENVIRONMENT_NAME=your_environment_name
set UGS_CLI_ENVIRONMENT_ID=your_environment_id
set UGS_CLI_BUCKET_NAME=your_bucket_name
set UGS_CLI_PROJECT_ID=your_project_id
```
```

--------------------------------

### Get Current Players

Source: https://docs.unity.com/en-us/multiplay-hosting-unreal/sdk-api/multiplay-server-query-handler-subsystem

Gets the current number of players connected to the server. The value is represented as a uint16, with a maximum of 65535.

```cpp
UFUNCTION(BlueprintGetter, Category="Multiplay | ServerQuery")
const int32& GetCurrentPlayers() const
```

--------------------------------

### Example Plastic Link for Label Diffs (Before Fix)

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

This example shows the format of a Plastic link for comparing labels before a fix was implemented. It highlights potential issues with special characters and encoding in label names.

```text
plastic://test.cloud/repos/NikkiTest1/labels/FirstCset..My nre super label %%/diff
```

--------------------------------

### Implement Vivox Token Provider in C#

Source: https://docs.unity.com/en-us/vivox-unity/developer-guide/vivox-unity-sdk-basics/using-vivox-access-tokens-together-with-uas

Implement the IVivoxTokenProvider interface to fetch Vivox Access Tokens. This example shows how to set up the token provider before initializing Unity Services and Vivox, and includes a basic structure for the GetTokenAsync method, emphasizing the need to obtain the UAS access token.

```csharp
public class VoiceManager : MonoBehaviour
{
    async void Start()
    {
        // Must be done before any other Vivox action otherwise tokens will not be generated properly.
        VivoxService.Instance.SetTokenProvider(new VivoxTokenProvider());
        await UnityServices.InitializeAsync();
        await VivoxService.Instance.InitializeAsync();
    }
}

class VivoxTokenProvider : IVivoxTokenProvider
{
    public Task<string> GetTokenAsync(string issuer = null, TimeSpan? expiration = null, string targetUserUri = null, string action = null, string channelUri = null, string fromUserUri = null, string realm = null)
    {
        if (!AuthenticationService.Instance.SessionTokenExists)
        {
          // Player not logged in!
        }
        var accessToken = AuthenticationService.Instance.AccessToken
        // Implement token fetching logic here.
        // The method parameters together with the accessToken from the AuthenticationService contain the necessary information for crafting the request payload.
        // This will be called whenever a token is needed for a Vivox action
    }
}
```

--------------------------------

### Get All Entities

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/core_functions

Retrieves a list of all entities currently stored in the database. Use this to get a comprehensive overview of available entities.

```python
core.getAllEntities() -> core.EntityList
```

--------------------------------

### Example Response for Server Save Operation

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-save

This is an example of a successful response when saving a server configuration. It confirms the operation's success and returns details of the saved server profile.

```plaintext
{
    "success": true,
    "server": {
        "profileid": <profileid>,
        "serverid": <serverid>,
        "name": <name>
    }
}
```

--------------------------------

### Get Mesh Definitions

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/polygonal_polygonalinterface

Retrieves a list of MeshDefinitions for multiple meshes. Pass a MeshList to get definitions for all contained meshes.

```csharp
[HandleProcessCorruptedStateExceptions]
public MeshDefinitionList GetMeshDefinitions(MeshList meshes)
```

--------------------------------

### TTS Injection Started Event

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_events_8h

Structure signifying the start of Text-to-Speech (TTS) injection, providing details about the utterance and destination.

```APIDOC
## vx_evt_tts_injection_started_t

### Description
Signifies the start of a Text-to-Speech (TTS) injection. It provides information about the number of consumers, the utterance ID, its duration, and the TTS destination.

### Members
- **base** (vx_evt_base_t) - The base event structure.
- **num_consumers** (unsigned int) - The number of consumers for this TTS injection.
- **utterance_id** (vx_tts_utterance_id) - The unique identifier for the TTS utterance.
- **utterance_duration** (double) - The duration of the TTS utterance in seconds.
- **tts_destination** (vx_tts_destination) - The destination for the TTS output.
```

--------------------------------

### Start Angle Field

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/cad_getrevolutionsurfacedefinitionreturn

Indicates the starting angle for the revolution surface. The type is double, allowing for precise angle values.

```csharp
public double startAngle
```

--------------------------------

### Example Plastic Link for Changeset Diffs (Incorrect Sorting)

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

This example demonstrates an incorrect Plastic link for comparing two changesets, where the source and destination are reversed. This issue has been fixed.

```text
plastic://test.cloud/repos/NikkiTest1/changesets/6..1/diff
```

--------------------------------

### Implement GoInGame RPC Systems in C#

Source: https://docs.unity.com/en-us/mps-sdk/build-with-netcode-for-entities

This script sets up systems for handling the GoInGame RPC, enabling client-server communication for game synchronization and prefab spawning. It includes client-side logic to send the request and server-side logic to process it.

```csharp
using UnityEngine;
using Unity.Collections;
using Unity.Entities;
using Unity.NetCode;
using Unity.Burst;

/// <summary>
/// This allows sending RPCs between a standalone build and the Editor for testing purposes in the event that, when you finish this example,
/// you want to connect a server-client standalone build to a client-configured Editor instance.
/// </summary>
[BurstCompile]
[WorldSystemFilter(WorldSystemFilterFlags.ClientSimulation | WorldSystemFilterFlags.ServerSimulation | WorldSystemFilterFlags.ThinClientSimulation)]
[UpdateInGroup(typeof(InitializationSystemGroup))]
[CreateAfter(typeof(RpcSystem))]
public partial struct SetRpcSystemDynamicAssemblyListSystem : ISystem
{
public void OnCreate(ref SystemState state)
{
SystemAPI.GetSingletonRW<RpcCollection>().ValueRW.DynamicAssemblyList = true;
state.Enabled = false;
}
}

// RPC request from client to server for game to go "in game" and send snapshots / inputs
public struct GoInGameRequest : IRpcCommand
{
}

// When client has a connection with network ID, go in game and tell server to also go in game
[BurstCompile]
[WorldSystemFilter(WorldSystemFilterFlags.ClientSimulation | WorldSystemFilterFlags.ThinClientSimulation)]
public partial struct GoInGameClientSystem : ISystem
{
[BurstCompile]
public void OnCreate(ref SystemState state)
{
// Run only on entities with a PlayerSpawner component data
state.RequireForUpdate<PlayerSpawner>();

var builder = new EntityQueryBuilder(Allocator.Temp)
.WithAll<NetworkId>()
.WithNone<NetworkStreamInGame>();
state.RequireForUpdate(state.GetEntityQuery(builder));
}

[BurstCompile]
public void OnUpdate(ref SystemState state)
{
var commandBuffer = new EntityCommandBuffer(Allocator.Temp);
foreach (var (id, entity) in SystemAPI.Query<RefRO<NetworkId>>().WithEntityAccess().WithNone<NetworkStreamInGame>())
{
commandBuffer.AddComponent<NetworkStreamInGame>(entity);
var req = commandBuffer.CreateEntity();
commandBuffer.AddComponent<GoInGameRequest>(req);
commandBuffer.AddComponent(req, new SendRpcCommandRequest { TargetConnection = entity });
}
commandBuffer.Playback(state.EntityManager);
}
}

// When server receives go in game request, go in game and delete request
[BurstCompile]
[WorldSystemFilter(WorldSystemFilterFlags.ServerSimulation)]
public partial struct GoInGameServerSystem : ISystem
{
private ComponentLookup<NetworkId> networkIdFromEntity;

[BurstCompile]
public void OnCreate(ref SystemState state)
{
state.RequireForUpdate<PlayerSpawner>();

var builder = new EntityQueryBuilder(Allocator.Temp)
.WithAll<GoInGameRequest>()
.WithAll<ReceiveRpcCommandRequest>();
state.RequireForUpdate(state.GetEntityQuery(builder));
networkIdFromEntity = state.GetComponentLookup<NetworkId>(true);
}

[BurstCompile]
public void OnUpdate(ref SystemState state)
{
// Get the prefab to instantiate
var prefab = SystemAPI.GetSingleton<PlayerSpawner>().Player;

// Ge the name of the prefab being instantiated
state.EntityManager.GetName(prefab, out var prefabName);
var worldName = new FixedString32Bytes(state.WorldUnmanaged.Name);

var commandBuffer = new EntityCommandBuffer(Allocator.Temp);
networkIdFromEntity.Update(ref state);

foreach (var (reqSrc, reqEntity) in SystemAPI.Query<RefRO<ReceiveRpcCommandRequest>>().WithAll<GoInGameRequest>().WithEntityAccess())
{
commandBuffer.AddComponent<NetworkStreamInGame>(reqSrc.ValueRO.SourceConnection);
// Get the NetworkId for the requesting client
var networkId = networkIdFromEntity[reqSrc.ValueRO.SourceConnection];

```

--------------------------------

### List Changesets with GUID and Server Spec

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/objectspec

Lists code with a specific changeset GUID, including the repository server specification.

```bash
cm ls /code --tree=ae1390ed-7ce9-4ec3-a155-e5a61de0dc77@code@skull:7070
```

--------------------------------

### List subdirectory at a specific changeset by GUID

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/list

Lists the content of a subdirectory at a specific changeset identified by its GUID, repository, and server.

```bash
cm ls /code --tree=ae1390ed-7ce9-4ec3-a155-e5a61de0dc77@myrep@denver:7070
```

--------------------------------

### Initialize Network SDK (Objective-C)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/flutter/build-custom-adapter-ios

Implement the init method in your Objective-C adapter to initialize the network SDK. Call the provided delegate methods for success or failure.

```objective-c
(void)init:(ISAdData *)adData
delegate:(id<ISNetworkInitializationDelegate>)delegate {
   ...
   // handle errors
   if (error-handling) {
      [delegate onInitDidFailWithErrorCode:ISAdapterErrorMissingParams 
                              errorMessage:error];
   }
   // init success
   [delegate onInitDidSucceed];
}
```

--------------------------------

### Install Plastic Change Tracker Service

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/6

Install the Plastic Change Tracker service for Windows by running 'plasticchangetrackerservice.exe --installservice'. The service helps precisely track file moves and renames.

```bash
plasticchangetrackerservice.exe --installservice

```

--------------------------------

### Move Xlink restriction example

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

Transformer rules cannot move xlinks. This example demonstrates an attempt to move an xlink, which is not supported.

```bash
$ mv /src/xlink /xlink
```

--------------------------------

### Example languages.conf File for Syntax Highlighting

Source: https://docs.unity.com/en-us/unity-version-control/config-files/languages-conf

Define custom syntax highlighting rules by mapping file extensions to specific languages in the `languages.conf` file. Ensure this file is placed in the `syntaxhighlight` directory under `plastic4`.

```conf
# syntax language definition by file extension
.js:JavaScript
.custom:XML
.txt:Plain text
```

--------------------------------

### Plastic Link Examples for Labels

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

Examples of plastic links for comparing labels. Supports single label or a range of two.

```plaintext
plastic://test.cloud/repos/NikkiTest1/labels/My+nre+super+label+%25%25/diff
```

```plaintext
plastic://test.cloud/repos/NikkiTest1/labels/Reviewed+Dpi+Training+Doc..My+nre+super+label+%25%25/diff
```

--------------------------------

### Plastic Link Examples for Changesets

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

Examples of plastic links for comparing changesets. Supports single changeset or a range of two.

```plaintext
plastic://test.cloud/repos/NikkiTest1/changesets/50/diff
```

```plaintext
plastic://test.cloud/repos/NikkiTest1/changesets/34..47/diff
```

--------------------------------

### Connect to Multiplay Server Queries

Source: https://docs.unity.com/en-us/multiplay-hosting-unreal/sdk-api/multiplay-server-query-handler-subsystem

Start listening for Multiplay server queries. Returns true if the query port was successfully bound.

```cpp
UFUNCTION(BlueprintCallable, Category="Multiplay | ServerQuery")
bool Connect()
```

--------------------------------

### Example of Bundling Local Scripts in Cloud Code

Source: https://docs.unity.com/en-us/cloud-code/scripts/how-to-guides/write-scripts/unity-editor

This example demonstrates bundling a script that requires a local module. 'lib.js' exports a string, and 'scriptToBundle.js' imports and uses it, with bundling enabled.

```javascript
module.exports.helloWorld = "Hello world!";
```

```javascript
const lib = require("./lib");

module.exports = async ({ params, context, logger }) => {
  return {
    value: lib.helloWorld,
  };
};

module.exports.bundling = true;
```

--------------------------------

### Example Output

Source: https://docs.unity.com/en-us/cloud-save/tutorials/cloud-code

This is the expected output when the `SaveData` and `GetData` functions are successfully called from the Unity client.

```text
Data retrieved: testValue
```

--------------------------------

### Create Start Buffer Capture Request

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_requests_8h

Allocates and initializes a vx_req_aux_start_buffer_capture_t object.

```cpp
VIVOXSDK_DLLEXPORT int vx_req_aux_start_buffer_capture_create(
    vx_req_aux_start_buffer_capture_t ** req
)
```

--------------------------------

### Example Internal Token

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/saml-auth-microsoft

An example of an internal token generated after a successful client login. This token is stored in the `tokens.conf` file.

```text
{
    "sub": "d65ccf6c-570c-44b6-bf71-4378b4dc271f",
    "atk":
"eyJhbGci0iJIUZI1NiIsInR5cCI6IkpXVCJ9.eyJzZXNzaW9uSWQiOiJfZTM2MjgzMjgtMTAZOS00MTVmLWFiYzItYzdjZTNhYzYzMDBiIiwic2Vzc21vbkV4cGlyYXRpb25EYXR1VXRjVGlja3Mi0jYZODQxNzAyNTA2NZEzNjk1MSwidG9rZW5EdXJhdGlvbkluTWludXRlcy16NjUsImV4cCI6MTcwNjEwNTcwNne.nETSFU1U1n_YfC5EZUhU-chccWBE-75ehdwctpLVFb4",
    "exp": 1704899706
}
```

--------------------------------

### Launch Desktop Client Wizard (Mac/Linux)

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/version-control-cli

Use this command on Mac or Linux to launch the Unity Version Control Desktop Client wizard for configuration.

```text
plasticgui --configure
```

--------------------------------

### LDAP Authentication Example

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/push

Example of providing authentication data for LDAPWorkingMode. The format for --authdata is specific to the authentication mode.

```bash
(--authmode=LDAPWorkingMode) --authdata=::0:dave:fPBea2rPsQaagEW3pKNveA
```

--------------------------------

### Initialize Unity Services SDK

Source: https://docs.unity.com/en-us/authentication/get-started

Call this method in your game's initialization logic to set up all Unity Services SDKs. It handles potential exceptions during initialization.

```csharp
using System;
using Unity.Services.Core;
using UnityEngine;

public class InitializationExample : MonoBehaviour
{
	async void Awake()
	{
		try
		{
			await UnityServices.InitializeAsync();
		}
		catch (Exception e)
		{
			Debug.LogException(e);
		}
	}
}
```

--------------------------------

### List Users with Filter Example

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/listusers

Example command to list only users whose names contain 'm' on a specified server.

```bash
cm listusers localhost:8084 --onlyusers --filter=m
```

--------------------------------

### Initialize and Fetch Remote Config

Source: https://docs.unity.com/en-us/ccd/use-game-overrides-with-ccd

Initializes Unity Services, signs in anonymously if needed, and sets up a listener to fetch and apply remote configurations. Ensure internet connectivity before proceeding.

```csharp
public struct userAttributes {}
public struct appAttributes {}

async Task InitializeRemoteConfigAsync()
{
  // initialize handlers for unity game services
  await UnityServices.InitializeAsync();

  // remote config requires authentication for managing environment information
  if (!AuthenticationService.Instance.IsSignedIn)
  {
    await AuthenticationService.Instance.SignInAnonymouslyAsync();
  }
}

async void Start()
{
    if (Utilities.CheckForInternetConnection())
    {
        await InitializeRemoteConfigAsync();
    }

    RemoteConfigService.Instance.appConfig = RemoteConfigService.Instance.GetConfig("ccd");
    RemoteConfigService.Instance.FetchCompleted += ApplyCcdConfig;
    RemoteConfigService.Instance.FetchConfigs("ccd", new userAttributes(), new appAttributes());
}
```

--------------------------------

### Matchmaker Server Subsystem Initialization

Source: https://docs.unity.com/en-us/matchmaker-unreal/integrate-using-cpp

Demonstrates how to retrieve the UMatchmakerServerSubsystem, which is necessary for server-side matchmaking operations.

```APIDOC
## Server-Side Matchmaking Initialization

### Description
This section shows how to obtain an instance of the `UMatchmakerServerSubsystem` to perform server-side matchmaking tasks.

### Code Example
```cpp
UWorld* GameWorld = GetWorld();
UGameInstance* GameInstance = GameWorld->GetGameInstance();
UMatchmakerServerSubsystem* MatchmakerServerSubsystem = GameInstance->GetSubsystem<UMatchmakerServerSubsystem>();
```

### Notes
- The Matchmaker is intended for use with Multiplay Servers.
- Server functions may require integration with Multiplay SDK functionality, such as `GetPayloadAllocation()` to populate `MatchProperties`.
```

--------------------------------

### Example Server Status Response

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-status

This is an example of the JSON response you can expect when querying a server's status. It includes details about the server's activity, allocation, configuration, and player information.

```plaintext
{
    "server: {
        "active: <active>,
        "allocated_uuid: <allocated_uuid>,
        "admin_locked: <admin_locked>,
        "country_code: <country_code>,
        "game_port: <game_port>,
        "ip: <ip>,
        "locationid: <locationid>,
        "machineid: <machineid>,
        "name: <name>,
        "profileid: <profileid>,
        "serverid: <serverid>,
        "query_info: {
            "players: <players>,
            "max_players: <max_players>,
            "map: <map>,
            "status: <status>
            "name": <name>
        }
    }
}
```

--------------------------------

### Example Bearer Token Response

Source: https://docs.unity.com/en-us/grow/is-ads/monetization/apis/authentication

This is an example of the Bearer token generated by the authentication request. The token is valid for 24 hours.

```text
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzZWNyZXRLZXkiOiJlODNkZWZiNjQ5MjI3YTlkMmE5NTJiMmM1ZWM4YjAyZSIsInJlZnJlc2hUb2tlbiI6IjU1MjU1NTNkN2NiODdjNGNhYjdlYmEwODI4NThkMjFhIiwiZXhwaXJhdGlvblRpbWUiOjE1NDY0Mzc2Mjd9.mqtDslsA1E_MnFvyiMrBCz3DgUhEQaSUChVd_Ajvvf8
```

--------------------------------

### Example server.json Configuration

Source: https://docs.unity.com/en-us/multiplay-hosting-unreal/get-started

This is a minimal server.json configuration required for the Multiplay Game Server SDK. Ensure 'queryPort' and 'serverID' are included, using the provided Multiplay variables.

```json
{
  "queryPort": "$$query_port$$",
  "serverID": "$$serverid$$"
}
```

--------------------------------

### SKAdNetwork Nonce Example

Source: https://docs.unity.com/en-us/grow/exchange/ios14-support

Example of the 'nonce' field, a unique ID for each ad response, adhering to UUID format requirements.

```json
"nonce":"385c9n44-a9ik-28fd-8247-gjk2efoa56a9
```

--------------------------------

### Create Bucket

Source: https://docs.unity.com/en-us/ccd/cli

Create a new bucket for a project. Optionally provide a description and set the bucket to private.

```bash
ugs ccd buckets create <bucket-name> [-d, --description <description>] [-p, --private]
```

--------------------------------

### Configure Wwise for Game Initialization

Source: https://docs.unity.com/en-us/vivox-unreal/developer-guide/ios/avaudiosession-and-wwise

Set the AVAudioSession to the Playback category with default mode for high-quality game audio. Ensures audio output to device speakers or Bluetooth.

```cpp
AkPlatformInitSettings platformInitSettings;
AK::SoundEngine::GetDefaultPlatformInitSettings(platformInitSettings);
platformInitSettings.audioSession.eCategory = AkAudioSessionCategory::AkAudioSessionCategoryPlayback;
platformInitSettings.audioSession.eMode = AkAudioSessionMode::AkAudioSessionModeDefault;
platformInitSettings.audioSession.eCategoryOptions = (AkAudioSessionCategoryOptions)(AkAudioSessionCategoryOptions::AkAudioSessionCategoryOptionDefaultToSpeaker | AkAudioSessionCategoryOptions::AkAudioSessionCategoryOptionAllowBluetooth);
AK::SoundEngine::iOS::ChangeAudioSessionProperties(platformInitSettings.audioSession);
```

--------------------------------

### Example Profile Validation Response

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/profile-validate

This is an example of a successful response when validating a profile. The response includes the profile ID that was affected.

```json
{
    "profileid": <profileid>
}
```

--------------------------------

### Example Profile Validation Request

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/profile-validate

Example cURL command to validate a profile. Ensure you replace YOUR_AUTH_CREDENTIALS with your actual credentials.

```bash
curl --location --request GET "https://api.multiplay.co.uk/cfp/v1/profile/<profileid>/validate" \
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Create a New Repository

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/clone

Creates a new repository on a specified server. This command is distinct from cloning and initializes an empty repository.

```bash
cm repository create project@mordor.home:8084
```

--------------------------------

### Example Output of Licensing Server Report Generation

Source: https://docs.unity.com/en-us/licensing-server/troubleshooting

This is an example of the output you might see in the PowerShell window after successfully generating a licensing server support archive. It indicates the progress of data collection and the final archive path.

```powershell
Creating temporary folder...Done
Collecting configuration files...Done
Collecting license files...Done
Collecting delegation files...Done
Collecting log files...Done
Creating summary file...Done
Archiving files...Done

Archive successfully created: D:\Licensing.Server.Support.2020-06-12-025617.zip
```

--------------------------------

### Minimal Manifest Configuration Example

Source: https://docs.unity.com/en-us/cloud/virtual-private-cloud/on-premises/installation/deployment

This YAML snippet shows a basic configuration for the `manifest.yaml` file. It includes essential settings for platform, release version, artifact synchronization, and networking.

```yaml
platform: onprem

releaseVersion: 0.9.0

artifactSync:
  sourceRepository: uccmpprivatecloud.azurecr.io

configuration:
  networking:
    appDomain: example.com
    allowedIngressCIDRs:
      - "10.0.0.0/8"
    ingress:
      traefik:
        type: LoadBalancer
    serviceMesh:
      istio:
        enabled: false
  kubernetes:
    namespace: asset-solutions
    docker:
      repository: <your-registry-url>
      namespace: <your-registry-namespace>
    imagePullSecret: regcred
    autoscaling:
      minReplicas: 1
      maxReplicas: 10
    storage:
      defaultStorageClass: <your-default-storage-class>
      readWriteManyStorageClass: <your-rwx-storage-class>
  infrastructure:
    sizing: medium
```

--------------------------------

### Initialize LevelPlay SDK (Kotlin)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/sdk-integration

Initialize the LevelPlay SDK using the provided app key and an optional user ID. Implement listeners to handle initialization success or failure.

```kotlin
val initRequest = LevelPlayInitRequest.Builder("AppKey")
        .withUserId("UserId")
        .build()
LevelPlay.init(context, initRequest, object : LevelPlayInitListener {
   override fun onInitFailed(error: LevelPlayInitError) {
       //Recommended to initialize again
   }
   override fun onInitSuccess(configuration: LevelPlayConfiguration) {
       //Create ad objects and load ads
   }
})
```

--------------------------------

### Manual Package Installation Versions

Source: https://docs.unity.com/en-us/services/sdk-upgrades

Use these versions for manual installation of Analytics and Remote Config packages through the Unity Package Manager.

```plaintext
com.unity.services.analytics | 4.0.1
```

```plaintext
com.unity.remote-config | 3.0.0
```

--------------------------------

### Create vx_req_aux_get_render_devices

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/group__devices

Allocates and initializes a vx_req_aux_get_render_devices object.

```c
VIVOXSDK_DLLEXPORT int vx_req_aux_get_render_devices_create(
    vx_req_aux_get_render_devices_t ** req
)
```

--------------------------------

### Install Vulkan on Linux

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/installation/system

Installs necessary Vulkan and OpenGL libraries on Debian-based Linux systems. Ensure your system is updated before running.

```bash
sudo apt-get install -y libopengl0 libegl1 libgl1-mesa-glx libvulkan1 libgomp1
```

--------------------------------

### GET /isInitialized

Source: https://docs.unity.com/en-us/grow/ads/ios-sdk/ios-api

Returns whether the SDK has been initialized successfully.

```APIDOC
## GET /isInitialized

### Description
Returns `YES` if the SDK is initialized successfully, and `NO` if it isn't.

### Method
GET

### Endpoint
/isInitialized

### Response
#### Success Response (200)
- **initialized** (BOOL) - `YES` if the SDK is initialized, `NO` otherwise.

#### Response Example
```json
{
  "initialized": true
}
```
```

--------------------------------

### Start UVCS Server Daemon (macOS)

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/start-stop-restart-server

Use this command to load the Unity Version Control server daemon on macOS. Requires sudo privileges.

```text
sudo launchctl load /Library/LaunchDaemons/com.codicesoftware.plasticscm.server.plist
```

--------------------------------

### Get Command Usage Information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/shelveset

To get more detailed usage information for a specific shelveset command, append the --usage flag.

```bash
cm shelveset <command> --usage
```

--------------------------------

### Get Command Usage Information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/profile

Append '--usage' to a 'cm profile' command to get specific usage details for that command.

```bash
cm profile <command> --usage
```

--------------------------------

### Get command usage information

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/lock

Append '--usage' to any LOCK command to get detailed usage information for that specific command.

```bash
cm lock <command> --usage
```

--------------------------------

### Ad Network Example

Source: https://docs.unity.com/en-us/grow/acquire/partner-integration/custom/postback-request

Specify the ad network name to track which network drove the post-install event.

```text
ad_network=UnityAds
```

--------------------------------

### Basic Get Status Usage

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/getstatus

The fundamental command to get the status of an item or multiple items. Use 'gs' as a shorthand for 'getstatus'.

```bash
cm getstatus <item_path>[ ...] [--format=<str_format>] [--stats] [-R | -r | --recursive]
```

--------------------------------

### Create a New Fleet

Source: https://docs.unity.com/en-us/multiplay-hosting/guides/api-fleet-workflow

Create a new fleet with specified build configurations, name, OS family, OS ID, and region settings. Replace placeholders with your actual IDs and credentials.

```bash
curl -X POST \
    -H "Authorization: Basic <SERVICE_ACCOUNT_CREDENTIALS>" \
    -H "Content-Type: application/json" \
    -d '{"buildConfigurations": [<BUILD_CONFIG_ID>], "name": "Example Fleet", "osFamily": "LINUX", "osID": "1111a1a1-a11a-11a1-a1a1-1a111aa11111", "regions": [{"maxServers": 10, "minAvailableServers": 10, "regionID": "<REGION_ID>"}]}' \
    https://services.api.unity.com/multiplay/fleets/v1/projects/{projectId}/environments/{environmentId}/fleets
```

--------------------------------

### Get Server Map - C++

Source: https://docs.unity.com/en-us/multiplay-hosting-unreal/sdk-api/multiplay-server-query-handler-subsystem

Gets the name of the server's current map. The returned value is a constant reference to an FString.

```cpp
UFUNCTION(BlueprintGetter, Category="Multiplay | ServerQuery")
const FString& GetMap() const
```

--------------------------------

### Set Placement Entry Point (Objective-C)

Source: https://docs.unity.com/en-us/grow/offerwall/ios/introduction/update-guide

Configure the entry point for a placement before requesting content. Use preset values like TJEntryPointMainMenu.

```Objective-C
TJPlacement *placement = [TJPlacement placementWithName:@"myPlacement" delegate:nil];
[placement setEntryPoint:TJEntryPointMainMenu];
[placement requestContent]; 

// Values available
TJEntryPointUnknown //Not set, but removes any value that was already set
TJEntryPointOther
TJEntryPointMainMenu
TJEntryPointHud
TJEntryPointExit
TJEntryPointFail
TJEntryPointComplete
TJEntryPointInbox 
TJEntryPointInitialisation
TJEntryPointStore 
```

--------------------------------

### Get All Servers (GET Request)

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-list-v3

Use this endpoint to retrieve a paginated list of game servers. Ensure to include your authorization credentials.

```bash
curl --location --request GET  'https://api.multiplay.co.uk/cfp/v3/servers?sort_by=<sort_by>&sort_dir=<sort_dir>'
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Sign in with OpenID Connect

Source: https://docs.unity.com/en-us/authentication/openid-connect

Use this method to sign in an existing player or create a new one using OpenID Connect credentials. If no player is associated with the credentials, a new player is created. Otherwise, the existing player is signed in. This function replaces the cached player.

```csharp
async Task SignInWithOpenIdConnectAsync(string idProviderName, string idToken)
{
    try
    {
        await AuthenticationService.Instance.SignInWithOpenIdConnectAsync(idProviderName, idToken);
        Debug.Log("SignIn is successful.");
    }
    catch (AuthenticationException ex)
    {
        // Compare error code to AuthenticationErrorCodes
        // Notify the player with the proper error message
        Debug.LogException(ex);
    }
    catch (RequestFailedException ex)
    {
        // Compare error code to CommonErrorCodes
        // Notify the player with the proper error message
        Debug.LogException(ex);
    }
}
```

--------------------------------

### Get Material Main Color C#

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/material_materialinterface

Gets the main color of any material pattern type. Requires a uint material ID.

```csharp
[HandleProcessCorruptedStateExceptions]
public ColorAlpha GetMaterialMainColor(uint material)
```

--------------------------------

### Initialization API

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/pxz_functions

Functions for starting and ending a Pixyz session.

```APIDOC
## POST /initialize

### Description
Start a new Pixyz session. This step is mandatory before using any SDK features. This function will acquire previously installed license (e.g using core.configureLicenseServer or core.installLicense).

### Method
POST

### Endpoint
/initialize

### Parameters
#### Request Body
- **productName** (String) - Optional - Optional name of the Pixyz product to initialize. Leave empty if using the 'PixyzSDK' product.
- **validationKey** (String) - Optional - Optional validation key linked to the specified product name. Leave empty if no product name was specified.
- **optionalTokenList** (StringList) - Optional - Optional token list for some products using a limited list of features.
- **license** (String) - Optional - Optional license file path to configure the session with. If not specified the session will use a previously installed license using core.configureLicenseServer or core.installLicense.

### Request Example
```json
{
  "productName": "PixyzSDK",
  "validationKey": "",
  "optionalTokenList": [],
  "license": "/path/to/license.lic"
}
```

### Response
#### Success Response (200)
- **status** (String) - Indicates the success of the initialization.

#### Response Example
```json
{
  "status": "initialized"
}
```
```

```APIDOC
## POST /release

### Description
Terminate the initialized Pixyz session, ensuring memory cleanup and license release. This call is optional, as these steps will automatically occur when the process terminates.

### Method
POST

### Endpoint
/release

### Parameters
No parameters required.

### Request Example
```json
{}
```

### Response
#### Success Response (200)
- **status** (String) - Indicates the successful release of the session.

#### Response Example
```json
{
  "status": "released"
}
```
```

--------------------------------

### Report Rewarded Video Ad Started Callback (Optional)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/build-custom-adapter

Implement the optional onAdStarted callback to indicate the start of an ad playable.

```java
// Indicates an ad playable started
void onAdStarted();
```

--------------------------------

### Gluon Xlink File Loading Example

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

Illustrates a scenario where a file might be incorrectly loaded under a parent xlink instead of its proper xlink due to matching internal IDs.

```text
/game (xlink)
/game/content/textures (xlink)
/game/content/textures/texture_A.01 (file)
```

```text
/game (xlink)
/game/texture_A.01 (file)
/game/content/textures (xlink)
```

--------------------------------

### Remove Progress Step Start Callback

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_coreinterface

Removes a previously registered progress step start callback using its unique identifier.

```csharp
public void RemoveProgressStepStartCallback(uint id)
```

--------------------------------

### Hydrate Changeset by GUID

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

Use this command to hydrate a specific changeset using its GUID. Previously, this required specifying the source branch.

```bash
cm pull hydrate cs:cadcf131-d7a4-4e4c-a665-fc04accb8c7f@myrepo@myserver:myport
```

--------------------------------

### Basic History Command

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/history

A basic example of how to view the history of a file.

```text
cm history file1.txt "file 2.txt"
```

--------------------------------

### Check and Show Content (C# - Unity)

Source: https://docs.unity.com/en-us/grow/offerwall/monetization/dashboard/messaging

Implement this C# code in Unity to verify content readiness before showing it. A comment indicates where to add logic for unavailable content.

```C#
if (p.IsContentReady()) {
    p.ShowContent();
} else {
    // Code to handle situation where content is not ready goes here
}
```

--------------------------------

### Example: Filter Changesets View in Plastic SCM

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

Example filter for the 'changesets' view in Plastic SCM, searching by 'created by' and 'comment'.

```text
"created by":mike comment:"first changeset"
```

--------------------------------

### Deploy C# Solution

Source: https://docs.unity.com/en-us/cloud-code/modules/how-to-guides/write-modules/cli

Provide the path to a .sln file to deploy a C# solution. Ensure the solution has a publish profile and excludes unit test projects. The solution should contain only one main project.

```bash
ugs deploy <path-to-sln-file>
```

--------------------------------

### Plastic Link Example for Shelvesets

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

Example of a plastic link used to share a shelveset. The link includes repository and shelveset information.

```plaintext
plastic://test.cloud/repos/NikkiTest1/shelvesets/2/diff
```

--------------------------------

### Plastic Link Examples for Branches

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

Example of a plastic link used to share a branch. The link includes repository and branch information.

```plaintext
plastic://test.cloud/repos/NikkiTest1/branches/main/Mi+rama/MiSuperRama%24%24/diff
```

--------------------------------

### Example Plastic Link for Label Diffs (After Fix)

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

This example shows the corrected format of a Plastic link for comparing labels after a fix. Special characters and spaces in label names are now properly encoded.

```text
plastic://test.cloud/repos/NikkiTest1/labels/FirstCset..My+nre+super+label+%25%25/diff
```

--------------------------------

### Example SSL Plastic Link

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

This is an example of a plastic link that includes SSL protocol information. It was fixed to be correctly opened by Gluon.

```plaintext
plastic://ssl://192.168.100.25:8085/repos/repo_zero/test/changesets/1/path/icongluonlink.png?ui=gluon
```

```plaintext
plastic://ssl://192.168.100.25:8085/repos/repo_zero/changesets/1/path/icongluonlink.png?ui=gluon
```

--------------------------------

### Run Unity Licensing Server CLI (Windows)

Source: https://docs.unity.com/en-us/licensing-server/server-setup

Execute the Unity Licensing Server CLI on Windows. Use this command to interact with the server for various operations.

```bash
.\Unity.Licensing.Server.exe
```

--------------------------------

### Example Jira Custom Field ID

Source: https://docs.unity.com/en-us/unity-version-control/vcs-plugins/issue-tracking/jira/configure-jira

This is an example of a custom field ID for Jira. UVCS uses this ID to identify the field.

```text
fieldID=customfield_1000
```

--------------------------------

### Example Directory Structure for Merge Scenario

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

Illustrates the initial file structure before a merge operation. This helps in understanding the context of directory removal and reloading during merge resolution.

```text
/
/src
/src/bar.c
/src/foo.c
```

--------------------------------

### Create New Leaderboard Configuration File

Source: https://docs.unity.com/en-us/leaderboards/configuration/cli

Use the `new-file` command to generate a new leaderboard configuration file with default content locally. Specify the desired file name.

```bash
ugs leaderboards new-file <file-name>
```

--------------------------------

### Initialize Vivox SDK

Source: https://docs.unity.com/en-us/vivox-core/quickstart-guide/core-call-initialize

Use this code to initialize the Vivox SDK. Ensure Vxc.h and VxcErrors.h are included. The function returns VxErrorSuccess on success.

```c
#include"Vxc.h"
#include"VxcErrors.h"
. . .
vx_sdk_config_t defaultConfig;
int status = vx_get_default_config3(&defaultConfig, sizeof (defaultConfig));

if (status != VxErrorSuccess)
{
    printf("vx_sdk_get_default_config3() returned %d: %s\n", status,
    vx_get_error_string(status));
    return;
}
config.pf_sdk_message_callback = &sOnResponseOrEventFromSdk;
status = vx_initialize3(&defaultConfig, sizeof (defaultConfig));

if (status != VxErrorSuccess)
{
    printf ("vx_initialize3() returned %d : %s\n", status, vx_get_error_string(status));
    return;
}
// Vivox Client SDK is now initialized

```

--------------------------------

### Define vx_resp_aux_capture_audio_start_t

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/group__devices

Defines the response structure for starting audio capture.

```c
typedef struct vx_resp_aux_capture_audio_start vx_resp_aux_capture_audio_start_t;
```

--------------------------------

### Mergetool Example with EOL Handling

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

Demonstrates how automatic merges can produce incorrect results when the base file lacks a newline and EOL is ignored. This example shows the input files and the resulting output when using the mergetool with specific flags.

```text
line1
line2
line3
```

```text
line1
line2
line3
line4
```

```text
line1
line2
line2-1
line3
```

```text
line1
line2
line2-1
line3line4
```

--------------------------------

### Connect to Game Server

Source: https://docs.unity.com/en-us/multiplay-hosting-unreal/cpp-integration

Use Connect() to establish a connection to the game server for receiving updates.

```cpp
ServerQueryHandlerSubsystem->Connect();
```

--------------------------------

### Example Server Restart Response

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-restart

This is a sample JSON response indicating the status of the server restart action. It confirms the action performed and whether it was successful.

```json
{
    "action": "restart",
    "success": true,
    "server": {
        "serverid": <serverid>
    }
}
```

--------------------------------

### Example Tapjoy Signature Header

Source: https://docs.unity.com/en-us/grow/offerwall/monetization/virtual-currency/self-managed-currency

This is an example of the X-Tapjoy-Signature header that Tapjoy includes in the POST request. The value is the generated HMAC-SHA256 hash.

```http
X-Tapjoy-Signature => 7205ccfdfa1fe28cd05a1b56a9508d898cc938aa555a6c18848097fe4ee0975b
```

--------------------------------

### Set Placement Entry Point

Source: https://docs.unity.com/en-us/grow/offerwall/android/introduction/update-guide

Before requesting content, set the entry point for the placement. This indicates where in the app the placement will be shown, using preset values.

```java
TJPlacement placement = Tapjoy.getPlacement("myPlacement", null);
placement.setEntryPoint(TJEntryPoint.ENTRY_POINT_MAIN_MENU);
placement.requestContent(); 

// Available values
TJEntryPoint.ENTRY_POINT_UNKNOWN
TJEntryPoint.ENTRY_POINT_OTHER
TJEntryPoint.ENTRY_POINT_MAIN_MENU
TJEntryPoint.ENTRY_POINT_HUD
TJEntryPoint.ENTRY_POINT_EXIT
TJEntryPoint.ENTRY_POINT_FAIL
TJEntryPoint.ENTRY_POINT_COMPLETE
TJEntryPoint.ENTRY_POINT_INBOX
TJEntryPoint.ENTRY_POINT_INIT
TJEntryPoint.ENTRY_POINT_STORE 
```

--------------------------------

### Curl POST Request Example

Source: https://docs.unity.com/en-us/grow/offerwall/monetization/api/reporting-api-best-practices

Example of making a POST request to the Reporting API using curl, with authorization and a JSON payload.

```curl
curl -H "Authorization: Bearer <OAuth Token>" -X POST -d \
"{\"query\": \"query { user { firstName } }\"}" https://api.tapjoy.com/graphql
```

--------------------------------

### Device IFV Example

Source: https://docs.unity.com/en-us/grow/exchange/ios14-support

Example of the IDFV (Identifier for Vendor) for the device, used when IDFA is not present. This is unique across apps from the same vendor.

```string
ABCDEFGH-ABCD-1234-1234-ABCDEFGHABCD
```

--------------------------------

### Initialize Web Offerwall SDK

Source: https://docs.unity.com/en-us/grow/offerwall/web/displaying-offerwall/custom-js-implementation

Include this script to initialize the Tapjoy SDK. Update SDK_KEY with your provided key and publisherUserId with a unique identifier for each user. The eventName is optional.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
  </head>

  <body>
    <script>
      (() => {
        var t, a, p, j, o, y;
        (t = window),
          (a = document),
          (p = 'https://rewards.unity.com/owp/web/sdk/latest'),
          'function' == typeof t[(j = 'Tapjoy')]
            ? t[j]('activator-reinitialized')
            : ((t[j] = function () {
                (t[j].q = t[j].q || []).push(arguments);
              }),
              (t[j].l = 1 * new Date()),
              (o = a.createElement('script')),
              (y = a.getElementsByTagName('script')[0]),
              (o.async = 1),
              (o.src = p),
              y.parentNode.insertBefore(o, y));
      })();
    </script>
    <script>
      Tapjoy('init', {
        sdkKey: '<SDK_KEY>',
        publisherUserId: '<USER_ID>',
        eventName: '<PLACEMENT_NAME>',
      });
    </script>

    <button onclick="javascript:Tapjoy('showOfferwall', {});">Click Me</button>
  </body>
</html>
```

--------------------------------

### List Branch Triggers Command

Source: https://docs.unity.com/en-us/unity-version-control/triggers/concepts/detailed-trigger-reference

Example command to list existing 'before-mkbranch' triggers.

```text
cm trigger list before-mkbranch
```

--------------------------------

### Device IDFA Example

Source: https://docs.unity.com/en-us/grow/exchange/ios14-support

Example of the preferred device advertising identifier (IDFA). It is set to a zero UUID when tracking permission is denied.

```string
ABC123AB-1234-5678-A1B2-123ABCBCD789
```

--------------------------------

### SKAdNetwork Fidelity Field Example

Source: https://docs.unity.com/en-us/grow/exchange/ios14-support

Example of the 'fidelity' field within the SKAdNetwork bid response, specifying the attribution tracking type.

```json
"fidelity": 0
```

--------------------------------

### Show Available Permissions

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/showpermissions

Lists the available permissions using the Unity Version Control CLI. No setup or imports are required.

```bash
cm showpermissions
```

--------------------------------

### SKAdNetwork Source Identifier Example

Source: https://docs.unity.com/en-us/grow/exchange/ios14-support

Example of a four-digit source identifier used in SKAdNetwork 4.0 and later to represent ad campaigns.

```json
"sourceidentifier": "1234"
```

--------------------------------

### Initialize Leaderboards SDK and Authenticate Player in Unity

Source: https://docs.unity.com/en-us/leaderboards/get-started

Initialize the Leaderboards SDK and its dependencies from a Unity script's Awake callback. This example uses anonymous authentication to create a player account. Ensure Unity Services are initialized before calling authentication methods.

```csharp
using UnityEngine;
using Unity.Services.Core;
using Unity.Services.Authentication;

public class LeaderboardsSample : MonoBehaviour
{
  private async void Awake()
    {
        await UnityServices.InitializeAsync();
        await AuthenticationService.Instance.SignInAnonymouslyAsync();
    }
}
```

--------------------------------

### Example Allocation Response (Plaintext)

Source: https://docs.unity.com/en-us/clanforge/legacy/allocations-payload

This is an example of a successful response from the Allocate V2 endpoint when a payload is included. It confirms the allocation details.

```plaintext
{
    "success": true,
    "messages": [],
    "allocation": {
        "profileid": <profileid>,
        "uuid": "<uuid>",
        "regions": "<regionid>",
        "requested": "<requesteddate>",
        "created": "<createddate>",
        "fleetid": "<fleetid>"
    }
}
```

--------------------------------

### Install DVCS Packages on OpenSUSE

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Install the Distributed Version Control System (DVCS) packages for Unity Version Control using zypper.

```bash
sudo zypper install plasticscm-dvcs
```

--------------------------------

### Add a User with umtool

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

Example of adding a new user named 'pablo' with the password 'pablo-password' using the 'umtool' command.

```bash
sudo /Applications/PlasticSCMServer.app/Contents/Applications/umtool.app/Contents/MacOS/umtool cu pablo pablo-password
```

--------------------------------

### Install Unity Version Control DVCS Packages on Fedora

Source: https://docs.unity.com/en-us/unity-version-control/install-uvcs-on-linux

Installs the DVCS packages for Unity Version Control on Fedora using dnf.

```bash
sudo dnf install plasticscm-dvcs
```

--------------------------------

### Create vx_req_connector_get_local_audio_info

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/group__devices

Allocates and initializes a vx_req_connector_get_local_audio_info object.

```c
VIVOXSDK_DLLEXPORT int vx_req_connector_get_local_audio_info_create(
    vx_req_connector_get_local_audio_info_t ** req
)
```

--------------------------------

### Synchronously Download URL Content (HTTP GET)

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Performs a synchronous HTTP GET request to download content from a specified URL. Memory for content and content type is automatically allocated and must be freed using vx_free_http().

```cpp
VIVOXSDK_DLLEXPORT unsigned int vx_get_http(
    const char * url,
    unsigned int * response_code,
    char ** content,
    size_t * content_len,
    char ** content_type,
    size_t * content_type_len
)
```

--------------------------------

### Set Placement Entry Point (Objective-C)

Source: https://docs.unity.com/en-us/grow/offerwall/ios/placements/sdk

Set the entry point for a placement using Objective-C before requesting content. This helps categorize content requests.

```objective-c
TJPlacement *placement = [TJPlacement placementWithName:@"myPlacement" delegate:nil];
[placement setEntryPoint:TJEntryPointMainMenu];
[placement requestContent]; 
```

--------------------------------

### Update and Install Unity Hub on Ubuntu

Source: https://docs.unity.com/en-us/hub/install-hub-linux

Updates the package cache and installs the Unity Hub package. This command should be run after configuring the repository.

```shell
sudo apt update
sudo apt install unityhub
```

--------------------------------

### Get Volume Adjustment

Source: https://docs.unity.com/en-us/vivox-unreal/reference-manual/unreal/class_i_audio_devices

Get the current audio gain for the device, a value between -50 and 50. This adjustment applies to all active audio sessions.

```cpp
virtual int VolumeAdjustment() =0
```

--------------------------------

### Run Support Bundle Command with Output File

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/support

Specify an output file path for the support bundle.

```bash
cm support bundle c:\outputfile.zip
```

--------------------------------

### Acquire Floating License (Windows)

Source: https://docs.unity.com/en-us/licensing-server/client-config

Run this command in the Unity Licensing Client directory on Windows to acquire a floating license. Ensure you have navigated to the correct client directory.

```bash
.\Unity.Licensing.Client.exe --acquire-floating
```

--------------------------------

### Get Specific Inventory Item

Source: https://docs.unity.com/en-us/economy/sdk/quick-reference

Retrieves a specific inventory item definition by its ID. Use this to get details about a particular item in the catalog.

```csharp
public InventoryItemDefinition GetInventoryItem(string id)
```

--------------------------------

### Show Ad with Specific Placement (Objective-C)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/ios/interstitial-integration

This Objective-C example demonstrates how to show an ad for a specific placement after confirming it's ready and not capped. Ensure the placement name is correctly provided.

```Objective-C
// Check that ad is ready and that the placement is not capped
if ([self.interstitialAd isAdReady] && ![LPMInterstitialAd isPlacementCapped:placementName]) {
    // Show ad with placement
    [self.interstitialAd showAdWithViewController:self placementName:@"PlacementName"];
}
```

--------------------------------

### GET /v1/server/list

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-list

Get a list of all game servers that match the criteria passed through the parameters. Note: Prefer the Server List V3 endpoint.

```APIDOC
## GET /v1/server/list

### Description
Get a list of all game servers that match the criteria passed through the parameters.

### Method
GET

### Endpoint
https://api.multiplay.co.uk/cfp/v1/server/list

### Parameters
#### Query Parameters
- **accountserviceid** (string) - Required - The account service ID (ASID) associated with the specified resource. The credentials in the request header must have access to the ASID to perform the request.
- **serverid** (string) - Optional - Accepts one or more game server IDs.
- **country_code** (string) - Optional - Accepts a single country code.
- **locationid** (string) - Optional - Accepts a single location ID. You can get a list of all location IDs with the Server Location endpoint.
- **active** (boolean) - Optional - If set to `1` or excluded, the response will include active game servers and inactive game servers. If set to `0`, the response will only include inactive game servers.
- **allocated** (boolean) - Optional - If set to `1` or excluded, the response will only include allocated game servers. If set to `0`, the response will only include unallocated game servers.
- **profileid** (string) - Optional - Accepts a profile ID. The response will only include game servers running the specified profile ID.
- **query_info** (boolean) - Optional - If set to `1`, the response will include query information about the game servers. If set to `0` or excluded, the response won't include query information.
```

--------------------------------

### Start Host with Relay Allocation

Source: https://docs.unity.com/en-us/relay/relay-and-ngo-standalone

This function creates a Relay allocation, requests a join code, and starts a host using the UnityTransport. It requires the maximum number of connections and the desired connection type (udp, dtls, or wss). Ensure UnityServices are initialized and the user is signed in.

```csharp
public async Task<string> StartHostWithRelay(int maxConnections, string connectionType)
{
    await UnityServices.InitializeAsync();
    if (!AuthenticationService.Instance.IsSignedIn)
    {
        await AuthenticationService.Instance.SignInAnonymouslyAsync();
    }
    var allocation = await RelayService.Instance.CreateAllocationAsync(maxConnections);
    NetworkManager.Singleton.GetComponent<UnityTransport>().SetRelayServerData(new RelayServerData(allocation, connectionType));
    var joinCode = await RelayService.Instance.GetJoinCodeAsync(allocation.AllocationId);
    return NetworkManager.Singleton.StartHost() ? joinCode : null;
}
```

--------------------------------

### Define vx_req_aux_render_audio_start Structure

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/structvx__req__aux__render__audio__start

Defines the structure for starting audio rendering requests. Include VxcRequests.h for usage.

```cpp
struct vx_req_aux_render_audio_start;
```

--------------------------------

### Get Entity Type Name

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/core_functions

Retrieves the string name of an entity's type. Pass the entity object to get its type name.

```python
core.getEntityTypeString(entity) -> core.String
```

--------------------------------

### Get Ellipse Curve Definition

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/cad_functions

Extracts parameters from an ellipse curve. Use this to get the semi-major axis, semi-minor axis, and transformation matrix.

```python
cad.getEllipseCurveDefinition(ellipseCurve) -> core.Double, core.Double, geom.Matrix4
```

--------------------------------

### Open with menu configuration format

Source: https://docs.unity.com/en-us/unity-version-control/config-files/openwith-conf

Defines the format for entries in the `openwith.conf` file. The shortcut defined can override predefined shortcuts.

```conf
[Name|Shortcut] "Path" @arguments
```

--------------------------------

### Capture Audio Start

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/group__devices

Starts audio capture from a specific device, ensuring it's functioning properly. Events are sent after successful invocation.

```APIDOC
## Capture Audio Start

### Description
Ensures that a specific selected capture device is functioning properly.

### Method
POST (Assumed, as it starts a process)

### Endpoint
/api/aux/capture/audio/start

### Parameters
#### Request Body
- **device_id** (string) - Required - The identifier for the capture device.

### Request Example
```json
{
  "device_id": "default_mic"
}
```

### Response
#### Success Response (200)
- **status** (string) - Indicates success or failure.

#### Response Example
```json
{
  "status": "success"
}
```
```

--------------------------------

### CreateBRepCone

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/cad_cadinterface

Creates a BRep Cone with a specified radius, height, and optional positioning matrix.

```APIDOC
## CreateBRepCone

### Description
Creates a BRep Cone whose axis is the Z axis centered on O.

### Method
POST (assumed, based on naming convention)

### Endpoint
/brep/cone (assumed)

### Parameters
#### Request Body
- **radius** (double) - Required - Cone radius.
- **height** (double) - Required - Cone height.
- **matrix** (Matrix4) - Optional - Positioning matrix of the Cone.

### Request Example
```json
{
  "radius": 5.0,
  "height": 10.0,
  "matrix": {
    "m00": 1.0, "m01": 0.0, "m02": 0.0, "m03": 0.0,
    "m10": 0.0, "m11": 1.0, "m12": 0.0, "m13": 0.0,
    "m20": 0.0, "m21": 0.0, "m22": 1.0, "m23": 0.0,
    "m30": 0.0, "m31": 0.0, "m32": 0.0, "m33": 1.0
  }
}
```

### Response
#### Success Response (200)
- **uint** - The ID of the created cone.

#### Response Example
```json
{
  "coneId": 201
}
```
```

--------------------------------

### Define Audio Unit Started Callback

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_types_8h

Callback function type called when an audio processing unit starts. No blocking operations should occur.

```cpp
typedef void(* pf_on_audio_unit_started_t) (void *callback_handle, const char *session_group_handle, const char *initial_target_uri);
```

--------------------------------

### Check Ad Readiness and Placement (Objective-C)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/ios/interstitial-integration

Use this Objective-C code to verify that an ad has loaded successfully and its placement is not capped before attempting to display it. This prevents show failures.

```Objective-C
// Check that ad is ready and that the placement is not capped
if ([self.interstitialAd isAdReady] && ![LPMInterstitialAd isPlacementCapped:placementName]) {
    [self.interstitialAd showAdWithViewController:self placementName:placementName];
}
```

--------------------------------

### Add Progress Step Start Callback

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_coreinterface

Registers a callback function to be invoked when a progress step starts. Returns a unique identifier for the callback.

```csharp
public uint AddProgressStepStartCallback(CoreInterface.ProgressStepStartDelegate callback, IntPtr userData)
```

--------------------------------

### Initialize Vivox SDK with Configuration

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Initializes the Vivox SDK with a specific configuration. This must be called before other Vivox APIs, except for vx_get_default_config3().

```cpp
VIVOXSDK_DLLEXPORT int vx_initialize3(
    vx_sdk_config_t * config,
    size_t config_size
)
```

--------------------------------

### Initialize GPUSceneList

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/view_gpuscenelist

Creates a new instance of the GPUSceneList class. Use the parameterless constructor for default initialization.

```csharp
public GPUSceneList()
```

--------------------------------

### Example Rotated Audit Log File

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

An example of a rotated audit log file name, following the pattern specified in the server configuration.

```text
audit_20250304_103250_657.log
```

--------------------------------

### Example Positional Channel Name

Source: https://docs.unity.com/en-us/vivox-core/developer-guide/channels/positional-channel-parameters

This is an example of a channel name that includes positional parameters, used when working with access tokens for Vivox servers.

```plaintext
sip:confctl-d-blindmelon-AppName.match72-team1-prox!p-30-1-1.000-1@tla.vivox.com
```

--------------------------------

### Synchronize Leaderboard Configurations Between Environments

Source: https://docs.unity.com/en-us/leaderboards/configuration/cli

Fetch configurations from one environment and deploy them to another. This is useful for migrating or backing up configurations. Specify the source directory, target environment, and services.

```bash
ugs fetch <out-dir> --services leaderboards --environment-name <environment-name>
```

```bash
ugs deploy <in-dir> --services leaderboards --environment-name <environment-name>
```

--------------------------------

### Display specific changelist status example

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/10

Example output of 'cm status --changelist=chlist1' displaying only the changes associated with the specified changelist.

```text
Changed
    Status         Size       Last Modified    Path
    Checked-out    5 bytes    1 hour ago       file1.txt
```

--------------------------------

### Example port configuration variable

Source: https://docs.unity.com/en-us/clanforge/legacy/configuration-variables

The network port on which the game server should bind for traffic.

```text
1234
```

--------------------------------

### Example UVCS Branch Filtering Parameters

Source: https://docs.unity.com/en-us/unity-version-control/vcs-plugins/teamcity-plugin

Demonstrates example values for enabling and configuring PlasticSCM branch filtering in TeamCity Kotlin DSL.

```text
"true"
"status=resolved"
"status=failed"
"status=tested"
"status=merged"
```

--------------------------------

### Example Session Data Token

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/saml-auth-microsoft

An example of a session data token, also stored in `tokens.conf`, containing session details and expiration information.

```text
{
    "sessionId": "_e3628328-1039-415f-abc2-c7ce3ac6300b",
    "sessionExpiration Date UtcTicks": 638417025067136900,
    "tokenDurationInMinutes" : 65,
    "exp": 1706105706
}
```

--------------------------------

### Install Timestamp Parameter

Source: https://docs.unity.com/en-us/grow/acquire/partner-integration/custom/send-postbacks

Include this timestamp parameter in your secondary postback URL. Milliseconds are the recommended best practice for timestamps.

```url
install_ts=1466637800175
```

--------------------------------

### Run First Pixyz Python Script

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/installation/python

A basic Python script to initialize the Pixyz SDK, print the version, configure logging, and attempt license server configuration. Ensure your license is set up before running.

```python
import pxz
from pxz import core

# init Pixyz
pxz.initialize()

# print Pixyz version
print(core.getVersion())

# set log level to INFO so you can see the logs in the console
core.configureInterfaceLogger(True, True, True)
core.addConsoleVerbose(core.Verbose.INFO)

# if no license is found, try to configure a license server
if not core.checkLicense():
    core.configureLicenseServer("company-server-hostname", 27000, True)

# use io.importScene to import a file and enjoy :)
```

--------------------------------

### StartRecording API

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/view_viewinterface

Initiates video recording for a specified viewer and saves it to a file with configurable encoder settings.

```APIDOC
## StartRecording

### Description
Record viewer in a file.

### Method
POST

### Endpoint
/websites/unity_en-us/StartRecording

### Parameters
#### Request Body
- **filePath** (string) - Required - File in which video while be saved.
- **viewer** (int) - Required - Viewer to use for recording video.
- **encoderSettings** (EncoderSettings) - Optional - Settings used for the encoder.

### Request Example
```json
{
  "filePath": "/path/to/save/recording.mp4",
  "viewer": 0,
  "encoderSettings": {
    "bitrate": 5000000,
    "frameRate": 30
  }
}
```

### Response
#### Success Response (200)
- **status** (string) - Indicates the success of the operation.

#### Response Example
```json
{
  "status": "Recording started successfully"
}
```
```

--------------------------------

### Example Server Stop Request

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-stop

Example cURL command to stop a game server. Ensure you replace `YOUR_AUTH_CREDENTIALS` with your actual authentication token.

```bash
curl --location --request GET 'https://api.multiplay.co.uk/cfp/v1/server/<serverid>/stop' \
--header 'Authorization: Basic YOUR_AUTH_CREDENTIALS'
```

--------------------------------

### Create New File

Source: https://docs.unity.com/en-us/search

Creates a new C# Module solution locally.

```APIDOC
## POST /api/modules/new-file

### Description
Creates a new C# Module solution locally filled with template code and a publish profile.

### Method
POST

### Endpoint
/api/modules/new-file

### Query Parameters
- **quiet** (boolean) - Optional - Reduce logging to a minimum.
```

--------------------------------

### Session Creation Shortcut Note

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/structvx__req__session__create

Note that creating a session automatically connects to audio media, serving as a shortcut. This request creates a new session group and session, returning handles for both.

```text
Creating a session automatically connects to the audio media, and you do not need to call Session.Connect. This request can be used as a shortcut to creating a session group and then adding a session to the session group. This request creates a new session group, creates a new session, and then returns the handles to both in the response.
```

--------------------------------

### Install Bash Autocompletion for 'cm' CLI

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

Install command-line autocompletion for the 'cm' utility in Bash. This modifies your .bashrc file, requiring a session restart.

```bash
$ cm autocomplete install
```

--------------------------------

### Create a CCD bucket

Source: https://docs.unity.com/en-us/ccd/cli-walkthrough

Create a new CCD bucket within your project. Replace `example_bucket` with your desired bucket name. Bucket names are case-sensitive.

```powershell
$ ugs ccd buckets create example_bucket
```

--------------------------------

### Lock Management Commands

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

Examples for the new 'lock' command to manage locks.

```text
cm lock list
cm lock
(list is optional if there are no arguments)
cm lock unlock 91961b14-3dfe-4062-8c4c-f33a81d201f5
```

--------------------------------

### Synchronous HTTP GET Request

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Synchronously downloads the content of a specified URL using the HTTP GET method. Memory for content and content type is allocated automatically and must be freed using `vx_free_http()`.

```APIDOC
## vx_get_http

### Description
Synchronously download the contents of the specified URL with the GET method.

### Method
Not Applicable (C function)

### Endpoint
Not Applicable

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
None

### Response
#### Success Response (0)
- **unsigned int** - 0 if successful, non-zero if failed.
- **unsigned int * response_code** - A pointer to the returned response code (0 on error, >= 200 after the request finished).
- **char ** content** - A pointer to the downloaded content, NULL-terminated. Memory is allocated automatically.
- **size_t * content_len** - A pointer to the returned content length.
- **char ** content_type** - A pointer to the downloaded content type, NULL-terminated. Memory is allocated automatically.
- **size_t * content_type_len** - A pointer to the returned content type length.

#### Response Example
None

### Notes
- The memory allocated for `content` and `content_type` must be freed using `vx_free_http()`.
```

--------------------------------

### Initialize and Login with Facebook SDK

Source: https://docs.unity.com/en-us/authentication/platform-signin/facebook

This script initializes the Facebook SDK and provides a function to log in users with specified permissions. Ensure the Facebook SDK is installed and configured in your Unity project.

```csharp
using System.Collections.Generic;
using UnityEngine;

// Other needed dependencies
using Facebook.Unity;

public class FacebookExampleScript : MonoBehaviour
{
    public string Token;
    public string Error;

    // Awake function from Unity's MonoBehaviour
    void Awake()
    {
        if (!FB.IsInitialized)
        {
            // Initialize the Facebook SDK
            FB.Init(InitCallback, OnHideUnity);
        }
        else
        {
            // Already initialized, signal an app activation App Event
            FB.ActivateApp();
        }
    }

    void InitCallback()
    {
        if (FB.IsInitialized)
        {
            // Signal an app activation App Event
            FB.ActivateApp();
            // Continue with Facebook SDK
        }
        else
        {
            Debug.Log("Failed to Initialize the Facebook SDK");
        }
    }

    void OnHideUnity(bool isGameShown)
    {
        if (!isGameShown)
        {
            // Pause the game - we will need to hide
            Time.timeScale = 0;
        }
        else
        {
            // Resume the game - we're getting focus again
            Time.timeScale = 1;
        }
    }

    public void Login()
    {
        // Define the permissions
        var perms = new List<string>() { "public_profile", "email" };

        FB.LogInWithReadPermissions(perms, result =>
        {
            if (FB.IsLoggedIn)
            {
                Token = AccessToken.CurrentAccessToken.TokenString;
                Debug.Log($"Facebook Login token: {Token}");
            }
            else
            {
                Error = "User cancelled login";
                Debug.Log("[Facebook Login] User cancelled login");
            }
        });
    }
}
```

--------------------------------

### Set Placement Entry Point (Swift)

Source: https://docs.unity.com/en-us/grow/offerwall/ios/placements/sdk

Configure the entry point for a Tapjoy placement in Swift. This is done after creating the placement object and before requesting content.

```swift
let placement = TJPlacement(name: "myPlacement", delegate: nil)
placement?.entryPoint = TJEntryPoint.mainMenu
placement?.requestContent() 
```

--------------------------------

### Purchase Starter Pack

Source: https://docs.unity.com/en-us/services/solutions/starter-packs

Initiates the starter pack purchase by calling a Cloud Code script. This script verifies the deal has not been claimed, deducts currency, and updates the deal status in Cloud Save.

```csharp
public async void OnBuyButtonPressed()
{
    // Disable the purchase button while the currency balance updates.
    m_PurchaseButton.SetInteractable(false);

    // Send a request to the Cloud Code service to execute the PurchaseStarterPack.js script.
    // For more information, see the "Purchase starter pack" section.
    // await CloudCodeService.Instance.RunCodeAsync("PurchaseStarterPack");

    // Update the UI to show the new currency balance.
    // For more information, see the "Retrieve and update currency balances" section.
    // LoadInventory();
}
```

--------------------------------

### Deploy Economy Configuration with UGS CLI

Source: https://docs.unity.com/en-us/economy/implementation

Deploy your Economy configuration file to the Economy service using the UGS CLI. This makes your configuration accessible to the game client.

```bash
ugs deploy <path-to-economy-file>
```

--------------------------------

### Install Unity Modules on macOS

Source: https://docs.unity.com/en-us/hub/hub-cli

Use this command to install specific Unity modules for a given Editor version on macOS via the command line.

```shell
/Applications/Unity\ Hub.app/Contents/MacOS/Unity\ Hub -- --headless install-modules --version 6000.3.7f1 -m ios android
```

--------------------------------

### Initialize Cloud Save and Authentication SDKs

Source: https://docs.unity.com/en-us/cloud-save/get-started

Initialize the Cloud Save SDK and its dependencies, including authentication, using the Core SDK. This example uses anonymous sign-in for authentication.

```csharp
using System.Collections.Generic;
using Unity.Services.Authentication;
using Unity.Services.CloudSave;
using Unity.Services.CloudSave.Models;
using Unity.Services.Core;
using UnityEngine;

public class CloudSaveSample : MonoBehaviour
{
    private async void Awake()
    {
        await UnityServices.InitializeAsync();
        await AuthenticationService.Instance.SignInAnonymouslyAsync();
        SaveData();
    }

    public async void SaveData()
    {
        var playerData = new Dictionary<string, object>{
          {"firstKeyName", "a text value"},
          {"secondKeyName", 123}
        };
        var result = await CloudSaveService.Instance.Data.Player.SaveAsync(playerData);
        Debug.Log($
```

--------------------------------

### Start CPU Eater Threads (C++)

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Starts a specified number of threads with tight loops to maximize CPU usage. This is useful on Android to prevent CPU frequency scaling and ensure accurate performance measurements. Use with caution as it can cause CPU overheating.

```cpp
VIVOXSDK_DLLEXPORT int vx_cpumonitor_start_eater(
    int nthreads,
    int priority
)
```

--------------------------------

### BeginAddPresenceSubscription

Source: https://docs.unity.com/en-us/vivox-unreal/reference-manual/unreal/class_i_login_session

Subscribes to a specified account, allowing the subscriber to see the account's online status. Returns 0 on success.

```cpp
virtual VivoxCoreError BeginAddPresenceSubscription(
    const AccountId & accountId,
    FOnBeginAddPresenceSubscriptionCompletedDelegate theDelegate =FOnBeginAddPresenceSubscriptionCompletedDelegate()
) =0
```

--------------------------------

### Manage Editors

Source: https://docs.unity.com/en-us/hub/hub-cli

List available Unity Editor releases and installed Editors on your machine. Options can filter the list to show all, only releases, or only installed editors.

```APIDOC
## GET /editors

### Description
Displays a list of available Unity Editor releases and/or installed Editors.

### Method
GET

### Endpoint
--headless editors

### Parameters
#### Query Parameters
- **all** (boolean) - Optional - Alias: -a - Displays both available releases and Editors installed on your machine.
- **releases** (boolean) - Optional - Alias: -r - Displays the available releases.
- **installed** (boolean) - Optional - Alias: -i - Displays the Editors installed on your machine.

### Request Example
```shell
/Applications/Unity\ Hub.app/Contents/MacOS/Unity\ Hub -- --headless editors -r
```

### Response
#### Success Response (200)
- **editors** (array) - A list of Unity Editor releases or installed versions.
```

--------------------------------

### Create a changelist using name and description files

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

Create a new changelist, providing both the name and description from separate files. The 'add' verb is deprecated.

```console
cm changelist create --filename="name.txt" --descriptionfile="desc.txt"
```

--------------------------------

### Update and Install Unity Hub on RHEL/CentOS

Source: https://docs.unity.com/en-us/hub/install-hub-linux

Updates the package cache and installs the Unity Hub package using yum. Run this after configuring the repository.

```shell
sudo yum update
sudo yum install unityhub
```

--------------------------------

### List Profiles with Custom Format

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/profile-list

Lists profiles with a custom format string. This example shows how to display the profile index and server, with specific alignment and spacing. The format string uses placeholders like {index} and {server} with width specifiers.

```bash
cm profile --format="{index,2} {server,-20}"
```

--------------------------------

### Provide SDK and Adapter Versions (Swift)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/flutter/build-custom-adapter-ios

Implement override methods in Swift to return the network SDK version and the adapter version. Ensure `customAdapterVersion` is correctly set.

```swift
public override func networkSDKVersion() -> String {
   return  yourNetworkSDKVersion()
}
public override func adapterVersion() -> String {
   return self.customAdapterVersion;
}
```

--------------------------------

### Add Ignored Files Example

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/7

Demonstrates adding ignored files and directories using the command line. If a directory is added, non-ignored files within ignored subdirectories are included.

```bash
cm add foo.c
```

```bash
cm add -R . --addprivateparents
```

--------------------------------

### Get Available Voices

Source: https://docs.unity.com/en-us/vivox-unreal/reference-manual/unreal/class_i_text_to_speech

Retrieves all voices available for speech synthesis, indexed by name. Use this to get a list of voices before setting the current voice.

```cpp
virtual const TMap< FString, ITTSVoice * > & GetAvailableVoices() =0
```

--------------------------------

### List Repositories in Table Format

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/repository-list

Lists repositories from a specific server and displays the output in a table format, including repository ID, name, and server name. This provides a structured overview.

```bash
cm repo ls localhost:8084 --format=TABLE
```

--------------------------------

### Get Channels Being Transmitted To

Source: https://docs.unity.com/en-us/vivox-unreal/developer-guide/unreal-upgrade-guide/transmission

Use ILoginSession::GetTransmittingChannels() to get an array of all ChannelIds the session is transmitting to. Alternatively, use IChannelSession::IsTransmitting() for a specific channel.

```csharp
ILoginSession::GetTransmittingChannels()
```

```csharp
IChannelSession::IsTransmitting()
```

--------------------------------

### Check Ad Readiness and Placement Capping

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/interstitial-integration

Before showing an ad, verify that it is ready and that the specific placement is not capped. This prevents show failures and ensures ads are displayed correctly.

```java
// Check that ad is ready and that the placement is not capped 
if (mInterstitialAd.isAdReady() && !LevelPlayInterstitialAd.isPlacementCapped(placementName)) {
    mInterstitialAd.showAd(this, placementName);
}
```

```kotlin
// Check that ad is ready and that the placement is not capped
if (mInterstitialAd.isAdReady() && !LevelPlayInterstitialAd.isPlacementCapped(placementName)) {
    mInterstitialAd.showAd(this, placementName)
}
```

--------------------------------

### GET /levelPlay/reporting/v1

Source: https://docs.unity.com/en-us/grow/levelplay/platform/api/reporting

Retrieve monetization data across ad formats and dimensions via a filtered GET call to the LevelPlay Ads Reporting API.

```APIDOC
## GET /levelPlay/reporting/v1

### Description
Retrieve monetization data across ad formats and dimensions via a filtered GET call to the LevelPlay Ads Reporting API. Use this API to receive all the reporting data from the monetization ad formats you serve with LevelPlay and/or ironSource Ads. This includes multiple metrics such as revenue, impressions, active users, and more across several breakdowns and optional filters.

### Method
GET

### Endpoint
https://platform.ironsrc.com/levelPlay/reporting/v1

### Parameters
#### Query Parameters
- **startDate** (String) - Required - YYYY-MM-DD (UTC Timezone)
- **endDate** (String) - Required - YYYY-MM-DD (UTC Timezone)
- **appKey** (String (comma separated)) - Optional - Application Key (as seen on the LevelPlay and ironSource Ads platform)
- **country** (String (comma separated)) - Optional - 2 letter country code, as per ISO 3166-1 Alpha-2.
- **adFormat** (String) - Optional - Options are: 'rewarded' / 'offerwall' / 'interstitial' / 'banner'
- **adNetwork** (String (comma separated)) - Optional - Mediated ad networks, Including ironSource Ads.
- **isLevelPlayMediation** (String (boolean)) - Optional - Relevant only for ironSource Ads network. Options are: true / false. Supported as of March 1st, 2024
- **isBidder** (String (boolean)) - Optional - Options are: true / false
- **platform** (String) - Optional - Options are: 'android' / 'ios'
- **abTest** (String) - Optional - Options are: ‘A' / ‘B' / ‘NULL' Single value expected(one of the above)
- **mediationGroup** (String (comma separated)) - Optional - Mediation Group (as seen on the LevelPlay platform)
- **mediationAdUnitId** (String (comma separated)) - Optional - ID of the ad unit which the revenue was generated from
- **metrics** (String (comma separated)) - Optional - For available metrics – See below
- **breakdowns** (String (comma separated)) - Optional - For supported breakdowns (see below)
- **page** (number) - Optional - Which page number to display
- **resultsPerPage** (number) - Optional - Number of results to display for each page

### Request Example
```json
{
  "startDate": "2023-01-01",
  "endDate": "2023-01-31",
  "adFormat": "rewarded",
  "metrics": "impressions,revenue",
  "breakdowns": "date,country"
}
```

### Response
#### Success Response (200)
- **data** (Array) - Array of reporting data objects.
  - **date** (String) - The date of the report.
  - **country** (String) - The country code.
  - **adFormat** (String) - The ad format.
  - **impressions** (Number) - The number of impressions.
  - **revenue** (Number) - The generated revenue.

#### Response Example
```json
{
  "data": [
    {
      "date": "2023-01-01",
      "country": "US",
      "adFormat": "rewarded",
      "impressions": 10000,
      "revenue": 50.75
    },
    {
      "date": "2023-01-01",
      "country": "US",
      "adFormat": "interstitial",
      "impressions": 5000,
      "revenue": 25.30
    }
  ]
}
```
```

--------------------------------

### Get Specific Virtual Purchase

Source: https://docs.unity.com/en-us/economy/sdk/quick-reference

Retrieves a specific virtual purchase definition by its ID. Use this to get details about a particular virtual item or offer.

```csharp
public VirtualPurchaseDefinition GetVirtualPurchase(string id)
```

--------------------------------

### Dockerfile for Custom Container Build

Source: https://docs.unity.com/en-us/multiplay-hosting/concepts/integration-requirements

This Dockerfile sets up the 'mpukgame' user and configures the container's entrypoint. Ensure your game files are copied correctly and the entrypoint points to your executable.

```dockerfile
# ======================================================== #
# Unity base image stuff                  #
# ======================================================== #

FROM ubuntu:22.04 AS mpuk

RUN addgroup --gid 2000 mpukgame && \
    useradd -g 2000 -u 2000 -ms /bin/sh mpukgame && \
    mkdir /game && \
    chown mpukgame:mpukgame /game && \
    apt update && \
    apt upgrade && \
    apt install -y ca-certificates
USER mpukgame

# ======================================================== #
# Custom game stuff                     #
# ======================================================== #

FROM mpuk AS game

# copy game files here
# for example:
WORKDIR /game
COPY --chown=mpukgame . .

# set your game binary as the entrypoint
ENTRYPOINT [ "./gamebinary" ]
```

--------------------------------

### Set Up Vivox SDK Logging Callback

Source: https://docs.unity.com/en-us/vivox-core/developer-guide/troubleshooting/vivox-client-sdk-logs

Implement the OnLog callback function and set it in the vx_sdk_config_t. This callback is invoked directly from Vivox SDK threads and must not block. Call this immediately after initializing the Vivox SDK.

```c
void OnLog(void *callback_handle, vx_log_level level, const char *source, const char *message)
{
    // The following line is for demonstration only. Because fprintf can block, do not call it from any SDK callback.
    fprintf(stderr, "%s: %s\n", vx_get_log_level_string(level), message);
}
. .
vx_sdk_config_t config;
vx_get_default_config3(&config, sizeof(config));
config.pf_logging_callback = OnLog;
vx_initialize3(&config, sizeof(config));
```

--------------------------------

### Improved cm find command examples

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

Examples for the `cm find` command have been updated with necessary double-quotes to ensure proper execution on macOS and Linux.

```console
# Example with double quotes for paths containing spaces
cm find --name "My Project" --path "/Users/username/Documents/Projects/My Project"
```

--------------------------------

### Initialize LevelPlay SDK

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/unity/migrate-from-unity-ads-to-levelplay

Initialize the LevelPlay SDK using your App Key. Ensure you receive the OnInitSuccess callback before creating ad objects. Handles initialization success and failure events.

```csharp
LevelPlay.OnInitSuccess += SdkInitializationCompletedEvent;
LevelPlay.OnInitFailed += SdkInitializationFailedEvent;
LevelPlay.Init("YOUR_APPKEY");

void SdkInitializationCompletedEvent(LevelPlayConfiguration config){
    Debug.Log($"[LevelPlaySample] Received SdkInitializationCompletedEvent with Config: {config}");
}

void SdkInitializationFailedEvent(LevelPlayInitError error){
    Debug.Log($"[LevelPlaySample] Received SdkInitializationFailedEvent with Error: {error}");	
}
```

--------------------------------

### Configure Ad Quality SDK Initialization Callback

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/integrate-ad-quality

Implement an ISAdQualityInitListener to receive callbacks for successful or failed Ad Quality SDK initialization. This requires initializing Ad Quality before LevelPlay if using both.

```java
ISAdQualityConfig.Builder builder = new ISAdQualityConfig.Builder().setAdQualityInitListener(new ISAdQualityInitListener() { 

    @Override 
    public void adQualitySdkInitSuccess() { 
        Log.d("AdQualityInitListener", "adQualitySdkInitSuccess"); 
    } 

    @Override 
    public void adQualitySdkInitFailed(ISAdQualityInitError error, String message) { 
        Log.d("AdQualityInitListener", "adQualitySdkInitFailed " + error + " message: " + message); 
    }
}); 

ISAdQualityConfig adQualityConfig = builder.build();
IronSourceAdQuality.getInstance().initialize(this, appKey, adQualityConfig);
```

--------------------------------

### Set Server Name

Source: https://docs.unity.com/en-us/multiplay-hosting-unreal/cpp-integration

Set the name of the game server. Example sets the name to "AwesomeServer".

```cpp
ServerQueryHandlerSubsystem->SetServerName(TEXT("AwesomeServer"));
```

--------------------------------

### Manually Start PlasticFS Executable

Source: https://docs.unity.com/en-us/unity-version-control/enable-dynamic-workspaces

Navigate to the UVCS client binaries directory and run the plasticfs.exe to manually enable dynamic workspaces.

```bash
plasticfs.exe
```

--------------------------------

### Archive One Revision Example

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/archive

Example of archiving a single revision of a file and storing it with a specified file prefix. Shows how to verify the archived file.

```bash
cm archive Assets/RoofTextures/Textures/Wooden_Roof_05.png --file=/Users/ruben/archive/battle
```

```bash
ls -al /Users/ruben/archive/battle* -rw-r--r--  1 ruben  staff  2220039 Nov  9 10:52 /Users/ruben/archive/battle-100280-167
```

--------------------------------

### Create Product View from Definition in C#

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/scene_sceneinterface

Creates a product view based on a provided ProductViewDefinition. No specific setup is mentioned.

```csharp
[HandleProcessCorruptedStateExceptions]
public uint CreateProductView(ProductViewDefinition definition)
```

--------------------------------

### Start Recording Viewer

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/view_functions

Use this function to record viewer activity to a specified file. Optional encoder settings can be provided.

```python
view.startRecording(filePath, viewer, encoderSettings=None)
```

--------------------------------

### Delete Mediation Group Request Body Example

Source: https://docs.unity.com/en-us/grow/levelplay/platform/api/groups

Example JSON payload for deleting mediation groups. Provide an array of group IDs to be removed.

```json
{
    "ids": [1458, 5769]
}
```

--------------------------------

### Provide SDK and Adapter Versions

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/build-custom-adapter

Implement methods to return the network SDK version and adapter version. It's recommended to use an API for the network SDK version for flexibility.

```java
@Nullable String getNetworkSDKVersion();
@NotNull String getAdapterVersion();
```

--------------------------------

### Mediation Group Update API URL Example

Source: https://docs.unity.com/en-us/grow/levelplay/platform/api/groups

This is an example of the request URL for updating mediation groups. Replace '{appKey}' with your actual application key.

```bash
https://platform.ironsrc.com/levelPlay/groups/v4/142401ac1/
```

--------------------------------

### Banner Bid Request Example

Source: https://docs.unity.com/en-us/grow/exchange/bid-requests

This is an example of a banner bid request. It specifies banner ad dimensions, attributes, and includes application and device information.

```json
{
  "id": "bcda7938-14eb-4a46-8dcb-bcd7587a964f",
  "imp": [
    {
      "id": "1",
      "banner": {
        "w": 320,
        "h": 50,
        "battr": [
          1,
          3,
          5,
          6,
          8,
          9,
          13
        ]
      },
      "pmp": {},
      "displaymanager": "unity sdk",
      "displaymanagerver": "3200",
      "tagid": "com.unity3d.ads.opstool-banner",
      "bidfloor": 3.95,
      "secure": 1
    }
  ],
  "app": {
    "id": "2aa377f91oo12398465d6af383",
    "name": "Example Game: Chapter Two",
    "publisher": {
      "id": "189857700"
    },
    "bundle": "com.devexample.thegamebundlename",
    "storeurl": "https://play.google.com/store/apps/details?id=com.devexample.thegamebundlename\u0026hl=en"
  },
  "device": {
    "ua": "Mozilla/5.0 (Linux; Android 9; Pixel Build/PQ3A.190705.001; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/75.0.3770.101 Mobile Safari/537.36",
    "geo": {
      "lat": 37.7958,
      "lon": -122.4203,
      "type": 2,
      "country": "USA",
      "region": "CA",
      "city": "San Francisco",
      "utcoffset": -480
    },
    "ip": "4.14.109.3",
    "devicetype": 4,
    "make": "Google",
    "model": "Pixel",
    "os": "android",
    "osv": "9.0",
    "hwv": "Google Pixel",
    "w": 320,
    "h": 50,
    "language": "en",
    "connectiontype": 2,
    "ifa": "d0a77d1b-e974-41f3-84c5-8fe75718ef2d"
  },
  "at": 1,
  "tmax": 500,
  "regs": {
    "ext": {}
  },
  "ext": {
    "sessionDepth": 1
  }
}
```

--------------------------------

### Example Import Process Output

Source: https://docs.unity.com/en-us/licensing-server/server-setup-lic

This output demonstrates the typical messages displayed in the Terminal or PowerShell window during the license archive import process, including validation, import status, and toolset selection.

```bash
Extracting files...Done
Validating archive content...Done
      LSD type import detected
Importing server license files...Done
Importing delegation file...Done
List of available toolsets on this server
  - [1] LicenseServer_3573461705080_1 [Unity Enterprise for Games(Floating)]
Enter the index number of the toolset that should be used by default: 1
```

--------------------------------

### Example JSON output for GetCatFact function

Source: https://docs.unity.com/en-us/cloud-code/modules/how-to-guides/external-services-integration

This is an example of the JSON output returned by the GetCatFact Cloud Code function, containing a random cat fact.

```json
{
    "output": {
        "fact": "The Amur leopard is one of the most endangered animals in the world.",
        "length": 68
    }
}
```

--------------------------------

### Branch Create Command Syntax

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/branch-create

This is the general syntax for creating a branch. Use '--changeset' or '--label' to specify the starting point, and '-c' or '-commentsfile' for comments.

```bash
cm branch | br [create | mk] <brspec> [--changeset=<csetspec> | --label=<lbspec>] [-c=<str_comment> | -commentsfile=<comments_file>]
```

--------------------------------

### Example Payload Retrieval Response (Plaintext)

Source: https://docs.unity.com/en-us/clanforge/legacy/allocations-payload

This is an example of a successful HTTP response when retrieving a payload. It includes the status code, headers, and the payload content itself.

```plaintext
HTTP/1.1 200 OK
Date: Mon, 26 Jul 2021 17:00:33 GMT
Content-Length: 23
Content-Type: text/plain; charset=utf-8
This can be anything.
```

--------------------------------

### Initialize FaceList with Size

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/cad_facelist

Creates a new instance of the FaceList class with a specified size.

```csharp
public FaceList(int size)
```

--------------------------------

### Example Server Locations Response

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-locations

This is an example of the JSON response you will receive when requesting server locations. It contains a list of location objects, each with an ID and name.

```json
{
    "locations": [
        {
            "locationid": <locationid>,
            "name": <name>
        },
        ...
    ]
}
```

--------------------------------

### Connect to Repository using UDT

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

Use the 'cm repo list' command with UDT or Secured UDT protocol to connect to a repository. This is experimental.

```console
# Regular connections:
> cm.exe repo list udt://192.168.221.142:7751

# Secured connections:
cm.exe repo list sudt://192.168.221.142:7751
```

--------------------------------

### Image Status Response Example

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-status

This is an example of a successful response when requesting image status. The 'fleets' object is included only if the 'detail' parameter was set to true.

```json
{
    "fleets": {
        <fleetid>: {
            "regions": {
                <regionid>: {
                    "name": <region_name>,
                    "pending_machines": <pending_machines>,
                    "completed_machines": <completed_machines>
                },
            },
            "pending_machines": <pending_machines>,
            "completed_machines": <completed_machines>
        },
        ...
    },
    "pending_machines": <pending_machines>,
    "completed_machines": <completed_machines>
}
```

--------------------------------

### Initialize RayHitList with size

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/scene_rayhitlist

Creates an empty RayHitList with a specified initial capacity. Useful for pre-allocating space.

```csharp
public RayHitList(int size)
```

--------------------------------

### Render Audio Start

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_requests_8h

Ensures a specific selected render device is functioning properly by playing a sound file. Can loop the audio playback.

```APIDOC
## POST /api/aux/render_audio/start

### Description
Ensure that a specific selected render device is functioning properly.

### Method
POST

### Endpoint
/api/aux/render_audio/start

### Parameters
#### Request Body
- **sound_file_path** (string) - Required - The local directory path to a monaural .wav or .au sound file.
- **loop** (integer) - Optional - Set to 1 to play the sound file in a continuous loop.

### Request Example
{
  "sound_file_path": "/path/to/sound.wav",
  "loop": 1
}

### Response
#### Success Response (200)
- **status** (string) - Indicates the success of the operation.

#### Response Example
{
  "status": "success"
}
```

--------------------------------

### OPUS Bitrate Configuration

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Set and get the bitrate for all OPUS encoders.

```APIDOC
## vx_opus_set_bit_rate

### Description
Set the bitrate for all OPUS encoders.

### Method
POST

### Endpoint
/vx_opus_set_bit_rate

### Parameters
#### Request Body
- **bits_per_second** (int) - Required - The desired bitrate in bits per second.

### Request Example
```json
{
  "bits_per_second": 64000
}
```

## vx_opus_get_bit_rate

### Description
Get the current OPUS bitrate.

### Method
GET

### Endpoint
/vx_opus_get_bit_rate

### Response
#### Success Response (200)
- **p_bits_per_second** (int*) - Pointer to an integer that will be updated with the current bitrate.

### Response Example
```json
{
  "p_bits_per_second": 64000
}
```
```

--------------------------------

### Initialize SDK and Launch Test Suite (Objective-C)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/ios/integration-test-suite

Initialize the LevelPlay SDK with the provided request builder and then launch the test suite upon successful initialization. Handle any initialization errors appropriately.

```objective-c
[LevelPlay setMetaDataWithKey:@"is_test_suite" value:@"enable"];
LPMInitRequestBuilder *requestBuilder = [[LPMInitRequestBuilder alloc] initWithAppKey:@"appKey"];
[requestBuilder withUserId:@"UserId"]; // optional

LPMInitRequest *initRequest = [requestBuilder build];
[LevelPlay initWithRequest:initRequest completion:^(LPMConfiguration *_Nullable config, NSError *_Nullable error) {
    if (error) {
        // Handle initialization error
    } else {
        // Initialization successful — launch test suite
        [LevelPlay launchTestSuite:self];
    }
}];
```

--------------------------------

### Install Unity Editor with Modules on macOS

Source: https://docs.unity.com/en-us/hub/hub-cli

Installs a new Unity Editor version along with specified modules on macOS using the Unity Hub CLI.

```shell
/Applications/Unity\ Hub.app/Contents/MacOS/Unity\ Hub -- --headless install --version 6000.3.7f1 --module android android-sdk-ndk-tools android-open-jdk
```

--------------------------------

### Create vx_req_aux_set_render_device

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/group__devices

Allocates and initializes a vx_req_aux_set_render_device object.

```c
VIVOXSDK_DLLEXPORT int vx_req_aux_set_render_device_create(
    vx_req_aux_set_render_device_t ** req
)
```

--------------------------------

### Initialize Unity Services and show PIPL consent flow

Source: https://docs.unity.com/en-us/analytics/privacy-and-consent/manage-data-privacy/sdk-compliance-opt-in

Initialize the Unity Services and then display the PIPL consent flow. Ensure you are using SDK version 5.0.0 or newer.

```csharp
async void Start()
{
   await UnityServices.InitializeAsync();
   
   ShowPIPLConsentFlow();
}
```

--------------------------------

### vx_req_aux_render_audio_start

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/structvx__req__aux__render__audio__start

Initiates audio rendering for a specified sound file on a given render device. Supports looping and optional account handle specification.

```APIDOC
## vx_req_aux_render_audio_start

### Description
Ensures that a specific selected render device is functioning properly by starting audio playback.

### Method
POST (Assumed, as it modifies state)

### Endpoint
/vx/aux/render/audio/start (Assumed)

### Parameters
#### Request Body
- **base** (vx_req_base_t) - Required - The common properties for all requests.
- **sound_file_path** (string) - Required - A local directory path name of a monaural .wav or .au sound file.
- **loop** (integer) - Optional - If set to 1, the sound system plays the file in a continuous loop until the "render audio stop" method is called. Defaults to 0.
- **path** (string) - Deprecated - Debug use only.
- **account_handle** (VX_HANDLE) - Optional - An optional parameter that specifies the account handle of the user whose render device will be used. If unset, the default account_handle is used.

### Request Example
```json
{
  "base": {},
  "sound_file_path": "/path/to/your/sound.wav",
  "loop": 1,
  "account_handle": null
}
```

### Response
#### Success Response (200)
- **base** (vx_resp_base_t) - The common properties for all responses.

#### Response Example
```json
{
  "base": {}
}
```
```

--------------------------------

### Access User Installation ID in Unity

Source: https://docs.unity.com/en-us/cloud/developer-data/access-install-id

Use this C# code to retrieve and log the user's installation ID. Ensure the `UnityEngine.Identifiers` namespace is imported.

```csharp
using UnityEngine.Identifiers;

string installationId = Identifiers.installationId;
Debug.Log($"Installation ID: {installationId}");
```

--------------------------------

### Initialize FilePathList with Size

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_filepathlist

Create a FilePathList with a specified initial size.

```csharp
public FilePathList(int size)
```

--------------------------------

### OPUS Bandwidth Configuration

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Set and get the bandwidth for all OPUS encoders.

```APIDOC
## vx_opus_set_bandwidth

### Description
Set the bandwidth for all OPUS encoders.

### Method
POST

### Endpoint
/vx_opus_set_bandwidth

### Parameters
#### Request Body
- **bandwidth** (int) - Required - The desired bandwidth.

### Request Example
```json
{
  "bandwidth": 4000
}
```

## vx_opus_get_bandwidth

### Description
Get the current OPUS bandwidth.

### Method
GET

### Endpoint
/vx_opus_get_bandwidth

### Response
#### Success Response (200)
- **p_bandwidth** (int*) - Pointer to an integer that will be updated with the current bandwidth.

### Response Example
```json
{
  "p_bandwidth": 4000
}
```
```

--------------------------------

### Install and Use Ruby Version with RVM

Source: https://docs.unity.com/en-us/build-automation/advanced-build-configuration/run-custom-scripts-during-the-build-process

Installs a specific Ruby version using RVM and executes commands with that version. This prevents system Ruby from being impacted.

```bash
#!/usr/bin/env bash

## Source profile
rvm install ruby-3.3.0
rvm ruby-3.3.0 do gem install fastlane
rvm ruby-3.3.0 do fastlane --help

exit 0
```

--------------------------------

### Launch Plastic GUI with Old Code Review Window

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/8

Use this command-line argument to launch the Plastic GUI application and display the old code review window instead of the new one.

```bash
plastic.exe --oldcodereview
```

--------------------------------

### Configure ReCap SDK Path in C#

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/io/import-recap

Configure the path to the ReCap SDK installation directory. Ensure Autodesk ReCap is installed with a valid license on the same machine.

```C#
pxz.Core.SetModuleProperty("IO", "RecapSDKPath", "*PATH_TO_RECAP_INSTALL*/bin/");
```

--------------------------------

### Launch Pixyz UI from Command Line

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/pixyzui/setup

Pass the path to the Pixyz SDK binaries as an argument to main.py to launch Pixyz UI from the command line.

```python
python main.py "../bin"
```

--------------------------------

### Configure ReCap SDK Path in Python

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/io/import-recap

Configure the path to the ReCap SDK installation directory. Ensure Autodesk ReCap is installed with a valid license on the same machine.

```Python
pxz.core.setModuleProperty("IO", "RecapSDKPath", "*PATH_TO_RECAP_INSTALL*/bin/")
```

--------------------------------

### GameUI Command Line Options

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

Utilize command-line options for custom client configuration files, specifying PlasticSCM servers, or custom cache servers.

```bash
* '--clientconf': Allows to specify a custom configuration file.

* '--server': Allows to specify a custom PlasticSCM server instead of the configured by default.

* '--cacheserver': Allows to specify a custom PlasticSCM cache server instead of the configured by default.
```

```bash
The usage of these parameters can be shown by tiping 'gameui.exe --help'.
```

--------------------------------

### Get Capture Devices

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_requests_8h

Returns a list of available audio capture devices. Similar to getting render devices, this list might not include all system-available devices.

```APIDOC
## GET /api/aux/capture_devices

### Description
Return a list of available audio capture devices.

### Method
GET

### Endpoint
/api/aux/capture_devices

### Parameters
None

### Request Example
None

### Response
#### Success Response (200)
- **devices** (array) - A list of available audio capture devices.

#### Response Example
{
  "devices": [
    {
      "name": "Capture Device Name 1",
      "specifier": "capture_device_specifier_1"
    },
    {
      "name": "Capture Device Name 2",
      "specifier": "capture_device_specifier_2"
    }
  ]
}
```

--------------------------------

### Get Help for a Partial Command

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/partial

Use '--usage' or '--help' flags with a specific partial command to get detailed information about its usage and options.

```bash
cm partial <command> --usage
```

```bash
cm partial <command> --help
```

--------------------------------

### Get All Player's Inventory Items

Source: https://docs.unity.com/en-us/economy/sdk/configuration

Gets all inventory items for the currently logged-in player. Requires the InventoryItemDefinition object obtained via GetInventoryItem or GetInventoryItems.

```C#
string itemID = "SWORD";
InventoryItemDefinition definition = EconomyService.Instance.Configuration.GetInventoryItem(itemID);
GetInventoryResult allThePlayersSwords = await definition.GetAllPlayersInventoryItemsAsync();
```

--------------------------------

### Initialize Unity Services and Fetch Remote Config

Source: https://docs.unity.com/en-us/game-overrides/reduce-ad-frequency

This C# script initializes Unity Services, signs in anonymously, and fetches configuration values from Remote Config. It sets up a default ad frequency and updates it based on fetched remote configurations. Attach this script to an empty GameObject in your scene.

```csharp
using Unity.RemoteConfig;
using Unity.Services.Authentication;
using Unity.Services.Core;
using UnityEngine;
public class UGS : MonoBehaviour
{

    public struct userAttributes { }
    public struct appAttributes { }

    public int adFrequency = 1; //Default is 1 ad on death

    async void Start()
    {

        await UnityServices.InitializeAsync();
        // remote config requires authentication for managing environment information
        if (!AuthenticationService.Instance.IsSignedIn)
        {
            await AuthenticationService.Instance.SignInAnonymouslyAsync();
        }
        ConfigManager.FetchCompleted += ConfigManager_FetchCompleted;
        ConfigManager.FetchConfigs(new userAttributes(), new appAttributes());
    }
   
    void ConfigManager_FetchCompleted(ConfigResponse configResponse)
    {

        switch (configResponse.requestOrigin)
        {
            case ConfigOrigin.Default:
                Debug.Log("Default values will be returned");
                break;
            case ConfigOrigin.Cached:
                Debug.Log("Cached values loaded");
                break;
            case ConfigOrigin.Remote:
                Debug.Log("Remote Values loaded");
                adFrequency = ConfigManager.appConfig.GetInt("adFrequency");
                break;
        }
    }
}
```

--------------------------------

### Get Player Balance for a Currency

Source: https://docs.unity.com/en-us/economy/sdk/configuration

Gets the balance for the currently signed-in player for a specific currency. Requires the CurrencyDefinition object obtained via GetCurrency or GetCurrencies.

```C#
string currencyID = "GOLD_BARS";
CurrencyDefinition goldCurrencyDefinition = EconomyService.Instance.Configuration.GetCurrency(currencyID);
PlayerBalance playersGoldBarBalance = await goldCurrencyDefinition.GetPlayerBalanceAsync();
```

--------------------------------

### Get Ruled Surface Definition

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/cad_functions

Retrieves the two defining curves of a ruled surface. This function is used to get the parameters that define a ruled surface in CAD.

```python
cad.getRuledSurfaceDefinition(ruledSurface) -> cad.Curve, cad.Curve
```

--------------------------------

### Initialize LevelPlay SDK in Kotlin

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/migrate-to-init-api

Implement callbacks for initialization success and failure. Call the LevelPlay init API using the appKey and user ID if relevant. This Kotlin example demonstrates LevelPlay SDK initialization.

```kotlin
val initRequest = LevelPlayInitRequest.Builder("AppKey")
        .withUserId("UserId")
        .build()

LevelPlay.init(context, initRequest, object : LevelPlayInitListener {
    override fun onInitFailed(error: LevelPlayInitError) {
        // Recommended to initialize again
    }
    override fun onInitSuccess(configuration: LevelPlayConfiguration) {
        // Create ad objects and load ads
    }
})
```

--------------------------------

### Create CA signed certificate on Windows

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/ssl/ssl-certificates

Generate .pvk and .cer files for a CA, then use them with `makecert` to create a server certificate, and finally combine into a .pfx file using `pvk2pfx`.

```bash
makecert -n "CN=My Company" -r -a sha1 -sv MyCompanyCA.pvk MyCompanyCA.cer
```

```bash
makecert -n "CN=TARDIS" -iv MyCompanyCA.pvk -ic MyCompanyCA.cer -sky exchange -a sha1 -pe -sv
        "UvcsServerTardis.pvk" UvcsServerTardis.cer
```

```bash
pvk2pfx -pvk "UvcsServerTardis.pvk" -spc "UvcsServerTardis.cer" -pfx "UvscServerTardis.pfx" -pi <password>
```

--------------------------------

### Get Import Formats

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/io_functions

Provides a list of format names and their extensions that can be imported into Pixyz. Set `forRuntimeOS` to `True` to get formats compatible with the current OS.

```python
io.getImportFormats(forRuntimeOS=True)
```

--------------------------------

### Check Ad Readiness and Placement Cap - Unity

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/react/rewarded-ads-integration

Before showing an ad, use these asynchronous APIs to ensure the ad is ready to display and that the specified placement is not capped. Both APIs must resolve to true for the ad to be shown.

```javascript
// Check that ad is ready and that the placement is not capped (both APIs are async)
const isReady = await rewardedAd.isAdReady();
const isPlacementCapped = await LevelPlayRewardedAd.isPlacementCapped('YOUR_PLACEMENT');
if (isReady && !isPlacementCapped) {
  await rewardedAd.showAd('YOUR_PLACEMENT');
}
```

--------------------------------

### Example Plastic Link URL

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/10

This is an example of a Plastic Link URL format. These links can be used to share diffs, files, and code reviews from Plastic repositories.

```text
plastic://myorg.cloud/repos/toolsrepo/changesets/50/diff
```

--------------------------------

### Display Hub CLI Help

Source: https://docs.unity.com/en-us/hub/hub-cli

Use this command to view all available CLI commands and their arguments. Note the different flag syntax for Linux compared to other operating systems.

```shell
/Applications/Unity\ Hub.app/Contents/MacOS/Unity\ Hub -- --headless help
```

```shell
C:\Program Files\Unity Hub> "Unity Hub.exe" -- --headless help
```

```shell
~/Applications/Unity\ Hub.AppImage --headless help
```

--------------------------------

### Plastic Triggers Repository Filtering Examples

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/10

Examples of using wildcards in Plastic Triggers for repository filtering. These patterns can apply triggers to single or multiple repositories.

```text
rep:*
```

```text
rep:website_intranet
```

```text
rep:website*
```

```text
rep:*web*
```

```text
rep:*intranet
```

--------------------------------

### Create Instance with CPM Pricing

Source: https://docs.unity.com/en-us/grow/levelplay/platform/api/instances-api-v4

Use this JSON body to create a new ad instance with specific CPM pricing for different countries and ad types. Ensure 'appKey' is provided.

```json
{
  "appKey": "d11a21a5",
  "configurations": {
    "ironSource": {
      "interstitial": [
        {
          "instanceName": "low_interstitial",
          "status": "active",
          "pricing": [
            {
              "country": [
                "FR",
                "DE"
              ],
              "eCPM": 3
            }
          ],
          "pricingType": "eCPM"
        },
        {
          "instanceName": "high_interstitial",
          "status": "active",
          "pricing": [
            {
              "country": [
                "IL",
                "US"
              ],
              "eCPM": 20
            }
          ]
        }
      ]
    },
    "adColony": {
      "rewardedVideo": [
        {
          "instanceName": "adcolony_rv",
          "status": "active",
          "zoneId": 102030,
          "rate": 10
        }
      ]
    }
  }
}
```

--------------------------------

### Initialize Tapjoy SDK in Swift

Source: https://docs.unity.com/en-us/grow/offerwall/ios/introduction/manual-integration

Integrate this code into your `application(_:didFinishLaunchingWithOptions:)` method. It's recommended to set the user ID using connect flags for the AppLaunch placement. Debug mode should be enabled only during development.

```Swift
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {

    NotificationCenter.default.addObserver(self, selector: #selector(AppDelegate.tjcConnectSuccess(notif:)), name: NSNotification.Name(rawValue: TJC_CONNECT_SUCCESS), object: nil)
    
    NotificationCenter.default.addObserver(self, selector: #selector(AppDelegate.tjcConnectFail(notif:)), name: NSNotification.Name(rawValue: TJC_CONNECT_FAILED), object: nil)

    NotificationCenter.default.addObserver(self, selector: #selector(AppDelegate.tjcConnectWarning(notif:)), name: NSNotification.Name(rawValue: TJC_CONNECT_WARNING), object: nil)

    //Turn on Tapjoy debug mode
    Tapjoy.loggingLevel = .debug //Only enable debug mode for development. Disable it before publishing your app.
    
    //If you are using Self-Managed currency, you need to set a user ID using the connect flags.
    let connectFlags = [TJC_OPTION_USER_ID : "<USER_ID_HERE>"]
    Tapjoy.connect("SDK_KEY_GOES_HERE", options: connectFlags)
    
    //If you are not using connect flags, you can omit them
    Tapjoy.connect("SDK_KEY_GOES_HERE")
    
    return true
}
```

--------------------------------

### Example Branch Naming for JIRA Task

Source: https://docs.unity.com/en-us/unity-version-control/vcs-plugins/issue-tracking/jira/configure-jira

This example demonstrates how to name a UVCS branch to link it to a specific JIRA issue (VCS-1) using a 'task' prefix.

```text
task_VCS-1
```

--------------------------------

### Provide SDK and Adapter Versions (Objective-C)

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/flutter/build-custom-adapter-ios

Implement methods to return the network SDK version and adapter version in Objective-C. Using a method for SDK version is recommended for flexibility.

```objective-c
- (NSString *) networkSDKVersion {
   return [ALSdk version];
}
- (NSString *) adapterVersion {
   return kAdapterVersion;
}
```

--------------------------------

### Integer Variable Management

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Functions for getting and setting integer variables.

```APIDOC
## GET /api/variables/int/{var_name}

### Description
Retrieves the integer value of a specified variable.

### Method
GET

### Endpoint
/api/variables/int/{var_name}

### Parameters
#### Path Parameters
- **var_name** (string) - Required - The name of the integer variable.

### Request Example
None

### Response
#### Success Response (200)
- **value** (int) - The integer value of the variable.

#### Response Example
```json
{
  "value": 100
}
```

## POST /api/variables/int/{var_name}

### Description
Sets the integer value of a specified variable.

### Method
POST

### Endpoint
/api/variables/int/{var_name}

### Parameters
#### Path Parameters
- **var_name** (string) - Required - The name of the integer variable.

#### Request Body
- **value** (int) - Required - The integer value to set.

### Request Example
```json
{
  "value": 100
}
```

### Response
#### Success Response (200)
- **status** (string) - Indicates success or failure.

#### Response Example
```json
{
  "status": "success"
}
```
```

--------------------------------

### Deploy Economy Resources

Source: https://docs.unity.com/en-us/economy/write-configuration/cli

Promote local Economy resources to the remote environment and publish them. Resources must be deployed to be available to the game client.

```bash
ugs deploy <path-to-economy-file> <path-to-economy-file>
```

```bash
ugs deploy <path-to-directory>
```

--------------------------------

### GitSync Error Output Example

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/6

Example of the new output when GitSync fails to push remote git references. Errors are now correctly shown by the command line.

```text
Failed to push some refs:
- refs/heads/master -> branch is currently checked out
```

--------------------------------

### Get SDK Version Info

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Retrieve basic version information for the Vivox SDK.

```cpp
VIVOXSDK_DLLEXPORT const char * vx_get_sdk_version_info(
    void 
)
```

--------------------------------

### Unity Licensing Server Administrator Credentials Prompt

Source: https://docs.unity.com/en-us/licensing-server/server-setup-cfg-v2

Prompts during Unity Licensing Server setup for creating administrator credentials.

```bash
Credentials are required to access the administration dashboard and API.
The administrator username is "admin".
Create a password for "admin" (8-12 characters):  ********
Confirm the password for "admin":  ********
```

--------------------------------

### JIRA Keyword-Status Mapping Example

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/6

Example of keyword-status mappings for JIRA integration. If a changeset comment contains '[FIXED]', the issue status changes to 'Ready for QA'.

```text
[FIXED]-Ready for QA|[WONTFIX]-Done
```

--------------------------------

### Create Changelist from Files

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/changelist

Creates a new changelist where the name and description are read from separate files.

```bash
cm changelist create --namefile="name.txt" --descriptionfile="desc.txt"
```

--------------------------------

### Start Recording Viewer

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/view_viewinterface

Initiates video recording for a specified viewer to a file. Optional encoder settings can be provided.

```csharp
[HandleProcessCorruptedStateExceptions]
public void StartRecording(string filePath, int viewer, EncoderSettings encoderSettings = null)
```

--------------------------------

### Unarchive (Restore) Revision Example

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/archive

Example of restoring an archived revision. This involves configuring the external data path in externaldata.conf and then using the --restore option.

```bash
vi /Users/ruben/.plastic4/externaldata.conf /Users/ruben/archive
```

```bash
cm archive Assets/RoofTextures/Textures/Wooden_Roof_05.png --restore
```

--------------------------------

### Example Message with Content and Attachment

Source: https://docs.unity.com/en-us/services/solutions/in-game-mailbox

This JSON demonstrates a message with specific content, an attachment identifier, and a defined expiration time. This example corresponds to the 'MESSAGE_005' key.

```text
{
"title": "Got new Use Case sample ideas?",
"content": "We'd love to hear your suggestions
about what kind of new samples you would like
us to deliver. Let us know at headstart@unity3d.com",
"attachment": "MESSAGE_005_GIFT",
"expiration": "0.00:10:00.00"
}
```

--------------------------------

### Create a new build using curl

Source: https://docs.unity.com/en-us/multiplay-hosting/guides/api-build-workflow

Use this command to create a new build. Ensure you replace placeholders like {projectId} and {environmentId} with your specific values. Authentication is handled via Basic authentication with service account credentials.

```bash
curl -X POST -H "Authorization: Basic <SERVICE_ACCOUNT_CREDENTIALS>" -H "Content-Type: application/json" \
    -d '{"buildName":"Dev Build A", "ccd": {}, "osFamily": "LINUX"}' \
    https://services.api.unity.com/multiplay/builds/v1/projects/{projectId}/environments/{environmentId}/builds
```

--------------------------------

### Get SDK Version Info

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Retrieves a string containing basic version information for the Vivox SDK.

```c
const char *vx_get_sdk_version_info(void);
```

--------------------------------

### Example Ticket and Player Data for 20 Teams Match

Source: https://docs.unity.com/en-us/matchmaker/rules-sample

Provides an example of ticket and player data compatible with the 20 teams of 3 players configuration.

```json
{
    "queueName": "Default",
    "attributes": {},
    "players": [
        {
            "id": "91isf42z1n95lpv52upxrjc4ttvj",
            "customData": {}
        }
    ]
}
```

--------------------------------

### Unity Default Launch Parameters

Source: https://docs.unity.com/en-us/multiplay-hosting/concepts/launch-parameters

Use these parameters for Unity games running in batch mode without graphics. Ensure the port and log directory are correctly configured using build variables.

```plaintext
-nographics -batchmode -port $$port$$ -logFile $$log_dir$$/Engine.log
```

--------------------------------

### 1v1 Ticket and Player Data Example

Source: https://docs.unity.com/en-us/matchmaker/rules-sample

Example JSON structure for ticket and player data, used when creating a match. Includes player ID and custom data.

```json
{
    "queueName": "Default",
    "attributes": {},
    "players": [{
        "id": "swsqozxo6qxm9fmm38khh3tddv35",
        "customData": {}
    }]
}
```

--------------------------------

### Checkout files with Unity Version Control CLI

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/checkout

Use this command to mark files as ready to modify. Specify items to be checked out, or use '.' for the current directory. Use '-R' for recursive checkout.

```bash
cm checkout | co [<item_path>[ ...]] [-R | -r | --recursive] [--format=<str_format>] [--errorformat=<str_format>] [--resultformat=<str_format>] [--silent] [--symlink] [--ignorefailed] [--machinereadable [--startlineseparator=<sep>] [--endlineseparator=<sep>] [--fieldseparator=<sep>]
```

--------------------------------

### Path Retrieval

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Function to get the path for specific system resources.

```APIDOC
## Path Retrieval

### Description
Retrieves system paths based on a provided ID.

### Enumerations

- `vx_path_id`:
  - `path_cache_folder`: Identifier for the cache folder path.

### Functions

- `vx_get_path(unsigned int path_id)`: Returns the system path associated with the given `path_id`.
```

--------------------------------

### App Suppression cURL Example

Source: https://docs.unity.com/en-us/grow/offerwall/user-acquisition/api/audience-api-overview

Example of how to make an app suppression request using cURL. Ensure you replace placeholders with your actual token and file path.

```bash
curl --header "Authorization: Bearer YOUR-TOKEN" --request POST --form devices=@/path/to/device_list.csv "https://api.tapjoy.com/v4/audiences?account_id=497670f6-a152-4bdd-a717-dbe7f7635dc7&app_id=6881899b-9c55-4d83-9afc-552f880289d4&description=LIST-DESCRIPTION&list_type=app_suppression&name=LIST-NAME&offer_id=" 
```

--------------------------------

### OPUS Complexity Configuration

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Set and get the complexity for all OPUS encoders.

```APIDOC
## vx_opus_set_complexity

### Description
Set the complexity for all OPUS encoders.

### Method
POST

### Endpoint
/vx_opus_set_complexity

### Parameters
#### Request Body
- **complexity** (int) - Required - The desired complexity level.

### Request Example
```json
{
  "complexity": 10
}
```

## vx_opus_get_complexity

### Description
Get the current OPUS complexity.

### Method
GET

### Endpoint
/vx_opus_get_complexity

### Response
#### Success Response (200)
- **p_complexity** (int*) - Pointer to an integer that will be updated with the current complexity.

### Response Example
```json
{
  "p_complexity": 10
}
```
```

--------------------------------

### VAST Bid Request Example

Source: https://docs.unity.com/en-us/grow/exchange/bid-requests

This is an example of a VAST bid request. It includes details about the ad placement, video specifications, application information, and device details.

```json
{
	"id": "bcaIDT1Nbv0zU8mn9tXQ6j", 
	"at": 1,
	"tmax": 200,
	"source": {
		"pchain": "12abcd3456789:12345"
		"omidpn": "Unity3d",
		"omidpv": "1.3.0"
	},
	"imp": [{
		"id": "1", 
		"secure": 1,
		"instl": 1,
		"tagid": "com.unity3d.ads.example-vast",
		"bidfloor": 3.95,
		"video": {
			"mimes": [
				"video/mp4","application/javascript" 
			],
			"minduration": 5,
			"maxduration": 30,
			"placement": 5
			"protocols": [2, 3, 5, 6],
			"pos": 7,
			"battr": [1, 3, 5, 8, 9, 13],
			"w": 1024,
			"h": 600,
			"api": [7],
			"companiontype": [1,2,3]
		}
		"displaymanager": "unity sdk",
		"displaymanagerver": "4001",
                "ext": {
    	          "skadn": {
                    "ext": {
          	        "ask": 1
                    },
                    "skoverlay": 1,
                      "productpage": 1
    	          }
              }
	  }], 
	"app": {
		"id": "d01234idnfld234ier6c70930a",
		"name": "Build A Town: All the games",
		"publisher": {
		  "id": "11972001l"
		},
		"bundle": "12312312399",
		"storeurl": "https://apps.apple.com/us/app/build-a-town/id12312312399" 
	},
	"device": {
		"ifa": "ab12c456-78de-90f1-ghi2-j3kl4567890m", 
		"make": "Apple", 
		"model": "iPhone", 
		"ua": "Mozilla/5.0 (iPhone; CPU iPhone OS 10_0 like Mac OS X) AppleWebKit/602.1.50 (KHTML, like Gecko) Mobile/14A345", 
		"os": "ios", 
		"ip": "12.34.5.6", 
		"devicetype": 4, 
		"carrier": "Apple", 
		"osv": "10.1", 
		"hwv": "iphone6", 
		"geo": {
			"lat": 55.5492, 
			"lon": 59.0456, 
			"country": "USA", 
			"city": "San Francisco", 
			"type": 2, 
			"utcoffset": 180 
		},
		"connectiontype": 3, 
		"language": "en", 
		"h": 1184, 
		"w": 768 
	},
	"regs": {
		"coppa": 0 
	}
}
```

--------------------------------

### Configure Linux Open Context Menu

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/9

Customize the 'Open' context menu for files in Linux by creating an 'openwith.conf' file. Specify menu text, shortcut, executable path, and arguments.

```console
[gedit|ControlMask+G] "/usr/bin/gedit" @file
```

```console
[vim|ShiftMask+V] "/usr/bin/vim" @file
```

--------------------------------

### Open Measurement API Example

Source: https://docs.unity.com/en-us/grow/exchange/bid-responses

Example indicating Open Measurement (OM) support via the API framework. A value of 7 signifies OM support.

```json
"api":7
```

--------------------------------

### CPU and Memory Monitoring

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

APIs for starting, stopping, and configuring CPU monitoring and memory dumping.

```APIDOC
## CPU and Memory Monitoring

### Description
Functions to manage CPU monitoring and memory dump intervals.

### Functions

- `vx_get_dump_memory_interval(void)`: Retrieves the interval for memory dumping.
- `vx_cpumonitor_start(int interval, int report_interval)`: Starts the CPU monitor with specified intervals.
- `vx_cpumonitor_stop(void)`: Stops the CPU monitor.
- `vx_cpumonitor_start_eater(int nthreads, int priority)`: Starts a CPU 'eater' thread for stress testing.
- `vx_cpumonitor_stop_eater(void)`: Stops the CPU 'eater' thread.
```

--------------------------------

### Get SDK Extended Version Info

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Retrieve extended version details for the Vivox SDK.

```cpp
VIVOXSDK_DLLEXPORT const char * vx_get_sdk_version_info_ex(
    void 
)
```

--------------------------------

### GET /levelPlay/network/instances/v4/

Source: https://docs.unity.com/en-us/grow/levelplay/platform/api/instances-api-v4

Retrieves a list of all application instances, both bidding and non-bidding. Requires an appKey as a query parameter.

```APIDOC
## GET /levelPlay/network/instances/v4/

### Description
Get a list of all the application instances, bidding and non bidding.

### Method
GET

### Endpoint
https://platform.ironsrc.com/levelPlay/network/instances/v4/

### Query Parameters
- **appKey** (String) - Required - application key (as seen on the platform)

### Request Example URL
https://platform.ironsrc.com/levelPlay/network/instances/v4/?appKey=142401ac1

### Response Parameters
- **instanceId** (Integer) - Unique instance ID
- **instanceName** (String) - The instance name
- **adUnit** (String) - The ad unit type per instance (rewardedVideo, interstitial, or banner)
- **adFormat** (String) - Rewarded, interstitial, banner or native
- **networkName** (String) - The ad network the instance belongs to
- **appConfig1** (String) - Application-level configuration field 1
- **appConfig2** (String) - Application-level configuration field 2
- **instanceConfig1** (String) - Instance-level configuration field 1
- **instanceConfig2** (String) - Instance-level configuration field 2
- **isBidder** (Boolean) - Indicates if the instance is a bidder instance (true or false)
- **groups** (Array of Integers) - An array of group ids, as sent in the LevelPlay Groups API
- **isLive** (Boolean) - Instance status can be active or inactive
- **rate** (Number) - Instance level rate (if defined)

### Response Example
```json
[
  {
    "instanceId": 1072562,
    "instanceName": "",
    "adUnit": "rewardedVideo",
    "adFormat": "rewarded",
    "networkName": "unityAds",
    "appConfig1": "qtr",
    "instanceConfig1": "trb",
    "isBidder": true,
    "groups": [101663],
    "isLive": true
  },
  {
    "instanceId": 1014428,
    "instanceName": "Default",
    "adUnit": "interstitial",
    "adFormat": "interstitial",
    "networkName": "unityAds",
    "appConfig1": "qertb",
    "instanceConfig1": "qtrb",
    "isBidder": false,
    "groups": [101664],
    "isLive": true,
    "rate": 25
  },
  {
    "instanceId": 1845809,
    "instanceName": "Default",
    "adUnit": "rewardedVideo",
    "adFormat": "rewarded",
    "networkName": "adManager",
    "appConfig1": "bqw",
    "instanceConfig1": "qqr",
    "isBidder": false,
    "groups": [101663 ],
    "isLive": true,
    "rate": 4
  }
]
```
```

--------------------------------

### Pagination Response Example

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/assets-api

Example JSON response for a paginated asset retrieval. It includes a subset of assets based on `resultsBulkSize` and the `requestId` needed for subsequent requests.

```json
{
	"assets": [{
		"id": 200305,
		"type": "video",
		"titleId": 501567,
		"orientation": "all",
		"source": "none",
		"duration": 30
	}, {
		"id": 200304,
		"type": "image",
		"titleId": 501567,
		"orientation": "all",
		"source": "none",
		"duration": null
	}],
	"totalResultsCount": 6,
	"requestId": "MjA1MzUzLjIwMDMwMy40LjM1OTY="
}
```

--------------------------------

### Legacy Initialization Flow with Consent Check

Source: https://docs.unity.com/en-us/analytics/sdks-and-apis/sdk5-migration-guide

This code demonstrates the legacy initialization flow where the SDK checks for required consents and prompts the user if necessary. Prior to SDK v5.0.0, this flow required internet connectivity for location lookup.

```csharp
await UnityServices.InitializeAsync();
List<string> requiredConsents = await AnalyticsService.Instance.CheckForRequiredConsents();

if (consents.Count > 0)
{
	// Show UI element asking the user for their consent //

	bool userGaveConsent = ...

	foreach (string legislationIdentifier in requiredConsents)
	{
		AnalyticsService.Instance.ProvideOptInConsent(identifier, userGaveConsent);
	}
}
```

--------------------------------

### Campaign Bid Response Example

Source: https://docs.unity.com/en-us/grow/is-ads/user-acquisition/apis/bidding-api

Example JSON response structure for bid data, including default bids, country-specific bids, and country-application specific bids.

```JSON
{
    "bids": [
  {
            "bid": 0.1
        },
        {
            "country": "US",
            "bid": 0.25
        },
        {
            "country": "US",
            "applicationId": 2222,
            "bid": 0.18
        },       
        {
            "country": "CA",
            "applicationId": 1212,
            "bid": 0.35
        }
    ]
   "totalResultsCount": 30043,
   "requestId": "MjU5NTY1Li41LjM1MDgwOA=="
}
```

--------------------------------

### Get Default SDK Configuration

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Retrieves the default configuration for the Vivox SDK. This should be called before initializing the SDK with vx_initialize3().

```cpp
VIVOXSDK_DLLEXPORT int vx_get_default_config3(
    vx_sdk_config_t * config,
    size_t config_size
)
```

--------------------------------

### Initialize Network SDK

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/android/build-custom-adapter

Implement the init API in the base adapter to handle SDK initialization. Call the initialization callbacks to indicate success or failure. The AdData parameter contains publisher-provided configuration.

```java
void init(@NotNull AdData adData, @NotNull Context context, @Nullable NetworkInitializationListener listener)
{
   ...
   if (init-success-condition) {
      // Initialization completed successfully
      listener.onInitSuccess();
   } else {
     // Initialization failed
     listener.onInitFailed(AdapterErrors.ADAPTER_ERROR_MISSING_PARAMS, error);
   }
}
```

--------------------------------

### Standard API Authentication Header Example

Source: https://docs.unity.com/en-us/grow/is-ads/monetization/apis/authentication

This is an example of the Authorization header for Standard API authentication. It uses a base64 encoded string of 'username:secret key'.

```text
Basic UG9wY2FwOjI3MGYwODRirrxNmM0YTliNmUyMmFkMjRkOTA1ZGYz
```

--------------------------------

### VIVOX_SDK_SESSION_GET_LOCAL_AUDIO_INFO_OBSOLETE Macro

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Marks the session get local audio info function as obsolete in the Vivox SDK.

```cpp
#define VIVOX_SDK_SESSION_GET_LOCAL_AUDIO_INFO_OBSOLETE 1
```

--------------------------------

### Example Push Message Format

Source: https://docs.unity.com/en-us/cloud-code/triggers/tutorials/use-cases/happy-new-year

This is an example of a push message received by the subscription. It includes details like message data, timestamp, message content, and identifiers.

```json
Got project subscription Message:{
  "data_base64": <BASE64-ENCODED-DATA>,
  "time": "2023-09-27T16:01:46.468321794Z",
  "message": "Happy new year!",
  "specversion": "1.0",
  "id": <ID>,
  "source": "https://cloud-code.service.api.unity.com",
  "type": "com.unity.services.cloud-code.push.v1",
  "projectid": <PROJECT-ID>,
  "environmentid": <ENVIRONMENT-ID>,
  "correlationid": <CORRELATION-ID>,
  "messagetype": "announcement",
}
```

--------------------------------

### Example Unreserve Server API Response

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/unreserve

This is an example of a successful response from the unreserve server API. The 'success' field indicates the status, and 'uuid' is the ID of the allocation.

```json
{
    "success": <status>,
    "messages": [],
    "uuid": <uuid>
}
```

--------------------------------

### Create workspace with default repository

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

When creating a workspace with `cm wk mk`, a default repository is selected if none is specified. The command now fails if a non-existent repository is provided, rather than silently falling back.

```console
> cm wk mk Project ./Project ProjectTYPO@thecompany@cloud
The specified repository couldn't be found: ProjectTYPO@thecompany@cloud.

> cm wk mk Project ./Project Project@thecompany@cloud
Workspace Project has been correctly created
```

--------------------------------

### Example Server Stop Response

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-stop

Example JSON response indicating the status of the server stop action. The `serverid` in the response will match the ID of the server that was targeted.

```json
{
    "action": "stop",
    "success": true,
    "server": {
        "serverid": <serverid>
    }
}
```

--------------------------------

### Initialize Vivox SDK

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Initializes the Vivox SDK. This function must be called before any other SDK functions. Ensure proper uninitialization using vx_uninitialize.

```c
int vx_initialize(void);
```

--------------------------------

### Start CPU Monitor

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Initiates the dumping of CPU load information to logcat. Recommended sampling interval is 1000ms and reporting interval is 5000ms. This function is specific to the Android platform.

```cpp
VIVOXSDK_DLLEXPORT int vx_cpumonitor_start(
    int interval,
    int report_interval
)
```

--------------------------------

### Example Response for Image Update Retry

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/image-update-retry

This is an example of a successful response when retrying an image update job. It includes details about the job's status and progress.

```json
{
    "updateid": <updateid>,
    "jobcreated": <jobcreated>,
    "joberror": <joberror>,
    "jobeta": <jobeta>,
    "jobfailed": <jobfailed>,
    "jobprogress": <jobprogress>,
    "jobstart": <jobstart>,
    "jobstateid": <jobstateid>,
    "jobstatename": <jobstatename>,
    "jobupdated": <jobupdated>
}
```

--------------------------------

### Sample Command Line for Trigger Creation

Source: https://docs.unity.com/en-us/unity-version-control/triggers/concepts/detailed-trigger-reference

Use this command to create a new trigger for the checkin operation. Specify the trigger name, the script to execute, and the path to the script.

```text
cm trigger create checkin-before "checkstyle" "c:\tmp\triggers\checkin-checkstyle.bat"
Trigger created on position 1.
```

--------------------------------

### Construct Kick from Channel Access Token

Source: https://docs.unity.com/en-us/vivox-core/server-to-server-api-reference/control-active-channels-api/kick-all-users-from-channel

This example shows how to construct an access token for kicking users from a channel. It requires specific parameters like issuer, expiration time, and channel URI.

```plaintext
e30.eyJ2eGkiOjEsImYiOiJzaXA6YmxpbmRtZWxvbi1BcHBOYW1lLWRldi1BZG1pbkBtdDFzLnZpdm94LmNvbSIsImlzcyI6ImJsaW5kbWVsb24tQXBwTmFtZS1kZXYiLCJ2eGEiOiJraWNrIiwidCI6InNpcDpjb25mY3RsLWctYmxpbmRtZWxvbi1BcHBOYW1lLWRldi50aGUtY2hhbm5lbEBtdDFzLnZpdm94LmNvbSIsImV4cCI6MTYwMDM0OTQwMH0.t-m7FvU9VnRVR3LdVjIOW-jJBj3rML_OBqUO2PKZ0Ms
```

--------------------------------

### Get Log File Path

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Retrieve the path to the SDK's log file. Note that file logging is not supported on all platforms.

```cpp
VIVOXSDK_DLLEXPORT char * vx_get_log_file_path(
    void 
)
```

--------------------------------

### Get System Statistics

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Retrieves statistics related to Vivox SDK's internal system performance.

```cpp
VIVOXSDK_DLLEXPORT int vx_get_system_stats(
    vx_system_stats_t * system_stats
)
```

--------------------------------

### Stop Plastic SCM Service (Linux - Installation Directory)

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-on-prem/start-stop-restart-server

Command to stop the Plastic SCM service using the script located in the server installation directory on Linux.

```text
/opt/plasticscm5/server/plasticsd stop
```

--------------------------------

### Add PubMatic Adapter with CocoaPods

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/ios/networks/guides/pubmatic

Use this line in your Podfile to integrate the PubMatic adapter with LevelPlay. Run 'pod install --repo-update' to install the adapter and SDK.

```ruby
pod 'LevelPlayPubMaticAdapter', '5.0.0.0'
```

--------------------------------

### Request URL for App Creation

Source: https://docs.unity.com/en-us/grow/is-ads/monetization/apis/application

Example of a complete request URL for creating an app.

```text
https://platform.ironsrc.com/partners/publisher/applications/v6?
```

--------------------------------

### Install Pixyz Python SDK without UI frontend

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/manual/installation/python

Install the Pixyz Python SDK without the UI frontend dependencies. This is useful if you only need the Python API.

```bash
pip install pxz --no-deps --extra-index-url https://unity3ddist.jfrog.io/artifactory/api/pypi/pixyz-pypi-prod-local/simple
```

--------------------------------

### Account Chat History Get Last Read

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_requests_8h

Get the last read message from a specified channel. The last read message is updated when a user disconnects from a channel.

```APIDOC
## GET /websites/unity_en-us/account/chat_history/last_read

### Description
Get the last read message from a specified channel.

### Method
GET

### Endpoint
/websites/unity_en-us/account/chat_history/last_read

### Parameters
#### Query Parameters
- **channel_id** (string) - Required - The ID of the channel.

### Request Example
None

### Response
#### Success Response (200)
- **message_id** (string) - The ID of the last read message.
- **timestamp** (integer) - The timestamp when the message was read.

#### Response Example
{
  "message_id": "msg222",
  "timestamp": 1678972800
}
```

--------------------------------

### Initialize and Sign In

Source: https://docs.unity.com/en-us/cloud-save/tutorials/unity-sdk-sample

Initializes Unity Services and signs the user in anonymously. This is a prerequisite for using Cloud Save.

```csharp
await UnityServices.InitializeAsync();
await AuthenticationService.Instance.SignInAnonymouslyAsync();
```

--------------------------------

### Get SDK Path

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Retrieve a specific SDK path using `vx_get_path` by providing a path ID. The returned buffer must be freed using `vx_free`.

```cpp
VIVOXSDK_DLLEXPORT char * vx_get_path(
    unsigned int path_id
)
```

--------------------------------

### Memory and CPU Monitoring API

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

APIs for monitoring memory usage and CPU load, including starting, stopping, and configuring monitoring intervals.

```APIDOC
## GET vx_get_dump_memory_interval

### Description
Get the current period of the Memory Usage information dumping to logcat.

### Method
GET

### Endpoint
/vx_get_dump_memory_interval

### Parameters
None

### Response
#### Success Response (200)
- **int** - The current memory dump interval in seconds.

### Response Example
```json
{
  "memory_dump_interval": 60
}
```

## POST vx_cpumonitor_start

### Description
Start the CPU load information dumping to logcat.

### Method
POST

### Endpoint
/vx_cpumonitor_start

### Parameters
#### Query Parameters
- **interval** (int) - Required - The interval in seconds for CPU load monitoring.
- **report_interval** (int) - Required - The interval in seconds for reporting CPU load.

### Request Example
```json
{
  "interval": 10,
  "report_interval": 30
}
```

### Response
#### Success Response (200)
- **int** - 0 on success, non-zero on failure.

### Response Example
```json
{
  "status": 0
}
```

## POST vx_cpumonitor_stop

### Description
Stop the CPU load information dumping to logcat.

### Method
POST

### Endpoint
/vx_cpumonitor_stop

### Parameters
None

### Response
#### Success Response (200)
- **int** - 0 on success, non-zero on failure.

### Response Example
```json
{
  "status": 0
}
```

## POST vx_cpumonitor_start_eater

### Description
Start the requested number of tight loop threads with the requested priority.

### Method
POST

### Endpoint
/vx_cpumonitor_start_eater

### Parameters
#### Query Parameters
- **nthreads** (int) - Required - The number of threads to start.
- **priority** (int) - Required - The priority for the threads.

### Request Example
```json
{
  "nthreads": 2,
  "priority": 10
}
```

### Response
#### Success Response (200)
- **int** - 0 on success, non-zero on failure.

### Response Example
```json
{
  "status": 0
}
```

## POST vx_cpumonitor_stop_eater

### Description
Stop all the CPU eater threads started with vx_cpumonitor_start_eater() call.

### Method
POST

### Endpoint
/vx_cpumonitor_stop_eater

### Parameters
None

### Response
#### Success Response (200)
- **int** - 0 on success, non-zero on failure.

### Response Example
```json
{
  "status": 0
}
```
```

--------------------------------

### Initialize OpenShellList with uint Array

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/cad_openshelllist

Creates a new instance of the OpenShellList class, initializing it with a provided array of uint values.

```csharp
public OpenShellList(uint[] tab)
```

--------------------------------

### Get Available Capture Devices

Source: https://docs.unity.com/en-us/vivox-core/developer-guide/in-game-audio-control/in-game-audio-device-selection

Use this request to get a list of available audio input devices. This includes OS default devices and specific devices that can be set.

```csharp
vx_req_aux_get_capture_devices
```

--------------------------------

### Apply Font and Get Energy Ratio

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Applies a font definition to an input file, saves it to an output file, and returns the energy ratio of the operation. The energy ratio is output via a double pointer.

```c
int vx_apply_font_to_file_return_energy_ratio(const char *fontDefinition, const char *inputFile, const char *outputFile, double *energyRatio);
```

--------------------------------

### Get Extended SDK Version Info

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Retrieves a string containing more detailed version information for the Vivox SDK, potentially including build numbers or specific features.

```c
const char *vx_get_sdk_version_info_ex(void);
```

--------------------------------

### Create a changelist using a description file

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/11

Create a new changelist, specifying the name as a literal and the description from a file. The 'add' verb is deprecated.

```console
cm changelist create "Physics-related changes" --descriptionfile="desc.txt"
```

--------------------------------

### Get Available Render Devices

Source: https://docs.unity.com/en-us/vivox-core/developer-guide/in-game-audio-control/in-game-audio-device-selection

Use this request to get a list of available audio output devices. This includes OS default devices and specific devices that can be set.

```csharp
vx_req_aux_get_render_devices
```

--------------------------------

### Handle Initialization Events: Unity Ads vs LevelPlay

Source: https://docs.unity.com/en-us/grow/levelplay/sdk/unity/migrate-from-unity-ads-to-levelplay

Map the callbacks for initialization success and failure events.

```csharp
IUnityAdsInitializationListener.OnInitializationComplete()
```

```csharp
LevelPlay.OnInitSuccess
```

```csharp
IUnityAdsInitializationListener.OnInitializationFailed(error, message)
```

```csharp
LevelPlay.OnInitFailed
```

--------------------------------

### Get Specific Real Money Purchase

Source: https://docs.unity.com/en-us/economy/sdk/quick-reference

Retrieves a specific real money purchase definition by its ID. Use this to get details about a particular real-world item or offer.

```csharp
public RealMoneyPurchaseDefinition GetRealMoneyPurchase(string id)
```

--------------------------------

### Unity Cloud Code Integration Example

Source: https://docs.unity.com/en-us/cloud-code/modules/how-to-guides/run-modules/unity-runtime

A full C# MonoBehaviour script demonstrating integration of Unity Services Authentication and Cloud Code. It initializes services, signs in anonymously, prepares arguments, and calls a Cloud Code endpoint.

```csharp
using System.Collections.Generic;
using UnityEngine;
using Unity.Services.Authentication;
using Unity.Services.CloudCode;
using Unity.Services.Core;

public class RollDiceExample : MonoBehaviour
{
    // ResultType structure is the serialized response from the RollDice script in Cloud Code
    private class ResultType
    {
        public int Roll;
        public int Sides;
    }

    // Call this method
    public async void CallMethod()
    {
        await UnityServices.InitializeAsync();
        // Sign in anonymously into the Authentication service
        if (!AuthenticationService.Instance.IsSignedIn) await AuthenticationService.Instance.SignInAnonymouslyAsync();

        // Creates a dictionary of arguments, setting diceSides to 6
        var args = new Dictionary<string, object> { ["diceSides"] = 6 };
        
        // Call out to the RollDice endpoint in the HelloWorld module in Cloud Code
        var response = await CloudCodeService.Instance.CallModuleEndpointAsync<ResultType>("HelloWorld", "RollDice", args);

        // Log the response of the module endpoint in console
        Debug.Log($"You rolled {response.Roll} / {response.Sides}");
    }
}
```

--------------------------------

### Start Game Server API Endpoint

Source: https://docs.unity.com/en-us/clanforge/api/endpoints/server-start-specific

Use this endpoint to start a game server. If the server is already running, this request will have no effect. The server ID is a required parameter.

```plaintext
https://api.multiplay.co.uk/cfp/v1/server/<serverid>/start
```

--------------------------------

### Conversion Attribution Parameter

Source: https://docs.unity.com/en-us/grow/acquire/partner-integration/custom/send-postbacks

Use this flag to indicate whether the original install was attributed to Unity. Use '1' for attributed and '0' for unattributed.

```url
was_conversion_attributed=1
```

--------------------------------

### Create Edge with Bounds

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/python/cad_functions

Creates an edge with a specified curve, start and end vertices, and boundary parameters. This is useful for defining edges with precise start and end points.

```python
cad.createEdgeWithBounds(curve, startVertex, endVertex, bounds)
```

--------------------------------

### Apply Vivox Font to WAV and Get Energy Ratio

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Applies a Vivox voice font to a .wav file and returns the energy ratio (Output Energy/Input Energy).

```cpp
VIVOXSDK_DLLEXPORT int vx_apply_font_to_file_return_energy_ratio(
    const char * fontDefinition,
    const char * inputFile,
    const char * outputFile,
    double * energyRatio
)
```

--------------------------------

### Load the entire workspace

Source: https://docs.unity.com/en-us/unity-version-control/uvcs-cli/partial-configure

Use '+' with the root path '/' to load all items into the workspace.

```bash
cm partial configure +/
```

--------------------------------

### Initialize Unity Cloud Python SDK

Source: https://docs.unity.com/en-us/cloud/asset-manager/python-sdk/get-started

Call this function once to initialize the SDK and log in the user. Ensure you check the authentication state before proceeding.

```python
def initialize():
    unity_cloud.initialize()
    unity_cloud.identity.user_login.use()
    # Check whether the user is signed in
    auth_state = unity_cloud.identity.user_login.get_authentication_state()
    if auth_state != unity_cloud.identity.user_login.Authentication_State.LOGGED_IN:
        unity_cloud.identity.user_login.login()
```

--------------------------------

### Example: Filter Pending Changes View in Plastic SCM

Source: https://docs.unity.com/en-us/unity-version-control/release-notes/5

Example filter for the 'pending changes' view in Plastic SCM, specifying status, item path, and type.

```text
status:changed item:bin/lib type:txt
```

--------------------------------

### Get Default Codecs Mask

Source: https://docs.unity.com/en-us/vivox-core/reference-manual/core/_vxc_8h

Provides a recommended default bitmask for available audio codecs, suitable for use with configured_codecs.

```cpp
VIVOXSDK_DLLEXPORT unsigned int vx_get_default_codecs_mask(
    void 
)
```

--------------------------------

### List Wanted License Tokens

Source: https://docs.unity.com/en-us/asset-transformer-sdk/2025.7/api/csharp/core_coreinterface

Retrieves a list of license tokens that are configured to be requested at product initialization.

```csharp
[HandleProcessCorruptedStateExceptions]
public StringList ListWantedTokens()
```