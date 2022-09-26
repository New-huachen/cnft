# Parse CNFT
A package that parses Cardano NFT's
- Converts metadata json to easy to use types
- Rejects any invalid nfts in accordance with [cip25](https://cips.cardano.org/cips/cip25/#abstract)

## Support
- Support development by delegating to [9000](https://ada9000.io)


## Quickstart example

```js
const metadataJsonString = `{
    "721": {
        "ba3afde69bb939ae4439c36d220e6b2686c6d3091bbc763ac0a1679c": {
            "bit_bot 0x0000": {
                "image": "ipfs://QmQJfWDun8h6ucvLpm7Z15zNbW3tBCUsgXpkZ8ETCisgm9",
                "mediaType": "image/svg",
                "name": "bit_bot 0x0000",
                "project": "bit_bots"
            }
        }
    }
}`
const {data, errors} = ParseCNFT(metadataJsonString);
console.log(data?.policyId);        // logs: ba3afde69bb939ae4439c36d220e6b2686c6d3091bbc763ac0a1679c
console.log(data?.assets[0].name);  // logs: bit_bot 0x0000
```
