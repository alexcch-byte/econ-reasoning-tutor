# Round 5 feedback (same simulated student, ECON BC1003 midterm prep)
Tested: desktop + 375px (no horizontal overflow in any module x tab; only the module nav scrolls sideways, by design). Every Explore widget screenshotted. Dark mode could NOT be emulated (the preview is a static snapshot and always renders light), so I injected the dark-theme CSS variables from the stylesheet and redrew: all 8 modules' charts read fine. Driven via JS: Cost table, Control buttons, PD (4 combos), incidence at 8 slider combos, exam end-to-end, module quiz + Retry missed, flashcards.

## Ratings (round 4 -> round 5)
- Clarity 4.5 -> 4.5 (hints clearer; PD widget is easy to follow)
- Usefulness 5 -> 5 (PD and cost table add depth; nothing is missing for a midterm)
- Accuracy 4.5 -> 5 (every number I recomputed is right; all three muddy hints fixed)
- Usability 4.5 -> 4.5 (price-control buttons fix the 0/1/2 slider, but see mobile and chart notes)

## Fixed since round 4
- Price controls: None/Ceiling/Floor are now buttons; Legal price is capped at D. Verified ceiling 30 (Qd 70, Qs 40, shortage 30, DWL 300), floor 60 (surplus 60, DWL 300), floor 100 (Qd 0, Qs 180, DWL 2,700); the not-binding message is correct.
- Prisoners' dilemma (M4): payoffs are a true PD (15>10, 5>2). Best-reply tiles and the "Stable?" flag are correct for all 4 choice combos (only Low/Low is stable). Predict box answer is right.
- Cost table (M2): TC, MC of q-th unit (= TC(q) - TC(q-1)) and ATC are correct, and they recompute when sliders move (checked d=0.2).
- Incidence: tax wedge/DWL shading and "After tax" dot are now drawn; burden now sums to 100% (13%/87% at a=0.25,b=1.75); revenue and DWL right at t=0/20/60 and a=b=3; elasticity labelled "(point, pre-tax)".
- Hints: M7 Q2, M4 Q4, M2 Q4 are all rewritten and now clear (M7 Q2 says the labor force is 120 + 10 = 130).
- Exam review: each missed question has its module name, there is a per-module table, and "Review weakest" picked the module with the most misses (M7, 0/2).
- Regression: quiz, Retry missed (3 of 3), Full quiz, flashcards (Again/I knew it/Prev/Next/Reshuffle) and the 12-question exam all work.

## Not fixed / new issues (all minor)
1. Cost table stops at q=10 always; the optimum q* (15 at the defaults, 25 at P=30) is never in it, and q* is not highlighted. The text says "compare it with the price", but the student cannot see where MC crosses P without scrolling to the chart.
2. Incidence chart: at low slopes (a=b=0.25) the equilibrium is past x=120, so the dot and shading disappear while the cards show revenue 2,800. The "S + tax" label sits on Demand at the right edge.
3. Chart polish: M1 "Indifference (U)" and "Budget" labels collide near the Optimum; PPF and growth charts have odd ticks (13.8, 27.6, 18.4; 24.8, 49.5, 74.3); the demand line dips slightly below the x-axis in the M3 charts; there is still no shortage/surplus bracket (Qd vs Qs) on the ceiling chart.
4. Mobile: the three control buttons stack in a tall column with wrapped text ("Ceiling (max price)"), and "Firm B:" wraps away from its buttons in the PD. Usable, not pretty.
5. PD toggle buttons have no aria-pressed, and the explanation text under the PD is static (always says Low/Low, even when High/High is selected).
6. Older nits (unchanged): predict boxes cannot take a guess; no flashcard position memory or reverse mode; M8 multiplier and M7 CPI have no predict prompt.

## Are further rounds worth it? No
Content is accurate and every previous major gap is closed. What remains is cosmetic (chart ticks and labels, mobile button wrapping, extending the cost table to q*). Fix items 1 and 3 in one pass if you have the time, but another full simulated-student round will mostly re-find the same polish items. Spend the time on studying instead, or re-test only after a larger change such as AD/AS.
