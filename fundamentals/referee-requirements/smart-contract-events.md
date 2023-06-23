---
description: Track smart contract events by referees to reward affiliates.
---

# Smart Contract Events

This section explains how to reward affiliates based on the smart contract events performed by the users they invite.

To add a Smart Contract Event requirement, navigate to your project's settings page. In the _Affiliates_ section, click on _Advanced Referee Requirements_, and choose _Smart Contract Event_ as the requirement type.

You will be asked to fill in the following fields:

* **Event Name** - a user friendly name that is displayed in our UI.
* **What is the minimum value required to be considered a referral?** - This is a numeric value threshold above which an affiliate is considered to be valid. You can leave this blank or set it to 0 if you'd like to allow any value.
* **Chain** - Which blockchain the event occurs on.
* **Smart Contract Address** - The smart contract on which to track the events.
* **Event ABI** - The ABI for the event to track. This can be copied and pasted from Etherscan. Ask a developer or reach out to us if you need help with this.
* **Event ABI Address Field** - This is the address to track within the event. For example,  if you have a staking event represented by `Stake(address staker, unit256 value)` this field would be set to `staker`.\
  Note, this field will only be editable once a valid ABI is set. Only indexed topics can be tracked.
* **Event ABI Value Field** - This is the value field to track within the event. For example,  if you have a staking event represented by `Stake(address staker, unit256 value)` this field would be set to `value`. So if you want to reward affiliates with 5 USDC for every referee that stakes at least 100 value, this is the field we'd check to see if the condition has been fulfilled.\
  Note, this field will only be editable once a valid ABI is set.

This is an example of settings for tracking Lido staking:

<figure><img src="../../.gitbook/assets/CleanShot 2023-06-23 at 17.39.58@2x.png" alt=""><figcaption><p>Tracking Lido staking</p></figcaption></figure>

You can require that referees complete multiple requirements to be considered eligible for a reward to be unlocked. To require multiple requirements, click on the plus icon at the bottom of a requirement. You can combine smart contract requirements with other types of requirements.

