# CosmWasm Smart Contracts I

## SETUP WSL2 (windows only)

Open PowerShell as Andmin and run

```bash
  dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

Check requirement for runing WSL2

```bash
    open Run and winver
```

Enable VM feature

```bash
  dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

Set WSL as your default version

```bash
  wsl --set-default-version 2
```

install Ubuntu 20.04 LTS in microsoft store

## Messages in CosmWasm

Cosmos blockchains operate by sending various kinds messages around. Messages are sent from users to contracts, from contracts to contracts, and even from contracts to other blockchains. Blockchain platforms are, after all, protocols for sending, processing, and logging authorized messages around. Most of these messages are commands to do something, but some are just queries for information.

We'll see a lot of CosmosMsg messages in our contract work, including:

- BankMsg
- StakingMsg
- DistributionMsg
- IbcMsg
- WasmMsg
- GovMsg

But the primary types of messages we need to worry about are the messages interacting with our smart contract.
All smart contracts need to handle three kinds of incoming messages:

- InstantiateMsg: what happens when an instance of a smart contract is created (startup code)
- ExecuteMsg: the kinds of actions users can tell a smart contract to execute (write operations)
- QueryMsg: the kinds of queries for information users can send to a smart contract (read operations)

Incoming messages of these three types will be passed off to our contract's entry points: the instantiate(), execute(), and query() functions. These may be indicated in the template you pull with the macro attribute

```bash
#[entry_point]
```

which you should now replace with:

```bash
#[cfg_attr(not(feature = "library"), entry_point)]
```

All of our core code will be located in these three functions, or in functions called by these three functions.

## Installing Rust

https://docs.microsoft.com/en-us/windows/wsl/install
https://docs.microsoft.com/en-us/windows/wsl/install-manual
