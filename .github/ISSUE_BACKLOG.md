# Issue Backlog (Project-Wide)

Use these issue drafts directly in GitHub. Each issue includes the expected file scope.

## 1) feat(frontend): Persist filter state in URL query params

Labels: `feature`, `frontend`

Acceptance criteria:

- Filter values are serialized into URL params.
- Reload restores the same filter state.
- Shared URL reproduces the same query.

Files to add/update:

- `frontend/src/pages/Index.tsx`
- `frontend/src/components/FilterPanel.tsx`
- `frontend/src/lib/urlState.ts` (new)
- `frontend/src/lib/urlState.test.ts` (new)
- `frontend/README.md`

## 2) bug(frontend): Prevent stale response override when filters change quickly

Labels: `bug`, `frontend`

Acceptance criteria:

- Only latest request updates UI state.
- Fast filter toggles do not show outdated data.

Files to add/update:

- `frontend/src/pages/Index.tsx`
- `frontend/src/lib/newsApi.ts`
- `frontend/src/lib/newsApi.test.ts`

## 3) feat(api): Add pagination (`offset`, `nextCursor`) to `/api/news`

Labels: `feature`, `api-gateway`

Acceptance criteria:

- Endpoint supports pagination fields.
- Response includes pagination metadata.

Files to add/update:

- `api-gateway/models.go`
- `api-gateway/params.go`
- `api-gateway/repository_postgres.go`
- `api-gateway/http.go`
- `api-gateway/main_test.go`
- `api-gateway/README.md`

## 4) refactor(api): Add service-level metrics and structured logs

Labels: `tech-debt`, `api-gateway`, `infra`

Acceptance criteria:

- Request timing and status metrics emitted.
- Consistent structured logs with request correlation ID.

Files to add/update:

- `api-gateway/main.go`
- `api-gateway/http.go`
- `api-gateway/service.go`
- `api-gateway/middleware_logging.go` (new)
- `docker-compose.yml`
- `README.md`

## 5) test(worker-fetcher): Add unit tests for query/topic mapping and dedupe

Labels: `testing`, `worker-fetcher`

Acceptance criteria:

- Topic alias/query mapping tested.
- Duplicate message suppression tested.

Files to add/update:

- `worker-fetcher/fetcher.py`
- `worker-fetcher/test_fetcher.py` (new)
- `worker-fetcher/requirements-dev.txt` (new)
- `worker-fetcher/README.md`

## 6) test(worker-summarizer): Add unit tests for summarization fallback logic

Labels: `testing`, `worker-summarizer`

Acceptance criteria:

- LLM error path falls back deterministically.
- Importance scoring and domain normalization covered.

Files to add/update:

- `worker-summarizer/summarizer.py`
- `worker-summarizer/test_summarizer.py` (new)
- `worker-summarizer/requirements-dev.txt` (new)
- `worker-summarizer/README.md`

## 7) feat(infra): Add CI workflow for lint + unit + docker build

Labels: `infra`, `ci-cd`

Acceptance criteria:

- CI runs frontend tests, api tests, and docker build checks.
- Fails fast on broken tests.

Files to add/update:

- `.github/workflows/ci.yml` (new)
- `frontend/package.json`
- `api-gateway/README.md`
- `README.md`

## 8) feat(infra): Add nightly regression workflow

Labels: `infra`, `ci-cd`, `testing`

Acceptance criteria:

- Nightly job spins up compose stack.
- Runs API contract smoke checks and key user flows.

Files to add/update:

- `.github/workflows/nightly-regression.yml` (new)
- `docker-compose.yml`
- `README.md`

## 9) chore(security): Add secret scanning and dependency auditing

Labels: `security`, `infra`

Acceptance criteria:

- Secret scan in PR pipeline.
- Dependency audit for Node and Python.

Files to add/update:

- `.github/workflows/security.yml` (new)
- `.pre-commit-config.yaml`
- `README.md`

## 10) feat(frontend): Add empty/error retry panel with contextual suggestions

Labels: `feature`, `frontend`

Acceptance criteria:

- Empty/error states explain cause and next step.
- One-click retry available.

Files to add/update:

- `frontend/src/pages/Index.tsx`
- `frontend/src/components/EmptyState.tsx` (new)
- `frontend/src/components/ErrorState.tsx` (new)
- `frontend/src/components/FilterPanel.tsx`

## 11) feat(frontend): Add saved searches

Labels: `feature`, `frontend`

Acceptance criteria:

- Save/load named filter presets.
- Presets survive page reload.

Files to add/update:

- `frontend/src/pages/Index.tsx`
- `frontend/src/components/FilterPanel.tsx`
- `frontend/src/lib/savedSearches.ts` (new)
- `frontend/src/lib/savedSearches.test.ts` (new)

## 12) feat(api): Add domain whitelist and query validation guardrails

Labels: `feature`, `api-gateway`

Acceptance criteria:

- Invalid domains are rejected with clear errors.
- Query length/syntax guardrails enforced.

Files to add/update:

- `api-gateway/params.go`
- `api-gateway/utils.go`
- `api-gateway/main_test.go`
- `api-gateway/README.md`

## 13) refactor(frontend): Move API/query state to React Query

Labels: `tech-debt`, `frontend`

Acceptance criteria:

- Requests and caching managed by React Query.
- Manual stale/race handling in page component removed.

Files to add/update:

- `frontend/src/pages/Index.tsx`
- `frontend/src/lib/newsApi.ts`
- `frontend/src/hooks/useNewsQuery.ts` (new)
- `frontend/src/main.tsx`

## 14) feat(observability): Add Sentry integration for frontend and API

Labels: `feature`, `infra`, `frontend`, `api-gateway`

Acceptance criteria:

- Unhandled errors captured with release tags.
- Sensitive data scrubbing configured.

Files to add/update:

- `frontend/src/main.tsx`
- `api-gateway/main.go`
- `docker-compose.yml`
- `README.md`

## 15) docs(project): Architecture Decision Records (ADRs)

Labels: `docs`, `tech-debt`

Acceptance criteria:

- ADR template present.
- Initial ADRs for queue, caching, and fallback strategy.

Files to add/update:

- `docs/adr/README.md` (new)
- `docs/adr/0001-queue-choice.md` (new)
- `docs/adr/0002-cache-strategy.md` (new)
- `docs/adr/0003-live-fallback-policy.md` (new)
- `README.md`
