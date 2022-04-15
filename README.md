# Kenshi D20

This is a sample project using the Kenshi VRF oracle,
you can deploy the `contracts/D20.sol` to any EVM chain on Remix.
You can find already deployed versions of this contract in the
table below.

|       **Chain**        |                                                           **Address**                                                           |
| :--------------------: | :-----------------------------------------------------------------------------------------------------------------------------: |
|      BSC testnet       |  [0x398d50B3494e3cd64018b8FD39BC88c02064BF98](https://testnet.bscscan.com/address/0x398d50B3494e3cd64018b8FD39BC88c02064BF98)   |
| Polygon Mumbai testnet | [0x17D7dC8B5B4C64c27A5F69Cd9De4F97D44Ca7af5](https://mumbai.polygonscan.com/address/0x17D7dC8B5B4C64c27A5F69Cd9De4F97D44Ca7af5) |
|     Fantom testnet     |  [0xc9De8dE11d09A5C1C3e5E9B5a104e3357ff6148d](https://testnet.ftmscan.com/address/0xc9De8dE11d09A5C1C3e5E9B5a104e3357ff6148d)   |
| Avalanche Fuji testnet |  [0x274F14d02c60933Db669B84A434608d5c262A603](https://testnet.snowtrace.io/address/0x274f14d02c60933db669b84a434608d5c262a603)  |

## After deployment

After you deploy the contract, you need to call the `setVRFConfig` function
with appropriate parameters. These parameters are:

|   **Name**    | **Type**  |                       **Description**                       |
| :-----------: | :-------: | :---------------------------------------------------------: |
| `coordinator` | `address` |         The Kenshi VRF Coordinator contract address         |
|   `verify`    |  `bool`   | Whether to verify the randomness on-chain (affects gas fee) |
|   `silent`    |  `bool`   |  Whether to emit an event on randomness (affects gas fee)   |

Notes: In the `setupVRF` function of the Kenshi VRF library, the last two parameters of the above
table are optional.

You can find the contract address of each chain on our documentation
website [here](https://docs.kenshi.io/services/vrf/contracts.html).

## After setup

Once the setup is done, you can call the `roll` function on the D20 smart contract.
This function asks the VRF coordinator for `randomness`. Once the requested `randomness`
is received, the `fulfillRandomness` function emits a `Rolled` event.

## Testnet Kenshi

Your contract needs to hold some testnet Kenshi to pay for VRF fees. You can request for
testnet Kenshi in our [Telegram chat](https://t.me/kenshi_token).
