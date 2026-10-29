# Community maintenance — 2026-10-28

## Acceptance contract

Review every open contribution against `CONTRIBUTING.md` and the [curation policy](curation-policy.md). Public documentation inspection supports a scoped description, not a runtime, security, billing or model-fidelity verdict. Mirror accepted entries in both language READMEs, track public gateway repositories for release refreshes, and retain attribution when hand-integrating content against current main. Close incorporated PRs only after the commit is published.

## Community review record

Sources below were read on 2026-10-28. Except where specified, entries describe project/vendor documentation; no submitted gateway was runtime-tested in this pass.

| PR | Contribution | Disposition and evidence boundary |
| --- | --- | --- |
| #147 | APIGOTO endpoint correction | Incorporate with attribution: the operator identifies the international endpoint in the PR; the [homepage](https://www.china-aiapi.com) still shows the mainland endpoint. Do not call the international endpoint the current homepage quickstart. |
| #148 | System One API | Incorporate as a structured-decision gateway. The [API page](https://system-one.dev/en/api) documents model selection, classification, scoring and extraction; omit the unsupported general multi-provider chat positioning and typed star count. |
| #149 | ShanHaiGateway | Incorporate the [MIT Go gateway](https://github.com/ffseika0304/shanhai-gateway) with account-authorization and provider-ToS caveats. Omit author-reported cost/cache-hit numbers and packaging measurements. |
| #150 | Gisoo | Incorporate using the [API documentation](https://gisoo.pro/docs). Omit volatile model/provider counts and unconfirmed payment details. |
| #151 | Relay | Incorporate the [documented TensorZero fork](https://github.com/caelum0x/railyard/tree/main/apps/relay); maintain attribution and avoid claiming production acceptance. |
| #152 | Switchyard | Incorporate the [MCP tool gateway](https://github.com/caelum0x/railyard/tree/main/apps/toolgate). OAuth, egress and settlement controls are project-documented; no independent security/billing verdict. |
| #153 | Roteo | Incorporate once in each language, using the [overview](https://www.roteo.ai/docs/overview); retain the Claude Code restriction and omit unconfirmed numeric payment terms. |
| #154 | Respan Gateway | Incorporate the [Rust gateway](https://github.com/respanai/respan-gateway), distinguishing it from the hosted observability service. |
| #155 | Paidyun AI | Pending accessible primary evidence. Fetching the submitted catalog failed with a TLS EOF through Python; a separate curl attempt could not resolve the hostname. These are this review environment's failures, not proof of global downtime. Request a reachable public quickstart/catalog; do not accept the model counts or payment claims from the submission alone. |
| #156 | relay-failover | Incorporate the [local Node.js proxy](https://github.com/huangjinpeng216/relay-failover). Auth-header adaptation is not protocol conversion, and safe mid-stream recovery was not established. |
| #157 | Argus | Incorporate the [Python policy gateway](https://github.com/karmendra8386/argus). Explicitly state that the packaged CLI is mock-only, real backends require code configuration, and streaming remains on the roadmap. |
| #158 | TeapotRouter | Incorporate using the [homepage](https://teapotrouter.com/) and [public pricing JSON](https://teapotrouter.com/api/pricing); omit unsupported minimum top-up, domain-age and security claims. |
| #159 | Load testing / backpressure reading | Incorporate the two [load-testing](https://modelflare.dev/articles/llm-api-load-testing) and [backpressure](https://modelflare.dev/articles/ai-api-backpressure) guides as vendor-authored reading, not independent measurements. |
| #160 | Scalekit | Incorporate the hosted tool-auth gateway using the [AgentKit documentation](https://docs.scalekit.com/agentkit/overview/); omit connector counts and untested security assurances. |
| #161 | CloudGPU Model API | Incorporate using the [API docs](https://cloudgpu.app/api/docs), [product page](https://cloudgpu.app/api) and public `GET /v1/models` response. Preserve beta/no-SLA status. Remove the Chinese-only unsupported mainland-China restriction and avoid treating catalog identifiers as verified served models. |

Standing issues #11 and #13 remain open for discovery and production experience. The new #12 comment from a disclosed NovAI affiliate supplies a reproduction recipe, not an independent verification; the existing self-reported watch-list status stays in place.

## Snapshot review backlog

Reproduced with `python3 scripts/check_freshness.py --today 2026-10-28 --max-age-days 30`. This is a structural review of the existing datasets, not a fresh verification of their underlying claims. No `as_of` dates were advanced. Issue #146 remains open.

| Dataset | Last snapshot | Observed review gap / required completion |
| --- | --- | --- |
| `data/models.json` | 2026-09-14 | Pricing provenance is mainly prose, without per-model primary pricing URLs. Benchmarks explicitly remain July extractions. Recheck provider prices and independent boards separately; a live reseller catalog cannot establish official prices. |
| `data/gateways_eval.json` | 2026-08-31 | The review note acknowledges partial coverage; rows have no primary source URLs. Reconstruct per-score evidence against the published rubric before treating scores as current. |
| `data/free_tiers.json` | 2026-08-31 | Recheck each provider's numeric quota, expiry, card requirement and training policy, including discontinued/trial-only rows. A homepage response is insufficient. |
| `data/data_retention.json` | 2026-08-31 | Recheck every primary policy, separating gateway and upstream retention. Cloudflare's existing `zdr` field says a mode exists while its caveat says no documented guarantee: reconcile that contradiction against current documentation. |
| `data/identity_matrix.json` | 2026-08-31 | Recheck tier gates, SSO/SCIM, role scope and audit export for each vendor; do not infer OSS availability from the repository license. |
| `data/supply_chain.json` | 2026-08-31 | Recheck current advisories, affected/fixed versions and signed release artifacts. Existing incident dates are historical evidence, not current advisory coverage. |
| `data/mcp_gateways.json` | 2026-08-31 | Recheck spec baseline, pinned implementation evidence and declared assessment counts. README additions since that snapshot are not automatically capability-assessed rows; preserve unknown/not-assessed values. |

`data/topup_terms.json` remains dated 2026-10-22 and is within the 30-day window on this review date. The README now shows the actual Daily update workflow status instead of labeling a last-commit timestamp “Data verified,” and carries an explicit historical-snapshot notice. A passing content CI does not close this backlog or prove the blocking Daily update freshness gate passes.
