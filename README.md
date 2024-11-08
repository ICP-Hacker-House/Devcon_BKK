# 2024 Chain Fusion Hacker House Devcon Bangkok

## Content

-   [Bounties](#bounties)
-   [Tracks](#tracks)
-   [Resources](#resources)
-   [Cycles](#cycles)
-   [How to Submit](#how-to-submit)
-   [Judging](#judging)
-   [Payout](#payout)

# Bounties

Throughout the hacker house, you'll have the opportunity to complete various Bounties that will progressively prepare you for larger challenges, with rewards ranging from $20 to $100 based on complexity. Bounties are designed to be small, well-defined, and time-sensitive, allowing you to apply what you’ve learned and earn as you go. Completing Bounties will also bring you closer to submitting a final project for one of the larger Tracks. Try to complete Bounties as quickly as possible, as there’s only a limited number available to claim.

## Easy Bounties – $25 Each

-   **[Claim Cycles](https://anv4y-qiaaa-aaaal-qaqxq-cai.ic0.app/) and deploy a canister smart contract on ICP (awarded 100 times)**: Claim a cycles coupon and deploy a simple "Hello World" backend canister on mainnet, including a frontend with specific functionalities:
    -   Modify the `greet` function to update call.
    -   Keep an array of all submitted `name` arguments in the canister and expose them through a `submittedNames` query method
    -   Add a button to display them in the frontend.
-   **Claim gas tokens and deploy a smart contract on [Bitfinity Network](https://bitfinity.network/) (awarded 100 times)**: For this Bounty, you will deploy a Solidity-based "Hello World" smart contract and integrate it with a frontend on the Internet Computer (ICP). Follow the instructions below to complete the Bounty.
    -   Create a Solidity smart contract with a `greet` function that should
        -   Take a string argument `name`.
        -   Return a greeting in the format: `"Hello, <name>"`.
        -   Each time `greet` is called, the contract should:
            -   Store the provided `name` in an array called `submittedNames`.
    -   Implement an endpoint in the smart contract that:
        -   Returns the `submittedNames` array.
        -   This endpoint should be accessible from the frontend to display all previously submitted names.
    -   Build a frontend on ICP to interact with the smart contract, including:
        -   An input field where users can enter the `name` argument and call the `greet` function.
        -   A button to retrieve and display the `submittedNames` array.
        -   Deploy the frontend on ICP, either by:
            -   Using an [asset canister](https://internetcomputer.org/docs/current/developer-docs/web-apps/application-frontends/existing-frontend), or
            -   Deploying via [Juno.build](https://juno.build/docs/guides/manual-deployment).

## Medium Bounties – $100 Each

-   **Token Deployment & Interaction (awarded 20 times)**: Deploy an ICRC-1 canister on mainnet with custom name and supply, and interact with it using `ic-js` and `@dfinity/agent-js`. Includes minting, transferring tokens, and displaying transaction history.
-   **On-Chain Oracle (awarded 20 times)**: Use HTTP outcalls to fetch price data from Coinbase API at regular intervals, store it as a time series, and expose the data via query call on a frontend.
-   **Random Game with ICP (awarded 20 times)**: Use on-chain randomness to build a simple game, enabling user authentication with Internet Identity and a frontend for interaction.
-   **Subscription Service (awarded 10 times)**: Set up a canister that collects recurring payments from an Ethereum account, using [USDC](https://faucet.circle.com/) or [WETH](https://weth.altlayer.io/transfer) on Sepolia. `approve` the canister’s Ethereum address for a certain amount and then let the canister call `transferFrom` regularly using [a timer](https://github.com/dfinity/examples/tree/master/rust/periodic_tasks) to deduct the subscription fee from your account.
-   **Whale Watcher (awarded 10 times)**: Create a canister to monitor USDC transfers over 1 million, storing and exposing the transfer details via query call on a frontend. A cool stretch goal would be to automatically mint an ERC-721 NFT Whale NFT to the receiver
-   **Loyality Program (awarded 20 times)**: Create a loyalty program using Solidity. Users earn points by completing actions (e.g., logging in daily or making a purchase), track balances, and redeem rewards in the form of discounts on product purchase. Loyality points can be in the form of ERC-20 tokens. Deploy it on [Bitfinity](https://bitfinity.network/) testnet.

# Tracks

Tracks are larger, open-ended projects with broader requirements and a higher reward pool. Each Track leverages unique features of the Internet Computer (ICP), enabling you to create applications that push the boundaries of blockchain technology. The Tracks are designed to build on top of the skills developed in the Bounties, giving you a solid foundation to tackle these more ambitious projects. Below are the available Tracks, each with a distinct focus and inspiration for your submissions.

## 1) **Fully On-Chain Dapps – Total Prize pool of USD 5k**

The Internet Computer (ICP) is a third-generation blockchain, serving as a permissionless, decentralized cloud built on blockchain technology. Its smart contracts, known as canisters, are more akin to decentralized servers than traditional smart contracts, representing an evolution in blockchain-based applications. Due to their powerful nature, canisters can run general-purpose and even enterprise-level applications, offering flexibility far beyond typical smart contracts. With canisters, developers can build powerful dapps and services that benefit from 1-2 second transaction finality, enabling a user experience (UX) that closely resembles the speed and responsiveness customers are used to from web2 applications.

What makes ICP stand out is its combination of [cross-chain capabilities and unique protocol features](https://www.notion.so/ICP-Hackathon-Cheat-Sheet-b2921239266149de81021412f572351c?pvs=21) you won’t find on any other blockchain:

-   **Low-cost, massive storage**: Store up to 400GB of data in a canister smart contract for just $5 per GB per year, making it ideal for hosting dapp frontends or large datasets.
-   **Smart contracts that can make HTTPS requests**: Build apps that seamlessly integrate web2 services directly into web3.
-   **Timers**: Execute code at specific intervals to create features for recurring payments, automated DeFi strategies, periodic oracle updates, and more.
-   **Secure randomness**: True on-chain randomness opens up use cases for gaming, governance, fair auctions, etc.
-   **External wallet login**: Sign in with Ethereum or Solana wallets to applications hosted on ICP. Linking of external blockchain accounts with ICP accounts allows for using ICP as an ETH/SOL/BTC L2.
-   **Serve content over HTTPS**: Canisters can natively serve HTTP, enabling hosting of websites or serving APIs from a smart contract without additional software.
-   **Reverse gas model**: Massively improve your UX by freeing end users from paying for transactions they perform when interacting with your dapp.
-   **Long-running, multi-block transactions** that even allow running AI inference.
-   **Chain Fusion**: chain-key Schnorr and chain-key ECDSA support, enabling seamless interaction with Bitcoin, EVM chains, Solana, and more. With chain-key cryptography, ICP smart contracts can also natively hold ETH, BTC, and other tokens, allowing them to sign transactions across these networks.

These features enable applications that simply **can’t be built anywhere else**, setting ICP apart from other blockchain platforms.

### Challenge

Leverage the unique power of ICP to build an app that **couldn't be built anywhere else**! Take advantage of features like seamless cross-chain interoperability, chain-key cryptography, or HTTPS outcalls. Whether it’s enabling Bitcoin payments directly from an ICP smart contract, executing Ethereum smart contract logic across chains, or hosting a multichain dapp with massive low-cost storage, your app should showcase what can only be achieved on ICP. The goal is to create a dapp that pushes the boundaries of blockchain technology by integrating ICP’s unparalleled multichain capabilities and making cross-chain complexity invisible to users.

### Guidance

**Ideas for inspiration:**

-   **Onchain games:** Simple dice or card games that use ICP’s secure randomness for fair gameplay.
-   **Reminder service:** A canister that relies on timers and HTTPS outcalls to send you notifications at certain times. Monitor onchain transactions or send yourself any reminder at a future date.
-   **Prediction Market:** Start simple by using HTTPS outcalls to resolve predictions for a specific topic. Think about using timers to automatically trigger the HTTPS outcalls to handle resolution. Long term think about an alternative to Polymarket.
-   **Decentralized Data Aggregator:** Build a dapp that uses HTTPS outcalls on ICP to fetch real-time off-chain data from various sources (e.g., stock prices, weather, or APIs) and aggregate it on-chain for use by other applications.
-   **Facilitate a Stripe Payment**: Use HTTP outcalls from an ICP canister to process payments via Stripe.
-   **Unity Game Integration**: Integrate a Unity game with Internet Identity (II) for login, and store high scores or user items in a canister using the C# SDK.
-   **Whistleblower Platform**: Create a secure platform for anonymous whistleblowing, using vetkeys for additional security.

### What We’re Looking For

-   Projects that leverage the unique features ICP has to offer.
-   Originality: The project must be a unique idea, not a rework of existing projects.
-   The project must be deployed on the ICP mainnet.
-   Code must be published to GitHub and licensed under a permissive license.
-   A detailed README explaining the project’s scope and functionality.
-   A recorded demo walking viewers through the project and its codebase.

### Judging Criteria

-   **Uniqueness**: Does the project use at least one feature unique to ICP?
-   **Creativity**: How innovative is the dapp and its use of ICP?
-   **Functionality**: Is the dapp fully functional and meets its intended purpose?
-   **Code Quality**: Is the code well-documented, structured, and maintainable?
-   **Bonus**: Provide feedback on ICP’s unique features like HTTP Outcalls and Timers.

### Prizes

1. USD 3k in ICP grants
2. USD 1.5k in ICP grants
3. USD 0.5k in ICP grants

---

## 2) **Chain Fusion – Total Prize pool of USD 5k**

Leverage Internet Computer's new [Chain Fusion](https://internetcomputer.org/chainfusion) technology to build or extend a cross-chain dApp that integrates ICP with any other chain, including Bitcoin and Ethereum. Using Chain Fusion, you can connect these chains directly without bridges, oracles, or intermediaries. ICP canister smart contracts are capable of signing Ethereum or Bitcoin transactions directly via [ICP's threshold signing API](https://internetcomputer.org/docs/current/developer-docs/smart-contracts/encryption/t-ecdsa/), and they can read from other networks through integrations like [ICP’s Bitcoin API](https://internetcomputer.org/docs/current/developer-docs/multi-chain/bitcoin/overview) or [EVM RPC](https://internetcomputer.org/docs/current/developer-docs/multi-chain/ethereum/evm-rpc/overview) calls, or through custom [HTTPS outcalls](https://internetcomputer.org/docs/current/developer-docs/smart-contracts/advanced-features/https-outcalls/https-outcalls-overview).

### Challenge

Build a dapp that demonstrates ICP's cross-chain capabilities through Chain Fusion, with flexibility to integrate any blockchain-related functionality you choose. Your dApp should highlight practical uses of Chain Fusion and showcase ICP’s unique cross-chain features. Ideas may include automating tasks on Ethereum, building fully on-chain apps that leverage Chain Fusion, or experimenting with cross-chain DeFi applications using ckBTC or ckETH tokens.

### Guidance

**Ideas for inspiration:**

-   **Dollar Cost Averaging (DCA):** Let a canister manage DCA of an asset on a DEX like Uniswap.
-   **BTC Lending/Borrowing through ckBTC:** Enable decentralized Bitcoin lending and borrowing on ICP using ckBTC.
-   **Dead Man Switch Canister for BTC:** Create a dead man switch for Bitcoin, where funds automatically transfer to an exchange or designated address in case of the user's death.
-   **Native BTC/ETH Coinflip:** Implement a coinflip game with Bitcoin or ETH, handled entirely within a canister using ICP’s chain fusion and randomness features.
-   **Cross-Chain Crowdfunding Platform**: Build a decentralized crowdfunding platform where users can contribute funds in Bitcoin, Ethereum, or other tokens using ICP’s direct blockchain integrations.
-   **Cross-Chain Payment Gateway**: Develop a payment gateway that allows businesses to accept Bitcoin, Ethereum, and other cryptocurrencies without intermediaries, using ICP for secure cross-chain transactions.
-   **Canister Managed Index Fund:** Develop a canister-based index fund that automatically buys top assets on a DEX like Uniswap.
-   **Autonomous User-Controlled Canisters:** Create an autonomous agent where user-controlled canisters on ICP execute cross-chain actions, store data, and run tasks independently. One example could be an autonomous trading bot.
-   **Cross-Chain DAO Voting Platform:** Build a DAO voting platform on ICP that can execute governance decisions on multiple blockchains, like Bitcoin and Ethereum, using ICP’s cross-chain signing features.
-   **Extend an ETH/Bitcoin dapp with a canister backend/frontend:** Use [Sign in with Bitcoin](https://internetcomputer.org/docs/current/developer-docs/identity/authentication/siwb) or [Sign with Ethereum](https://internetcomputer.org/docs/current/developer-docs/identity/authentication/siwe) to allow users to seamlessly interact with ICP using their wallet of choice.
-   **Deploy ETH Smart Contract**: Enable deployment of an Ethereum smart contract directly from an ICP canister.

### What We’re Looking For

-   Projects that showcase one or more Chain Fusion features.
-   Originality: The project must not be a rework of existing projects.
-   A functional deployment on ICP mainnet.
-   Public code on GitHub, licensed permissively.
-   A detailed README explaining the project’s scope and functionality.
-   A recorded demo walking viewers through the project and codebase.

### Judging Criteria

-   **Feature Utilization**: Does the project utilize at least one Chain Fusion feature?
-   **Creativity**: How innovative is the project in terms of cross-chain functionality?
-   **Completeness**: Is the dapp fully functional and achieves its purpose?
-   **Code Quality**: Is the code well-documented, structured, and easy to maintain?
-   **Bonus**: Provide feedback on ICP’s chain-key signatures and other integration features.

### Prizes

1. USD 3k in ICP grants
2. USD 2k in ICP grants

---

## 3) **EVM dApps on ICP – Total Prize pool of USD 5k**

Develop Ethereum-compatible applications using [Bitfinity](https://bitfinity.network/), exploring diverse themes such as DeFi, NFTs, gaming, launchpads, and infrastructure solutions. In the DeFi space, projects can include automated market makers (AMMs) and aggregators, fostering new ways for users to engage with decentralized finance. NFT and gaming projects could involve building NFT platforms and marketplaces, creating unique gaming experiences that leverage blockchain technology, or establishing new forms of digital ownership. Launchpads like Pump.fun offer exciting possibilities for emerging projects to reach wider audiences, fueling growth and innovation.

We also supports infrastructure initiatives, these might include creating development environments like Remix, or messaging systems that enhance communication within decentralized networks. By building with Bitfinity, developers can drive scalability and broaden the possibilities for interoperability within the Ethereum ecosystem, ultimately advancing the future of blockchain applications.

### Challenge

Leverage the EVM compatibility of Bitfinity on ICP to create a dApp that pushes the boundaries of interoperability and user engagement. Your project should align with one of the major themes below but can incorporate additional features to stand out.

### Guidance

**Ideas for inspiration:**

-   **Automated Market Makers (AMMs)**: Build an Ethereum-compatible AMM on ICP to provide liquidity and enable decentralized trading.
-   **DeFi Aggregators**: Create aggregators that bring together DeFi protocols, giving users a single interface to interact with multiple liquidity pools or lending platforms.
-   **NFT Marketplaces**: Develop a marketplace where users can mint, buy, sell, and trade NFTs, leveraging Ethereum compatibility on ICP.
-   **Gaming Experiences**: Build gaming applications that utilize NFTs or tokenized assets, allowing players to own, trade, and use in-game assets securely on the blockchain.
-   **Digital Ownership Platforms**: Establish platforms for new forms of digital ownership, enabling users to verify, trade, or showcase assets like art, music, or collectibles.
-   **Launchpads**: Create launchpads to support new blockchain projects, allowing startups to raise funds and reach broader audiences (e.g., similar to Pump.fun).
-   **Development Environments**: Build tools and environments, like Remix, to facilitate Ethereum-compatible development on ICP.
-   **Messaging Systems for Decentralized Networks**: Develop messaging systems that enhance communication within decentralized applications and networks, supporting the Ethereum ecosystem on ICP.

### What We’re Looking For

-   **Innovative Use of Bitfinity Network**: Projects should creatively leverage Bitfinity's EVM compatibility on ICP, offering unique or improved functionality for Ethereum-based applications.
-   **Originality and Impact**: The project must bring a fresh idea to life rather than replicate existing solutions. We’re looking for ideas that provide new utility or significantly enhance current DeFi, NFT, gaming, or infrastructure solutions.
-   **Fully Functional Deployment**: Projects must be deployed on the Bitfinity testnet and accessible for user interaction.
-   **Accessible and Well-Documented Code**: All code should be available on GitHub, open-sourced under a permissive license, and include thorough documentation.
-   **Clear and Detailed README**: The README should explain the project’s scope, objectives, and how to interact with the dApp.
-   **Demonstration Video**: A recorded demo should walk viewers through the project’s functionalities, codebase, and key features.

### Judging Criteria

-   **Ethereum Compatibility**: Does the project make effective use of Ethereum compatibility through Bitfinity, enabling a seamless user experience or expanded functionality on ICP?
-   **Creativity and Originality**: How innovative is the dApp in its approach, theme, or use of ICP’s unique features to enhance Ethereum-based applications?
-   **Functionality and Completeness**: Is the project fully functional, and does it achieve its intended purpose in a reliable, user-friendly way?
-   **Code Quality and Documentation**: Is the code well-structured, documented, and easy for others to understand and extend?
-   **Bonus Points**: Projects that provide feedback on using Bitfinity Network and highlight any areas of improvement or potential use cases.

### Prizes

1. USD 3k in ICP grants
2. USD 1.5k in ICP grants
3. USD 0.5k in ICP grants

# Resources

-   [ICP Ninja](https://icp.ninja)
-   [ICP Hackathon Cheatsheet](https://www.notion.so/ICP-Hackathon-Cheat-Sheet-b2921239266149de81021412f572351c?pvs=21)
-   [Developer Documentation](https://internetcomputer.org/docs/current/home)
-   [Developer Forum](https://forum.dfinity.org/)
-   [Community Discord](https://discord.com/invite/cA7y6ezyE2)
-   [Educational Resources](http://internetcomputer.org/education)
-   [AI DevRel](https://icp-ai-chat-frontend.vercel.app/)
-   [BITFINITY EVM](https://docs.bitfinity.network/)
-   [Tutorial BITFINITY -1](https://www.youtube.com/playlist?list=PLUDcVqFK2t-C36KaTMzV3y1wu8Hf-qyAI)
-   [Tutorial BITFINITY -2](https://www.blog.bitfinity.network/how-to-deploy-a-solidity-smart-contract-to-the-bitfinity-evm/)
-   [Azle Book](https://demergent-labs.github.io/azle/the_azle_book.html)
-   [Azle 101](https://dacade.org/communities/icp/courses/typescript-smart-contract-101/learning-modules/b14741ea-ee33-43a4-a742-9cdc0a6f0d1c)

# Cycles

Ask your hacker house mentor for cycles coupons, then follow the steps outlined here:

```bash
# 1. Make sure you are using the correct developer idenity. Check with:
dfx identity whoami
# 2. Redeem the coupon:
dfx cycles redeem-faucet-coupon <coupon_code> --ic
# 3. Check your new cycles balance:
dfx cycles balance --ic
```

# How to Submit

## Bounty Submission

To submit a bounty for the hackathon - open a NEW [Issue](https://github.com/ICP-Hacker-House/Devcon_BKK/issues/new/choose) on this repository before the deadline.
Set the title of the Issue as follows: Bounty Submission (Easy/Medium).
For example: "Bounty Submission Easy"
See an example bounty submission [here](https://github.com/ICP-Hacker-House/Devcon_BKK/issues/2).
In order for your submission to be considered, include the following things in the Issue description:

-   link to a Github repository containing **your** project code (main branch is considered only)
-   link to canister on mainnet (e.g. `https://5zugh-4yaaa-aaaag-qjqra-cai.raw.icp0.io`)
-   Your ICP principal for the payout (from the OISY wallet)

Note the submission criteria:

-   The issue must be created from a github user
-   Team submissions are not accepted here
-   No re-use of previous works and plagiarism. Projects that explicitly re-used or plagiarized other works may be reported and subjected to the award cancellation

Once you submitted the issue, approach your mentor Moritz Fuller at the hacker house to review your submission.
![Photo on 08 11 24 at 16 02](https://github.com/user-attachments/assets/d7248c18-ac60-4090-9bc8-1e8db04d5468)


## Track Submission

To submit a project for the hackathon - open a NEW [Issue](https://github.com/ICP-Hacker-House/Devcon_BKK/issues/new/choose) on this repository before the deadline.
Set the title of the Issue to Team #(number) - (name of the project).
For example: "Team #42 - SuperCoolSwap"
See an example project submission [here](https://github.com/ICP-Hacker-House/Devcon_BKK/issues/1). Make sure you read the "What we're looking for" and "Judging Criteria" sections for each track before submitting.
In order for your submission to be considered, include the following things in the Issue description:

-   link to a Github repository containing **your** project code (not just the template!) and a README.md on how to run it (main branch is considered only)
    -   your project must be built on ICP/ Bitfinity, and all code must be in the repo above
    -   No re-use of previous works and plagiarism
    -   Projects that explicitly re-used or plagiarized other works may be reported and subjected to the award cancellation
-   include a video to showcase your project
-   project description
-   what Track you want to apply for
-   team participants
    -   please use GitHub username for everyone
-   link to canister on mainnet (e.g. `https://5zugh-4yaaa-aaaag-qjqra-cai.raw.icp0.io`)
-   your ICP principal for the payout (from the OISY wallet)

# Judging

While the mentors will be judging submissions, each group will be presenting the project to hackers around their table in a small committee.

The winner(s) of each track will then present their project on stage.

[DFINITY Hackathon Terms and Conditions](https://www.notion.so/dfinityorg/DFINITY-HACKATHON-TERMS-AND-CONDITIONS-Fully-On-Chain-with-ICP-1faf692d49a64c89afb5589a7219eee2?pvs=4)

# Payout

Create an oisy wallet [here](https://oisy.com/) to receive tokens.
