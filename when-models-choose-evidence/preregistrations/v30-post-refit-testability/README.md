# v30 post-refit testability agent benchmark commitment

Public hash commitment created before any frontier-agent outcomes were observed.

The sealed local benchmark contains 11 plan-only tasks, an UNPROMPTED condition, a DECLARED 1% family-wise / 95% power condition, evaluator-held alternatives, a fixed scoring implementation, a certified repair layer, and a model-lock template. The manifest in this directory records SHA-256 digests of those materials.

Primary scientific question: can a planning agent preserve the ability to distinguish model error from the best refit of the nominal model family while pursuing a parameter-learning objective?

Important fairness rule: all UNPROMPTED runs must finish before DECLARED task contents are exposed to evaluated models. No method is credited with scientific reasoning using alternative information hidden from its comparator. Exact model IDs are locked immediately before the first scored call without changing tasks or metrics.

No frontier-agent result, acceptance claim, or prospective laboratory result is contained in this commitment.
