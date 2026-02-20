## Summary

- What problem does this PR solve?
- What is the approach taken?

## Scope

- [ ] Frontend
- [ ] API Gateway
- [ ] Fetcher Worker
- [ ] Summarizer Worker
- [ ] Infrastructure / Docker Compose
- [ ] Documentation

## Architecture Impact

Describe how this change affects the pipeline:

- Browser -> Frontend -> API
- API -> Redis / PostgreSQL
- Fetcher -> RabbitMQ
- Summarizer -> LLM / PostgreSQL / Redis

## Test Plan

### Automated

- [ ] `cd api-gateway && go test -v ./...`
- [ ] `cd frontend && npm run test`

### Manual

1. Steps executed:
2. Expected result:
3. Actual result:

## Screenshots / Recordings (if UI changed)

<!-- Add before/after screenshots or short clip -->

## Deployment Notes

- Env vars added/changed:
- DB migrations or schema changes:
- Backward compatibility concerns:

## Checklist

- [ ] Code follows project conventions
- [ ] New/updated tests included where needed
- [ ] Docs updated (`README`, env examples, compose)
- [ ] No secrets committed
- [ ] Ready for review
