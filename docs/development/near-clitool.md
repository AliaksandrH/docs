---
id: near-clitool
title: NEAR Shell
sidebar_label: NEAR Shell
---

## Overview

NEAR Shell is a fully featured NodeJS command line application that wraps `nearlib`.

You use NEAR Shell to connect to the NEAR platform from the terminal to create accounts, deploy contracts and more.

## Installation

```bash
npm install -g near-shell
```

## Usage

In command line, from directory with your project:

```bash
near <command>
```

### Commands

For account:
```bash
  near login                                       # logging in through NEAR protocol wallet (also can create new account)
  near create_account <accountId> <masterAccount>  # create a developer account with --masterAccount(required), publicKey and initialBalance
  near state <accountId>                            # view account state
  near keys <accountId>                            # view account public keys
  near send <sender> <receiver> <amount>           # send tokens to given receiver
  near stake <accountId> <stakingKey> <amount>     # create staking transaction (stakingKey is base58 encoded)
  near delete <accountId> <beneficiaryId>          # delete an account and transfer funds to beneficiary account
```

For smart contract:
```bash
  near build                                   # build your smart contract
  near deploy                                  # deploy your smart contract
  near call <contractName> <methodName>        # schedule smart contract call which
  [args]                                       # can modify state
  near view <contractName> <methodName>        # make smart contract call which can
  [args]                                       # view state
  near clean                                   # clean the smart contract build locally(remove ./out )
```

For transactions:
```bash
  near tx-status <hash>                        # lookup transaction status by hash
```

### Options

| Option                    | Description                                   | Type      | Default               |
| --------------------------|:---------------------------------------------:| :---------|:----------------------|
| --help                    | Show help                                     | [boolean] |                       |
| --version                 | Show version number                           | [boolean] |                       |
| --nodeUrl, --node_url     | NEAR node URL                                 | [string]  |"http://localhost:3030"|
| --networkId, --network_id | NEAR network ID for different keys by network | [string]  |"default"              |
| --helperUrl               | NEAR contract helper URL                      | [string]  |                       |
| --keyPath                 | Path to master account key                    | [string]  |                       |
| --homeDir                 | Where to look for master account              | [string]  |"~/.near"              |
| --accountId, --account_id | Unique identifier for the account             | [string]  [required]|             |
| --masterAccount           | Account used to create requested account.     | [string]  [required]|             |
| --publicKey               | Public key to initialize the account with     | [string]  [required]|             |
| --initialBalance          | Number of tokens to transfer to newly account | [string]  [required]|             |
