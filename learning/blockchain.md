# Blockchain Learning Resources

- [Blockchain Learning Resources](#blockchain-learning-resources)
  - [Courses](#courses)
  - [Books](#books)
  - [Youtube](#youtube)
  - [Blog Posts](#blog-posts)
  - [Blockchains](#blockchains)
    - [Bitcoin](#bitcoin)
    - [Cardano](#cardano)
    - [Polkadot](#polkadot)
    - [Tendermint](#tendermint)
  - [Exercises](#exercises)
    - [Ethereum](#ethereum)

## Courses

- [Applied Cryptography](https://www.youtube.com/playlist?list=PLAwxTw4SYaPnCeih6BPvJ5GdqqThGcWlX)
- [Become a Blockchain Developer](https://www.udacity.com/course/blockchain-developer-nanodegree--nd1309)
- [BerkeleyX: Blockchain Technology](https://www.edx.org/learn/blockchain/university-of-california-berkeley-blockchain-technology)
- [Blockchain A-Z](https://www.udemy.com/course/build-your-blockchain-az/)
- [Ethereum and Solidity: The Complete Developer's Guide](https://www.udemy.com/course/ethereum-and-solidity-the-complete-developers-guide/)
- [Ethereum Blockchain Developer Bootcamp With Solidity](https://www.udemy.com/course/blockchain-developer/)
- [Plutus programming language](https://www.udemy.com/course/plutus-reliable-smart-contracts/)

## Books

- [Applied Cryptography Protocols, Algorithms, and Source Code in C](https://www.amazon.de/-/en/Bruce-Schneier/dp/1119096723/ref=pd_lpo_2?pd_rd_i=1119096723&psc=1)
- [Cryptography Engineering: Design Principles and Practical Applications](https://www.amazon.de/-/en/Niels-Ferguson/dp/0470474246/ref=pd_lpo_1?pd_rd_i=0470474246&psc=1)
- [Practical Cryptography](https://www.amazon.de/-/en/Niels-Ferguson/dp/0471223573)
- [Decentralized Applications: Harnessing Bitcoin's Blockchain Technology](https://www.amazon.com/Decentralized-Applications-Harnessing-Blockchain-Technology/dp/1491924543)
- [Mastering Blockchain: Unlocking the Power of Cryptocurrencies, Smart Contracts, and Decentralized Applications](https://www.amazon.com/Mastering-Blockchain-Cryptocurrencies-Decentralized-Applications/dp/1492054704/ref=pd_bxgy_img_d_sccl_1/136-3163128-8380850)
- [Blockchain Basics: A Non-Technical Introduction in 25 Steps](https://www.amazon.com/Blockchain-Basics-Non-Technical-Introduction-Steps/dp/1484226038/ref=pd_sim_d_sccl_3_5/136-3163128-8380850)
- [Token Economy: How the Web3 reinvents the Internet](https://www.amazon.com/Token-Economy-Web3-reinvents-Internet/dp/3982103819/ref=pd_sim_d_sccl_3_7/136-3163128-8380850)
- [Web3: What is Web3? Potential of Web 3.0](https://www.amazon.com/WEB3-Potential-Contracts-Blockchains-Decentralized/dp/B09TMYWFRX)

## Youtube

- [Blockchain & Cryptocurrency](https://youtube.com/playlist?list=PLzvRQMJ9HDiQF_5bEErheiAawrJ-2zQoI&si=NtVJqfnYaz_f0271)
- [Dapp University](https://www.youtube.com/@DappUniversity/featured)
- [EatTheBlocks](https://www.youtube.com/@EatTheBlocks/videos)
- [Blockchain at Berkeley](https://www.youtube.com/@BlockchainatBerkeley)
- [Input Output](https://www.youtube.com/@IohkIo/videos)

## Blog Posts

- [Essential Cardano](https://www.essentialcardano.io/content)
- [Chainlink's Blog](https://blog.chain.link/category/education/)

## Blockchains

### Bitcoin

As a starting point for learning blockchain Bitcoin has a special place,
it could be a good reference to understand the idea and basic concepts
of the blockchain technology.

- [Bitcoin development guide](https://developer.bitcoin.org/devguide/index.html)

### Cardano

Of course as we are working primarily with the Cardano ecosystem
some understanding how Cardano works would be beneficial.

- [Cardano documentation](https://docs.cardano.org)

### Polkadot

As an example of Rust developed blockchain and a great successful case of applying
and idea of sidechains Polkadot and it's ecosystem good to know.
Also as they have a Rust blockchain framework for building blockchains based on WASM,
it is also great to explore in that context what we are want to build with hermes.

- [Polkadot Protocol](https://spec.polkadot.network/id-polkadot-protocol)
- [Polkadot Wiki](https://wiki.polkadot.network/docs/general-index)
- [Polkadot SDK](https://github.com/paritytech/polkadot-sdk)
- [Substrate Documentation](https://docs.substrate.io/)

### Tendermint

As another reference of blockchain framework with applying sidechain idea but on another language, Go land.

- [Tendermint Core](https://tendermint.com/core/)
- [Tendermint SDK](https://tendermint.com/sdk/)
- [IBC Protocol](https://ibcprotocol.org/)

## Exercises

### Ethereum

Blockchain operations:

1. Install ethereum node daemon https://geth.ethereum.org/docs/getting-started/installing-geth.
2. Take a look of all available commands to the ethereum daemon (geth) https://geth.ethereum.org/docs/fundamentals/command-line-options.
3. Create an ethereum metamask wallet account https://metamask.io (available as an browser extension).
5. Export private keys from metamask https://github.com/Kuzirashi/gw-gitcoin-instruction/blob/master/src/component-tutorials/5.extract.ethereum.private.key.md and import them to the ethereum daemon (geth) https://ethereum.stackexchange.com/questions/465/how-to-import-a-plain-private-key-into-geth-or-mist.
6. Start sync of the ethereum daemon with the network, sync up to 1000 blocks (or whatever amount you want, depends on your machine performance) https://geth.ethereum.org/docs/fundamentals/sync-modes. You can run sync in whatever mode you want, but try to learn what the difference.
7. Check your latest block (tip) on the ethereum explorer website that they are the same https://etherscan.io
8. (*Optionally*) Try to run mining of the ethereum block https://geth.ethereum.org/docs/fundamentals/mining (**NOTE** if you want to successfully mine the block, better to mine in the testnet, difficulty there much more less than in the mainnet).

Wallet operations (all for testnet (Goerli network)):

1. With already created wallet for metamask, get some free test coins https://goerlifaucet.com.
2. Create a new wallet account (you can make it in some another wallet application https://ethereum.org/en/wallets/find-wallet/, but it is not so important, you can create just a new one in metamask).
3. Send coins from one account to another, and check that transaction https://etherscan.io  (don't forget to change the network, by default its for mainnet, (top left button)).