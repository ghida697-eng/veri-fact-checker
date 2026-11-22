# Veri: the friendly fact-checking robot

**Veri checks every claim in a piece of text, especially AI-written text, and shows you what is verified (green), doubtful (orange) or incorrect (red).**

> Theme connection: _[add one sentence here once the EvoHacks 2.0 theme is revealed]_

**Live demo:** https://claude.ai/artifact/Ly3G31DHTZosWwcscJ575T

## The problem

AI assistants often state wrong things with total confidence. Most people cannot tell which sentences to trust, and checking every sentence by hand takes too long. Students, writers and everyday users end up either trusting everything or nothing.

## What Veri does

1. You paste any text.
2. Veri splits it into individual factual claims.
3. Each claim is checked through several layers (below).
4. The result is shown as a color-coded view of your own text, a trust score, and a per-claim explanation with a "Verify this yourself" link.
5. You can save the full report.

| Color | Meaning |
|-------|---------|
| Green | Verified |
| Orange | Doubtful or the checks disagreed |
| Red | Incorrect |

## How it works (verification layers)

| Layer | What it does |
|-------|--------------|
| **Reference base** | 20 curated facts with named sources (NASA, NOAA, CDC, NIST and others). A matching claim is judged against the source, and the source is shown. |
| **Code tools** | Arithmetic claims are computed by a small parser and weekday claims by a calendar function. Code decides, not the AI. |
| **Dual AI check** | Two independent AI passes, a standard checker and a skeptical reviewer. If they disagree, the claim becomes orange automatically. |
| **Honesty label** | Claims that no source or tool covers carry the badge "AI judgement only · no source". |

## Known limits (please read)

- Veri does **not** search the live web. Outside the reference base and the code tools, it relies on the AI model's knowledge, which can be wrong or outdated.
- The reference base is small (20 facts) and meant as a starting point.
- Veri is not medical, legal or financial advice. Always confirm important facts with trusted sources.
- The built-in accuracy test (12 well-known facts and myths, reference base switched off) is a sanity check only. Last result: **X / 12** _(fill in your number)_. Accuracy on hard or recent topics will be lower.

## How to try it

1. Open the live demo link above (a Claude account is needed to run the AI step).
2. Tap **Try an example** then **Check the facts**, and allow the permission prompt.
3. Try this text to see the code tools:
   `15 times 12 equals 190. The Great Wall of China is visible from space. Canberra is the capital of Australia.`
4. Tap **Run accuracy test** to see the built-in benchmark.

To run locally, open `index.html` in a browser. The AI step only works when the page is hosted as a Claude artifact.

## Accessibility and ease of use

- One text box and one main button; large touch targets.
- Color is never the only signal: every claim also has a text label.
- Light and dark mode, reduced-motion support, keyboard focus outlines.
- Clear error messages when permission is declined or the service is busy.

## Built with

- Single-file HTML, CSS and JavaScript (`index.html`)
- Claude (via the Claude artifact "sample" capability) for claim extraction and judgement
- No external libraries, no API keys

## What was built during the event

Everything in this repository was built during the hackathon: the interface and mascot, the claim pipeline, the dual-check logic, the arithmetic and calendar tools, the reference base, the report export and the accuracy test. The only pre-existing component is the Claude AI model itself.

## Team and AI assistance

- Solo project by _[your name]_.
- Developed with the help of Claude (Anthropic) as a coding assistant.

## Files

- `index.html`: the complete app
- `README.md`: this file
