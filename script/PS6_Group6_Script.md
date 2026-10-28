# Group 6 script: 13-slide talk (11 minutes)

Oct 27, 2026 · Kevin Christianto Husein

## Timing

The talk runs 11 minutes over 13 slides, at about 130 spoken words a minute. Say the plain text; do what is in **[brackets]**. **LIVE** means switch to the browser for a few seconds. The screenshots on the slides are your evidence: point to them, and switch to the browser only where the script says LIVE.

| Part | Speaker | Slides | Time |
| --- | --- | --- | --- |
| 1 · The assessor | Kevin | 1–3 | 2 min |
| 1 · The assessor | Sanesh | 4–6 | 2 min |
| 1 · The assessor | Kartik | 7 | 2 min |
| 2 · Working as a team | Sean | 8–10 | 3 min |
| 3 · A month of mornings | Kartik | 11–13 | 2 min |

Before you start, open these tabs: Kevin’s dashboard, Kartik’s dashboard, the Public Storage release on sec.gov, and Kevin’s GitHub repository.

## Kevin · Part 1 · slides 1–3 · 2 minutes

**Slide 1 · The assessor (10 s)**

Good morning, we are Group 6. Our agent is the assessor: a second AI agent that checks the first agent’s work, like a teacher marking homework. Each of us built our own pair, so today you will see four of them.

**Slide 2 · Two prompts, two schedules, one fetch (1 min)**

It works in four steps. **[Click SEC fetch]** At 5:10 every morning, a small robot on GitHub downloads the night’s company filings from sec.gov and saves a copy, because Claude’s cloud cannot reach sec.gov itself. **LIVE:** show sec-fetch.yml. **[Click Watcher]** At 6:07 the watcher, a Claude Routine, an agent on a timer, picks two companies and writes a short brief with exact quotes. Its instructions are in PROMPT_WATCH.md. **[Click Assessor]** At 6:37 the assessor runs on its own instructions, PROMPT_ASSESS.md. It asks three questions: is the number right, is the company doing better or worse, and does management’s story fit the numbers? Then it gives three marks out of five: correct, complete and useful. **[Click Dashboard]** Everything appears on our dashboard. Neither agent may ever give buy or sell advice.

**Slide 3 · Tuesday, on four dashboards (50 s)**

Here are both agents at work on Tuesday. Each row is one of us. **[Click Show the pattern]** Look at the orange column. For all four of us, GitHub ran the download about three hours late, so at 6 AM the watcher had nothing new. The good part: it did not guess; it said it could not read the SEC. **[Point to the screenshots]** Our run logs prove it. On mine, the 6:10 watcher read 0 of 4 sources, and Run now at 6:13 PM read 64 filings. On Sean’s, the assessor ran at 9:37, after the meeting. Now Sanesh shows what the assessor found.

## Sanesh · Part 1 · slides 4–6 · 2 minutes

**Slide 4 · First, what the numbers say (30 s)**

Thanks, Kevin. Before judging what a company says, the assessor builds a fundamentals table from the official report, the 10-Q, not from the press release. **[Point to the screenshot]** This is that table on Kevin’s dashboard, for TPG RE Finance Trust, a property lender. Profit was 22 million dollars a year ago, 13 last quarter, and 9.4 now: down 57% in a year. Keep that number in mind.

**Slide 5 · Guess the verdict (45 s)**

Here is what managers said. Does each claim fit the numbers? **[Read card 1, ask the room, then click]** “Continued successful execution”, but profit fell 57%: does not match. **[Click card 2]** Meta: “The core business is strong”, but operating income fell 37%: does not match. **[Click card 3]** Boyd Gaming: “Continued growth”, but revenue fell 1.4%: does not match. **[Click card 4]** Business First: “Stronger returns”. The assessor said it matches, but in the release that is only true on an adjusted measure. **[Point to the screenshots]** Both verdicts are shown here, straight from our dashboards. A claim can be true and still leave something out.

**Slide 6 · Its best catch, and its marks against ours (45 s)**

Now the assessor’s best catch. **[Click What the watcher wrote]** Kevin’s watcher wrote net income of 5.82 million: only the part left for ordinary shareholders, after preferred shareholders are paid first. **[Click What the 10-Q says]** The full figure is 9.37. **[Point to the screenshots]** On Kevin’s dashboard the assessor flagged it as a mismatch, and gave the brief 3 out of 5 on all three marks. **[Click the tab Its marks against ours, then Kartik and Sanesh]** We compared its marks with our own checks. Every one of us disagreed with at least one, and it never gave “correct” less than 5, as the screenshots show. Kartik will show you why, live.

## Kartik · Part 1 · slide 7 · 2 minutes

**Slide 7 · One figure and one claim, against the release (2 min)**

Thanks, Sanesh. Let’s check the agent ourselves, live on sec.gov. This is Public Storage. Each tab shows the screenshot from my dashboard; then I confirm it in the release. **LIVE:** open the release.

**[Tab 1 · A figure]** My brief says revenue was 1,366.19 million, marked confirmed. In the release I search “Total revenues”: 1,366,190 thousand. Same number, just written in thousands.

**[Tab 2 · A claim]** The CEO says results were “better than expected”. I search the phrase, and it is there word for word. The assessor called it a match, because revenue grew 11.6%. So far, the assessor is right.

**[Tab 3 · A label]** But look at net income. My brief says 366.9 million, which is income for shareholders only. Total net income is 378.3. The number matched a line in the release, so the assessor still gave full marks for correct.

**[Tab 4 · A one-off]** One more search: “Transaction and integration”. That is a 114.6 million dollar one-time cost of buying another company. **[Click Add back the one-off]** Operating income fell 35.5%; without that one cost, it fell only 12.2%. The assessor never saw it, because the watcher never wrote it down.

So the assessor checks numbers well, but a person still has to step in for labels and one-off costs. Over to Sean.

## Sean · Part 2 · slides 8–10 · 3 minutes

**Slide 8 · Eight agents, four people (70 s)**

Thanks, Kartik. How did we work as a team? Each of us built a watcher and an assessor, so eight agents in total. The agents read the filings, wrote the briefs and did the first check. We wrote their instructions, re-ran them when the data was late, checked each other’s work on sec.gov, and made the final call. **[Point to the cards]** Kevin traced why the data was late and fixed a wrong setting. Kartik checked Public Storage line by line. Sanesh checked Business First and showed how to build a bank’s revenue. I checked NVE and found OFG’s missing net income.

**[Click How we rated each other]** We also rated each other’s briefs. **[Click S1]** “Correct” is high everywhere: the numbers were right. **[Click S5]** “Reliable” is low everywhere, because the late download hit all of us. **[Click S2]** “Complete” is where we disagreed most.

**Slide 9 · A teammate found what two agents missed (50 s)**

Here is one catch. Kartik’s watcher wrote down Public Storage’s numbers. **[Click Next step]** Kartik’s assessor confirmed them and agreed with the CEO, as the screenshot shows. **[Click Next step]** Then Kevin checked the release and found the 114.6 million one-off cost that both agents missed. Two agents said “fine”; a teammate said “wait”. **[Point to the right screenshot]** And my run log shows a second catch: my assessor was set for 9:37, after the meeting.

**Slide 10 · One rule, two opposite calls (60 s)**

And a disagreement. The watcher has a rule: never use “net income for ordinary shareholders”. At TPG, Kevin’s watcher broke the rule, and that was wrong, because preferred shareholders made a real difference; the screenshot shows it flagged. At OFG, my watcher kept the rule and wrote “not given”, although the release gives 56.6 million; you can see it in my screenshot. OFG has no preferred shareholders, so that line was the real profit. Same rule, opposite results. **[Click How we settled it]** We agreed: use that line when it is the only one in the release, and label it. **[Click What our survey says]** Our lowest survey score was T3: we had not agreed what a good brief looks like before judging one. Kartik will wrap up.

## Kartik · Part 3 · slides 11–13 · 2 minutes

**Slide 11 · Who checks, what, and when (50 s)**

Last question: with an assessor already checking, who still checks? All four of us gave the same answer: the analyst presenting at 8:30, because they own the conclusion. Here is what they check, and when. **[Tick 6:40]** Did the agents read today’s data? On Tuesday, they did not. **[Tick 6:50]** Open every orange flag. **[Tick 7:15]** Check two numbers by hand, especially thousands against millions. **[Tick 7:45]** Test any “matches” claim for one-off costs. **[Tick 8:00]** Check the quarter date, so old results are not taken as new. And once a week, the owner checks the settings.

**Slide 12 · Four fixes, one per person (40 s)**

What would we change first? Each of us proposed one fix. **[Click each card]** Kevin: make the watcher list every one-off cost. Me: check the accounting label, not just the number. Sanesh: a clear rule for a bank’s revenue. Sean: test every claim against both a year ago and last quarter. Our first change is Kevin’s, because listing one-offs would have caught the TPG write-off, the Public Storage deal cost and the Citizens Community provision release.

**Slide 13 · Two computer helpers, and one person who decides (30 s)**

To sum up in plain words. One computer program reads the companies’ results every morning and writes a short summary. A second program checks that summary, like a teacher marking homework. And a person reads both and makes the decision. **[Click What we learned]** First, the helpers save time. **[Click]** Second, they only check what they are shown. **[Click]** Third, a person still decides, with a short check every morning. **[Click]** In one line: let the computer do the reading, and keep a person for the judgment. Thank you, we are happy to take questions.
