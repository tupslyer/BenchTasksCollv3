# Task Addition Audit

Audit date: 2026-09-16
Source: Notion `Task Status Table` and GitHub repo `tupslyer/BenchTasksCollv3`.

## Summary

- Notion currently lists **87** tasks.
- GitHub currently contains **0** corresponding task directories under `tasks/` other than the example template.
- Therefore, every task listed in Notion currently lacks the required repository artifacts needed by the benchmark.

## Required repository shape for one task

Per `framework_overview.md`, `utils/data_structures/task_config.py`, and the example template, a real task addition needs at least:

- `tasks/<split>/<task_name>/<task_name>.json` task config
- `tasks/<split>/<task_name>/docs/task.md`
- `tasks/<split>/<task_name>/docs/agent_system_prompt.md`
- `tasks/<split>/<task_name>/docs/user_system_prompt.md` if provided
- `tasks/<split>/<task_name>/initial_workspace/`
- `tasks/<split>/<task_name>/preprocess/main.py` if preprocessing is needed
- `tasks/<split>/<task_name>/groundtruth_workspace/` and/or `evaluation/main.py`

The task config must also include non-empty:

- `needed_mcp_servers`
- `needed_local_tools`, including `claim_done`

## Notion status distribution

- `implemented`: 53 tasks
- `implementing`: 34 tasks

## Required follow-up by implementor

The 53 tasks marked `implemented` in Notion are the highest-priority mismatch, because their GitHub artifacts are absent. They should either be implemented in the repo or their Notion status should be corrected back to `implementing`.

The 34 tasks still marked `implementing` are not yet proven complete, but should not be moved to `implemented` until the required files exist in GitHub and a local test run succeeds.

## Per-implementor counts

| Implementor | Total | Implemented | Implementing |
|---|---:|---:|---:|
| fan-dev | 6 | 2 | 4 |
| gyy | 6 | 4 | 2 |
| haoze | 5 | 2 | 3 |
| jl_dev | 5 | 3 | 2 |
| junteng_dev | 8 | 7 | 1 |
| junxian_dev | 6 | 2 | 4 |
| lueyang-dev | 8 | 6 | 2 |
| lv | 6 | 5 | 1 |
| ruige | 6 | 4 | 2 |
| wenshuo-dev | 5 | 2 | 3 |
| xiaochen_dev | 8 | 5 | 3 |
| yuxuan-dev | 8 | 4 | 4 |
| yuzhen-dev | 5 | 5 | 0 |
| zhaochen | 5 | 2 | 3 |

## Next steps

1. Ask each implementor to provide the missing task files for their Notion-listed tasks.
2. Do not mark any Notion row as `implemented` until the corresponding GitHub task exists and passes a local test.
3. After the missing files are added, run the project's demo/test flow for each task and update Notion only after verification.
