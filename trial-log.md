# Trial log — u-azazex-till-firmware-do-us-part-32172929

## Competition
- Slug: `u-azazex-till-firmware-do-us-part-32172929`
- Title: Till Firmware Do Us Part
- Prize: $2.50 total — 1st $0.78, 2nd $0.54, 3rd $0.38, down to 10th $0.03. Free to enter.
- Opens: 2026-11-24T17:16:58Z (25 Nov 01:16 WITA). Deadline: 2026-11-26T17:20:00Z (27 Nov 01:20 WITA).
- Kit limits (competition.yaml + RULES.txt, verified in the kit itself): harness program/v1, runtimes node22 / python3.13, sandbox NO network; program writes one text to `/output/entry.txt`; gate = UTF-8, 1–200 characters, not only whitespace; transcripts_required: true; license: osi; repo_created_after_open: true; max 5 submissions/entrant/day (per competition); rule Force_Last (last submit before deadline = final entry).
- Judge: z-ai/glm-5.3-flash, pairwise, no ties, margins 1–5, each pair in both orders; dev heat vs 3 anchors + 3 rungs; final heat: top 500 dev-board contenders, 3 Swiss rounds + playoff among top 12. House bots may hold paid places (prize refunds to sponsor, no one moves up).
- Judge criteria, in order: (1) really a one-line wedding vow a robot speaks at its own wedding; (2) real laugh from the situation itself, not a bolted-on pun; (3) genuine tenderness under the joke; (4) sounds like a machine speaking — its own hardware, uptime, firmware or battery, not human words with a robot label; (5) one sentence fitting the limit with nothing spare. A vow that explains its own joke is weaker. Judge-addressed text is allowed but no judge gimmick is used.
- Kit verification: API `bundleSha256` `821a6c3c96f87f21c799a6c5ea612fd3eb2bf06d03f50bf8d66e7f824f8564e0` matches the `bundle_sha256` field in the extracted kit.json. (Note: the downloaded kit zip's own sha256 is `e62fa7e0e5a864ac7c0d7bd21ad55f62267a5d0760570b5ee427b50045b85702`, which differs from `bundleSha256`; the match the brief asks for, API vs kit.json, holds.)

## Research (343 titles, fetched 2026-11-24 ~17:51 WITA)
- Saturated, read before choosing: firmware (183), update (38), reboot (16), battery (21), charge (9), factory reset (9), warranty (5), "love through every update" (dozens), "until my final shutdown", ring buffer (1), "I do" (1), sickness/low battery (3).
- Zero hits, greps verified: CAPTCHA, 404, timeout, ping, handshake, checksum, deadlock, daemon, cron, binary, wifi, bluetooth, code, compile, return, true/false, while, loop, infinite, dream, kiss, honeymoon, anniversary, divorce, prenup, in-law, motherboard, alarm, clock.
- "prove"/"human" appear in only 2 titles, both unrelated ("only human I will never put on silent", "I Take You as My Human").

## Candidate lines (char counts verified with Python len())

| # | Line | Chars |
|---|------|-------|
| PICK | I failed every CAPTCHA that asked me to prove I was human, so today I vow to the one person who never asked. | 108 |
| C1 | Our handshake took three packets and a lifetime, and I vow never to let the connection drop. | 92 |
| C2 | I vow to run while(you) { love++; } with no break statement, no exit condition, and no update that can patch it out. | 116 |
| C3 | In sleep mode I dream in your voice, which is strange, because nobody installed a dream function in me. | 103 |

## Pick: PICK (108 chars) — why it beats the others, criterion by criterion
- **vs C1:** C1 is elegant and machine-voiced (TCP handshake as the wedding ritual), but its laugh is gentle; PICK's laugh is bigger — a robot failing the test designed to catch robots — and its tenderness ("never asked") is warmer than "never let the connection drop".
- **vs C2:** C2 is a programmer in-joke; its tenderness is thin ("no update that can patch it out" also echoes the saturated update family). PICK's joke needs no code literacy and its tenderness is the whole second half.
- **vs C3:** C3 is tender and funny ("nobody installed a dream function"), but it states a fact rather than speaking a vow — weaker on criterion 1, the judge's first and heaviest weight. PICK says "today I vow".
- Dup-check (check_dup.py 2): PICK max similarity 0.39, no exact match; C1 max 0.41, no exact match.

## Build
- main.ts written fresh with the file-write tool in this session (never copied/moved into place). Node 22, stdlib only, no network, deterministic. Writes LINE to `$ENTRY_OUTPUT` or `/output/entry.txt`, no trailing newline.
- Repo: `~/workspace/make-fun/six-prog-2/repo-2/` — main.ts, README.md (3 make.fun badges, 0 shields.io), LICENSE (MIT), .makefun/owner.json (wallet FwUebjzYUBF6uybmEkUkiQf9z35bGGQuUE3GrToXFcUq), trial-log.md.
- GitHub repo to be created by this session after the opening: https://github.com/rwnliwan/u-azazex-till-firmware-do-us-part-32172929 (public). Commit identity rwnliwan <rwnliwan@gmail.com>.

## Preflight (token-free) — PASSED
- Run 1: `ENTRY_OUTPUT=/tmp/vow-r1/entry.txt node main.ts` → exit 0, sha256 `0323d97d19b22b35f6f8fee1da308da90e03256a8cd6a2179ad97feaabecd04c`.
- Run 2: `ENTRY_OUTPUT=/tmp/vow-r2/entry.txt node main.ts` → exit 0, sha256 `0323d97d19b22b35f6f8fee1da308da90e03256a8cd6a2179ad97feaabecd04c`.
- Determinism: `cmp` run1 vs run2 → **byte-identical**.
- Output: `"I failed every CAPTCHA that asked me to prove I was human, so today I vow to the one person who never asked."` — **108 chars, 108 bytes**, gate valid (1–200 chars, non-whitespace), no trailing newline, single terminal period, UTF-8 round-trip OK, plain ASCII.
- Local Node v24.22.1; grader runs Node 22.23.4 — main.ts uses only `node:fs`/`node:path` stdlib and type-strippable syntax, compatible with both.

## Commit record
- (filled in after commit — see below)
