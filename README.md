# Kenshi D20

This is a sample project using the Kenshi VRF oracle,
you can deploy the `contracts/D20.sol` to any EVM chain on Remix.
You can find already deployed versions of this contract in the
table below.

|       **Chain**        |                                                           **Address**                                                           |
| :--------------------: | :-----------------------------------------------------------------------------------------------------------------------------: |
|      BSC testnet       |  [0xa1A0f77E6970de78B9463Da40AEA8948FA298c6a](https://testnet.bscscan.com/address/0xa1A0f77E6970de78B9463Da40AEA8948FA298c6a)   |
| Polygon Mumbai testnet | [0xa95b1401B44F1855C5147f94064d9EeeBE50085b](https://mumbai.polygonscan.com/address/0xa95b1401B44F1855C5147f94064d9EeeBE50085b) |
|     Fantom testnet     |  [0x62d9b73C79365cff0C21ac58428a42D20E274e64](https://testnet.ftmscan.com/address/0x62d9b73C79365cff0C21ac58428a42D20E274e64)   |

## After deployment

After you deploy the contract, you need to call the `setVRFConfig` function
with appropriate parameters. These parameters are:

|   **Name**    | **Type**  |                       **Description**                       |
| :-----------: | :-------: | :---------------------------------------------------------: |
| `coordinator` | `address` |         The Kenshi VRF Coordinator contract address         |
|    `utils`    | `address` |            The Kenshi VRF Utils contract address            |
|   `kenshi`    | `address` |          The Kenshi ERC1363 token contract address          |
|   `verify`    |  `bool`   | Whether to verify the randomness on-chain (affects gas fee) |

You can find the contract address of each chain on our documentation
website [here](https://docs.kenshi.io/services/vrf/contracts.html).

## After setup

Once the setup is done, you can call the `roll` function on the D20 smart contract.
This function asks the VRF coordinator for `randomness`. Once the requested `randomness`
is received, the `fulfillRandomness` function emits a `Rolled` event.

## Testnet Kenshi

Your contract needs to hold some testnet Kenshi to pay for VRF fees. You can request for
testnet Kenshi in our [Telegram chat](https://t.me/kenshi_token).
