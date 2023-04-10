# Forge DEX | Evmos Tokenlists

Token Lists is a specification for lists of token metadata (e.g. address, decimals, etc.) that can be used by any dApp
interfaces that needs one or more lists of tokens. Anyone can create and maintain a token list, as long as they follow
the specification. 

## Adding Your Token to an Existing List

### General Requirements
1. Token should be verified on the [eScan.live](https://escan.live/) or [Mintscan](https://www.mintscan.io/evmos) explorer.
2. Token must be added to a list that it qualifies for:
    * **Mainnet Tokenlist**: Token must be on the Evmos network (9001).
    * **Testnet Tokenlist**: Token must be on the Evmos testnet (9000).


## Adding Your Token
1. Add an entry in the `tokens` field of the appropriate tokenlist. Here is an example using WEVMOS:
    ```json
    {
      "name": "Wrapped Evmos",
      "symbol": "WEVMOS",
      "chainId": 9001,
      "decimals": 18,
      "address": "0xD4949664cD82660AaE99bEdc034a0deA8A0bd517",
      "logoURI": "https://storage.googleapis.com/us-central1-dgc-berlin-0-470cbba9-bucket/tokenlist/wevmos.png"
    }
    ```
2. Update the `timestamp` field to the current timestamp.
3. Update the `version` field to adhere to semantic versioning:

    * Increment major version when tokens are removed
    * Increment minor version when tokens are added
    * Increment patch version when tokens already on the list have minor details changed (name, symbol, logo URL, decimals)

    ***Note:*** Changing a token address or chain ID is considered both a remove and an add, and should be a major version update.
