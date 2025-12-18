# USD Vote

USD Vote ($USDV) is a **stablecoin-native coordination primitive** that turns dollars into durable, on-chain signals.

Each $USDV token issued is backed 1:1 by a stable asset ($USDC) and remains freely transferable at all times. $USDV does **not** earn yield, require staking, or lock funds. Instead, it introduces a new non-financial property to money: the ability to express **scarce, sustained conviction**.

$USDV is designed to cut through spam, algorithms, and low-cost signaling by making influence explicit, bounded, and economically meaningful.

---

## Core Idea

> **Money should be able to speak.**

$USDV holders allocate portions of their balance to topics they care about. These allocations represent real influence, backed by real dollars, and update automatically as balances move.

Influence is:
- **Non-custodial** — funds never leave the wallet
- **Bounded** — total influence is capped at 100%
- **Deterministic** — outcomes are predictable and simulatable
- **Transfer-aware** — influence follows the money
- **Spam-resistant** — small or stale opinions are removed automatically

$USDV is not a DAO token, a polling system, or a yield product.  
It is a **stable unit of account for attention**.

---

## How It Works

### Allocation Model

- Influence is expressed in **percentage allocations** of a holder’s balance
- Allocations are integer percentages
- The system enforces strict invariants to preserve signal quality

**Parameters:**

- Minimum allocation per topic: **5%**
- Maximum allocation per topic: **100%**
- Total allocation limit: **≤ 100%**
- Implicit maximum topics per user: **20**

No explicit topic cap is required — the minimum allocation enforces it naturally.

---

### Voting

A vote assigns a percentage of a holder’s balance to a topic.

- A topic can be any string (in practice any url)
- Votes must be between **5% and 100%**
- Each topic may have at most one active vote per user
- Votes can be updated or removed at any time
- No default or passive allocations exist

Votes represent **explicit conviction**.

---

### Over-Allocation Resolution (FIFO)

If a new vote causes total allocation to exceed 100%, the system resolves the excess automatically using a **First-In-First-Out (FIFO)** process.

Votes are processed from **oldest to most recent** until the excess is removed:

1. **Reduction (preferred)**  
   Reduce the vote just enough to eliminate the excess, but never below 5%.

2. **Eviction (only if necessary)**  
   If reducing to 5% is insufficient, the vote is removed entirely.

This ensures:
- Newer intent takes precedence
- Older intent persists only if it remains strong
- No residual or dust allocations exist

A vote exists **if and only if** it is at least 5%.

---

### Transfers

$USDV behaves like money:

- Tokens are freely transferable
- No staking, lockups, or cooldowns
- No interaction with voting is required to transfer

However, influence **automatically adjusts**:

- On transfer, all topic allocations are recalculated
- Topic totals update deterministically
- Vote ordering and timestamps remain unchanged

Influence always reflects **current economic weight**.

---

## Fees

$USDV uses minimal, transparent fees to support long-term operation.

- **Swap Fee:**  
  **0.05%** applied symmetrically on buys and sells (with USDC)

- **No voting fees**  
  Expressing or updating conviction is free aside from gas

This preserves accessibility while discouraging frivolous churn.

---

## Design Principles

$USDV is intentionally opinionated:

- **Stablecoin first** — influence is denominated in a neutral, familiar unit
- **Conviction over precision** — small signals don’t matter
- **Scarcity over breadth** — attention is limited by design
- **Determinism over discretion** — no subjective interpretation
- **On-chain enforcement** — no off-chain trust required

These constraints are features, not limitations.

---

## Formal Invariants

At all times, the following must hold:

1. Total allocation ≤ 100%
2. All active votes ≥ 5%
3. Allocations are integer percentages
4. Maximum active topics per user ≤ 20
5. Each topic has at most one vote per user
6. Vote ordering is determined only by vote creation or update
7. Transfers do not modify vote ordering
8. Reduction always precedes eviction
9. Eviction occurs only when reduction cannot resolve excess

---

## What $USDV Is (and Isn’t)

**$USDV is:**
- A stablecoin-backed signaling primitive
- A way to express real, sustained attention
- Infrastructure for coordination and discovery

**$USDV is not:**
- A yield-bearing asset
- A governance token
- A staking system
- A polling or reputation system

---

## Summary

$USDV preserves everything people expect from money — liquidity, simplicity, predictability — while adding a new property: **voice**.

By making attention scarce, explicit, and economically grounded, $USDV turns dollars into signal and ensures that what rises is what people are truly willing to back.

---

*Turns dollars into voice.*
