# ClaimFlex Clarity Smart Contract

## Overview

**ClaimFlex** is a Clarity smart contract for managing STX airdrops with advanced admin controls, batch assignments, claim eligibility, and reclaim logic. It is designed for use on the Stacks blockchain.

## Features

- **Admin Controls:**  
  - Assign claimable STX to users (single or batch)
  - Set claim deadlines and minimum claim thresholds
  - Pause/unpause claiming
  - Reclaim unclaimed or expired STX
  - Withdraw unused STX
  - Transfer contract ownership

- **User Actions:**  
  - Claim assigned STX if eligible
  - Automatic eligibility and deadline checks

- **Security:**  
  - Only the contract owner can perform admin actions
  - Error codes for all failure cases

## Contract Structure

- **Maps:**  
  - `claimable-stx`: Tracks claimable STX per user
  - `has-claimed`: Tracks claim status per user

- **Data Vars:**  
  - `contract-owner`: Current admin
  - `total-assigned`, `total-claimed`: Track totals
  - `claim-deadline`: Optional deadline for claiming
  - `claim-paused`: Pause status
  - `min-claim-amount`: Minimum claimable amount

- **Key Functions:**  
  - `set-claimable`, `batch-assign`
  - `claim`
  - `reclaim-unclaimed`, `reclaim-expired`
  - `set-claim-deadline`, `set-claim-paused`, `set-min-claim`
  - `withdraw-unused`, `transfer-ownership`

## Usage

1. **Deploy the contract** to the Stacks blockchain.
2. **Admin assigns STX** to users via `set-claimable` or `batch-assign`.
3. **Users claim** their STX using the `claim` function.
4. **Admin can reclaim** unclaimed or expired STX, pause claims, or withdraw unused funds as needed.

