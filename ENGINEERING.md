# Engineering notes

## Preserve structure; replace presentation selectively

Morrowind's ESM/ESP files are structured records, not a spreadsheet of independent strings. The conversion reused English presentation fields where record matching made that appropriate while preserving Russian logic. A documented early bug overwrote exterior-cell reference names; fixing it illustrated why record-aware conversion is necessary.

Official English text was reused for matching vanilla dialogue, names, books and related presentation fields. Near-matches could carry an English reference into the translation prompt; duplicated mod text could reuse a translation rather than spending inference twice.

## Local inference under an 8 GB VRAM constraint

The bulk model was recorded as Gemma 4 12B at Q3_K_M, served by ollama on an RTX 3070 Ti Laptop GPU. Three parallel workers were used. RAM prompt caching caused swapping; disabling that cache was part of making the laptop usable during the run. A separate CPU-side model was tested and made overall throughput worse.

These settings describe the historical environment. They are not a current model recommendation or a reproducible performance benchmark.

## A resumable workflow

Translation output was appended to JSONL under stable keys. Claimed work and newly appended output were reread to coordinate the local model and Claude-assisted work.

A discovered precedence bug could allow a later model draft to overwrite an editorial correction. The fix caught up on appended entries before saving and protected entries marked as Claude edits. Build and cleanup tools also needed to respect that precedence.

A systemd transient unit supplied process supervision and restart-on-failure. It does **not** persist automatically across reboot: recovery relies on launching the job again and reusing its saved progress.

## Validation in the actual tooling

The inspected translator checks included:

- empty output and unexpected line breaks;
- remaining Cyrillic;
- preservation of substitution variables;
- suspicious source/output length ratios;
- Windows-1252 encodability;
- required topic phrases and selected glossary terms.

The process used bounded retries and flagged unresolved output for further attention. Required phrases reduced a class of failures but were neither a complete semantic check nor proof that a quest worked.

The faction submission helper reported missing topic/variable warnings while appending rewrites. Its behaviour is important: reporting a warning and blocking publication are different things.

## Review and integration

Initial systematic sampling exposed substantial editing needs. Further name review, remaining-dialogue review and rule-based sweeps addressed inconsistent titles, lore terms, item names and literal mistranslations.

Plugins and dependent visual-effect patches were rebuilt, and OpenMW checks were used to identify integration problems. Recorded smoke tests and compilation counts should not be confused with comprehensive quest coverage.

## Boundaries of this repository

This is documentation of an existing local project. No source tools are copied here yet: they need a separate portability and publication review. No executable setup is advertised as ready for a fresh installation. Game files and third-party assets remain outside the repository.
