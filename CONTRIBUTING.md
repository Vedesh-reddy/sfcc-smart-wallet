# Contributing

Start from `main` and create a focused `feature/`, `fix/`, or `docs/` branch. Keep behavior changes and documentation accurate together.

```sh
npm ci
npm run validate
npm run package:metadata
```

CI mocks cannot check platform quotas, real e-mail delivery, payment processors, Business Manager permissions, multipart uploads or metadata installation. For a platform behavior change, exercise the affected feature on a sandbox, following the sandbox verification plan in [docs/TESTING.md](docs/TESTING.md). In the PR, say which checks were automated and which were manual.

Preserve these rules:

- every money movement is one balanced, idempotent double-entry journal; balances are never edited directly;
- a hold is captured or released exactly once; the available balance can never go negative;
- top-ups stay closed outside sandbox mode until `walletLiveMoneyApproved` is set after sign-off;
- a custom object query uses at most 4 custom attribute expressions (the test harness enforces it);
- every storefront post and desk action validates CSRF, and every amount is recomputed on the server.

Keep credentials and generated output out of Git. Add new attributes to the metadata and to [docs/METADATA.md](docs/METADATA.md), and new text to the resource bundle.

See [NOTICE.md](NOTICE.md) for attribution and terms.
