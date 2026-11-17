# Understanding Interaction Models

**Contributor:** Seyeon Park

**Full citation:** Brambor, Thomas, William Roberts Clark, and Matt Golder. 2006. "Understanding Interaction Models: Improving Empirical Analyses." *Political Analysis* 14(1): 63–82. doi:10.1093/pan/mpi014.

## 1. What the paper establishes

The conditional hypothesis of political science ("X raises Y only when Z is present") can be tested using a multiplicative interaction model. However, in this model, the analytical habits of the linear-additive model do not apply as they would. If the constitutive terms (X, Z) are removed, all the remaining coefficients may become biased. The coefficient of X is the effect at Z=0, not the average effect. The conditional marginal effects of interest (β₁ + β₃Z) and their standard errors cannot be determined by looking at a traditional regression results table alone. A review of 156 APSR, AJPS, and JOP papers from 1998 to 2002 found that only 16 papers (10%) met all three criteria.

## 2. Checks for a reviewer

**(a) Verify whether the conditional hypothesis is tested using the linear-additive model.** If the theory or hypothesis is in the form of "the effect of X varies with Z," but only X and Z are placed side by side without an interaction term, the model cannot test the hypothesis. While the method of splitting samples and performing regression separately is allowed, it is important to see whether the efficiency loss is acknowledged.

**(b) Verify whether all constitutive terms are included, and if any are missing, verify whether the omission is justified.** Given X×Z, if X or Z is missing, check whether both of the following conditions are met.
1. There is a natural zero in the variable that interacts with the omitted variable.
2. The fully specified model was estimated to show that β₂ ≈ 0, and its coefficients and standard errors were reported.
- Additionally, "because of multicollinearity" or "because the variables were centered" is not a valid justification.

**(c) Verify whether the constitutive term coefficients are interpreted as unconditional effects.** Look to see whether the coefficient of X is called the "main effect," "average effect," or "independent effect," or whether it is stated as "X is significant and therefore increases Y." This coefficient is only the effect at Z=0. Emphasizing the fact that the coefficient of X has become insignificant after including the interaction term as "the effect of X has disappeared" is the same error.

**(d) Verify that the conditional marginal effects and their standard errors have been reported within a meaningful range of Z.**
1. Binary modifying variable: Report the marginal effects at Z=0 and Z=1, as well as the standard errors (four numbers) for each.
2. Continuous modifying variable: Report the marginal effects and confidence interval plots over the observed range.
- A significant interaction coefficient does not mean that the effect of X is significant at a given Z. Conversely, even if the interaction coefficient is not significant, the effect of X can be significant at a meaningful Z-value. 
- Additionally, look at how many actual observations are included in the interval where the confidence interval excludes zero.

## 3. Evidence

**For (a).** p. 64: "Analysts should include interaction terms whenever they have conditional hypotheses." 
- Estimating a conditional relationship with an unconditional model yields an estimate that reflects not only the causal relationship between X and Y but also the distribution of Z, so "it makes little sense to talk about the unconditional or average effect of X on Y when you have a conditional hypothesis" (p. 73).

**For (b).** p. 66: "Analysts should include all constitutive terms when specifying multiplicative interaction models except in very rare circumstances."
- Removing Z is equivalent to assuming β₂=0. If Z is correlated with X or XZ, then β₀, β₁, and β₃ all exhibit omitted variable bias (p. 67).
- The authors present two necessary conditions for the allowance of omission: natural zero and testing through a fully specified model (pp. 68–69). 
- Multicollinearity cannot be a basis for omission. The larger standard error is the "correct" standard error that reflects the lack of information in the data (p. 70). Centering is merely an algebraic transformation; it changes nothing (p. 71).

**For (c).** p. 72: "the coefficient on the constitutive term X must not be interpreted as the average effect of a change in X on Y as it can in a linear-additive regression model."
- The authors emphasize that the expressions "unconditional," "main," "independent," and "average" are all incorrect.
- When the interaction term is added, the coefficients change because the meaning of the coefficients has changed, not as a sign of multicollinearity (p. 70).

**For (d).** p. 74: "The analyst cannot even infer whether X has a meaningful conditional effect on Y from the magnitude and significance of the coefficient on the interaction term either."
- The quantity of interest is β₁ + β₃Z, whose standard error includes cov(β₁, β₃) (p. 70, equation 8). Since this covariance is rarely reported in regression tables, readers cannot calculate the standard error (p. 74).
- Even if the interaction coefficient is not significant, the marginal effect can be significant at a meaningful Z value. The significance of the interaction coefficients should not be used to determine whether to include an interaction term (p. 74).
- If the modifying variable is dichotomous, four numbers are required; if it is continuous, then a graph is required (p. 74). 
- This principle also applies to limited dependent variable models such as logit and probit (pp. 76–77).

## 4. Scope

**Applies to:** Regression analysis that tests conditional hypotheses using multiplicative interaction terms (X×Z, X², X×Z×J, etc.).
- The modifying variable applies whether it is binary or continuous (p. 66). It applies regardless of whether the dependent variable is continuous or limited (pp. 76–77). 
- Checks (b)–(d) apply when there is an interaction term; check (a) applies when the hypothesis is conditional but there is no interaction term.

**Does not apply to:** when the interaction term is included for control purposes rather than hypothesis testing. For example, the year × region fixed effects do not test a conditional hypothesis, so they are not subject to including the constitutive terms or reporting marginal effects.

**Does not directly apply to:** designs where the estimand is β₃ itself, such as in the 2×2 difference-in-differences (DiD). Brambor et al.'s check targets the conditional marginal effect that "the effect of X depends on Z" (pp. 64–65, 73). Since in DiD, β₃, the difference in change between the treatment group and the control group, is itself the quantity of interest, β₃ and its standard error are the immediate answers. Since this paper does not directly address DiD, it is noted that this boundary is a judgment derived from the paper's purpose. However, even for a DiD paper, if β₁ (the treatment group dummy) is interpreted as a "treatment effect," check (c) applies.

**Edge case:** when the constitutive terms cannot be included due to perfect multicollinearity. For example, the interaction with a variable defined only within a specific group (p. 70, footnote 8). If the author has stated the reason, (b) should stay silent. In the case of discrete modifying variables, including both X×Z and X×¬Z instead of X alone (p. 69, equation 7) is also not a missing constitutive term.

## 5. What failure looks like

The paper estimates models including X, Z, and X×Z, reporting only the coefficients of these three terms. It interprets the coefficient of X as a main or average effect, and concludes that X has an effect conditional on the value of Z merely because the interaction term is significant. There is no marginal effect plot with confidence intervals even though Z is a continuous variable, and no conditional effect is presented with standard errors. This also includes removing an interaction term from the final model on the grounds that it is not significant, or omitting a constitutive term without justification.

## 6. Test cases

**SHOULD trigger:** Gimpel, James G., Karen M. Kaufmann, and Shanna Pearson-Merkowitz. 2007. "Battleground States versus Blackout States: The Behavioral Implications of Modern Presidential Campaigns." *Journal of Politics* 69(3): 786–797.
- The effects of the interaction between battleground status (0–4) and the low-income dummy on voter participation among low-income groups in the election campaign are tested.
- All constitutive terms are included, and citing Brambor et al., the battleground status coefficient is correctly described as the effect on the non-poor (p. 790).
- However, the authors later call the same coefficient the "main effect for battleground status" and read it as general evidence of campaign targeting (p. 791). Triggers check (c).
- The conclusion of the effect on low-income groups is drawn from the significance of the interaction coefficient. Triggers check (d).
- Since the constitutive terms are included, (b) does not apply, and because an interaction model is used, (a) also does not apply.

**Should NOT trigger:** Villamil, Francisco, and Laia Balcells. 2021. "Do TJ Policies Cause Backlash? Evidence from Street Name Changes in Spain." *Research & Politics* 8(4). doi:10.1177/20531680211058550.
- Equation (1) has a Removal × April2019 interaction term, and the results are reported as interaction coefficients (p. 4). Therefore, the careless agent wants to trigger check (d), saying, "This is a binary modifying variable, but you did not report the four numbers."
- However, this study is a 2×2 DiD, with the estimand being β₃ itself (p. 4).
- All constitutive terms are included, β₁ is not interpreted as a treatment effect, and the simulated DiD estimates are presented with confidence intervals (p. 5, Figure 2).
- In this case, if the check triggers, the agent ends up repeating the same criticism in every DiD paper.
