# AwesomeRealignment
a list of resources that help one understandf the current popular topics in Ethereum ecosystem

## Native Rollups

arbitrary horizontal scaling using an EVM-in-EVM precompile to cheaply verify EVM execution within the EVM. This precompile would allow developers to programmatically spin up new L1 EVM instances, unlocking a supercharged version of execution sharding where the number of shards is unbounded (rather than capped to 64 or 1024 shards) and individual shards are programmable rollups (with programmable governance, sequencing, gas) known as "native rollups"

- [OG reddit post](https://www.reddit.com/r/ethereum/comments/1f81ntr/ama_we_are_ef_research_pt_12_05_september_2024/)
- [What might an "enshriend ZK-EVM" look like](https://notes.ethereum.org/@vbuterin/enshrined_zk_evm)
- [Ethereum Endgame re-viisted](https://research.anoma.net/t/ethereum-endgame-revisited/810#p-3268-state-transition-function-3)
- [SNARK proving ASICs (time-stamped)](https://youtu.be/URCH2d1cdyg?feature=shared&t=371)

## Based Rollups / Sequencing / Preconfs

A rollup is said to be based, or L1-sequenced, when its sequencing is driven by the base L1. More concretely, a based rollup is one where the next L1 proposer may, in collaboration with L1 searchers and builders, permissionlessly include the next rollup block as part of the next L1 block. Based rollups can offer users preconfirmations (preconfs) on transaction execution. Based preconfs offer a competitive user experience for based sequencing vs. centralized sequencing, with latencies on the order of 100ms.

- [Minimal viable merged consensus(OG Based rollups)](https://ethresear.ch/t/minimal-viable-merged-consensus/5617?u=0xapriori)
- [Based Rollups—superpowers from L1 sequencing](https://ethresear.ch/t/based-rollups-superpowers-from-l1-sequencing/15016)
- [Spire Litepaper](https://static1.squarespace.com/static/63d9d0eeb883fa4084c0e70d/t/66e22cc722499d7d97411495/1726098634802/The+Based+Stack+by+Spire+Labs+-+Litepaper.pdf)
- [Vanilla Based Sequencing](https://ethresear.ch/t/vanilla-based-sequencing/19379)
- [Based Sequencer Selection](https://ethresear.ch/t/based-sequencer-selection/19747)
- [Rollup-Centric Considerations of Based Preconfimations](https://ethresear.ch/t/rollup-centric-considerations-of-based-preconfimations/20160)
- [Taiko-mono](https://github.com/taikoxyz/taiko-mono)
- [Facet Protocol Docs](https://docs.facet.org/)
- [Based Preconfs FAQ](https://hackmd.io/@samlaf/based-preconfs-faq)
- [Preconfdotwtf (ZuBerlin)](https://preconf.wtf/)
- [The Preconfirmation Gateway ~ Unlocking Preconfirmations: From User to Preconfer](https://ethresear.ch/t/the-preconfirmation-gateway-unlocking-preconfirmations-from-user-to-preconfer/18812)
- [Avoiding Accidental Liveness Faults for Based Preconfs](https://ethresear.ch/t/avoiding-accidental-liveness-faults-for-based-preconfs/19888)
- [Credibly Neutral Preconfirmation Collateral](https://ethresear.ch/t/credibly-neutral-preconfirmation-collateral-the-preconfirmation-registry/19634)
- [Analyzing BFT & Proposer-Promised Preconfirmations](https://hackmd.io/@EspressoSystems/bft-and-proposer-promised-preconfirmations)
- [Leaderless and Leader-Based Preconfirmations](https://ethresear.ch/t/leaderless-and-leader-based-preconfirmations/19971)

## Booster Rollups

Booster rollups are rollups that execute transactions as if they are executed on L1, having access to all the L1 state, but they also have their own storage. This way, both execution and storage are scaled on L2, with the L1 environment as a shared base. Put another way, each L2 is a reflection of the L1, where the L2 directly extends the blockspace of the L1 for all applications deployed on L1 by sharding the execution of transactions and the storage.

- [Booster rollups - scaling L1 directly](https://ethresear.ch/t/booster-rollups-scaling-l1-directly/17125)
- [Booster rollups part 2: ZK-EVM as a ZK coprocessor](https://ethresear.ch/t/booster-rollups-part-2-zk-evm-as-a-zk-coprocessor/17279)


## Beam Chain

![image](https://github.com/user-attachments/assets/580d73fb-69e0-4d39-8331-f4e16ece2dbf)

- [Keynote: [title redacted]](https://app.devcon.org/schedule/8GH8TR)
- [Proving multi-client Beam chain](https://ethresear.ch/t/proving-multi-client-beam-chain/21027)
- [You’re Not Bullish Enough! Ethereum Roadmap & Beamchain (time-stamped)](https://www.youtube.com/watch?v=8mJDt8TGebc)
- [Deep Dive into Ethereum's Beam chain](https://www.youtube.com/watch?v=88FDeg5JaUk&pp=ygUgYmFua2xlc3MganVzdGluIGRyYWtlIGJlYW0gY2hhaW4%3D)
- [Peter Szilagyi on Beam Chain](https://x.com/peter_szilagyi/status/1856353006729736456?s=46&t=bVZ6b-mdBr3JpXAez04mAg)

## Censorship Resistance - Multiple Concurrent Proposers / FOCIL

Basic ingredients of BRAID (MCP):
1. Run k separate parallel chains using the same validator set.
2. All chains are synchronized (i.e. slot i is common to all chains)
3. The “block” in slot i is the union of all transactions in slot i of all k chains.
4. After consensus on the union, execution/ state transition occurs using agreed upon deterministic rule, e.g. Decreasing priority fees (Robinson and White), Knapsack (maximize set of priority fees you can execute), Execute As needed (to be released)

- [BRAID: Implementing Multiple Concurrent Block Proposers](https://www.youtube.com/watch?v=mJLERWmQ2uw)
- [BRAID: Devcon lightning talk](https://www.youtube.com/watch?v=afmlcyB3h0I)
- [Multiple Concurrent Proposers (Protocol Symposium)](https://www.youtube.com/watch?v=NNWfYRUMtf4)
- [Censorship resistance in On-chain Auctions](https://www.mechanism.org/spec/01)
- [Multiplicity: A Gadget for Multiple Concurrent Block Proposers](https://ethresear.ch/t/multiplicity-a-gadget-for-multiple-concurrent-block-proposers/14962)
- [Fork-Choice enforced Inclusion Lists (FOCIL): A simple committee-based inclusion list proposal](https://ethresear.ch/t/fork-choice-enforced-inclusion-lists-focil-a-simple-committee-based-inclusion-list-proposal/19870)
- [EIP-7805: Fork-choice enforced Inclusion Lists (FOCIL)](https://eips.ethereum.org/EIPS/eip-7805)
- [On Multi-proposer Gadgets and Protocols (FOCIL vs. BRAID)](https://hackmd.io/xz1UyksETR-pCsazePMAjw)

## Application Specific Sequencing 

Application specific sequencing gives individual apps the power to take control of how their transactions are sequenced via verifiable sequencing rules. 

- [Credible Decentralized Exchange Design via Verifiable Sequencing Rules](https://arxiv.org/pdf/2209.15569)
- [Atlas whitepaper](https://www.fastlane.xyz/Atlas_Whitepaper.pdf)
- [A New Era of DeFi with App-Specific Sequencing](https://sorellalabs.xyz/writing/a-new-era-of-defi-with-ass)
- [How do we make dApps great again with Application-Specific Sequencing](https://www.semanticlayer.io/blog/10)
- [Application specific sequencing infrastructure trade-offs](https://arxiv.org/pdf/2209.15569)
- [Intents & Solvers Are Just ASS (App Specific Sequencing)](https://www.youtube.com/watch?v=LHpybw9xHCA)

## Ethereum is the World Computer, always has been

The _World Computer_ is a global shared mainframe on top of which applications can be built, enabling those applications and the users participating
in them to seamlessly interact without needing to agree on a shared actor that everyone trusts.

- [Revisiting the World Computer](https://user.fm/files/v2-261b7914c204931fbf213d7d35307264/worldcomputer.pdf)
- [Ethereum's North Star](https://dba.xyz/ethereums-north-star/)

