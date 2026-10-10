# Round 1 feedback (simulated first-year student, ECON BC1003 midterm prep)
Tested: laptop-width pane + 375px mobile emulation; read all source for content/math checks; stress-tested widgets via sliders.

## Ratings (1-5)
- Clarity: 3 (Learn text is tidy but dense; widgets assume algebra the Learn tabs never introduce)
- Usefulness: 3 (good module coverage; thin practice, no review of mistakes, several course topics have no visual)
- Accuracy: 4 (econ content and quiz keys are correct; errors are in widget edge cases and one wording issue)
- Usability: 2 (broken layout styling, no keyboard/screen-reader support for cards and sliders)

## P1 - Bugs / errors
1. Layout: tabs, widgets and quizzes are not styled as intended. `el()` returns a wrapper div, so `tabs`, `widget()` box and `quiz()` box append children to the wrapper, not to the `.tabs` / `.card` element inside it. Result: Learn/Explore/Quiz/Flashcards look like default grey browser buttons, the active tab is not highlighted, and an EMPTY white rounded box appears above every widget and every quiz question (seen on desktop and mobile). Fix: use `firstChild` (as done for `cv`/`out`) for `tabs` and `box`.
2. Lorenz (Income Distribution): no ordering constraint. Set Poorest 20% = 200 and others = 1: Gini = -0.78, "Top 20% share 0%", curve bows above the 45 degree line. Fix: enforce non-decreasing sliders (sort values before computing) or use "share" sliders that auto-rebalance; label raw slider numbers as relative incomes.
3. Supply/Demand + tax: with D=50, S=60 (both reachable by sliders) equilibrium quantity is negative (Q0 = -6.7) and DWL shows -133; with D=50, S=30, t=40 (tax exceeds the gap) Q=0 but DWL = 267 when the true loss is 133 (all of pre-tax surplus). Fix: clamp S < D (e.g. S max = D - 10), cap DWL at 0.5*Q0*(D-S), and add a "tax so high the market disappears" note.
4. Cournot: with a=40 and c=60 (sliders allow it) Total quantity = -10, price 50 (above intercept), profit 100. Fix: clamp c <= a - 5.
5. Unemployment widget: population 100m, employed 200m gives participation 207% and a normal-looking unemployment rate. Fix: cap employed+unemployed <= population (dynamic slider max) or show a warning.
6. Firm costs chart: fixed axes (q to 30, price to 60) so q* goes off-chart (F=50, c=0, d=0.2, P=50 gives q*=125, point and "q*" drawn outside the plot). Fix: scale xmax to max(30, 1.3*q*) or clamp slider ranges. ATC/AVC/P=MR labels also overlap at the right edge on mobile and desktop.
7. Growth widget wording: with A=5%, B=2% the note says "B is 0.2x richer than A". Say "A is 5x richer" / "B is only 0.2x as rich" depending on direction; also says "both started equal" - fine - but ties give "1x richer".
8. Quiz keys are guessable: correct answer is B in about 30 of 47 questions, and Module 3 (Market Transactions) has B correct for all 7. Options are never shuffled on first attempt. Fix: shuffle options per question (store index of correct text) every attempt.

## P2 - Learning-value improvements
1. Mistake review: quiz ends with just "Score x/y". Add a list of missed questions with the correct answer and explanation, a "retry missed only" button, and save missed items so Mixed exam weights them. Exam score is not saved at all and the nav percent has no "best" label.
2. Explanations only say why the right answer is right ("Stagflation.", "Net exports."). Add one line per wrong option or a common-mistake hint (e.g. "8.3% is 10/120 - you forgot unemployed are in the labor force").
3. Missing Explore widgets for topics the Learn/quiz cover: PPF and comparative advantage graph (PPF is defined but never drawn); demand/supply shifts with shortage/surplus and price ceiling/floor (rent control is in Learn and quiz, not Explore); elasticity calculator (midpoint formula) with revenue effect; monopoly graph with MR and MC (Learn says MR < P but no MR curve is shown in Cournot widget); prisoners' dilemma payoff matrix; AD/AS and Phillips curve; real vs nominal GDP / GDP = C+I+G+NX calculator; marginal product/diminishing returns table.
4. S&D incidence claim cannot be tested: the note says the steeper side bears more tax, but there is no elasticity/slope slider. Add slopes for demand and supply so the student sees incidence change.
5. Math level: Costs widget uses TC = F + c*q + d*q^2 and MC = c + 2dq with no derivation in Learn; Budget widget uses Cobb-Douglas with alpha. A no-calculus student will be lost. Add a plain-language "what the sliders mean" line and a numeric table (q, TC, MC, ATC) beside the graph; explain alpha as "share of income spent on X".
6. Learn tabs are walls of text with no worked examples. Add 1 worked numeric example per module (e.g. compute CPI, unemployment rate, opportunity cost) and "common exam traps" boxes (absolute vs comparative advantage, movement vs shift, nominal vs real).
7. "Predict before you look" is advertised on the home page but not implemented. Add a prediction prompt per widget ("what happens to the Gini if the richest 20% lose half?") with reveal.
8. Flashcards: add "I knew it / Again" self-rating with a missed pile, plus a reverse mode (definition -> term). Shuffle permanently mutates the deck order.
9. Mixed exam: header says "12 random questions from every module" but it is 12 random of 47, so some modules may be absent. Sample proportionally or say so; add optional timer and per-module score breakdown at the end.
10. Persist the current module/tab and flashcard position across reloads; show overall progress on the home page.
11. Wording/ambiguity: M2 baker question should say "accounting profit of $60k" (otherwise unclear if her own pay is already deducted); M1 lecture question has near-duplicate options "$40 plus value of lecture" vs "About $40" and "About" is hedgy; M8 adverse selection question is awkwardly phrased ("buyers who know they're sick are most likely to buy it"); M4 cartel question lists "They are illegal" which is also true in many countries - keep "mainly" but note it. M3 elasticity question gives 0.4 without stating absolute value convention.
12. Gini from 5 groups understates true Gini; note "approximate" in output box.

## P3 - Polish / accessibility
1. Flashcards are a div with onclick: not focusable, no role/tabindex, no Enter/Space, no arrow-key navigation. Make it a button with aria-live back text.
2. Slider `<label>` is not tied to its input (no for/id), values are not announced (no aria-live/aria-valuetext); number inputs in the advantage and CPI tables have no accessible names; canvases have no aria-label or text summary (the output boxes help but charts are otherwise invisible to screen readers).
3. Quiz: focus is lost after "Next" (DOM replaced); feedback is not in an aria-live region; right/wrong is shown by color plus text, which is good; after answering, other options stay focusable. Option buttons need no `aria-pressed` but should be a radiogroup or announce result.
4. Nav buttons: add aria-current for the selected module; the percentages are unlabeled ("83%" of what?). On mobile the module strip scrolls horizontally with no hint the Mixed exam button exists off-screen.
5. Mobile: slider rows give a 110px label column, so labels like "Starting GDP/capita ($k)" wrap; tap targets of tabs (default buttons, see P1-1) are small; header subtitle wraps awkwardly. Chart text is 12px and small on phones.
6. `resize` listeners are added per widget and never removed (leak on repeated tab switching); canvas redraw does not react to a live dark/light OS theme switch.
7. Chart nits: "Equality" label clipped at top-right in Lorenz; Efficient/Market point labels can overlap in the externality chart; no shaded DWL triangle there (add it, as in the tax chart); consider a log-scale toggle on Growth so compounding at different rates stays comparable.
8. CPI widget: quantities are fixed and not shown as editable; blank price makes base cost 0 and shows NaN/Infinity. Guard divide-by-zero. Advantage calculator silently turns 0 into 0.001, producing huge opportunity costs; show a message instead.
9. Home page: add a "start here" button and a study-plan suggestion (e.g. Learn -> Explore -> Quiz).

## Verified correct
Budget optimum x = aI/Px, y = (1-a)I/Py; comparative advantage numbers (Ana 0.5 bread/coffee, Ben 1); min ATC = c + 2*sqrt(F*d); S&D CS/PS/DWL/incidence formulas; Cournot Q, P, profit, DWL; Pigouvian DWL for tax below and above e; multiplier; CPI example (105.2, inflation 5.2%); all 47 quiz keys are economically correct.
