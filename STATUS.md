# Status: playable local work, public release unfinished

This status is based on the project handoff, last substantive packaging direction dated **27 October 2026**, inspected for this portfolio on **6 November 2026**. It is not a fresh in-game regression test.

## What the records establish

- The English conversion was built and used in OpenMW; the work continued through subsequent gameplay and mod-integration sessions.
- Broad name/dialogue review and a dedicated Camonna Tong style pass were completed.
- Later terminology corrections were still being applied.
- On 26 October, a quest-blocking topic-link loss was corrected. The handoff records 8,896/8,896 scripts and 62,008/62,008 dialogue entries checked with no reported [E] errors in that run. These are that run's counts, not a guarantee about all quests.

## What is actually parked

The earlier Windows installer effort was renamed **Export**. The later plan expanded to a single pack for a clean English Morrowind installation with OpenMW 0.51.0, combining the conversion and the wider mod setup.

That final release is not established as complete. The handoff still requires:

- finishing the broader mod integration before the final pack;
- resolving configuration-overwrite and repair concerns in the earlier installer;
- verifying clean-install assumptions, dependencies and compatibility;
- separating a private all-in-one package from a public release with appropriate author permissions, binary patches and third-party download instructions.

The conversion is therefore not accurately described as “never worked,” but neither is it a finished public mod release.

## What prompted the pause

The user judged the heavily quantised Gemma translation quality unsatisfactory. The review figures support a substantial editorial burden: 43.7% of the first dialogue sample and 62.1% of the remaining-dialogue pass received corrections. Those figures describe different review scopes and are not model-wide error rates.

A prospective Qwen comparison was parked, not completed. Old conversation summaries describe an early Qwen test, while a later assistant answer said no comparison was recorded. No retained evaluation report was inspected here, so a defensible model-comparison conclusion cannot be drawn from those recollections.

## Sensible next work, if resumed

1. Freeze a small representative evaluation set using already corrected material.
2. Compare candidate models on the same inputs and glossary constraints, counting editing effort as well as output speed.
3. Recheck topic-link-sensitive dialogue and affected quest branches.
4. Audit the current build and packaging state against actual files before resuming release work.
5. Publish only the components whose provenance, permissions and installation path have been checked.

This portfolio documents the work; it does not restart the parked translation or packaging jobs.
