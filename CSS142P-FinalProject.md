CHAPTER 1\. PROJECT TITLE AND TEAM INFORMATION

Project Title:  
Monte Carlo Simulation of Player Retention Under Alternative Pity Systems in an FGO-Style Gacha Model

Team Members:  
\[Member 1 Name\] – \[Student Number\] – \[Role\]  
\[Member 2 Name\] – \[Student Number\] – \[Role\]  
\[Member 3 Name\] – \[Student Number\] – \[Role\]  
\[Member 4 Name\] – \[Student Number\] – \[Role\]

Course and Section:  
CSS142P: Modeling and Simulation Theory  
Section: BM17

Instructor:  
Prof. Crizepvill F. Dumalaog

Primary WSC Track:  
Analysis Methodology

Secondary WSC Track:  
Data Science for Simulation

Assigned Team Roles:  
Project Lead – John Benedick B. Bagorio  
Simulation Model Developer – Carmelo Jose M. Acampado  
Data and Parameter Researcher – Christian Emmanuel C. Uson  
Experimentation, Results, and Validation Lead – Abraham Judah C. Mamaril

Documentation Lead \- Carmelo Jose M. Acampado

Brief Project Description:  
This project investigates how alternative pity-system designs affect target acquisition, player frustration, and simulated player retention in an FGO-style gacha model. The study will use Monte Carlo simulation to compare a baseline hard-pity system with alternative designs such as improved base rates, soft pity, carryover pity, and token-based exchange. The system is realistically motivated by gacha mechanics used in free-to-play games, where players spend limited resources to obtain rare target characters. The study focuses on whether certain pity-system policies can reduce extreme bad-luck outcomes and improve simulated retention, especially for free-to-play and low-spending players.

CHAPTER 2\. CASE BACKGROUND AND PROBLEM CONTEXT

Free-to-play games commonly use randomized reward systems as part of their monetization and engagement design. One common form is the gacha system, where players use in-game currency, premium currency, tickets, or real money to receive a random character or item. The most desired rewards, such as rare characters or limited units, usually have low drop probabilities. Because of this, players may obtain the target reward in only a few attempts, while others may fail after many attempts despite spending the same amount of resources.

This study uses an FGO-style gacha system as a realistically motivated case. Fate/Grand Order is a well-known character-based gacha game with a low-probability target reward structure and a hard-pity system. In this project, “FGO-style” does not mean that the study will reproduce the complete commercial system of Fate/Grand Order. Instead, it refers to a simplified gacha structure with low target probability, limited banners, fixed pull resources, and a hard pity guarantee after a large number of pulls.

The main stakeholders in this system are players, game designers, publishers, and consumer protection researchers. Players are affected because gacha design influences their chance of obtaining desired characters, their sense of progress, and their willingness to continue playing. Game designers and publishers are affected because gacha design may influence engagement, player satisfaction, and long-term retention. Consumer protection researchers are affected because randomized monetized rewards are often discussed in relation to fairness, transparency, spending behavior, and gambling-like mechanisms.

The current behavior of the system can be summarized as follows. A player enters a limited-time banner with a certain amount of available currency. The player repeatedly performs pulls until the target character is obtained, the player runs out of currency, or the pity threshold is reached. In systems without carryover pity, failed progress may be lost when the banner ends. This can create frustration because the player may spend a large number of pulls without receiving the target or preserving progress for the next banner.

The practical problem is that not all pity systems provide the same player experience. A hard pity system may mathematically protect players from the worst possible outcome, but if the pity threshold is too high, many players may never reach it. A simple increase in the base drop rate may improve average success, but it may not solve the problem of wasted progress. A carryover pity or token-based system may feel fairer because failed attempts still contribute toward future success. However, these alternatives must be evaluated under controlled and comparable conditions.

Simulation is appropriate for this case because gacha systems are stochastic. The result of each pull is random, and player outcomes vary across repeated trials. Monte Carlo simulation is suitable because it can generate thousands of virtual player experiences under different policy scenarios. This allows the study to estimate average outcomes, uncertainty intervals, extreme bad-luck rates, and retention-related effects without requiring private player data from actual game companies.

CHAPTER 3\. RESEARCH QUESTION, OBJECTIVES, AND SCOPE

Primary Research Question:  
How do alternative pity-system designs affect target acquisition rate, player frustration, and simulated player retention in an FGO-style gacha model?

Specific Objectives:

1. To develop a Monte Carlo simulation model of an FGO-style gacha system with a low target SSR rate and hard pity threshold.  
2. To compare the baseline hard-pity system with alternative policies, including improved base rate, soft pity, carryover pity, and token-based exchange.  
3. To estimate target acquisition rate, average pulls required, pity activation rate, extreme bad-luck rate, frustration score, and simulated retention rate under each scenario.  
4. To evaluate whether player segment affects the results by comparing free-to-play, low-spending, medium-spending, and high-spending player profiles.  
5. To conduct sensitivity analysis on key uncertain inputs such as target rate, pull budget, frustration tolerance, and pity threshold.  
6. To recommend the most balanced pity-system design based on fairness, retention, and player experience metrics.

System Boundary:  
The system begins when a simulated player enters a banner with available pull currency and ends when the player either obtains the target, reaches pity, runs out of pulls, or exits the banner. Across multiple banners, the system tracks whether the player continues playing or churns based on simulated frustration and retention probability.

Time Horizon:  
The proposed time horizon is multiple limited-time banners, such as 6 to 12 simulated banners. Each banner represents one decision period where the player may attempt to obtain a target character.

Unit of Analysis:  
The unit of analysis is one simulated player participating in repeated gacha banners.

Performance Measures:  
The main performance measures are:

1. Target acquisition rate  
2. Average pulls required  
3. Median pulls required  
4. Probability of reaching pity  
5. Extreme bad-luck rate  
6. Average frustration score  
7. Simulated retention rate  
8. Segment-level retention rate by player type  
9. Wasted progress rate  
10. Currency depletion rate

Inclusions:  
The study includes target SSR probability, hard pity, soft pity, carryover pity, token exchange, pull budget, player segments, frustration score, and simulated retention probability.

Exclusions:  
The study excludes real-money revenue optimization, actual private player spending data, social influence, character popularity differences, story attachment, game balance, multiple-copy mechanics, PvP ranking pressure, and exact reproduction of any commercial gacha game.

Baseline Scenario:  
Scenario A: FGO-style hard pity system with low target probability and high hard-pity threshold. Pity does not carry over between banners.

Alternative Scenarios:  
Scenario B: Improved base rate with the same hard pity threshold.  
Scenario C: Soft pity system where the target probability increases after a specified number of failed pulls.  
Scenario D: Carryover pity system where failed pull progress continues across banners.  
Scenario E: Token or spark exchange system where each pull grants tokens that can eventually be exchanged for the target.

CHAPTER 4\. CONFERENCE TRACK AND REVIEW OF RELATED LITERATURE

Selected WSC Track:  
The selected primary WSC track is Analysis Methodology because the project focuses on designing and evaluating a simulation-based comparison method for alternative policy scenarios. The study uses Monte Carlo simulation, uncertainty estimation, replication, and sensitivity analysis to compare different gacha pity-system policies. The optional secondary track is Data Science for Simulation because the model uses synthetic player profiles, parameter assumptions, and data-informed behavioral modeling.

Alignment with WSC Reading Set:  
This study is aligned with the supplied WSC paper by Jamali and Lazarova-Molnar on data-driven agent-based modeling. Their work is relevant because it discusses how simulation models can represent systems involving heterogeneous agents, behavioral assumptions, and data-informed parameters. Although the proposed study uses Monte Carlo simulation rather than a full agent-based model, it still uses heterogeneous simulated player segments and behavioral rules to represent repeated decision-making under uncertainty. The supplied paper supports the idea that simulation can be used to explore complex systems when direct experimentation or full real-world data collection is difficult.

Related Literature:

Gan developed a formal model of gacha game pricing using prospect theory and discussed how pity-like mechanisms can function as a form of worst-case insurance after repeated failure. This is highly relevant to the present study because the proposed simulation treats pity systems as design interventions that reduce extreme unlucky outcomes. Gan’s work supports the idea that gacha systems can be analyzed not only as entertainment mechanics but also as probabilistic economic systems.

Xiao, Fraser, and Newall examined player opinions on probability disclosures and pity timers in loot box systems. Their findings are useful because they show that pity timers are recognized by players and can be viewed as relevant fairness mechanisms. This supports the present study’s focus on pity systems as more than a technical probability rule; they may also affect perceived fairness and player willingness to continue.

Ballou, Gbadamosi, and Zendle emphasized that loot box and randomized reward systems contain many design features and should not be treated as a single uniform mechanic. Their work supports the need to compare different gacha structures separately. In the present study, hard pity, soft pity, carryover pity, and token exchange are treated as distinct policies with different effects on player experience.

Mustač et al. studied player churn prediction in a free-to-play mobile video game using supervised machine learning. Their work supports the importance of retention and churn as key outcomes in free-to-play game research. While the present study does not predict churn from real behavioral logs, it uses retention as a simulated response variable affected by repeated success, failure, and frustration.

Burelli discussed customer lifetime value prediction in free-to-play games and highlighted the importance of modeling long-term player value and behavior. This supports the broader relevance of the proposed study because player retention is central to free-to-play game sustainability.

Xiao and Newall argued that probability disclosures alone may not be enough to make loot-box systems ethical or understandable, especially when reward structures are complex. This supports the present study’s view that simply showing drop rates may not fully address fairness concerns. The structure of pity, carryover, and progress preservation also matters.

Several recent reviews and empirical studies have also examined links between loot boxes, microtransactions, gambling-like behavior, financial risk, and problematic gaming. These studies do not directly simulate pity systems, but they establish that randomized reward mechanics are important enough to be studied carefully. The present study builds on this literature by focusing on a specific modeling and simulation question: which pity-system design produces better simulated outcomes under controlled assumptions?

Research Gap:  
Existing studies discuss gacha pricing, loot box complexity, probability disclosure, player spending, and gambling-related risks. However, fewer studies directly compare alternative pity-system designs using a reproducible simulation model that includes target acquisition, frustration, and retention outcomes. This project addresses that gap by using Monte Carlo simulation to compare several pity-system policies under the same synthetic player population.

CHAPTER 5\. PROPOSED CONCEPTUAL MODEL

System Boundary Diagram Description:  
The system contains four major components: the player population, the gacha banner, the pity-system policy, and the retention model.

The player population contains synthetic player types with different pull budgets and frustration tolerance levels. The gacha banner contains the target reward probability, banner duration, pity threshold, and available summon rules. The pity-system policy determines whether progress resets, carries over, increases probability, or accumulates tokens. The retention model updates the player’s continuation probability based on success, failure, currency depletion, and wasted progress.

Conceptual Flow:

1. Initialize player profile.  
2. Assign player type, pull budget, and frustration tolerance.  
3. Select gacha policy scenario.  
4. Start banner.  
5. Player performs pull.  
6. Random number determines success or failure.  
7. If success, record target acquisition and pulls used.  
8. If failure, update pull count, pity progress, token count, and frustration.  
9. If pity condition is reached, award target and record pity activation.  
10. If player runs out of pulls, record failure and update frustration.  
11. If banner ends, reset or carry over progress depending on policy.  
12. Compute retention probability.  
13. Determine whether player continues to next banner.  
14. Repeat until the time horizon ends or the player churns.

Entities or Agents:  
The main entity is the simulated player. Each player has a type, pull budget, frustration tolerance, pity progress, token count, success history, and retention state.

Resources:  
The main resource is pull currency. This may represent Saint Quartz, tickets, premium currency, or a generalized gacha resource. The model does not distinguish between free and paid currency unless the team decides to add a spending proxy later.

State Variables:

1. Player type  
2. Remaining pulls  
3. Pull count on current banner  
4. Pity counter  
5. Token count  
6. Number of successful banners  
7. Number of failed banners  
8. Frustration score  
9. Retention probability  
10. Active or churned status

Events:

1. Start of banner  
2. Pull attempt  
3. Target obtained  
4. Pity triggered  
5. Currency depleted  
6. Banner ended  
7. Pity progress reset or carried over  
8. Retention decision  
9. Player churn

Rules:

1. Each pull generates a random number between 0 and 1\.  
2. If the random number is less than or equal to the current target rate, the target is obtained.  
3. In the hard pity scenario, the target is guaranteed at the pity threshold.  
4. In the soft pity scenario, the target probability increases after a specified number of failed pulls.  
5. In the carryover pity scenario, pity progress is preserved across banners.  
6. In the token scenario, each pull adds one token, and the player can exchange tokens for the target at the exchange threshold.  
7. Frustration increases when the player fails after spending many pulls, runs out of currency, or loses progress.  
8. Frustration decreases or resets partially when the player obtains the target.  
9. Retention probability decreases as frustration increases.  
10. A player churns when the retention decision fails.

Key Equations:  
Let p be the target probability and n be the number of pulls.

Probability of failing after n pulls:  
P(failure after n pulls) \= (1 \- p)^n

Probability of obtaining the target within n pulls:  
P(success within n pulls) \= 1 \- (1 \- p)^n

A simple frustration score may be defined as:  
F \= alpha(L) \+ beta(B) \+ gamma(W) \- delta(S)

Where:  
F \= frustration score  
L \= number of failed pulls  
B \= number of failed banners  
W \= wasted pity progress or lost progress  
S \= successful target acquisitions  
alpha, beta, gamma, and delta \= weighting parameters

A simple retention probability may be defined as:  
R \= max(0, min(1, 1 \- lambda(F)))

Where:  
R \= retention probability  
lambda \= frustration impact coefficient  
F \= frustration score

Assumptions:

1. Each pull is independent unless modified by pity rules.  
2. The player wants one target SSR per banner.  
3. Player behavior can be approximated using pull budget and frustration tolerance.  
4. Retention can be represented by a simplified frustration-based probability.  
5. The model does not predict actual commercial retention rates; it compares relative policy outcomes.  
6. Synthetic player segments are sufficient for exploratory simulation.  
7. All scenarios use the same player population for fair comparison.

CHAPTER 6\. DATA AND INPUT-MODELING PLAN

Required Data:  
The study requires the following inputs:

1. Target SSR rate  
2. Hard pity threshold  
3. Soft pity starting point  
4. Soft pity rate increase  
5. Token exchange threshold  
6. Pull budget per player type  
7. Number of banners  
8. Frustration weights  
9. Retention probability coefficient  
10. Number of simulated players  
11. Number of replications

Expected Data Sources:  
The study will use a combination of public documentation, related literature, and synthetic assumptions. Public gacha documentation will be used for baseline parameters such as target rate and pity threshold. Academic literature will be used to justify the relevance of pity systems, loot-box design complexity, retention, and randomized reward mechanics. Synthetic data will be used for player profiles and behavioral parameters because private player logs are not available.

Observed Values:  
Observed or publicly documented values may include baseline target rate, hard pity threshold, and whether pity progress carries over or resets.

Estimated Values:  
Estimated values may include reasonable pull budgets for free-to-play, low-spending, medium-spending, and high-spending player segments.

Assumed Values:  
Assumed values may include frustration weights, retention coefficients, number of simulated banners, and exact soft pity rate increments.

Calibrated Values:  
If time permits, the team may perform simple calibration by adjusting frustration parameters until the model produces reasonable retention behavior, such as higher churn after repeated failed banners and lower churn after successful acquisition.

Proposed Player Segments:

1. Free-to-play player: low pull budget per banner.  
2. Low spender: moderate pull budget but unlikely to reach pity often.  
3. Medium spender: enough resources to approach pity in selected banners.  
4. High spender: enough resources to reach pity more consistently.

Synthetic Data Generator:  
The synthetic generator will create N players. Each player will be assigned:

1. Player type  
2. Pull budget  
3. Frustration tolerance  
4. Initial retention state  
5. Random seed stream

Limitations of Synthetic Data:  
Synthetic data allows the team to complete the simulation without collecting private or confidential data. However, it limits the conclusions. The results cannot claim to represent real player retention rates. The study can only compare relative outcomes between gacha policy scenarios under the stated assumptions.

CHAPTER 7\. PROPOSED SIMULATION METHODOLOGY AND IMPLEMENTATION PLAN

Simulation Paradigm:  
The study will use Monte Carlo simulation. This is appropriate because the gacha system is based on repeated random trials, and the goal is to estimate outcome distributions across many simulated players and replications.

Software or Programming Environment:  
The proposed implementation environment is Python. Possible libraries include:

1. NumPy for random number generation and array operations.  
2. Pandas for storing simulation results.  
3. Matplotlib for graphs.  
4. SciPy or Statsmodels for confidence intervals if needed.

Model Time Unit:  
The model time unit is one banner. Within each banner, the pull attempt is the smallest event step.

Initialization Procedure:  
At the beginning of each replication:

1. Set the random seed.  
2. Generate the player population.  
3. Assign player types and parameters.  
4. Initialize pity progress, token count, frustration score, and active status.  
5. Select the scenario to be simulated.

Stopping Condition:  
The simulation stops when all banners in the time horizon have been completed or when all players have churned.

Random-Seed Policy:  
Each scenario will use documented random seeds. The same seed list will be used across scenarios to improve comparability. For example, the study may use seeds 42, 123, 2026, 777, and 999 for independent replications.

Preliminary Pseudocode:

For each scenario:  
For each replication:  
Set random seed  
Generate player population  
For each banner:  
For each active player:  
Assign available pulls  
While player has pulls and target not obtained:  
Generate random number  
Determine current target rate  
If random number \<= current target rate:  
Mark success  
Update satisfaction/frustration  
Stop pulling  
Else:  
Update failed pulls  
Update pity counter or token count  
If pity threshold reached:  
Mark success through pity  
Stop pulling  
If player failed:  
Update frustration  
Apply reset or carryover rules  
Compute retention probability  
Determine whether player remains active  
Save outputs  
Compute summary statistics and uncertainty intervals

Justification of Approach:  
Monte Carlo simulation is suitable because gacha outcomes are probabilistic and player-level results vary widely. The method can estimate expected values, variation, and extreme outcomes across thousands of simulated players. It also allows policy scenarios to be compared under identical assumptions.

CHAPTER 8\. VERIFICATION AND VALIDATION PLAN

Verification Procedures:  
The study will use at least four verification checks.

Verification Check 1: Deterministic Success Case  
Set the target probability to 1.0. Every player should obtain the target on the first pull. If not, the pull logic is incorrect.

Verification Check 2: Deterministic Failure Until Pity  
Set the target probability to 0.0 and enable hard pity. No player should obtain the target before pity, and all players with enough pulls should obtain the target exactly at the pity threshold.

Verification Check 3: Conservation of Pull Counts  
For every player and banner, the number of successful pulls, failed pulls, remaining pulls, pity progress, and token count must be logically consistent. The model should not create extra pulls or lose pull attempts.

Verification Check 4: Boundary Test for Zero Pulls  
Players with zero available pulls should not be able to obtain the target unless the model has an explicit free reward rule, which this study does not include.

Verification Check 5: Scenario Rule Check  
In the non-carryover scenario, pity progress should reset after a failed banner. In the carryover scenario, pity progress should remain. This check ensures that scenario-specific policy rules are correctly implemented.

Validation Approaches:  
The study will use at least two validation approaches.

Validation Approach 1: Face Validation  
The team will check whether the model behavior is reasonable based on common understanding of gacha systems. For example, increasing the target rate should generally increase acquisition rate, and adding carryover pity should reduce wasted progress.

Validation Approach 2: Analytical Probability Comparison  
For a simple case without pity, the simulated probability of success within n pulls will be compared with the analytical formula:  
P(success within n pulls) \= 1 \- (1 \- p)^n

If the simulated result is close to the analytical probability within expected sampling error, the basic random pull logic is considered valid.

Validation Approach 3: Extreme-Condition Validation  
The model will be tested under extreme conditions, such as very high pull budgets, very low pull budgets, probability of 0, probability of 1, and very low pity thresholds. The model should behave logically under these conditions.

Validation Conclusion Criteria:  
The model will be considered adequate for the intended purpose if it passes the verification checks, produces results close to analytical expectations in simple cases, and behaves reasonably under extreme conditions. The model will not be claimed to be universally valid for real player behavior.

CHAPTER 9\. EXPERIMENTAL AND ANALYSIS PLAN

Baseline and Alternatives:  
Scenario A: Baseline hard pity system  
Scenario B: Improved base target rate  
Scenario C: Soft pity after a defined number of failed pulls  
Scenario D: Carryover pity across banners  
Scenario E: Token or spark exchange system

Experimental Factors:

1. Target SSR rate  
2. Pity threshold  
3. Pull budget  
4. Player segment  
5. Frustration tolerance  
6. Carryover rule  
7. Token threshold  
8. Number of banners

Proposed Factor Levels:  
Target rate: 0.8 percent, 1.0 percent, 1.2 percent  
Hard pity threshold: 200, 250, 300, 330 pulls  
Pull budget: low, moderate, high  
Player segment: free-to-play, low spender, medium spender, high spender  
Frustration coefficient: low, medium, high  
Carryover rule: no carryover, full carryover  
Token threshold: 200, 250, 300 tokens

Response Measures:

1. Target acquisition rate  
2. Average pulls required  
3. Median pulls required  
4. Probability of reaching pity  
5. Extreme bad-luck rate  
6. Wasted progress rate  
7. Average frustration score  
8. Simulated retention rate  
9. Retention difference by player segment  
10. Scenario ranking

Run Length:  
The proposed run length is 6 to 12 banners per simulated player.

Warm-Up Treatment:  
A warm-up period is not required because the model does not represent a steady-state queueing system. Each player begins with defined initial conditions, and the study focuses on finite-horizon banner outcomes.

Replication Count:  
The initial plan is to use at least 30 independent replications per scenario, with each replication containing at least 10,000 simulated players if computationally feasible. If runtime becomes a concern, the team may reduce the number of players but will report this limitation.

Uncertainty Intervals:  
For each principal output, the study will compute a point estimate and a 95 percent confidence interval. A basic confidence interval may be computed as:  
mean ± t-value × standard error

Where:  
standard error \= sample standard deviation / square root of number of replications

Comparison Procedure:  
The scenarios will be compared based on principal outputs. The preferred scenario should show improvement in retention and fairness metrics without producing unreasonable or inconsistent behavior. The team will avoid claiming that one system is universally best if the result depends heavily on assumptions.

Sensitivity or Robustness Analysis:  
The study will vary important assumptions to test whether the preferred scenario remains strong. Sensitivity tests will include:

1. Lower and higher target rates  
2. Lower and higher pity thresholds  
3. Lower and higher pull budgets  
4. Lower and higher frustration coefficients  
5. Different numbers of banners  
6. Alternative token thresholds

Recommendation Criteria:  
The recommended policy will be the scenario that provides the strongest balance of:

1. Higher target acquisition rate  
2. Lower extreme bad-luck rate  
3. Lower wasted progress  
4. Lower frustration score  
5. Higher simulated retention rate  
6. Consistent performance across player segments

CHAPTER 10\. WORK PLAN, RESPONSIBILITIES, AND RISKS

Proposed Work Plan:  
Day 1: Finalize topic, research question, scope, and scenario definitions.  
Day 2: Complete literature review and parameter table.  
Day 3: Develop conceptual model and pseudocode.  
Day 4: Implement baseline simulation model.  
Day 5: Implement alternative scenarios.  
Day 6: Perform verification checks and fix model errors.  
Day 7: Run experiments and collect outputs.  
Day 8: Conduct validation and sensitivity analysis.  
Day 9: Prepare tables, graphs, and written interpretation.  
Day 10: Finalize proposal or report, reproducibility package, and presentation materials.

Responsibilities:  
Project Lead:  
Coordinates the team, checks progress, ensures the report follows the required chapter format, and manages final integration.

Literature Review Lead:  
Collects and summarizes references on gacha systems, loot boxes, pity timers, probability disclosure, retention, and simulation methodology.

Model Development Lead:  
Implements the Monte Carlo simulation, scenario rules, random seed policy, and output collection.

Verification and Validation Lead:  
Designs and executes verification checks, analytical comparisons, and extreme-condition tests.

Results and Presentation Lead:  
Creates tables, graphs, interpretation, sensitivity analysis, and presentation materials.

Risks and Mitigation:

Risk 1: Lack of real player data  
Mitigation: Use synthetic data and clearly state that the study compares relative outcomes, not actual commercial retention.

Risk 2: Simulation logic errors  
Mitigation: Use deterministic tests, boundary tests, event traces, and scenario rule checks.

Risk 3: Overly complex retention model  
Mitigation: Use a simple frustration-based retention formula and clearly state assumptions.

Risk 4: Time constraints  
Mitigation: Focus on a small number of scenarios and use reproducible Python scripts.

Risk 5: Ethical concerns about gacha systems  
Mitigation: Frame the study as an evaluation of fairness and player retention, not as a tool for maximizing exploitative spending.

Risk 6: Misinterpretation of results  
Mitigation: Report uncertainty intervals, limitations, and sensitivity analysis. Avoid making claims beyond the simulation evidence.

\[1\] Tan Gan. 2023\. Gacha Game: When Prospect Theory Meets Optimal Pricing. arXiv:2208.03602. Available at: [https://arxiv.org/abs/2208.03602](https://arxiv.org/abs/2208.03602)

\[2\] Leon Y. Xiao, Tullia C. Fraser, and Philip W. S. Newall. 2022\. Opening Pandora’s Loot Box: Weak Links Between Gambling and Loot Box Expenditure in China, and Player Opinions on Probability Disclosures and Pity-Timers. Journal of Gambling Studies. DOI: 10.1007/s10899-022-10148-0.

\[3\] Leon Y. Xiao and Philip W. S. Newall. 2022\. Probability Disclosures Are Not Enough: Reducing Loot Box Reward Complexity as a Part of Ethical Video Game Design. Journal of Gambling Issues.

\[4\] Nick Ballou, Charles Gbadamosi, and David Zendle. 2022\. The Hidden Intricacy of Loot Box Design: A Granular Description of Random Monetized Reward Features. Proceedings of DiGRA 2022 Conference: Bringing Worlds Together. DOI: 10.26503/dl.v2022i1.1327.

\[5\] Kuzma Mustač, Krešimir Bačić, Lea Skorin-Kapov, and Mirko Sužnjević. 2022\. Predicting Player Churn of a Free-to-Play Mobile Video Game Using Supervised Machine Learning. Applied Sciences, 12(6), 2795\. DOI: 10.3390/app12062795.

\[6\] Paolo Burelli. 2022\. Predicting Customer Lifetime Value in Free-to-Play Games. arXiv:2209.12619. Available at: [https://arxiv.org/abs/2209.12619](https://arxiv.org/abs/2209.12619)

\[7\] Ruhollah Jamali and Sanja Lazarova-Molnar. 2024\. A Comprehensive Framework for Data-Driven Agent-Based Modeling. Proceedings of the 2024 Winter Simulation Conference. Available at: [https://informs-sim.org/wsc24papers/inv188.pdf](https://informs-sim.org/wsc24papers/inv188.pdf)

\[8\] Emma Gibson, Mark D. Griffiths, Filipa Calado, and Andrew Harris. 2022\. The Relationship Between Videogame Micro-Transactions and Problem Gaming and Gambling: A Systematic Review. Computers in Human Behavior, 131, 107219\. DOI: 10.1016/j.chb.2022.107219.

\[9\] Leon Y. Xiao, Laura L. Henderson, and Philip W. S. Newall. 2023\. What Are the Odds? Poor Compliance with UK Loot Box Probability Disclosure Industry Self-Regulation. PLOS ONE, 18(9), e0286681. DOI: 10.1371/journal.pone.0286681.

\[10\] Anu Sirola, Ruoho Han, and Andrzej Strzelecki. 2023\. Loot Box Purchasing and Indebtedness: The Role of Psychosocial Factors and Problem Gambling. Addictive Behaviors Reports.

\[11\] Joaquín González-Cabrera, Vanessa Caba-Machado, Adoración Díaz-López, and colleagues. 2024\. The Mediating Role of Problematic Use of Loot Boxes Between Internet Gaming Disorder and Online Gambling Disorder: Cross-Sectional Analytical Study. JMIR Serious Games, 12, e57304. DOI: 10.2196/57304.

\[12\] Fate/Grand Order Wiki. 2024\. Rate-Up SSR Pity System. Available at: [https://fategrandorder.fandom.com/wiki/Rate-Up\_SSR\_Pity\_System](https://fategrandorder.fandom.com/wiki/Rate-Up_SSR_Pity_System)

\[13\] GamePress. 2022\. Fate/Grand Order Summon Simulator and Rate-Up Information. Available at: [https://gamepress.gg/grandorder/](https://gamepress.gg/grandorder/)

APPENDIX A. REPRODUCIBILITY PACKAGE OUTLINE

The reproducibility package for this project will include the following items:

1. The simulation model source code.
2. The synthetic data generator or parameter initialization script.
3. A configuration file listing scenario settings, replication counts, and seed values.
4. A dependency list for the runtime environment, such as Python package versions.
5. A documented random-seed procedure for replication and scenario comparison.
6. Instructions for running the baseline and alternative scenarios.
7. Output tables and figures used in the final analysis.

APPENDIX B. FINAL REPORT ROADMAP

The current document is structured as a proposal draft. The final report will later expand this work into the following chapters:

1. Introduction and case background.
2. Objectives, scope, and conference-track alignment.
3. Review of related literature.
4. Conceptual model and assumptions.
5. Data and input modeling.
6. Model implementation.
7. Model verification.
8. Model validation.
9. Experimental design.
10. Results.
11. Sensitivity and robustness analysis.
12. Discussion, limitations, and responsible practice.
13. Conclusions and recommendations.
14. Reproducibility and team contributions.
15. References.

