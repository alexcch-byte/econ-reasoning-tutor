# Round 2 feedback (same simulated student, ECON BC1003 midterm prep)
Tested: laptop-ish pane (758px), 375px mobile emulation (reset to desktop after); clicked every Explore widget incl. new PPF and Price ceilings/floors at slider extremes; full quizzes in M1 and M3 (deliberately missed some), "Retry missed only", flashcard Again / I knew it / Prev / Next / Reshuffle, and the mixed exam (+ its retry). Re-derived the new widgets' math. Caveat: the preview is a data: snapshot, so localStorage is blocked and I could not test persistence across reloads.

## Ratings (round 1 -> round 2)
- Clarity: 3 -> 4 (styled tabs/cards, "approximate Gini" and tax-disappears notes, prices/slider labels readable; Learn tabs still dense with no worked examples)
- Usefulness: 3 -> 4 (PPF + price controls fill the biggest gaps, missed-question review and retry work, exam breakdown; still thin on explanation depth and practice volume)
- Accuracy: 4 -> 5 (every widget formula and every quiz key I checked is right; round-1 edge-case errors are gone)
- Usability: 2 -> 4 (layout bug fixed, flashcards are real buttons, ctl labels tied to inputs, answer order shuffles; no persistence of position, a few small flow oddities below)

## Round-1 items: fixed / not fixed
FIXED
- P1-1 layout: tabs highlight, cards and quiz boxes render properly, no empty boxes (desktop + mobile, no horizontal scroll).
- P1-2 Lorenz ordering: values auto-sorted (200,1,1,1,1 now gives Gini 0.78, top share 98%); note says Gini is approximate (also P2-12).
- P1-3 Tax edge cases: D min 60 / S max 40 so Q0 > 0; D=60,S=40,t=40 gives Q=0, DWL 133 (= 0.5*13.3*20, correct) plus "market disappears" note.
- P1-4 Cournot: c max 40 vs a min 60; no negative quantity.
- P1-5 Unemployment: warning when employed+unemployed > population (but see P2-3).
- P1-6 Costs axes: xmax scales (F=50,c=0,d=.2,P=50 gives q*=125, on-chart, labels readable on mobile).
- P1-7 Growth wording: "A is 4.3x as rich as B" is directional now.
- P1-8 Quiz key guessing: options reshuffled each question (M3 correct positions were 0,2,3,2,0,0,3).
- P2-1 (mostly): missed-question list with your answer / correct answer / explanation, "Retry missed only", exam best score saved and shown as "best N%".
- P2-3 (partly): PPF and price ceiling/floor widgets added. Math verified: PPF y = B*sqrt(1 - x^2/A^2), slope = -(B^2 x)/(A^2 y) (A80,B60,x40 -> y 52.0, slope 0.43); price control Qd=D-P, Qs=2(P-S), P0=(D+2S)/3, ceiling -> Q=Qs, shortage=Qd-Qs, floor -> Q=Qd, surplus=Qs-Qd, DWL triangle placed correctly (p=20 gives shortage 60; p=60 gives surplus 60).
- P2-9 Exam: now one question from every module + 4 random, header says so, per-module breakdown shown.
- P2-8 Flashcards: Again (to back of deck) / I knew it (removes, counter) work; deck-complete screen. P2-11 wording fixes (baker, lecture, adverse selection) done.
- P3-1/2/3/4 a11y: card is a focusable button, labels tied to sliders, number inputs named, aria-live feedback, aria-current on nav, "best" label on percent, Next gets focus.
- P3-8 CPI/advantage divide-by-zero guarded.

NOT FIXED (or only partly)
- P2-2 Explanations still only say why the right answer is right; no wrong-option/common-mistake hints.
- P2-3 Still no elasticity calculator, monopoly MR/MC explore for non-n=1, prisoners' dilemma matrix, AD/AS + Phillips, GDP = C+I+G+NX / real vs nominal calculator, marginal-product table.
- P2-4 Tax incidence: note still says steeper side bears more, but there are no slope sliders to test that.
- P2-5 Costs math (TC = F + cq + dq^2) still unexplained for non-calculus students; no q/TC/MC/ATC table; alpha not described as "share of income spent on X".
- P2-6 No worked numeric examples or "exam traps" boxes in Learn.
- P2-7 "Predict before you move a slider" is only advice in the home text; no per-widget prompt/reveal.
- P2-10 No persistence of module/tab/flashcard position (untestable here; code only saves quiz bests). Missed questions are not saved or used to weight the exam (P2-1 tail).
- P3-5/6/7 minor chart nits (see below), no log-scale on Growth, no DWL shading issues remain except growth number formatting.

## New items
P1 (confusing / wrong behavior)
1. "Retry all (reshuffled)" after "Retry missed only" retries only the 2-4 missed questions (it reuses the shrunken list), so the label lies and the student cannot get back to the full quiz without leaving the tab. Fix: keep the original question list and use it for "Retry all", or rename to "Repeat these questions" and add "Full quiz".
2. PPF "Food produced" slider is not clamped to "Max Food": set Max Food 20 and Food 40 -> slider still reads 40 but the output says Food 20, Gadgets 0. Fix: set the Food slider's max to A (and update value) whenever Max Food changes.

P2 (learning value)
1. Price-control widget: no legal-price-relative-to-equilibrium cue and no welfare outputs. Add equilibrium quantity, "Qd / Qs at the legal price" markers on the chart axis, and CS/PS/DWL numbers; label a price above equilibrium for a ceiling as "not binding" (right now any price above P0 is auto-called a floor, so a student cannot see that a ceiling above equilibrium does nothing). Also set xmax ~ D+20 (demand ends at 96 but axis runs to 160, so shortage/surplus bars look small).
2. Price-control: floor cases are hard to read; with p=150 the surplus bar runs off the chart and the label vanishes (output box still correct). Cap the slider at ~ D or clip with an arrow.
3. Unemployment overflow case still shows inconsistent numbers (LF 100m but unemployment rate 13% computed from 230m) next to the warning. Limit the sliders instead (employed max = pop - unemployed) so no impossible state is displayed.
4. Mixed-exam breakdown lists modules in random order and shows raw "1/2" with no verdict. Sort by module number, show %, and add a "Weakest: Competition - open Learn" link. With only 12 questions, per-module n is 1-3, so say that it is a rough signal.
5. Review list on score screen: show missed items grouped with the module tab link (for exam) and include the wrong-option hint idea from P2-2; the list currently runs on without visual separation between question and answer lines.
6. Add 1 worked example and a 3-bullet "exam traps" box per Learn tab (the top remaining gap for a no-background student).

P3 (polish)
1. PPF chart: axes fixed to 110 so the frontier fills only ~70% of the plot; "Slope = -0.4" label sits on the tangent line and collides with "You are here" on mobile. Use xmax=A*1.15, ymax=B*1.15 and offset the slope label.
2. Growth: 10%/10%/100 years/$50k start prints "$689,030.6k" and "13,780.6x"; format as $689m / "about 14,000x".
3. Flashcards: after "Deck complete" show which cards needed "Again" and offer "review those"; there is still no reverse (definition to term) mode.
4. Costs chart on mobile: "MC", "q*" and "P = MR" labels crowd at the top-right when q* is large.
5. Tab buttons use role=tab without arrow-key navigation / tabpanel wiring; either drop the roles or complete the pattern.

## Overall
The app is now genuinely usable and the economics checks out. The next-best learning gains are not more widgets but (a) wrong-answer explanations, (b) a worked example per module, (c) persisting position/missed questions. Fix the two small P1 flow bugs first.
