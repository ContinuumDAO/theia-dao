# Theia DAO: On-chain governance using Aragon OSx

## Notes

### How does the DAO work?

A DAO has a **core contract** specific to that organisation. **Plugins** are accessed via an on-chain repository that can be connected to the DAO. The set of rules that govern the relationship between the DAO and the plugins are called **permissions**. There are some Aragon plugins available, and custom plugins can be built and added to the registry to allow them to be accessed by the DAO.

### The DAO Contract

The DAO contract holds funds, manages permissions, and holds metadata and the ENS name. There are six base functionalities:

1. Execution of arbitrary actions
    - Execute on-chain decisions made by the DAO
    - Send money as decided by the DAO
2. Asset management
    - Track balances
    - Includes native, ERC20, ERC721, and more, as defined by plugins
3. Upgradeability
    - Can be upgraded in the future
4. Callback handling
    - Can include callback functions
    - Includes onERC__Received
5. Signature validation
    - Can process transactions that were signed off chain
    - Forwards them to a signature validator
6. Permission management
    - The previous five functionalities are only allowed by addresses as defined by this module.
    - Usually the authorised address is only the DAO
    - Can also include EOAs if desired