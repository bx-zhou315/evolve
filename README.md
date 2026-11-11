# EVolve

*EV + evolve: improve your poker by judging every decision on its expected value.*

A bilingual (Chinese/English) Texas hold'em trainer I built to practise GTO-based decision-making, from preflop through to the river. It runs entirely in the browser.

**Live site:** https://bx-zhou315.github.io/evolve/ (English: [en.html](https://bx-zhou315.github.io/evolve/en.html))

## Features

- **Thinking guide:** the ten things worth memorising, a five-step decision routine for live play, and default plans by street, board type and hand class
- **Preflop:** drills for opening, facing an open, facing a 3-bet and facing a 4-bet, by position, with a 13×13 range chart and the GTO frequencies for every hand
- **Flop:** practice against pre-computed solver results on 14 representative boards
- **Turn and river:** an in-browser DCFR solver computes strategies on the spot for preset scenarios, random boards or your own custom board, pot, stack sizes and ranges
- **Guided mode:** each river decision is broken into steps (opponent's range, range and nut advantage, where your hand sits) and checked against the solver before you act
- **Review:** frequency and EV for every action, your EV loss, and your whole range's strategy at that node
- **Training record:** accuracy by step, a leak finder, and confidence calibration (how well your stated confidence matches your actual accuracy), saved in the browser

## How it works

| File | Purpose |
|---|---|
| `index.html` | Chinese version: the whole app, including the turn and river solver |
| `en.html` | English version |
| `preflop.json` | Preflop ranges (6-max, 100bb, no rake) converted to the app's format |
| `flops/*.json` | Pre-computed flop solutions for 14 boards |

## Sources and copyright

- **Preflop ranges:** Leakproof 6max-100bb-norake 1.0.0 ([a-hanamoto/leakproof-preflop-ranges](https://github.com/a-hanamoto/leakproof-preflop-ranges)), used under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Changes: converted to this app's format, action names translated, and two of the ranges used as inputs for the flop solves. The author notes the frequencies are rounded and not guaranteed to be accurate.
- **Flop solutions:** computed with the open-source [postflop-solver](https://github.com/b-inary/postflop-solver) by Wataru Inariba (AGPL-3.0). Only the results are published here; none of the solver's code is included.
- **Turn and river:** solved in the browser by this app's own DCFR implementation. The ranges in these scenarios are simplified, hand-written approximations for practising the thought process, not authoritative answers.
- **Fonts:** Bricolage Grotesque, Noto Sans SC and JetBrains Mono via Google Fonts (SIL Open Font Licence).
- GTO Wizard, PioSOLVER and similar names belong to their respective owners; this app is not affiliated with them.

## Responsible use

For offline study only. Real-time assistance tools are banned on almost all online poker sites. Only play with money you can afford to lose; in the UK, support is available from [GamCare](https://www.gamcare.org.uk).
