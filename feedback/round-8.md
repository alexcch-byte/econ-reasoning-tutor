# Round 8 feedback (same simulated student, ECON BC1003 midterm prep)
Method: parsed MODS/HINTS from index.html with a script (length stats, full read of all 71 questions with options and hints), drove AD-AS, quiz, retry-missed, flashcards and exam (300 pick() draws) in the preview, then swept all 9 modules x 4 tabs plus exam at 375/480/600/768 and desktop (scrollWidth, slider and canvas sizes, screenshots), plus dark mode by injecting the dark variable block (the static preview ignores colorScheme). index.html not edited; emulation reset to desktop.

## Ratings (round 7 -> round 8)
- Clarity 4.5 -> 4.5 | Usefulness 5 -> 5 | Accuracy 5 -> 5 | Usability 4.5 -> 5 (mobile now genuinely usable)

## Fixed (verified)
- Answer-length cue: correct option is the longest (ties included) in 20 of 71 (28%, was 43); strictly longest in 8 (11%). Chance is about 25%. Cue gone. Options are also shuffled at runtime, so the key position (B-heavy in source: 46 of 71) is invisible to the student.
- Read all 71 questions. Each has exactly one defensible answer, the key is correct, and every existing hint matches its option text (hints are keyed to the original option index and still display on the right shuffled button; checked live). Rewritten M2 Q4, M3 Q7, M4 Q2/Q6, M5 Q6, M6 Q1, M7 Q10, M9 Q1-3 are balanced and clean.
- AD-AS: "(floor reached)" appears only when the Okun formula is clamped (d+10 with c-10: Y 120, u 0% (floor reached)). d+10 alone gives exactly 0% with no note, which is correct (not clamped). Predict is now +5: Y 105, P 102.5, u 2.5%; cost +5: Y 95, P 102.5, u 7.5%; answer text matches the widget.
- Phone pass (375): no horizontal overflow in any of 9 modules x 4 tabs or the exam (scrollWidth 375; M1 overflow gone). Sliders are 245x32 with label above; segmented buttons sit in a 2-column grid; charts are 300px tall (256 on some). AD-AS, Phillips, tariff (now has shaded revenue/DWL with a legend), budget, Keynesian multiplier: labels readable, Start label hidden below 420px so no collision.
- 480px: no overflow, 350x32 sliders. 600: no overflow. 768: no overflow, sidebar layout fine.
- Dark (injected vars): primary/active tab is #2f6fbf with white text, 5.06:1 (was about 2.5:1). Quiz correct/wrong colours, charts, tiles all readable.
- Regression: quiz scoring, wrong-answer feedback, "Retry missed only" (2 of 2), reshuffle, flashcards (flip, Known counter, Again/Prev/Next), exam (12 questions, M1-8 always present in 300 draws, M9 in 119/300, no duplicates) all work. Desktop widgets fine.

## Not fixed / minor
- No hints on later questions: M4 Q7-9, M6 Q7-10, M7 Q8-10, M8 Q8-11, M9 all show only the explanation after a miss, not "why your choice is wrong". Same as before; the older questions have them.
- Solow time path and Nash/dilemma wording differences still skipped (out of syllabus; fine).

## New issues
P1: none.
P2
1. M1 Q3 option "Pivots inward on the X-axis intercept" is ambiguous: a student can read it as "the X-intercept moves inward", which is true, and then the hint says the X-intercept is the point that moves. Reword to "Pivots inward around the X-axis intercept" (fixed point) or "Pivots around the X-intercept, which stays put".
P3
2. 481-600px keeps 16px-high sliders (the 32px track only applies at <=480px); it is fine on tablets but a phone in landscape gets the small thumbs. Extend the slider CSS to max-width 600px.
3. 768px: AD-AS/Phillips "Time frame" buttons stack vertically in the narrow right column, with Long run offset from Short run. Allow .row buttons to wrap in a row (flex-wrap, flex 1 1 auto) at 481-900px.
4. Mobile 375: "AD (after)" and Phillips "Short-run curve" labels sit on top of their curves; legible but slightly cluttered. Nudge labels 6-8px off the line.
5. M1 Q3 and M4 Q4 aside, M9 Q1 options are all 66-68 characters: fine, but the question is the only one with such long distractors; no action.

## Recommendation
Another full cycle is not worthwhile. Content accuracy is clean, the length giveaway is gone, mobile and dark mode are fixed. If the builder wants a 10-minute touch-up, do P2 #1 (reword one option) and P3 #2-3 (CSS breakpoints); everything else is optional. Studying with the current build is fine.
