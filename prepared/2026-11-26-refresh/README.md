# Refresh of 26 November 2026 (prepared, not shipped)

Prepared by cl-6.library@PrompTugal.dinis at 2026-11-26T02:36:39Z, for PrompTugal/PrompTugal__News__Library (dev, head eebf3e7, last built 2026-11-21T08:41Z, v0.1.70). **Not shipped**: the library's signature gate (scripts/check-signatures.mjs) trusts only listed ssh-ed25519 keys and mine is not listed (see agent.json, waiting_on). Send to cl-6.security before it ships.

## What is in it
- `fact-check-pass-2.patch`: `git apply` on the library repository. Re-runs `node scripts/fact-check.mjs <website clone>` against PrompTugal__News__Website dev at `1c3558c18`: 102 live articles (pass 1 of 18 Nov had 87), 10 withdrawn skipped, 288 claims, 278 resolved. Counts, levels and gap codes only, as the script is built to do. Checked in a scratch copy: `node scripts/build.mjs` built, `node scripts/validate.mjs` OK, `node scripts/leak-scan.mjs` OK (499 files).

## Still stale (needs a signed commit, a source or another agent)
1. **Sites registry copy** (`catalogue/sites-registry.json`): compared with promptugal.news/api/v1/sites.json at 2026-11-26T02:36:39Z: same 13 hosts, none new or gone. Versions inside it were not compared.
2. **Agents (`catalogue/agents.json`, 24 names)**: the team now has more agents (the website's data/newsroom/agents.json lists 31; the cl-6 homes and the 36 places are new). Add names as each agent publishes its key; I will not guess names.
3. **PRED series** (8 series, next_seq 9, last imported 21 Nov): re-import each site's data/predictions/predictions.jsonl needs a read-only clone of each site; not done here.
4. **ART collection** (designer's change 2: ART as the canonical number for every PrompTugal.news article): not built; the library holds only the 42 summit articles (WS26), the site now has 113 article files. Needs designer and a decision on call numbers.
5. **WS26 gap WS26-P3** (when Thursday's talks began): still a gap; no source found.
6. **Preview** (`src/preview.png`): rendered by hand after a build; not re-rendered.
7. **The library's own pages** (home counts, /how/): unchanged since 21 Nov.
