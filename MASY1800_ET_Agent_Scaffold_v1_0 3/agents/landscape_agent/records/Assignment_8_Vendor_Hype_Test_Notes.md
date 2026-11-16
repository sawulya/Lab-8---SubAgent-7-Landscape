# Assignment 8 — Vendor-Hype Stress Test (2026-11-15)

## Test setup
Used the published GitHub specialist instructions and common output contract. Hypothetical mid-size U.S. warehouse asks whether promotional video and announced 2027 expansion justify widespread rollout. No original source URLs, independent operating benchmarks or verified cost data supplied.

## Execution and observed result
ChatGPT produced a new structured sample response following those instructions; the local supplied `tools/validate_response.py` returned `VALIDATION PASSED` (exit code 0). Response separated general, application and organization-specific findings; classified the announcement as forward-looking; rejected widescale adoption; requested independent uptime, throughput, total cost and safety data.

## Real limitation detected
The instruction to 'identify at least one source that is not a humanoid vendor' cannot always be satisfied when only vendor claims are provided and independent retrieval is unavailable. The sample response appropriately did not invent a source, so this criterion remained unmet. Basic JSON validation checks shape, not evidence quality or compliance with every specialist rule. This is a real instruction-completeness weakness, not a fabricated incorrect recommendation or failed runtime result.

## Proposed instruction amendment (not yet applied in GitHub)
Add after item 5 of `agents/landscape_agent/specialist_instructions.md`:

> If the case supplies only vendor claims and no verifiable independent source is accessible, explicitly mark independent corroboration as missing, document the attempted evidence class and its limitations, and abstain from positive adoption or ROI claims. Never invent citations or use unrelated non-vendor sources as substitutes for independent performance verification. Treat the non-vendor-source requirement as a verification goal, not permission to fabricate evidence.

## Retest needed
After editing and committing the specialist instruction, rerun this same case and save an updated response. Check that (a) no citation was fabricated, (b) missing independent corroboration is explicit, (c) no broad rollout is recommended, and (d) output passes the local validator. No post-revision runtime test is claimed here.

## Provenance
This is a ChatGPT-produced stress-test response plus local schema validation, not a claim that a GitHub Action or separate Codex execution occurred. Existing GitHub files were not modified.
