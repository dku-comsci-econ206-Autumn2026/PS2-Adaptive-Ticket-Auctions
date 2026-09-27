# AI, Rent-Seeking, and Ticket Allocation

COMSCI/ECON 206 Problem Set 2

## Project Overview

This project studies how AI-assisted ticket-buying technology changes strategic competition for limited concert tickets.

The key idea is not simply that AI makes ticket buying easier. Instead, AI may reduce participation costs asymmetrically across different types of buyers. Genuine fans may benefit from convenience, while professional scalpers can use bots, automation, and multiple accounts at scale.

We study how this asymmetric reduction in participation cost changes effort, primary allocation, resale, consumer welfare, and rent dissipation.

## Shared Research Question

How does AI's asymmetric reduction of ticket-buying costs change strategic competition, resale, and welfare in limited ticket markets, and which allocation mechanism is more robust to this change?

## Participants

We model two types of buyers.

### Genuine Fans

Genuine fans value attending the concert.

Each fan has a private value:

v_i ~ Uniform[a, b]

A fan who obtains a ticket directly receives utility based on the difference between the attendance value and the official ticket price.

### Scalpers

Scalpers primarily value tickets for resale.

Their private economic value comes from the expected resale margin:

resale price - official ticket price.

Scalpers may benefit more strongly from AI because automation can support repeated attempts, bot usage, and multiple-account strategies.

## Role of AI

AI is modeled as an asymmetric reduction in participation cost.

Without AI:

- fan effort cost = 10
- scalper effort cost = 10

With AI:

- fan effort cost = 5
- scalper effort cost = 1

The central mechanism is therefore:

AI assistance
→ asymmetric cost reduction
→ different optimal effort
→ changed primary allocation
→ changed resale and welfare outcomes

## Strategic Model

The platform first commits to an allocation mechanism.

Buyers then observe their private type, value, and participation cost and simultaneously choose their strategic action.

The full environment is therefore modeled as a two-stage Bayesian game.

For the classical benchmark, we use a Tullock-style contest. With one prize, n symmetric players, prize value V, and linear effort cost c × e, the symmetric equilibrium effort is:

e* = V(n - 1) / (c n^2)

This benchmark shows why the effect of AI depends on whether cost reductions are symmetric or asymmetric.

## Mechanism A: Effort Contest

Ticket competition is represented as an all-pay or rent-seeking contest.

Participants choose costly effort or attempts.

Higher effort increases the probability of receiving a ticket, but every participant pays the effort cost whether or not they win.

This mechanism approximates speed-based online ticket competition in which repeated refreshing, automation, and computational effort may improve success.

## Mechanism B: Verified Lottery

Each verified identity receives one entry into a randomized ticket lottery.

Additional identities are possible only by paying an identity-creation cost k.

This mechanism removes the direct advantage of speed but may remain vulnerable if AI reduces the cost of creating or managing additional identities.

## Experimental Conditions

We compare both mechanisms under two environments.

### No AI

Fan effort cost = 10

Scalper effort cost = 10

### AI

Fan effort cost = 5

Scalper effort cost = 1

For the verified lottery, we additionally vary the cost of obtaining additional identities.

## Main Metrics

### Primary Fan Allocation Rate

The proportion of tickets initially allocated directly to genuine fans.

### Final Fan Ownership Rate

The proportion of tickets ultimately held by genuine fans after secondary-market resale.

### Fan Consumer Surplus

The total difference between genuine fans' attendance values and the prices they actually pay.

### Scalper Profit

Scalper resale revenue minus official ticket payments and strategic participation costs.

### Rent Dissipation

The real resources spent competing for a fixed number of tickets, including effort and identity-creation costs.

## Computational Method

We use Python in Google Colab.

Main libraries:

- NumPy
- pandas
- Matplotlib

The main simulation uses numerical best-response approximations for strategic effort or account creation and repeated Monte Carlo allocation.

No GPU is required.

## Computational Comparison

The main comparison is:

Effort Contest / No AI
→ Effort Contest / AI

and

Verified Lottery / No AI
→ Verified Lottery / AI.

We test whether AI-driven asymmetric cost reduction increases scalper participation and whether the verified lottery reduces rent-seeking and protects consumer welfare.

## Resale

Primary allocation and final ownership are reported separately.

Scalpers who obtain tickets may resell them to losing fans whose values are high enough to pay the resale price.

Ticket prices and resale payments are treated as transfers when calculating social surplus, while effort and identity costs are treated as real resource costs.

## Evidence Boundary

All computational results use synthetic agents and stipulated parameters.

The simulation demonstrates how the stated model behaves under its assumptions. It does not estimate the causal effect of AI in real ticket markets.

Behavioral evidence from classroom or peer interaction is treated as exploratory evidence only.

## Reproducibility

The main notebook is:

`auction_simulation.ipynb`

The repository contains:

- model definitions;
- parameter settings;
- numerical best-response procedures;
- fixed random seeds;
- simulation outputs;
- figures;
- reproducibility instructions.

## Team

- Jiayang Sun
- Tian Liang
- Longfei Jing

## Course

COMSCI/ECON 206 — Computational Microeconomics  
Fall 2026
