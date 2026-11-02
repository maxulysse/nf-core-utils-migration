# nf-core-utils-migration

A Claude Code skill that migrates an nf-core pipeline from the vendored utils subworkflows (`utils_nextflow_pipeline`, `utils_nfcore_pipeline`, `utils_nfschema_plugin`) and local helper copies to the [nf-core-utils](https://github.com/nf-core/nf-core-utils) Nextflow plugin.

It covers:

- inventory of what a pipeline has already migrated
- reading plugin signatures from the exact pinned version
- replacing each vendored helper with its plugin call (`references/function-map.md`)
- pinning plugins in every external `plugins {}` block (Seqera Platform megatests, `-c` configs)
- diagnosing `Missing process or function X ... Did you mean 'X'` after a plugin change
- verification and PR checklist

Out of scope: tool citations from module `meta.yml` (`citationsOnTheFly`) and nf-test infrastructure.

Built from the migrations in nf-core/rnavar#233, nf-core/rnavar#252, nf-core/seqinspector#241, nf-core/rnaseq#1977 and nf-core/createpanelrefs#88 / #107.

## Install

```bash
git clone https://github.com/maxulysse/nf-core-utils-migration.git
ln -s "$PWD/nf-core-utils-migration/skills/nf-core-utils-migration" ~/.claude/skills/nf-core-utils-migration
```
