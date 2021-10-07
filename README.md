# The Graph Allocation Optimization

## ⚠️ Automatic Allocations

The possibility of running the allocation script automatically is now pushed to the main repository.
But **be careful**, there are still many **edge cases** where the script doesn't work like desired.
Allocations to broken subgraph leads to problems in the automatic deallocation. If broken allocations
are created, you have to manually close these allocations with a 0x0 POI. See [The Graph Academy - Manually Closing Allocations](https://docs.thegraph.academy/technical-documentation/tips-and-tricks/manuallyclosingallocationsforfailedsubgraphs).

It is recommended to use the semi-automated way of using the tooling. So for the cli tool set the flag --automation to false
(default false). And in the dropdown in the web application set the automation to false.
## General
Allocations are a very important tool for indexers. Depending on the amount of allocations and the distribution of allocations on different subgraphs the indexing reward is calculated. Of course, this could be done manually - or a rule for the distribution of the stake could be set in advance. However, this might lead to not getting the optimum indexing reward.

Therefore, we developed a tool (contributions appreciated) that calculates the optimal allocation distribution using optimization algorithms. For this purpose, the relevant variables in the indexing reward formula are queried using the meta subgraph, these are transferred to a linear optimization model and the model calculates the optimal distribution of the allocations on the different subgraphs.

The tool creates an allocation script (**script.txt**) that can be used to change the allocations. It is possible to supply different parameters such as **indexer address** , **parallel allocations**, **threshold**, **maximal allocation in % per Subgraph**. The thresholds can be set as the minimum percentage increase of the indexing rewards and also taking into account the transaction costs for reallocations.

The **goal** is to provide TheGraph indexers a tool to gain the highest possible return of indexing rewards from their invested stake and to react to changes in the ecosystem in an automated way. The optimization process takes every allocation and distribution of allocations and signals into consideration. After every successful optimization the results for the next optimization will differ from the previous one. It is an **ever changing process of optimization** because the relevant variables for the formula change. Therefore everyone who would use our allocation optimization script would benefit from it. Manually keeping track of changing circumstances in the ecosystem and distribution would be too time consuming.

## Anyblock Analytics and Contact

Check out [anyblockanalytics.com](https://anyblockanalytics.com/). We started participating in TheGraph ecosystem in the incentivized testnet as both indexers and curators and are Mainnet indexers from the start. Besides professionally running blockchain infrastructure for rpc and data, we can provide benefits through our data analytics and visualization expertise as well as ecosystem tool building.

**Contact:**

Discord: yarkin#5659  
E-Mail: [yarkin@anyblockanalytics.com](mailto:yarkin@anyblockanalytics.com)