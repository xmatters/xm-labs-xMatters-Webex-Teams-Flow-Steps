# xMatters Webex Teams Flow Steps

This xMatters communication plan contains 10 Webex Teams Custom xMatters Flow Designer Steps.

<kbd>
  <img src="https://github.com/xmatters/xMatters-Labs/raw/master/media/disclaimer.png">
</kbd>

# Pre-Requisites

- xMatters account - If you don't have one, [get one](https://www.xmatters.com)!

# Files

- [WebexTeams.zip](WebexTeams.zip) - Flow Steps Workflow package

# How it works

1. Import this communication plan and set Usage Permissions to give access to xMatters users or groups.
2. Get Access Tokens from Webex Teams for authentication.

# Included Custom Steps

<kbd>
    <img src="/media/steps.png" width="650px">
</kbd>
<br><br>


**MESSAGES API** [link](https://developer.webex.com/docs/api/v1/messages)

- Create a Message
- List Messages (Must get Integration Access Token using __Get Token__ Flow step and provide __access_token__ as an input to this step) 


**ROOMS API** [link](https://developer.webex.com/docs/api/v1/rooms)

- Create a Room
- Update a Room
- Get Room Details
- Get Room Meeting Details
- Delete a Room

**MEMBERSHIPS API** [link](https://developer.webex.com/docs/api/v1/memberships)

- Create a Membership
- Create Memberships from List of Emails

**AUTHENTICATION** 

- Get Token (Gets the access token so you can use List Messages Flow Step) 


# Webex Teams Configuration


## Create a Webex Teams Bot and Get Auth Token

[How to create a Webex Teams Bot and Get an Access Token](https://developer.webex.com/docs/bots)


All flow steps in this communication plan will work with the Bot Access Token with the exception of:

- __Get Token__ : This step uses a refresh token to generate a new access token.
- __List Messages__: This step gets all messages in a room. It requires an Integration Access Token. A bot Access token will not work.


A bot can only access messages sent to it directly. In group spaces, bots must be @mentioned to access the message. In 1-to-1 spaces, a bot has access to all messages from the user.

If you want to use the Flow Step for __List Messages__ you will need to [Get Webex Teams Integration Refresh Token](#get-webex-teams-integration-refresh-token)


## Get Webex Teams Integration Refresh Token

To use the __List Messages__ Flow Step, you will need to get a Webex Teams Integration Refresh Token.

[How to Create a Webex Teams Integration and get a Refresh Token](https://developer.webex.com/docs/integrations)

After successfully setting up the Webex Teams integration, you will have the following:

	- grant_type
	- client_id
	- client_secret
	- refresh_token

These values are the inputs for the __Get Token__ Flow step. 

The __Get Token__ Flow step will get the __access_token__ required as an input to the __List Messages__ Flow step.


# xMatters Configuration


## Import the xMatters Communication Plan

1. Download the [Webex Teams Communication Plan](WebexTeams.zip)

2. Follow instructions for [Importing a communication plan](https://help.xmatters.com/ondemand/xmodwelcome/communicationplanbuilder/exportcommplan.htm)



## Set Usage Permissions on the Steps you would like to share

1. On the Developer tab, click Edit beside the **Webex Teams** communication plan and go to **Flows**.

2. Click on **Webex Teams Flow**.

3. Follow instructions for [Sharing a Custom Flow Step](https://help.xmatters.com/ondemand/xmodwelcome/flowdesigner/share-steps.htm)



## Create xMatters Constant for __teams_bot_token__

1. Go to Webex Teams communication plan or whatever plan you want to configure this step, click __Edit__ and go to __Integration Builder__. 

2. Click __Edit Constants__.

3. Add constant with the name __teams_bot_token__

4. Set the constant value to your Webex Teams Bot Access Token.

[How to create a Webex Teams Bot and Get an Access Token](#create-a-webex-teams-bot-and-get-auth-token)


<kbd>
    <img src="/media/constants.png" width="650px">
</kbd>
<br><br>



## Use the Webex Teams Flow Steps

1. Drag the Webex Teams step on the canvas and configure the step.

[Get help using Flow designer](https://help.xmatters.com/ondemand/xmodwelcome/flowdesigner/flow-designer.htm)

The Webex Teams API documentation will help you understand the inputs and outputs for each step.
[Get help with Webex Teams API](https://developer.webex.com/docs/platform-introduction)


## Sample Flow

Below is an example of an xMatters flow that you could build using these steps.

<kbd>
    <img src="/media/Sample-Flows.png">
</kbd>
<br><br>



# Troubleshooting

[Get help using Flow designer](https://help.xmatters.com/ondemand/xmodwelcome/flowdesigner/flow-designer.htm)

[Get help with Webex Teams API](https://developer.webex.com/docs/platform-introduction)

[Get help with Webex Teams Bot Creation](https://developer.webex.com/docs/bots)

[Get help with Webex Teams Integration](https://developer.webex.com/docs/integrations)
