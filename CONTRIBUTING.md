# Contributing

## Repository layout

```
.claude-plugin/plugin.json       plugin manifest
.claude-plugin/marketplace.json  makes this repo installable as a marketplace
.mcp.json                        expected connectors (Foreplay, Meta Ads, BigQuery)
shared/canon.md                  shared definitions — the single source of truth
shared/evidence.md               2026 evidence, citations, never-state list
skills/<name>/SKILL.md           14 skills, each independently usable
skills/<name>/references/*.md    libraries, loaded only when a step needs them
```

## The rules that keep this maintainable

**1. Canon is not duplicated.** `shared/canon.md` owns the shared models — the golden hook rules, the awareness-to-script-flow mapping, the hook stack, the glossary, the iteration ladder, the two-lane metric rule. No skill restates them; skills cite the section. A duplicated definition is a bug.

**2. SKILL.md stays under 150 lines.** Hard limit is enforced by the platform at a higher number, but 150 is the house rule. Anything longer belongs in `references/`.

**3. Description must be under 1024 characters.** The platform rejects the plugin otherwise, and the failure only surfaces at install. Check before committing:

```bash
python3 - <<'PY'
import glob, re, os
for p in sorted(glob.glob('skills/*/SKILL.md')):
    fm = re.match(r'^---\n(.*?)\n---\n', open(p).read(), re.S).group(1)
    d = ' '.join(re.search(r'^description:\s*>?\s*\n?(.*?)(?=\n[a-z_]+:|\Z)', fm, re.S|re.M).group(1).split())
    flag = '  <-- OVER LIMIT' if len(d) > 1024 else ''
    print(f'{len(d):5d}  {os.path.basename(os.path.dirname(p))}{flag}')
PY
```

**4. Two edits per library entry, never one.** A new hook tactic or visual format needs its full entry in the shard *and* its row in the owning index (`hook-system/references/tactics.md`, `creative-concepting/references/visual-formats.md`). An entry with no index row is invisible to the skill.

**5. No invented statistics.** If a number cannot be sourced with publisher and date, say it is unavailable. `shared/evidence.md` is the authority even when a fresher-looking search result disagrees.

**6. Scripts are executed, never read.** `creative-brief-builder/scripts/build_brief.py` is ~870 lines. Reading it into context is the single most expensive mistake available in this repo.

## Packaging a release

```bash
zip -r viden-ads-engine.plugin . -x '.git/*' -x '*.DS_Store' -x '*__pycache__*'
```

Then save it through the desktop app, or install this repo directly as a marketplace.

## Testing the docx builder

```bash
python3 skills/creative-brief-builder/scripts/build_brief.py --self-test --out /tmp/t.docx
```
