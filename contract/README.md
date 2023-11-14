PotFighter Smart Contract Documentation
Overview
PotFighter is a decentralized application (DApp) implemented as a smart contract on the Ethereum blockchain. It allows users to create and participate in pots, where participants contribute funds, and the pot is distributed among players based on predefined rules. The contract is developed using Solidity and inherits from the OpenZeppelin Ownable contract.

Contract Details
Name: PotFighter
Version: 1.0.0
License: MIT
Developer: anwarservices22@gmail.com
Contract Structure
The contract is structured into several key components:

Variables:

potFee: Fee required to create a new pot.
rewardPerSecondPercent: Percentage of the pot balance distributed as rewards per second.
potId: Counter for assigning unique identifiers to pots.
reserveWallet: Address for the reserve wallet.
devTeam: Address for the development team.
distribution: Array representing the distribution percentages for rewards among participants.
Events:

PotCreated: Triggered when a new pot is created.
PotJoined: Triggered when a user joins a pot.
Modifiers:

potFreezed: Ensures that the pot is not frozen.
userBlackListed: Checks if the user is blacklisted.
Structs:

participant: Represents a participant in a pot.
Pot: Represents a pot.
Mappings:

createdPots: Maps potId to the corresponding Pot struct.
freezedPot: Monitors the freezing status of pots.
blackListedUser: Restricts the activity of blacklisted users.
Functions
createPot
Description: Allows a user to create a new pot by paying the required fee.
Effects:
Increments potId.
Adds the organizer as the first player.
Emits PotCreated and PotJoined events.
joinPot
Description: Allows a user to join an existing pot by paying the participation fee.
Effects:
Calculates and distributes rewards.
Adjusts pot balance and fees.
Emits PotJoined events.
activateClaiming
Description: Allows the pot owner to activate claiming after the pot has ended.
Effects:
Distributes remaining pot balance among participants.
Marks the pot as ended and activates claiming.
distributeFees
Description: Distributes fees among the pot creator, reserve wallet, development team, and previous players.
setDevWallet
Description: Allows the contract owner to set a new development team wallet address.
claimReward
Description: Allows participants to claim their earned rewards.
setReserveWallet
Description: Allows the contract owner to set a new reserve wallet address.
blackListUser and UnBlackListUser
Description: Allows the contract owner to blacklist or whitelist a user.
freezePot and unFreezePot
Description: Allows the contract owner to freeze or unfreeze a pot.
getPotParticipants and getPotBalance
Description: Retrieve information about participants and the balance of a specific pot.
userReward
Description: Retrieve the reward of a specific user in a pot.
getPlayerEarnings
Description: Retrieve earnings of the last 5 players and the caller.
getPotInfo
Description: Retrieve information about the number of players, start time, and end time of a pot.
pushValue
Description: Utility function to push a value to an array.
readParticipationFee, isClaimingActive, allRewardClaimed
Description: Query functions to retrieve specific information about a pot.
getAllPots
Description: Retrieve information about all created pots.
Usage
Deploy the PotFighter contract on the Ethereum blockchain.
Interact with the contract using Ethereum wallets or DApps.
Considerations
Ensure the appropriate fee is paid when creating or joining pots.
Pot owners have control over claiming and freezing/unfreezing pots.
Blacklisted users cannot participate in pots.
Regularly check pot status and claim rewards before pot claiming is activated.
Disclaimer
This documentation is for informational purposes only. Use the PotFighter contract at your own risk.

Contact
For inquiries or support, contact the developer at anwarservices22@gmail.com.

Version History
1.0.0 (Date): Initial release.