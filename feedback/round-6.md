# Round 6 feedback (same simulated student, ECON BC1003 midterm prep)
Method: read the new Learn text, Explore widgets, quiz and hints in the source and in the live page. Drove every new widget through JS at defaults plus 4-10 other settings and recomputed by hand. Answered every option of all new questions through the real quiz UI. Tested desktop and 375px mobile, 300 simulated exams, flashcards. index.html was not edited.

## Ratings (round 5 -> round 6)
- Clarity 4.5 -> 4.5 (new Learn text is clear; Nash and tariff are very readable)
- Usefulness 5 -> 5 (AD-AS, Phillips, banking, trade fill the real gaps; M9 and Solow go beyond the official topic list)
- Accuracy 5 -> 4.5 (numbers are all right; two explanatory notes are wrong in edge settings, see P1)
- Usability 4.5 -> 4.5 (nine-module nav and exam work on mobile; AD-AS shift is hard to see)

## Verified correct (by hand and in the page)
- Tariff: defaults (P_w 20, t 10) give home price 30, imports 60 -> 30, revenue 300, consumers -750, producers +300, DWL 150. Also correct at (10,10): 600/850/100/150; (20,20) prohibitive: 1,400/800/600; (30,10) and (35,10) cap at 40; (40,x) shows "nothing to import". CS loss = revenue + PS gain + DWL holds each time. The tariff worked example and M9 Q4 ($300) match the widget.
- FX: 1.2 gives EUR 120 and $83.3; 0.8 gives EUR 80 and $125; 1.4/200/50 gives EUR 280 and $35.7. Direction wording (dollar appreciates -> US exports fall) is right.
- Money multiplier: 100 @10% = 1,000 and loans 900; 1000 @5% = 20,000; 300 @25% = 1,200. Interest-rate chain: -1 pt gives +20, +80, and bond $96.15 -> $97.09; +1 gives $95.24; -3 gives $99.01. Bond price falls when rates rise: correct.
- AD-AS: Y = 100 + d - c and P = 100 + (d + c)/2 are correct for all 10 settings tried. Predict answers (110/105 and 90/105) are right. Long run returns Y to 100 with P = 100 + d.
- Phillips: pi = pe + 0.5(5 - u) is correct everywhere tried; the default long-run switch gives u 5%, pi 4%.
- Nash: all three games give the right equilibria (PD: Cheat/Cheat; Coordination: two; Entry: two). Underlines and shading render correctly.
- Solow: k* = (sA/d)^2 gives 36, 12, consumption 8.4 at defaults; 100 and 20 at s = 50% (predict answer right); growth sign flips correctly at start > 100%. M6 Q8 (k = 36) is right.
- Quiz: 20 new questions (3 in M4, 4 in M6, 3 in M7, 4 in M8, 6 in M9). Each answer key is right. Every wrong option shows a hint and the hints are aligned to the correct option. Review-what-you-missed shows them too.
- Regression: M1-M8 quizzes and flashcards still work; exam always returns 12 questions with all 9 modules (300 runs); nav has 10 buttons and scrolls sideways at 375px; no overflow except M1 Explore (+5px).

## Issues
Note: the brief says 26 new questions; I count 20 (3+4+3+4+6). Please confirm nothing is missing.

### P1 (wrong or misleading text shown to the student)
1. AD-AS note (M7) "The shocks partly offset each other" appears whenever neither strict case matches. At demand +10 and cost -10 output is 120 (price 100), and at demand -10 and cost +10 output is 80, so the shocks add up in output. Fix: set the note from the signs of (Y-100) and (P-100) separately, e.g. "Output rises 20 and the price level is unchanged: both shocks push output the same way."
2. Phillips long-run note (M7) always says "once people expect the higher inflation". At u = 7, pe = 5 the long-run switch lands on inflation 4% and expected 4%, so expectations FALL (disinflation). Fix: branch on u > 5: "expectations adjust down, the curve shifts down, unemployment returns to 5% and inflation settles at X%".

### P2
3. AD-AS chart (M7) draws only the new AD curve, so a demand shift is not visible against the old one. Fix: draw a dashed "AD (before)" in short run as the SRAS already is in long run.
4. Unemployment rule is 5 GDP points per 1 point of unemployment. Okun's law in textbooks is about 2 to 1, so a student may memorize the toy ratio. Fix: use 0.5 x (Y - 100) with a "real Okun is about 2 to 1" label, or keep it and say so in the Learn text.
5. Exam: M9 (off-syllabus) is guaranteed at least 1 of the 12 questions, and Nash/Solow questions can be drawn too. Fix: an "Include extra topics" checkbox, default off for M9.
6. Answer-length cue: the correct option is far longer in M9 Q1 (129 vs 30 chars), M4 Q7, M4 Q9, M7 Q10, M9 Q2/Q3. Fix: shorten the key or lengthen the distractors.
7. M7 Q10 distractor "Gets steeper in the long run" is arguably true (the long-run curve is vertical) and the hint only says it does not. Fix: replace it with "Becomes upward sloping".
8. Phillips (M7): in long run the "Expected inflation" tile shows 4% while the slider still reads 5%, which confuses. Fix: label the tile "Expected inflation after adjustment".
9. Tariff chart (M9) does not shade the consumer loss or producer gain (750, 300), and the "World price + tariff" line is drawn at 45 even when the home price is capped at 40. Fix: shade the two areas; stop the line or label it "capped at no-trade price".

### P3
10. Solow (M6) has no time path, so "growth slows and stops" is only told. Fix: add a small k-over-time line. Steady-state k ranges from 0.44 to 10,000 across sliders; limit A to 3 and s to 40.
11. FX (M9) shows only prices; the claim "exports fall" is never quantified, and the inverse quote (dollars per euro) is never shown. Fix: add a "dollars per euro = 1/e" tile.
12. M9 Q4 hint for $900 ("multiplies 30 by 30") is contrived. Fix: "$900 is not tariff x imports under any setting; recompute 10 x 30."
13. Money chart (M8) stops at round 15 and reaches only 79% of the limit at 10%, so it does not look like it converges; ticks 230/460/690 are odd. Fix: 25 rounds, round the y ticks.
14. Learn M8 lists the reserve requirement as a Fed tool without saying it has been 0% since 2020. AD-AS "Inflation this year" in the long run shows a one-time price-level jump as annual inflation.
15. Mobile (375px): AD-AS "Start" label is clipped ("tart"); the Time-frame buttons stack; M1 Explore overflows 5px; the 7 tariff tiles stack in one column (long scroll).
16. Older nits remain: dilemma explanation text is static; Nash widget uses Cooperate/Cheat while the dilemma widget uses High/Low; odd chart ticks.

## Recommendation for next cycle
Fix P1 items 1 and 2 (about 10 lines of note logic), then items 3, 5 and 7. A short round 7 only on the AD-AS and Phillips notes (all sign combinations) is enough. Nothing else needs a full retest. The old rule "a bigger change needs a retest" is now met, and this round found only text-branch bugs, not number bugs. For studying, the Learn text, quizzes and tariff, Nash and bond examples are good enough to rely on; treat M9 and Solow as optional extras.
