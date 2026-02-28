## Linked Issue

Closes #

## Summary

- Problem:
- Approach:
- Why this approach:

## Scope

- [ ] Frontend
- [ ] API Gateway
- [ ] Fetcher Worker
- [ ] Summarizer Worker
- [ ] Infrastructure / Docker Compose
- [ ] Documentation

## Files Changed

List the most important files and why they changed.

## Architecture Impact

Describe impact on:

- Browser -> Frontend -> API
- API -> Redis / PostgreSQL / fallback provider
- Fetcher -> RabbitMQ
- Summarizer -> LLM / PostgreSQL / Redis

## Test Plan

### Unit

- [ ] `cd api-gateway && go test ./...`
- [ ] `cd frontend && pnpm test`

### Integration

- [ ] `docker compose up -d --build`
- [ ] `curl http://localhost:18080/api/health`
- [ ] Relevant `/api/news` query verified

### Regression

- [ ] Filter change flow verified (date/topic/country/count)
- [ ] Load/Refresh behavior verified
- [ ] Error/empty state behavior verified

## Screenshots / Recordings (UI changes)

<!-- Add before/after images or a short clip -->

## Deployment Notes

- Env vars added/changed:
- Data/schema changes:
- Backward compatibility:
- Rollback plan:

## Checklist

- [ ] Tests added/updated where needed
- [ ] Docs updated (root/module README or env examples)
- [ ] No secrets committed
- [ ] Ready for review
