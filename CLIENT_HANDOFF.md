# Client test handoff

## What changed

- All answer options are shuffled per attempt, including the 18 options at Stage 19. The order stays fixed during a retry and reshuffles on restart.
- A new alert illustrated instructor replaces the exhausted GIF and generic officer art. The uniform is a stylized Russian-inspired training illustration; the client should approve its look before formal use.
- The supplied video plays after the greeting. Seeking ahead is restricted; after completion the trainee must tick the viewing confirmation before continuing to the supplied call recording.
- After a correct action, each corresponding supplied PDF appears in a dedicated task screen. The trainee opens it and confirms the specified review task before proceeding. All 14 distinct PDFs remain locally bundled.
- The supplied call recording plays immediately after the video confirmation, before the quiz.
- The final screen summarizes the attempt. It no longer waits until the end to reveal every document.

## Still needed from the client / instructor

1. Review the Stage 19 answer key if additional offenses should count as correct. Multiple selection is enabled, but the supplied scenario currently marks only commercial bribery as correct.
2. Approved final question sequence and missing O-02 text/options. The supplied detailed script has 20 implemented nodes; the route map lists 21.
3. Review of inconsistent names, dates, times and evidence details across the script and PDFs (for example the M-05 and M-14 dates). Do not grade trainees against contradictory material.
4. Approval of the illustrated uniform and establishing scene, or official visual assets that the client has permission to use. The video is deliberately labelled as a training dramatization.
5. If this becomes an assessed exam, move answer checking and scoring off the browser. `scenario-data.js` is inspectable by learners, even with a private GitHub repository or protected Vercel page.
6. Confirm access controls for the PDF evidence before publicly sharing a Vercel URL. Static PDF URLs are directly reachable by people who can access the deployment.

## Silent three-minute video deliverable

`police-academy-walkthrough-draft-silent.mp4` is a 180-second **illustrative mechanics storyboard**, not a literal browser screen recording. It has no audio and is arranged as 12 segments of 15 seconds. Replace its panels with live captures from the deployed site for a submission that explicitly requires screen footage. Record at 1280×720 or higher, disable microphone/system audio, and export H.264 MP4 with no audio track.

### Live capture and later subtitle shot list

| Time | Capture / action | Suggested subtitle note |
| --- | --- | --- |
| 00:00–00:15 | Show project files: HTML, JS, `materials/`, and media assets. | A static site keeps the case local and portable. |
| 00:15–00:30 | Open greeting with the new instructor. | The red patience meter fills after critical mistakes. |
| 00:30–00:45 | Play the supplied case intro, tick confirmation, and continue. | The dramatization is context, not evidence. |
| 00:45–01:00 | Enter V-00, then D-01. | The supplied call plays after the video confirmation. |
| 01:00–01:15 | Show the ordered stages and progress bar. | Each decision advances the investigation. |
| 01:15–01:30 | Show the choice positions; restart and show a changed order. | Correct answers are shuffled per attempt. |
| 01:30–01:45 | Briefly show the answer-shuffle and status check in `game.js`. | Scoring follows the answer status rather than its position. |
| 01:45–02:00 | Choose a critical wrong answer. | A critical error fills one third of the red meter. |
| 02:00–02:15 | Show an ordinary wrong answer or supervisor hint. | An explanation returns the trainee to the same node. |
| 02:15–02:30 | Complete O-03 correctly and pause on M-08. | The shoeprint PDF unlocks immediately after the action. |
| 02:30–02:45 | Open M-08, review, tick the confirmation, continue. | The document is part of the task flow. |
| 02:45–03:00 | Show summary or later stage; use an instructor run-through if needed. | The result records decisions and reviewed material. |

For quick filming, use the browser at 100% zoom, hide bookmarks and notifications, avoid showing account data, and keep the mouse visible. The full quiz needs correct answers at prior nodes to reach O-03; use a rehearsal run and record in segments if necessary.

## October 2 revisions

- Replaced hearts with the red «Терпение начальника» meter: three critical mistakes end the attempt; minor mistakes retain the hint/retry behavior.
- M-02 was corrupted in the working package. Restored the intact original 15-page PDF and added local page-image viewers for M-02, M-08, M-09 and M-10. Other documents have an embedded PDF viewer plus download/open links.
- M-03, M-04, M-06, M-07, M-11, M-12, M-14 and M-15 require a nonblank written response after opening. Spaces alone do not pass; responses survive reopening the material. Other materials keep confirmation checkboxes.
- Condensed correct options; the correct answer is shorter than a distractor in 10 stages. Feedback, answer statuses and scenario order are preserved.
- Stage 19 has all 14 requested new alternatives (18 total), a two-column desktop layout, and exact-set multiple-answer checking. Added «Возможна совокупность нескольких правонарушений.» after the situation. Added alternatives are marked incorrect under the existing scenario key; an instructor must identify any additional correct alternatives before changing grading.
- Validation: JavaScript syntax, simulated interaction tests across all 20 stages, video confirmation/seek handling, text gates, multi-select and meter behavior passed. All 14 PDFs render, and bundled raster images decode. Full browser/device playback and visual QA still need a client test.
