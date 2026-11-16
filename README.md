# Markdown Render Speed — a from-scratch Markdown parser

A dependency-free Markdown parser written from scratch that renders Markdown to HTML byte-for-byte identical to marked 18.1.3 with its default options. It passes all 720 practice cases (the CommonMark and GFM spec examples plus 40 generated documents) and runs faster than the marked baseline, at about 1.17x median speedup measured on CPU time.

Built for the [make.fun bounty](https://make.fun/bounty/markdown-render-speed-02).

[![make.fun · markdown-render-speed-02](https://make.fun/badge/markdown-render-speed-02.svg)](https://make.fun/bounty/markdown-render-speed-02?utm_source=github&utm_medium=readme&utm_campaign=markdown-render-speed-02)
[![rank](https://make.fun/badge/markdown-render-speed-02/LeviosaEXC/markdown-render-speed-02/rank.svg)](https://make.fun/bounty/markdown-render-speed-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=markdown-render-speed-02)
[![reward](https://make.fun/badge/markdown-render-speed-02/LeviosaEXC/markdown-render-speed-02/reward.svg)](https://make.fun/bounty/markdown-render-speed-02?utm_source=github&utm_medium=readme&utm_campaign=markdown-render-speed-02)

## How it works

The harness runs the program as `node /bot/main.ts` on Node 22. The entrypoint reads every case from `/input/cases.json` (a JSON array of `{"id", "markdown"}` objects), renders each one with the from-scratch parser in `parse.js`, and writes the results to `/output/html.json` as a JSON array of HTML strings in the cases' order. The entrypoint renders Markdown to HTML with no network access, using only Node's built-in modules and the source committed here.
