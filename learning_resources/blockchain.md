# Blockchain Learning Resources

## Bitcoin

As a starting point for learning blockchain Bitcoin has a special place,
it could be a good reference to understand the idea and basic concepts
of the blockchain technology

- https://developer.bitcoin.org/devguide/index.html

## Cardano
Of course as we are working primarily with the Cardano ecosystem
some understanding how Cardano works would be beneficial

- https://docs.cardano.org/


## Polkadot/Substrate

As an example of Rust developed blockchain and a great successful case of applying
and idea of sidechains Polkadot and it's ecosystem good to know.
Also as they have a Rust blockchain framework for building blockchains based on WASM,
it is also great to explore in that context what we are want to build with hermes.

Polkadot:
- https://spec.polkadot.network/id-polkadot-protocol
- https://wiki.polkadot.network/docs/general-index

Substrate (renamed to polkadot-sdk):
- https://github.com/paritytech/polkadot-sdk
- https://docs.substrate.io

## Tendermint and Cosmos-SDK

As another reference of blockchain framework with applying sidechain idea but on another language, Go land.

- https://tendermint.com/core/
- https://tendermint.com/sdk/
- https://tendermint.com/ibc/ (sidechain's protocol)

# Blockchain exercises

## Ethereum
Blockchain operations:

1. Install ethereum node daemon https://geth.ethereum.org/docs/getting-started/installing-geth.
2. Take a look of all available commands to the ethereum daemon (geth) https://geth.ethereum.org/docs/fundamentals/command-line-options.
3. Create an ethereum metamask wallet account https://metamask.io (available as an browser extension).
5. Export private keys from metamask https://github.com/Kuzirashi/gw-gitcoin-instruction/blob/master/src/component-tutorials/5.extract.ethereum.private.key.md and import them to the ethereum daemon (geth) https://ethereum.stackexchange.com/questions/465/how-to-import-a-plain-private-key-into-geth-or-mist.
6. Start sync of the ethereum daemon with the network, sync up to 1000 blocks (or whatever amount you want, depends on your machine performance) https://geth.ethereum.org/docs/fundamentals/sync-modes. You can run sync in whatever mode you want, but try to learn what the difference.
7. Check your latest block (tip) on the ethereum explorer website that they are the same https://etherscan.io 
8. (*Optionally*) Try to run mining of the ethereum block https://geth.ethereum.org/docs/fundamentals/mining (**NOTE** if you want to sucessfully mine the block, better to mine in the testnet, difficulty there much more less than in the mainnet).

Wallet operations (all for testnet (Goerli network)):

1. With already created wallet for metamask, get some free testcoins https://goerlifaucet.com.
2. Create a new wallet account (you can make it in some another wallet application https://ethereum.org/en/wallets/find-wallet/, but it is not so important, you can create just a new one in metamask).
3. Send coins from one account to another, and check that transaction https://etherscan.io  (dont forget to change the network, by default its for mainnet, (top left button)).