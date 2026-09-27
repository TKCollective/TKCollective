# Tanilo

Pre-action verification for AI agents: checks the claim an agent is about to act on and signs a receipt anyone can verify offline. (Tanilo was AgentOracle until September 2026; packages and repositories created under the old name keep working.)

## Verify a receipt offline

```bash
pip install tanilo-receipt-verify
```

```python
from tanilo_receipt_verify import verify

result = verify(envelope, jwks_by_issuer={
    "https://agentoracle.co/.well-known/jwks.json": ao_jwks,
    "https://agenttrust.uk/.well-known/jwks.json": at_jwks,
})

if result.status == "valid":
    print("verified — canonical:", result.canonical_sha256)
```

## Read more

- IETF Internet-Draft (individual submission, work in progress): draft-krausz-verification-state — https://datatracker.ietf.org/doc/draft-krausz-verification-state/ (working repo: [agentoracle-ietf-id](https://github.com/TKCollective/agentoracle-ietf-id))
- Spec + conformance vectors: [tanilo-receipt-spec](https://github.com/TKCollective/tanilo-receipt-spec)
- Offline verifier: [tanilo-receipt-verify](https://github.com/TKCollective/tanilo-receipt-verify) ([PyPI](https://pypi.org/project/tanilo-receipt-verify/))
- Benchmark: [tanilo-benchmark](https://github.com/TKCollective/tanilo-benchmark) + [tanilo-eval-harness](https://github.com/TKCollective/tanilo-eval-harness)
- MCP server: [tanilo-mcp](https://github.com/TKCollective/tanilo-mcp)
- Free Article 12 self-check: https://tanilo.io/article-12

Contact: joe@tanilo.io · https://tanilo.io
