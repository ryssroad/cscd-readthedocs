# Modules

A module refers to a set of components performing specific network functions.  These modules work together to ensure the proper functioning and security of the Cascadia blockchain.

Here are the production-grade modules that can be used in Cascadia applications:

| abci                | Manages the ABCI protocol communication.                                                 |
| ------------------- | ---------------------------------------------------------------------------------------- |
| api                 | Facilitates the creation of APIs for interacting with the server.                        |
| auth                | Manages authentication operations, accounts, and signatures.                             |
| authkeeper          | Handles the storage and retrieval of authentication data.                                |
| authsims            | Supports simulations within the authentication module.                                   |
| authz               | Provides support for granting and revoking authorization.                                |
| authzkeeper         | Handles the storage and retrieval of authorization data.                                 |
| authzmodule         | Provides module interfaces for authorization operations.                                 |
| authtx              | Manages transaction operations within the authentication module.                         |
| authtypes           | Contains type definitions for authentication operations.                                 |
| baseapp             | A foundational structure upon which the  application is built.                           |
| bank                | Manages token transfer and balance tracking operations.                                  |
| bankkeeper          | Handles the storage and retrieval of banking data.                                       |
| banktypes           | Contains type definitions for banking operations.                                        |
| capability          | Provides support for capability-based security.                                          |
| capabilitykeeper    | Handles the storage and retrieval of capability data.                                    |
| capabilitytypes     | Contains type definitions for capability operations.                                     |
| claims              | Manages operations related to user claims.                                               |
| client              | Provides interfaces and functions for client-side interactions.                          |
| codec               | Offers codec utilities for message encoding and decoding.                                |
| config              | Manages server configuration settings.                                                   |
| crisis              | Manages crisis situations, such as invariant failures.                                   |
| crisiskeeper        | Handles the storage and retrieval of crisis data.                                        |
| crisistypes         | Contains type definitions for crisis operations.                                         |
| dbm                 | Offers a simple database interface for the system.                                       |
| distr               | Manages operations for token distribution and delegation rewards.                        |
| distrclient         | Provides client-side interactions for the distribution module.                           |
| distrkeeper         | Handles the storage and retrieval of distribution data.                                  |
| distrtypes          | Contains type definitions for distribution operations.                                   |
| epochs              | Manages operations related to blockchain epochs.                                         |
| erc20               | Manages operations related to ERC20 token standards.                                     |
| evidence            | Manages evidence of Byzantine behavior.                                                  |
| evidencekeeper      | Handles the storage and retrieval of evidence data.                                      |
| evidencetypes       | Contains type definitions for evidence operations.                                       |
| evm                 | Manages operations related to the Ethereum Virtual Machine.                              |
| feegrant            | Provides support for granting and revoking fee allowance.                                |
| feegrantkeeper      | Handles the storage and retrieval of fee grant data.                                     |
| feegrantmodule      | Provides module interfaces for fee grant operations.                                     |
| feemarket           | Manages operations related to the fee market.                                            |
| genutil             | Provides utility functions for genesis operations.                                       |
| genutiltypes        | Contains type definitions for genesis utility operations.                                |
| gov                 | Manages governance operations within the Cascadia network.                               |
| govclient           | Provides client-side interactions for the governance module.                             |
| govkeeper           | Handles the storage and retrieval of governance data.                                    |
| govtypes            | Contains type definitions for governance operations.                                     |
| govv1               | Contains governance-related types and functions for v1.                                  |
| govv1beta1          | Contains governance-related types and functions for v1 beta 1.                           |
| ica                 | Manages operations for interchain accounts.                                              |
| icacontrollerkeeper | Handles the storage and retrieval of ICA controller data.                                |
| icacontrollertypes  | Contains type definitions for ICA controller operations.                                 |
| incentives          | Manages operations related to blockchain incentives.                                     |
| inflation           | Manages operations related to token inflation.                                           |
| log                 | Provides logging utilities for operations.                                               |
| node                | Provides GRPC-based client-side interactions for nodes.                                  |
| params              | Manages operations related to network parameters.                                        |
| paramsclient        | Provides client-side interactions for the params module.                                 |
| paramskeeper        | Handles the storage and retrieval of parameters data.                                    |
| paramstypes         | Contains type definitions for params operations.                                         |
| paramproposal       | Contains types and functions related to parameter change proposals.                      |
| posthandler         | Manages operations for processing transactions after they have been included in a block. |
| revenue             | Manages operations related to revenue distribution.                                      |
| servertypes         | Contains type definitions for server operations.                                         |
| simapp              | Provides the simulation application.                                                     |
| simappparams        | Contains parameters used for simulations.                                                |
| slashing            | Manages the slashing of validators for misbehavior.                                      |
| slashingkeeper      | Handles the storage and retrieval of slashing data.                                      |
| slashingtypes       | Contains type definitions for slashing operations.                                       |
| staking             | Manages operations related to staking and validators.                                    |
| stakingkeeper       | Handles the storage and retrieval of staking data.                                       |
| stakingtypes        | Contains type definitions for staking operations.                                        |
| streaming           | Provides support for streaming data from the state database.                             |
| storetypes          | Contains type definitions for store operations.                                          |
| tmos                | Provides OS-level utility functions for operations.                                      |
| tmservice           | Provides GRPC-based service interfaces.                                                  |
| types               | Provides foundational types and interfaces for the codec.                                |
| upgrade             | Manages the upgrade of the blockchain software.                                          |
| upgradeclient       | Provides client-side interactions for the upgrade module.                                |
| upgradekeeper       | Handles the storage and retrieval of upgrade data.                                       |
| upgradetypes        | Contains type definitions for upgrade operations.                                        |
| vesting             | Manages operations related to vesting schedules.                                         |
| version             | Manages the current version.                                                             |
