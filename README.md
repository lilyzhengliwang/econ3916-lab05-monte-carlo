# econ3916-lab05-monte-carlo

# Monte Carlo Engine -- Probability & Simulation

## Objective
I used Monte Carlo simulation in Python to estimate probabilities and risk measures by drawing many random cases and counting the results.

## Methodology
- Simulated 10,000 fair coin flips and plotted the running share of heads on a log-scale x-axis, then found the flip after which it stays within 0.01 of 0.5.
- Simulated 10,000 Monty Hall games for the "always stay" and "always switch" strategies and counted the wins for each.
- Calculated the chance of being sick given a positive test with Bayes' Theorem (prevalence 1%, sensitivity 95%, specificity 90%), then checked it by simulating 100,000 people.
- Simulated 10,000 daily returns for a $1M portfolio from a Normal distribution (mean 0.04%, standard deviation 1.2%) and computed Value at Risk (VaR) and Expected Shortfall (ES) at the 95% and 99% levels.
- Estimated pi at several sample sizes (100 to 100,000), averaged the error over 50 trials per size, and fitted a log-log slope to check that error shrinks like 1/sqrt(n).

## Key Findings
- **Coin flips:** 10,000 flips gave 4,985 heads (0.4985). The running share of heads stayed within 0.01 of 0.5 from flip 6,455 onward. Early values were unreliable: the share was 0.5000 at 50 flips, then fell to 0.4700 at 100.
- **Monty Hall:** Switching won 6,694 of 10,000 games (66.9%) and staying won 3,306 (33.1%), close to the theoretical 2/3 and 1/3. Switching won about twice as often as staying.
- **Disease screening:** Only 9.2% of positive tests came from sick people (997 of 10,847), close to the 8.8% from Bayes' Theorem. The disease is rare, so false positives outnumber true positives.
- **Portfolio risk:** On a $1M portfolio, the 95% VaR was $19,494 and the 95% ES was $24,230. The 99% VaR was $27,046 and the 99% ES was $31,221. ES is larger than VaR because it averages the losses beyond the VaR threshold.
- **Convergence rate:** The log-log slope of Monte Carlo error against sample size was -0.532, close to the -0.5 expected for 1/sqrt(n).
