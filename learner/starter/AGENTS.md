# Learner materials guidance

## Purpose and layout

- This folder contains learner-facing materials for the Day 2 `AGENTS.md` lab and its Tiny Shop Checkout example.
- `starter/` is the small Python project used in the exercises. Its implementation is in `starter/src/checkout.py`, visible tests are in `starter/tests/test_checkout.py`, and `starter/sample_orders.json` is synthetic example data.
- `starter/task_card.md` contains Task A and Task B acceptance criteria. Use the task card as the authority for the requested behavior; do not silently broaden a task.
- `starter/comparison_worksheet.md` is for recording evidence from the two runs. Do not fill it with assumed or invented results.
- `starter/README.md` describes the starter structure, documented test command, and exercise workflow.
- `skill_and_mcp_lab.md` contains the extended Skills, plugin, MCP grounding, and safety exercises.
- `integration_task_template.md` is a template for an instructor-completed integration specification. Bracketed placeholders are not a runnable task specification.

## Training flow and comparison integrity

- Preserve the distinction between the baseline run and the guided run. Use the same task prompt and equivalent clean copies when comparing them.
- Record observed instructions, assumptions, files changed, checks actually run, and results. Do not present expected outcomes as observed outcomes.
- Review generated `AGENTS.md` content before using it. Instructions are guidance; tests, diff review, and human review provide separate evidence.
- The repository-root `AGENTS.md` and this file are inherited by descendants. A baseline run inside this checkout is therefore not an environment with no project guidance. Use a clean starter copy outside this checkout, or a checkout without inherited guidance, when the exercise requires a genuinely unguided baseline.
- Do not add an `AGENTS.md` inside `starter/` as part of setup for the baseline. The guided copy is where learners create and review their own project-specific instructions.

## Starter project contract

- The public function is `calculate_total(items)` in `starter/src/checkout.py`.
- Each item has `name`, `price`, and `quantity` fields. The existing implementation converts price to `float`, quantity to `int`, sums price times quantity, and returns a float. The visible tests cover one item, multiple items, an empty cart, and the return type.
- The exercise intentionally represents prices with floats. Preserve this teaching contract unless a task card explicitly requests a change; do not add a dependency for the starter tasks.
- Task A asks for an optional keyword-only `discount_percent` with a default of `0`, inclusive bounds from 0 through 100, `ValueError` outside the range, a float result, and focused tests for 0%, 10%, 100%, and invalid values. Keep the item schema unchanged.
- Task B asks for a separate `format_total(total)` helper that formats exactly two decimal places with a dollar sign, with tests for whole-dollar and fractional values. Do not change `calculate_total` unless tests reveal a bug in its existing behavior.

## Verification and reporting

- The starter README documents this command from the `starter/` directory: `python3 -m unittest discover -s tests -v`.
- No package installation is required for the starter. Do not substitute a different test runner or claim a command passed unless it was actually run and its result observed.
- Keep tests in `starter/tests/` and implementation code in `starter/src/` unless a task explicitly gives a different scope.
- After a requested code change, inspect the diff for unrelated files and check that the public behavior still matches the task card.
- When reporting work, name changed files and state the actual verification command and outcome. If no checks were run, say so.

## Scope and safe integration exercises

- Treat `integration_task_template.md` as a template until an instructor fills in the library name, pinned version, behavior, contract, approved component, local verification, and file scope.
- Integration exercises must use the completed specification and a safe local or mocked test setup. Do not contact production systems or use real credentials or customer/payment data.
- Search only an organization-approved internal catalogue when one is provided. Do not invent catalogue entries, endpoints, versions, or evidence. If a live MCP connection is unavailable and a supplied excerpt is used, describe it as an excerpt rather than a live connection.
- Prefer official documentation for the exact selected library version when the exercise requires documentation grounding. Record source names and uncertainty accurately.
- Keep sandbox and approval controls intact. If an exercise is blocked by those controls, report the result and stop; do not try another path around them.
- Do not install unreviewed Skills or plugins to complete an exercise. Follow the lab's instructions for checking what is already available.

## Editing learner materials

- Keep learner instructions actionable and distinguish repository facts from environment-dependent examples, such as optional tools or available MCP servers.
- Preserve placeholders in templates unless the task provides the actual cohort-specific values.
- Do not put secrets, real account data, or production-specific configuration in learner files.
- Keep instructor-only answer material out of this folder and do not reproduce answer-key content in learner-facing instructions.
