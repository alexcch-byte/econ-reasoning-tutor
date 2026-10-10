# Peer-course comparison (simulated first-year student, no econ background)

Method: web search/fetch of public catalog pages; app content read from index.html (8 modules, ~50 quiz questions, 14 Explore widgets, flashcards, worked examples, mixed exam). Detailed week-by-week syllabi were NOT found for Harvard, Yale, NYU or Princeton (current); I list only what catalog text says.

## 1. Courses and sources
| Course | Source | Key topics (as found) |
|---|---|---|
| Harvard Ec 10a / 10b | https://mankiw.scholars.harvard.edu/class/economics-10a-principles-economics.md ; https://laibson.scholars.harvard.edu/class/ec-10b-principles-economics-macroeconomics ; DCE E-10a https://coursebrowser.dce.harvard.edu/course/principles-of-economics-3 | 10a: markets, efficiency and failure, firm/consumer behavior, taxation, trade, environment, distribution. 10b: growth, inflation, unemployment, business cycle, financial system, capital flows/trade imbalances, monetary and fiscal policy. E-10a adds tariffs, exchange rate. No syllabus PDF found (Mankiw page returned 403 on fetch). |
| Yale ECON 108/110/111 | https://economics.yale.edu/undergraduate/courses/introductory-courses | Page only describes format (108 = no-calculus, quantitative; 110/111 small sections; 111 ~ 116 macro). Topic list NOT found. Only Yale summer S115E syllabus (consumer theory, uncertainty/information, firms, factor markets, general equilibrium) https://summer.yale.edu/sites/default/files/uploaded-files/syllabi/econ-s115e.pdf - a different course; do not treat as 108. |
| NYU ECON-UA 1 (macro) / 2 (micro) | https://bulletins.nyu.edu/undergraduate/arts-science/courses/econ-ua | UA1: measurement (unemployment, inflation, output), long-run growth, booms/recessions, banking system and Fed, stock/bond markets, policy; algebra prerequisite. UA2: consumer choice, profit maximization, product-market equilibrium. No syllabus found. (Note: UA2 is micro, not macro.) |
| MIT 14.01 | https://ocw.mit.edu/courses/14-01-principles-of-microeconomics-fall-2023/pages/syllabus | Supply/demand, consumer theory, production, monopoly, oligopoly, welfare, public goods, externalities; some single-variable calculus. 14.01SC adds international trade, social insurance. |
| Stanford Econ 1 | https://bulletin.stanford.edu/courses/2144841 ; https://summer.stanford.edu/sites/default/files/media/document/2024/ECON%201%20Syllabus%20Fall%202023.pdf | Micro + macro in one course; S&D, competitive equilibrium and efficiency, firms/industries, fiscal and monetary policy, gains from trade, tariffs/quotas (topic outline from a secondary site). |
| Princeton ECO 100/101 | https://www.princeton.edu/~adsera/ECO101_syllabus_Spring2012.pdf | Only a 2012 syllabus found (Baumol & Blinder macro, exams/psets). Current topics not verified; not used in the matrix. |

## 2. Coverage matrix (topics common to peers vs app)
| Topic | Peers | App |
|---|---|---|
| Scarcity, opportunity cost, PPF, comparative advantage | all | Covered |
| Supply and demand, elasticity, surplus, taxes, price controls | all | Covered (strong, with widgets) |
| Consumer theory (utility, indifference, budget) | all micro | Covered (verbal + widget) |
| Costs, profit max, shutdown | all micro | Covered |
| Perfect competition, monopoly | all micro | Covered |
| Oligopoly / game theory | MIT, Stanford, Harvard (some) | Partly (Cournot, prisoners' dilemma only) |
| Externalities, public goods | all | Covered |
| Information (adverse selection, moral hazard) | MIT, Yale S115E | Partly (one paragraph + 1 question) |
| Factor markets / income distribution | Harvard, Yale S115E | Covered |
| GDP accounting, growth | all macro | Covered |
| Unemployment, CPI, inflation | all macro | Covered |
| Business cycles / AD-AS | all macro | Partly (text only, no AD-AS graph or widget) |
| Money, banking, Fed, financial markets | NYU, Harvard, Stanford | Partly (one callout box; no money creation, bonds, stocks) |
| Fiscal/monetary policy | all macro | Partly (multiplier arithmetic; no policy-rate mechanics) |
| International trade, tariffs, exchange rates, trade balance | Harvard, Stanford, MIT SC, NYU | Missing (only comparative advantage; NX as a GDP term) |
| Solow-style growth model | Harvard 10b (likely), intermediate | Missing (verbal diminishing returns only) |
| Behavioral economics | Harvard (varies) | Missing (not found in any catalog text I read) |
| Uncertainty, risk, expected value | Yale S115E, MIT | Missing |
| Economic data / empirics | Yale (intro data courses exist) | Missing |

## 3. Depth comparison
- Math: peers use algebra (NYU) to single-variable calculus (MIT); the app stays at arithmetic and linear formulas. That fits a no-calculus student but is shallower than MIT/Yale 110.
- Graphs: app has strong interactive S/D, costs, Lorenz widgets; peers additionally draw AD-AS, money market, IS-style or exchange-rate diagrams (not in app).
- Game theory: peers vary; the app has a 2x2 PD and Cournot, roughly Stanford/Harvard level, but no Nash equilibrium labeling beyond "dominant strategy", no repeated games.
- Trade, money/banking, AD-AS, Solow, behavioral: one-paragraph or none. This is the main depth gap.
- Columbia's own listed topics (the eight modules) are fully mapped; the gaps are mostly beyond that list.

## 4. Top 8 additions (effort S/M/L; * = beyond the Columbia topic list)
1. AD-AS interactive widget (demand and supply shocks, stagflation) - M. Within Unemployment and Inflation.
2. Money and banking mini-module: money creation, bonds vs interest rates, Fed tools - M. Partly within Columbia's government/inflation topics.
3. International trade: tariffs, quotas, exchange rates, trade balance, with a tariff widget - M.*
4. Game theory expansion: Nash equilibrium, simple payoff-matrix quiz, repeated play - S/M. Within Competition.
5. Solow-style growth widget (savings, depreciation, diminishing returns, tech shock) - M. Within Growth, but graph is beyond intro level.
6. Business-cycle and GDP gap section with recession/Okun's law examples - S. Within Columbia list.
7. Uncertainty and information: expected value, insurance, risk aversion - M.*
8. Behavioral economics short module (framing, loss aversion, present bias) - S/M.* Not verified as a peer-core topic; lowest confidence.
(Also cheap: more quiz items per module, 6-7 now, vs. peers' problem sets - S.)

## 5. What the app does that peer materials do not (from what I could see)
- Predict-first prompts on every widget, tiered per-option hints on wrong answers, and a mixed exam biased toward missed questions.
- Plain-language "common exam traps" and a worked example per module, aimed at beginners; peer pages I found are catalog text only, so the comparison on pedagogy is partial (I did not see their problem sets or lecture videos; MIT OCW and Stanford offer videos/problem sets the app lacks).
- Self-contained, offline, no-calculus path; MIT 14.01 requires calculus and Yale 108 is the only listed no-calculus option.

Caveat: the matrix is based on catalog descriptions, not full syllabi; "peer-common" is my judgment from those blurbs.
