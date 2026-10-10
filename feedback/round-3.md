# Round 3 feedback (same simulated student, ECON BC1003 midterm prep)
Tested: desktop pane + 375px emulation (reset to desktop; scrollWidth stayed 375 on all 8 Learn tabs). Drove the page via JS plus screenshots: Learn tab of all 8 modules, price ceiling/floor and PPF widgets at many settings, M3 quiz (answered badly on purpose) -> "Retry missed only" -> "Full quiz again", and the mixed exam breakdown + "Review weakest". Re-did the arithmetic of every worked example. Caveat: preview is a data: snapshot, so localStorage is blocked; persistence judged from code only.

## Ratings (round 2 -> round 3)
- Clarity: 4 -> 4.5 (worked examples make each Learn tab concrete; numbers are small and easy to follow)
- Usefulness: 4 -> 4.5 (worked example + traps is the biggest gain; missed-question weighting in the exam is smart; wrong-option explanations still absent)
- Accuracy: 5 -> 5 (all 8 worked examples correct; widgets correct; one wording nit below)
- Usability: 4 -> 4.5 (both flow bugs fixed; no overflow states left; remaining friction is the 0/1/2 slider and no flashcard position memory)

## Worked examples + exam traps (all 8 present in every Learn tab, checked)
M1 $60, $10/$5: 6 tickets/12 snacks, slope -2, $90 -> 9/18: correct. M2 MC = 168-150 = 18 < P 20: correct. M3 midpoint: -20/90 = -22.2%, 2/11 = 18.2%, e = 1.22 (elastic), revenue 1000 -> 960 (consistent, falls when elastic): correct. M4 MR = 100-2Q = 20 -> Q 40, P 60, profit 1,600, competitive Q 80, DWL 800: correct and matches the Cournot widget at n=1. M5 shares 5/10/15/20/50%, poverty 3/20 = 15%: correct. M6 GDP 70+20+25+(10-15) = 110, real growth ~3.5%, 70/2.5 = 28: correct. M7 LF 162, 4.3%, 62.3%, CPI 105, real wage about -1%: correct and matches the widget defaults. M8 Pigouvian tax $20, multiplier 4, +$400b: correct. Traps are all econ-correct (imports-subtracted explanation, AVC vs ATC shutdown, flow vs stock, level vs change).

## Round-2 items: fixed / not fixed
FIXED
- P1-1 "Retry all" after "Retry missed only": now shows "Full quiz again" and returns to the full 7 (checked 7 -> 6 missed -> retry 6 -> full 7).
- P1-2 PPF slider clamp: replaced by "% of max" slider; A=20/B=100/100% gives Food 20, Gadgets 0, consistent.
- P2-1 Price control rework: type slider 0/1/2; non-binding ceiling (p 60, D100/S10) and floor (p 20) say "Not binding ... changes nothing" with DWL 0; binding ceiling p=30 gives shortage 30, DWL 300 (= 0.5*20*30, correct); floor p=60 gives surplus 60, DWL 300; p=1 or p=150 gives DWL 2,700 = total surplus, correct; axis now xmax = D so bars are not tiny.
- P2-3 Unemployment overflow: pop min 230 = max emp 200 + max un 30, so impossible states can no longer occur.
- P2-4 Exam breakdown: sorted by module number, % and "review" flag, "rough signal" caveat, "Review weakest" button works (jumps to that module's Learn tab).
- P2-6 Worked example + exam traps per Learn tab.
- P2-10 (code): module/tab saved in econ-pos and restored; missed question texts saved in econ-missed and used to weight the exam's 8 non-guaranteed slots. Both look right in code.
- P3-1 PPF axes now 1.15 x A/B, slope label no longer on the line. P3-2 Growth now prints "$689m", "about 14,000x". P3-5 role=tab removed (aria-pressed instead).
NOT FIXED
- P2-2 / wrong-option explanations still absent. P2-5 costs math (no q/TC/MC/ATC table, alpha not explained). P2-7 per-widget "predict first" prompt (still only the home-page sentence). P2-3 elasticity, AD/AS, game theory, GDP/real-vs-nominal widgets. Tax-incidence slopes. Flashcard position not persisted, no reverse mode, no "cards you needed Again" review. Log-scale growth. Review list does not name the module for each missed exam question.

## New items (prioritized)
P2
1. Price-control slider "Type: 0 none, 1 ceiling, 2 floor" is a bare number slider; use 3 radio/segment buttons. Legal price slider goes to 150 but silently caps at D (D=100: slider 150 behaves as 100, floor note says "at 100"). Set its max to D.
2. Wording: p exactly equal to equilibrium says "above the equilibrium price of 40" (it is equal). Say "at or above".
3. Price-control still has no CS/PS numbers and no Qd/Qs markers on the chart (only one "Quantity traded" dot); the shortage/surplus is only in the outputs. Draw the gap as a bracket.
4. "Review weakest" tie-break picks 0/1 (M1) over 0/2 (M3); weigh by number missed, not just %. Missed-question review in exam mode should show the module name beside each question so the student knows where to go.
P3
5. PPF at 100% says "all remaining Gadgets" when none remain; at 0% says opportunity cost 0 (true, slope 0, but confusing to a beginner: add "rises as you move right").
6. Exam retry: "Full quiz again" after an exam retry drops the module breakdown (mixed flag lost); minor.
7. Home page "Progress: x of 8 modules quizzed" does not show missed-question count or exam best.

## Diminishing returns? Mostly yes
Layout, correctness, and flow are now solid; I found no wrong numbers. Remaining gains are content depth. Top 3 for learning, in order:
1. Per-wrong-option explanations (or at least a "common mistake" line) in the 47 quiz items: the single biggest teaching gap, since the review list now exists but only repeats the right-answer explanation.
2. Elasticity widget (midpoint formula, revenue effect) fused with slope sliders in the tax-incidence chart: closes the "steeper side bears more" claim that still cannot be tested, and elasticity is an almost-certain midterm topic.
3. Per-widget "predict, then reveal" prompts plus a q/TC/MC/ATC table for the Costs widget: turns the sliders from toys into practice, and de-mystifies TC = F + cq + dq^2 for non-calculus students. (AD/AS and a prisoner's-dilemma matrix are next, only if the syllabus covers them.)
