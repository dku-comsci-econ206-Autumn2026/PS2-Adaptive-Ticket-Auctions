# AI, Rent-Seeking, and Ticket Allocation:
## Mechanism Design under Asymmetric Participation Costs

**COMSCI/ECON 206 — PS2**  
**Team FP6 — Longfei Jing, Tian Liang, Jiayang Sun**

---

## 1. Research Question

How does AI's asymmetric reduction of ticket-buying costs change strategic competition and welfare, and which ticket-allocation mechanism is more robust to this change?

Our central idea is that AI does not necessarily reduce participation costs equally for all users.

For a genuine fan, AI may make ticket purchasing somewhat easier. For a professional scalper, automation may support repeated attempts, faster strategic action, or multiple identities at much larger scale.

We therefore model AI as an **asymmetric participation-cost shock**, rather than as a decision maker or perfect anti-scalping detector.

We compare two mechanisms:

1. **Effort Contest**
2. **Verified Lottery**

The project combines game theory, social choice, mechanism design, computational simulation, and exploratory behavioral reflection.

---

## 2. Three-Lens Framework

### Game Theory

The strategic actors are:

- genuine fans;
- professional scalpers;
- the ticketing platform as mechanism designer.

Under the Effort Contest, participants choose costly strategic effort.

For participant \(i\),

\[
u_i
=
V_i
\frac{e_i}{\sum_j e_j}
-
c_i e_i,
\]

where:

- \(V_i\) is the participant's value of winning;
- \(e_i\) is strategic effort;
- \(c_i\) is the marginal cost of effort.

The probability of winning is proportional to effort.

We use an exact heterogeneous complete-information Nash equilibrium as a computational benchmark after values are realized.

---

### Social Choice

The main stakeholders are:

- genuine fans;
- scalpers;
- ticketing platforms;
- performers;
- regulators.

We do not define fairness using only one metric.

We separately evaluate:

- primary fan allocation;
- final fan ownership;
- fan consumer surplus;
- scalper profit;
- rent dissipation;
- social surplus.

This distinction matters because a mechanism can perform poorly for **primary access** while still producing high **final fan ownership** after resale.

Therefore:

> fairness, final ownership, and welfare are not identical objectives.

---

### Mechanism Design

We compare two allocation rules.

#### Mechanism 1: Effort Contest

Participants invest costly effort.

Winning probability is:

\[
p_i
=
\frac{e_i}{\sum_j e_j}.
\]

AI is modeled as a reduction in marginal effort cost.

Main conditions:

- No AI:  
  \[
  (c_F,c_S)=(10,10)
  \]

- AI stress test:  
  \[
  (c_F,c_S)=(5,1)
  \]

The AI treatment is intentionally used as a **stress test**. It is not an empirical estimate of real-world AI cost reductions.

---

#### Mechanism 2: Verified Lottery

Each genuine fan receives one verified entry.

Scalpers may attempt to obtain additional identities.

A scalper choosing \(q\) identities has winning probability:

\[
p_S(q)
=
\frac{q}
{N_F + N_S q}.
\]

Extra identities carry a cost.

Main conditions:

- No AI identity cost:
  \[
  k=0.25
  \]

- AI stress-test identity cost:
  \[
  k=0.10
  \]

The Verified Lottery removes the direct return to speed, but it can still become vulnerable when duplicate identities become sufficiently cheap.

---

## 3. Market Environment

Each simulation represents one representative scarce concert ticket.

### Participants

- 200 genuine fans
- 50 professional scalpers

### Ticket market

- Official ticket price: 100
- Resale price: 180
- Scalper resale-margin value: 80

### Genuine-fan values

Fan attendance values are drawn from:

\[
V_F \sim U[120,260].
\]

### Resale

If a scalper wins the primary allocation, resale occurs when the highest-value remaining fan values attendance at least as much as the resale price.

This allows us to distinguish:

- **primary fan allocation**, and
- **final fan ownership**.

---

## 4. Computational Method

The simulation is implemented in Python using:

- NumPy
- pandas
- Matplotlib

Random seed:

```text
2026
