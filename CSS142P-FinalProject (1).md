PROJECT PROPOSAL PLAINTEXT ADDITIONS / REVISIONS

ADD TO CHAPTER 2\. CASE BACKGROUND AND PROBLEM CONTEXT

This study does not treat the simulation results as direct market research data from Fate/Grand Order or from any other commercial gacha title. Instead, the study frames the model as a simulation-based policy comparison using an FGO-style baseline. Actual market research would require direct player surveys, official player retention records, spending logs, or validated behavioral datasets from game companies or player communities. Since such data is not publicly available and may involve privacy or access restrictions, this project uses public gacha mechanics and synthetic player segments to conduct a controlled simulation experiment.

Therefore, the study should be interpreted as market-informed simulation evidence rather than actual market measurement. The model can show how different gacha design policies may affect target acquisition, frustration, wasted progress, and churn propensity under stated assumptions. However, it cannot claim to predict actual FGO player retention or commercial revenue. This framing keeps the study realistic, ethical, and defensible within the limits of a modeling and simulation project.

ADD TO CHAPTER 3\. RESEARCH QUESTION, OBJECTIVES, AND SCOPE

Additional Objective:  
To distinguish between actual market research and simulation-based market insight by clearly identifying which inputs are publicly documented, which are estimated, and which are synthetic assumptions.

Additional Scope Statement:  
The current project will not claim that its churn results are actual player churn rates. Instead, the churn-related output will be interpreted as simulated churn propensity or modeled churn tendency. This means that the model estimates how likely a synthetic player is to stop participating under the defined frustration assumptions, not how real players actually behave in Fate/Grand Order or in any commercial title.

REVISE BASELINE AND ALTERNATIVE SCENARIOS IN CHAPTER 3

Baseline Scenario:  
Scenario A: FGO-style hard pity system  
The baseline uses a low target rate and a high hard pity threshold. Pity progress does not carry over across banners. This scenario represents the reference policy.

Alternative Scenarios:  
Scenario B: Lower hard pity threshold  
The target rate remains the same as the baseline, but the hard pity threshold is reduced. This tests whether making pity easier to reach improves acquisition and churn propensity.

Scenario C: Improved base rate  
The target rate is increased while keeping the baseline hard pity rule. This tests whether a direct rate increase improves acquisition and reduces frustration.

Scenario D: Carryover pity  
The target rate and hard pity threshold remain the same as the baseline, but pity progress carries over between banners. This tests whether preserving failed progress reduces wasted effort and improves simulated retention.

Scenario E: Token or spark exchange  
Each pull grants one token. When enough tokens are accumulated, the player can exchange them for the target reward. This tests whether visible guaranteed progress improves player outcomes compared with hard pity alone.

ADD TO CHAPTER 5\. PROPOSED CONCEPTUAL MODEL

Additional Output Variable:  
Churn Propensity

The model will use the term churn propensity instead of actual churn rate. Churn propensity refers to the simulated tendency of a player to stop participating based on the model’s frustration and retention formula. This is not equivalent to real-world player churn. The term is used to avoid overstating the meaning of the output.

Additional State Variables:

1. Churn propensity  
2. Wasted pity progress  
3. Carryover pity progress  
4. Token balance  
5. Scenario policy state  
6. Player segment

Additional Rules:

1. In the baseline scenario, pity progress is reset when the banner ends.  
2. In the lower-pity scenario, the pity threshold is reduced but progress still resets.  
3. In the improved-rate scenario, the target probability increases but pity behavior remains unchanged.  
4. In the carryover-pity scenario, unused pity progress is preserved for the next banner.  
5. In the token/spark scenario, each pull grants one token, and accumulated tokens can be exchanged for the target once the threshold is reached.  
6. Churn-related output is recorded as churn propensity, not as actual market churn.

REVISE CHAPTER 6\. DATA AND INPUT-MODELING PLAN

Data Framing:  
The project uses three levels of input evidence:

1. Publicly documented mechanics  
   These include public references for gacha rate structures, hard pity, and whether pity progress carries over. These values are used only to motivate the simplified FGO-style baseline.  
2. Literature-supported assumptions  
   These include ideas from prior studies on gacha monetization, pity systems, probability disclosure, loot box complexity, microtransactions, and player retention. These sources justify why the modeled factors are relevant.  
3. Synthetic simulation assumptions  
   These include player pull budgets, frustration weights, churn propensity coefficients, player segments, and behavioral thresholds. These values are not claimed to represent actual FGO players. They are used for controlled comparison across scenarios.

Additional Parameter-Provenance Entries:

Parameter: Churn output label  
Value: Churn propensity  
Source Type: Modeling decision  
Rationale: Avoids claiming that synthetic retention behavior represents actual market churn.

Parameter: Carryover pity rule  
Value: No carryover or full carryover  
Source Type: Scenario design  
Rationale: Tests whether preserving failed progress improves simulated retention-related outcomes.

Parameter: Token/spark threshold  
Value: 200, 250, or 300 tokens  
Source Type: Assumed scenario design  
Rationale: Represents a visible guaranteed-progress system.

Parameter: Player segment  
Value: Free-to-play, low spender, medium spender, high spender  
Source Type: Synthetic assumption  
Rationale: Allows testing whether pity systems affect different resource levels differently.

Parameter: Replication count  
Value: At least 30 independent replications per scenario  
Source Type: Simulation methodology  
Rationale: Supports confidence intervals and uncertainty estimation.

Parameter: Confidence interval  
Value: 95 percent interval for main stochastic outputs  
Source Type: Statistical analysis plan  
Rationale: Shows whether observed scenario differences are stable across replications.

ADD TO CHAPTER 7\. PROPOSED SIMULATION METHODOLOGY AND IMPLEMENTATION PLAN

Updated Scenario Matrix:

Scenario A: Baseline FGO-style hard pity  
Base rate: 0.008  
Pity threshold: 330  
Carryover: No  
Token/spark: No

Scenario B: Lower hard pity  
Base rate: 0.008  
Pity threshold: 250  
Carryover: No  
Token/spark: No

Scenario C: Improved base rate  
Base rate: 0.010 or 0.012  
Pity threshold: 330  
Carryover: No  
Token/spark: No

Scenario D: Carryover pity  
Base rate: 0.008  
Pity threshold: 330  
Carryover: Yes  
Token/spark: No

Scenario E: Token/spark exchange  
Base rate: 0.008  
Pity threshold: 330 or none, depending on final implementation  
Carryover: Optional  
Token/spark: Yes, exchange at 250 or 300 tokens

Additional Methodological Note:  
The initial simulation output that varies only base rate and pity threshold will be treated as a pilot experiment. The final experiment will include carryover pity and token/spark exchange because these policies better represent alternative fairness mechanisms. This improves the study by comparing different structural designs rather than only changing numerical rate parameters.

ADD TO CHAPTER 8\. VERIFICATION AND VALIDATION PLAN

Additional Verification Check: Token Conservation  
For the token/spark scenario, the model must verify that each pull adds exactly one token and that tokens are deducted or reset only according to the defined exchange rule. The model should not create or remove tokens unexpectedly.

Additional Verification Check: Carryover Preservation  
For the carryover scenario, a player who fails to obtain the target should retain pity progress into the next banner. For the no-carryover scenarios, the same player should lose pity progress after the banner ends.

Additional Validation Approach: Analytical Probability Check  
For a no-pity case, the simulated target acquisition rate will be compared against the analytical probability:

P(success within n pulls) \= 1 \- (1 \- p)^n

This validates the basic random pull logic before more complex pity rules are interpreted.

Additional Validation Approach: Pattern Validation  
The model should produce expected behavioral patterns. Increasing the target rate should increase acquisition. Lowering the pity threshold should reduce extreme bad luck for players who can reach pity. Carryover pity should reduce wasted progress. Token exchange should increase visible progress toward guaranteed acquisition. If the model does not show these expected patterns, the implementation or assumptions must be reviewed.

ADD TO CHAPTER 9\. EXPERIMENTAL AND ANALYSIS PLAN

Additional Analysis Requirement:  
The final analysis will report 95 percent confidence intervals for major outputs, including acquisition rate, average pulls, frustration score, and churn propensity. This prevents the study from relying only on single-run results.

Pilot Result Framing:  
The current base-rate and pity-threshold simulation will be reported only as a pilot result. The pilot suggests that increasing the base rate may have a stronger effect on target acquisition than reducing the hard pity threshold from 330 to 250, especially if many players do not have enough pulls to reach pity. However, the pilot is not enough to support the final recommendation because it does not yet include carryover pity, token/spark exchange, player-segment analysis, or uncertainty intervals.

Additional Sensitivity Tests:

1. Vary base rate from 0.008 to 0.010 and 0.012.  
2. Vary pity threshold from 330 to 250\.  
3. Compare no-carryover pity against carryover pity.  
4. Compare hard pity against token/spark exchange.  
5. Vary token threshold from 250 to 300\.  
6. Vary frustration coefficient to test whether churn propensity is sensitive to behavioral assumptions.  
7. Analyze results separately by player segment.

Revised Recommendation Criteria:  
The recommended policy should not be selected only by highest acquisition rate. It should be selected based on the best balance of acquisition rate, lower wasted progress, lower frustration, lower churn propensity, and consistency across player segments.