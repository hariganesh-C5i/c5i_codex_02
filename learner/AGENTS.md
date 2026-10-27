# Repository guidance

## Scope and purpose

- This repository is a self-contained training bundle for the Day 2 `AGENTS.md` lab; it is not the Tiny Shop application itself.
- Keep bundle-level training material under `learner/` and instructor-only material under `instructor/` when those files are part of the checked-out bundle.
- Treat the lab's instructions and task cards as the source of truth for exercise steps and acceptance criteria.

## Learner starter boundary

- `learner/starter/` is intentionally presented as a clean, unguided learner project. Do not add project guidance, generated output, or exercise solutions there unless the task explicitly asks for it.
- This root file is inherited by paths below it. Therefore, a genuinely unguided baseline must be run from a clean copy of `learner/starter/` outside this repository or from a checkout without this root file. Do not claim that a session inside this checkout had no project guidance.
- Keep changes to the starter limited to the task card being performed; preserve its intentionally small Python example and its visible contract.

## Tiny Shop starter facts

- The starter implementation is `learner/starter/src/checkout.py`; its public function is `calculate_total(items)`.
- Visible tests are in `learner/starter/tests/test_checkout.py` and use Python's standard-library `unittest`.
- The documented verification command, run from `learner/starter/`, is `python3 -m unittest discover -s tests -v`.
- No package installation is required for the starter. Do not add dependencies unless a task specifically requires them.
- The starter uses floats for this teaching exercise. Keep calculation and any requested presentation formatting separate unless the task card explicitly changes that contract.

## Scope and safety

- Follow the specific task's listed files, acceptance criteria, and out-of-scope boundaries.
- For integration exercises, use only the completed instructor specification and approved local or mocked verification described by that specification. Do not use production accounts, real credentials, or real customer/payment data.
- Do not invent an internal catalogue endpoint, SDK version, or approval. Use available repository evidence and clearly identify any unresolved assumption.
- Do not edit instructor answer-key material as part of a learner exercise.
