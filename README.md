arm PELION Device Shadow bridge for Google CloudIoT                    
  
03/07/2019: refresh builds

01/05/2019: docker build trigger update

01/04/2019: Happy New Year! minor update to mbed-properties-editor

11/26/2018: updated bridge - removed outdated scripts - no longer needed. Default CloudIoT set to HTTP implementation.

11/07/2018: updated bridge - new Google CloudIoT HTTP-based implementation (optional) in leu of MQTT

11/04/2018: updated bridge - reoganized for future AWS and Google HTTP implementations

11/03/2018: updated bridge - new IoTHub HTTP-based implementation (optional) in leu of MQTT

Container Bridge Instance Installation:

1). Clone this repo into a Linux instance that supports docker images

2). cd into the cloned repo and run: ./run-reload-bridge.sh

Once the container instance is live, you must configure the bridge and bind it between your mbed Pelion account and your PubSub Service in Google Cloud

1). In Google Cloud, create your project... your project will be named.  Save this name

2). Create a PubSub instance in your project - enable the PubSub API.

3). In Google Cloud IAM, create a service account and authentication JSON for project. This will be your "IAM credential JSON"

4). Next go to https://os.mbed.com and create your mbed Account. You can then request a Pelion developer account using the same credentials at https://portal.us-east-1.mbedcloud.com

5). Once your Pelion account is created, you need to "Access Keys" to create a Pelion API Key/Token. Record the Token Value

Now that you have your:

    - Google Cloud Project Name. Enter this as your "google_cloud_application_name" value

    - Google Cloud Project IAM credential JSON. Enter this as your "google_cloud_auth_json" value

    - Pelion API Key/Token generated

Go to:  https://[[your containers public IP address]]:8234

    - username: "admin" (no quotes)

    - password: "admin" (no quotes)

Enter each of application name value, auth json value, and Pelion API Token

    - Please press "SAVE" after *each* is entered... 

    - Once entered, press "Restart" to restart the bridge

Your Pelion bridge should now be configured and operational. 

Additionally, a Google Cloud PubSub example has been published here:

    - https://github.com/ARMmbed/GoogleCloudConnectorExerciser

This sample provide an example on how, from within Google Cloud, you can read and react to events and telemetry via the bridge.

Bridge source (Apache 2.0 licensed - Enjoy!): https://github.com/ARMmbed/pelion-bridge.git

Copyright 2018. ARM Ltd. All rights reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License. 
