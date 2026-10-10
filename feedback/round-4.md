# Round 4 feedback (same simulated student, ECON BC1003 midterm prep)
Tested: desktop + 375px emulation (reset to desktop; no horizontal overflow on any of 8 modules x Learn/Explore/Quiz/Flashcards). Drove the page via JS: every Predict box (toggle + answer re-derived by hand), all 51 quiz questions answered wrongly through the real UI with the rendered hint compared to the stored one, the full text of every hint read, the new Tax incidence widget at 10 slider combos, then regression (module quiz, Retry missed, Full quiz again, 12-question exam breakdown, flashcards). Caveat: preview is a data: snapshot, so localStorage is blocked; persistence judged from code only.

## Ratings (round 3 -> round 4)
- Clarity 4.5 -> 4.5 (hints and predict boxes are short and plain; nothing new to confuse)
- Usefulness 4.5 -> 5 (the two biggest gaps I named, wrong-option explanations and elasticity/incidence, are both closed; predict boxes make sliders purposeful)
- Accuracy 5 -> 4.5 (no wrong numbers anywhere; two hints are vague/misleading, see below)
- Usability 4.5 -> 4.5 (unchanged: price-control type is still a bare 0/1/2 slider)

## Fixed since round 3
- Per-widget "Predict first" now above every Explore widget (M1 x3, M2, M3 x3, M4, M5, M6, M7, M8 first widget). Answers hidden until "Show answer", toggle to "Hide answer" works. All 12 answers verified by using the widget: budget doubling (20/10 at I=200), PPF rising cost, Ben coffee 6 -> 0.33 < Ana 0.5, costs q* 15 -> 25, $20 tax buyers +13.3 / sellers -6.7, steeper demand a=3 -> buyers 75%, ceiling at/above 40 not binding, Cournot, Lorenz High inequality Gini 0.46, growth 114.7/26.9 = 4.3x, discouraged worker, Pigouvian tax. All correct.
- Wrong-option hints: all 51 questions have a hint for every wrong option (none on the right one); UI shows the hint matching the option clicked (51/51 matched, also in the end-of-quiz review list and exam review). Retry/shuffle does not misalign them.
- Tax incidence + elasticity widget (M3): elasticity = (P0/Q0)/slope is right (1.2 at a=b=1; 0.5 vs 1.4 at a=3,b=1); buyer/seller burden = a/(a+b), b/(a+b) is right and matches the dollars shown; revenue t*Q and DWL 0.5*t*dQ right; t=0 shows "Add a tax"; t=60 and a=b=3 are fine; no NaN. The "steeper side bears more" claim is now testable.
- Round-3 nit "at or above the equilibrium price" fixed.

## NOT fixed from round 3
Price-control type is still a 0/1/2 slider and Legal price still goes to 150 (silently capped at D); no Qd/Qs bracket; "Review weakest" still tie-breaks by order (M1 0/1 over M5 1/3 and M8 1/3 with more misses) and exam review does not name the module per missed question; PPF endpoint wording; no flashcard position memory/reverse mode.

## New issues
Hints (the only content problems I found; all minor, none contradicts a right answer):
1. M7 Q2 (120 employed, 10 unemployed, 70 not in LF), option "10%": hint says "uses 100 as the denominator". No 100 exists in the problem, so this confuses; say "10 out of 100 is not a number in the problem; the labor force is 130".
2. M4 Q4 (cartels), option "Firms are small": "Cartel members are usually large firms" is an overgeneralization. Say instead "Size is not the issue; each member profits by cheating."
3. M2 Q4 option "Firms should stop hiring": "not necessarily zero" is unclear (zero what?). Say "hire until the extra worker's value equals the wage".
4. Give-aways (arguably fine as teaching, but they hand over the answer): M2 Q5 option $10k ("60 - 70, not 70 - 60"), M6 Q3 option 7 years ("70 / 3.5 = 20"), M3 Q3 option "Cannot tell" ("revenue rises").
5. M1 Q3 option "Pivots inward on the X-axis intercept": hint half-agrees then says the right option, which reads muddled to a beginner.
Widget:
6. Incidence lead text still says "a $20 per-unit tax" but the tax is a slider. Burden rounding can sum to 101% (a=0.25, b=1.75 shows 13% and 88%). Chart shows only the "After tax" dot, no tax wedge/DWL shading like the supply-demand widget above it. Elasticity is point elasticity at the pre-tax equilibrium (not the midpoint formula taught in the worked example), unlabeled.
7. Predict boxes are read-and-reveal only (no way to commit a guess); M8 Fiscal multiplier and M7 CPI calculator have no predict prompt.

## Diminishing returns? Yes
Correctness, flow and layout are solid; I found no wrong numbers or broken states. Further gains are polish and depth. Top 3:
1. Fix the three muddy hints above (M7 Q2, M4 Q4, M2 Q4) and the exam review: show the module name beside each missed exam question and rank "Review weakest" by count missed.
2. Replace the price-control 0/1/2 slider with three buttons, cap Legal price at D, and add the shortage/surplus bracket; add the tax wedge and "buyers = Es/(Es+Ed)" line to the incidence widget.
3. Content depth only if the syllabus needs it: AD/AS and a prisoner's-dilemma payoff matrix, and a q/TC/MC/ATC table for the Costs widget.
