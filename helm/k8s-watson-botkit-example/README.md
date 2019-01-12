# Kubernetes Watson Assistant <--> Botkit example
This is a slightly modified version of the sample app (with the same source file  name) available with [the middleware to connect  Watson Assistant skills to different chat channels using Botkit](https://github.com/watson-developer-cloud/botkit-middleware).

This version is designed to be run on Kubernetes and includes a Helm chart that injects the required parameters as ENV vars into the container that runs the app. The values are taken from  the Helm values instead of the file **.env** that was used in the original version.

The following  values can be set  when you install the Helm Chart.

  | Name          | Description | Required ? |
  | ------------- | ----------- | ---------- |
  | assistantIamApiKey | The apikey of the Watson Assistant instance with the skill to be connected to Slack | Yes |
  | slackToken | The Slack OAUTH token for the Bot created in Slack to interface with Watson Assistant | Yes |
  | slackSigningSecret | The Slack Signed Secret used by the middleware to verify that incoming requests are from Slack | Yes |
  | workspaceId | The Workspace ID of the Watson Assistant  skill to be connected to Slack | Yes |
  | assistantUrl | The API endpoint for the Watson Assistant instance with the skill to be connected to Slack | No |


Once the Helm Chart is installed you can launch Slack and send direct messages to your Slack bot and get responses from your Watson Assistant workspace.

![promisechains](https://cloud.githubusercontent.com/assets/5727607/19366644/fe122c2a-9165-11e6-9728-b18a5d9e1198.gif)
