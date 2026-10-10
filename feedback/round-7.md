# Round 7 feedback (same simulated student, ECON BC1003 midterm prep)
Method: drove AD-AS and Phillips through the real sliders/buttons (all sign combos, both time frames), 300 exam draws via pick(), computed option-length stats over all 71 quiz questions, then a 375px pass of all 9 modules x 4 tabs plus the exam (overflow and tap-target measurement, screenshots of every chart type), plus injected dark CSS variables. index.html was not edited. Preview emulation was reset to desktop.

## Ratings (round 6 -> round 7)
- Clarity 4.5 -> 4.5 | Usefulness 5 -> 5 | Accuracy 4.5 -> 5 (no wrong text found now) | Usability 4.5 -> 4.5 (mobile unchanged)

## Fixed (verified)
- AD-AS notes: all 9 shock combos in short run are now right. d+10/c-10 gives Y 120, P 100 "push output the same way... price stays 100"; d-10/c+10 gives Y 80, P 100 (same wording); d+10/c+10 and d-10/c-10 say output cancels and the price moves to 110 / 90. Long run: notes right for every combo (Y 100, P = 100 + d).
- "AD (before)" dashed curve appears for any demand shift in the short run (desktop and mobile, light and dark). Good.
- Okun rule: u = 5 - 0.5(Y-100), floored at 0: d+10 gives 0%, d-10/c+10 gives 15%. Explanatory note under the chart states the rule and the floor.
- Phillips: u 3/pe 3 gives "higher inflation... shifts up"; u 7/pe 5 now says "lower inflation... shifts down" and settles at 4%; u 5 gives the natural-rate note; u 9/pe 8 and u 1/pe 3 also correct. Tile now reads "Expected inflation after adjustment".
- Exam: 300 draws, always 12 questions, modules 1-8 always present (0 misses). M9 appears in 109/300 (36%), mostly one question, up to 3. Not forced any more. Fair.
- M7 Q10 distractor is now "Becomes upward sloping..." and its hint is accurate. Rewritten M9 Q2/Q3 and M4 Q7/Q9 have one clear answer; no ambiguous option found.
- Money chart now visibly converges to the limit line (round 15, $400b).

## Not fixed / only partly fixed
- Answer-length cue: the correct option is still the longest in 43 of 71 questions (61%; chance would be about 25-30%). Worst ratios: M4 Q2 (49 vs 17 avg), M4 Q7 is better but M6 Q7 (48 vs 21), M5 Q3 (51 vs 24), M9 Q1 (82 vs ~56), M4 Q8, M7 Q7, M8 Q4 (all about 2x). Test-wise students will exploit this.
- Skipped by the builder (confirmed still present): tariff chart has no consumer/producer shading and labels collide on mobile; no Solow time path; M1 Explore still overflows 5px (table 343px in a 335px card, page scrollWidth 380); Nash/dilemma wording differs between modules.

## New issues
P1
- None.
P2
1. AD-AS default example hits the floor. Predict prompt says "+10": output 110, price 105, unemployment 0.0%, and the Okun note is only below the chart. A beginner will read 0% unemployment as "full employment is broken" or a bug. Simplest fix (one line): in compute, when Y>100 and the max(0,...) clamps, append " (floor reached: unemployment cannot go below 0%)" to the tile, AND change the PRED/Predict example to +5 (u = 2.5%, Y 105, P 102.5). Alternative: raise the AD-AS natural rate to 6%; costs consistency with Phillips (5%).
2. Dark mode: active buttons (.btn.primary, tabs.on) are white text on #6aa9f0, about 2.5:1 contrast. Fix: in the dark block set a darker --accent for buttons (e.g. #2f6fbf) or use color:#0b1220 on primary.
3. Mobile range sliders are 125px wide and 16px tall, which is a hard tap target; the label column wastes width. Fix: at max-width 480px make .ctl a column (label above, slider 100% wide, min-height 32px thumb).
4. Mobile segmented buttons (Time frame, Game, Nash) stack in a narrow right column (125px, Long run button 61-83px tall). Fix: at <=480px make .row buttons flex:1 1 45% / full width below the label.
P3
5. AD-AS mobile: "Start" label sits under "New equilibrium" and the dot (reads "Sta rt"). Offset the Start label left/below when the shift is small. Tariff mobile: "Made at home" and "Quantity bought", and "World price"/"World price + tariff" overlap the fills; budget chart: "Optimum", "Indifference (U)", "Budget" overlap. Phillips: "Long-run curve" overlaps the x-axis. Fix: drop to 10px font and alternate label sides, or hide secondary labels under 400px (the legend/outputs already say it).
6. Mobile charts are only about 190px tall (Phillips, tariff); use aspect-ratio 4/3 below 480px.

## Other checks
- Mobile overflow: only M1 Explore (+5px); every other module/tab and the exam have scrollWidth 375. Quiz, Flashcards and Learn are fine; buttons are 40px high. Tabs and nav reachable.
- Dark: charts, notes and tiles are readable; only the primary-button contrast is weak (P2 #2).

## Recommendation
One more small build cycle is worthwhile but optional: about 30 minutes for P2 items 1-4 (the floor note plus +5 example, dark button colour, mobile slider/button CSS) and trimming the roughly dozen longest correct options. Content accuracy is now at the point where I found no wrong statements; remaining issues are polish and mobile ergonomics. Skip the Solow time path, tariff shading and Nash wording: they are beyond the syllabus. If the exam is soon, studying with the current build is fine.
