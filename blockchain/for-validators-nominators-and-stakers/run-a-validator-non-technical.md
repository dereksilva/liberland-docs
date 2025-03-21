# Run a validator

[Join the node operator room](https://matrix.to/#/#liberland-node:matrix.org)

## Introduction

This guide will walk you through the process of setting up a new validator on Liberland Chain for non technical people.
[You can follow along a outdated but still working video here](https://www.youtube.com/watch?v=ufV7igODxcQ)

## Requirements

* Liberland wallet with at least 200 LLD. [Ask to be onboarded](https://matrix.to/#/#liberland-node:matrix.org)
* [PolkadotJs wallet](https://polkadot.js.org/extension/)
* A helper [Ask here if you dont have one](https://matrix.to/#/#liberland-node:matrix.org)
* [On-chain citizenship](../for-citizens/onboarding.md)

## Claim on-chain citizenship
* You will need your LLD, LLM, and an onchain citizenship to proceed. Follow the [Claim citizenship](../for-citizens/onboarding.md) steps to proceed.
* At the end of this process, you should have a wallet, and a funded citizen account on the mainnet. Log into [blockchain.liberland.org](https://blockchain.liberland.org/signin)
  with your liberland account to verify everything works so far.

## Set up a server
* In this step, we will buy some server space and give access to a helper so he can setup the technical part of a validator for us.
* This guide is for AWS lightsail or DigitalOcean, but other server providers will work too.

### Option 1: AWS Lightsail

[Go to AWS](https://aws.amazon.com/) and create an account.

* In search, type lightsail
* Under Instances, click Create instance
* Select Linux/Unix, OS Only, Ubuntu 22.04 LTS, scroll down and select the plan with at least 4 GB RAM, 1 vCPU and 60gb SSD
* Scroll down and click on "Create instance"
* Wait for a few minutes for a server to initialize
* Ask for your helper to guide you through the next steps

### Option 2: Digital Ocean

[Go to Digital ocean](https://www.digitalocean.com/)

* Ask your helper for his ssh pubkey.
* Create a digital ocean account
* Click on create, and pick droplet
* Create a Ubuntu, version 22 droplet with at least 50 of disk and 4GB of RAM.
* When creating a droplet, under access it will give option of password or ssh. Pick ssh. This will allow your helper to securely connect to your server.
* Add the ssh pubkey from your helper to the server.
* Create the droplet.

* Wait for a minute for droplet to initialize.
* Click on the droplet and copy the IP address and sent the IP to your helper.
* Wait for the helper to inform you that a validator is running. This might take a few hours or days
* Do note that at this time, the helper has full access to your validator, and may decide to *hack* it, which is a potential security risk.
* In order to revoke access to your helper Go to Settings > Security and under SSH keys find your helper and under more pick delete.
* If something is wrong and you need to re-add access to your helper, go to Settings > Security and add ssh key of your helper again.

* At this point, your helper will give you your validator id which is needed for the next step

## Add validator

> Note that in order to do this step you will need some LLD, so ask someone to give you some if you dont already have it.

1. Visit Staking in Liberland dAPP:
   * [Mainnet](https://blockchain.liberland.org/home/staking)
   * [Bastiat (Testnet)](https://testnet.liberland.org/home/staking)
2. Click "Switch to validator" button.
3. Set your commission (20 is fine) and session keys you got from installation step to `Keys from rotateKeys` form.
   * Note: if you lost your session keys, see [Regenerating session keys](regenerate_session_keys.md)
4. Click "Start validator" button and sign the transaction.
5. Optionally, click on add stake and stake some LLDs

## Verify

Immediately after adding validator, you should see it as "Waiting":

1. Visit Staking Accounts on Polkadot.js Apps:
    * [Mainnet](https://polkadotjs.blockchain.liberland.org/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/staking/actions)
    * [Bastiat (Testnet)](https://polkadotjs.blockchain.liberland.org/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/staking/actions)
2. Click "Waiting" button.
3. You should see your Stash account in the "Intentions" table.

You are now officially a validator on Liberland! Enjoy the staking rewards!

Now you have to wait to see if it gets elected to current set of validators. You may need to wait until new era starts and then the chance of being elected is based on the amount of staked LLD. To see current set of validators:

* If everything works so far, congratulations, you are now a validator on Liberland!
* It is customary to tip your helper after getting a validator. 50 LLD is a good amount, that you will earn back quickly with your newly running validator.

## Optional: add nominators
[Join the node operator room](https://matrix.to/#/#liberland-node:matrix.org)
Once your validator is up and running and you have a solid track record of no downtime you can ask other LLD holders to nominate your validator node.
