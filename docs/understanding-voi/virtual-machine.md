# Virtual Machine

Every node in the Voi blockchain runs a virtual machine that evaluates the logic in smart contracts and smart signatures with the transactions that are calling them. 

Right now this virtual machine interprets TEAL which contains the order of operation for the logic that is to be executed. This ultimately results in a success or a fail. 

If the virtual machine fails to resolve the logic then any state changes that would have occurred are not committed to the ledger.  

If the virtual machine successfully resolves the logic then any state changes are recorded in the next block that is written to the ledger. 

In future, nodes in the Voi blockchain will be able to run multiple virtual machines in a modular way. 