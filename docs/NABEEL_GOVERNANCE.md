# NABEEL Station repository governance

This repository participates in the NABEEL Station open-source integration stack.

## Repository authority

- Codestra fork: `https://github.com/ingtrader21-spec/MediaMTX.git`
- Upstream source: `https://github.com/bluenviron/mediamtx.git`
- Codestra integration branch: `nabeel/integration`
- Upstream code is synchronized by fetch/review; upstream history is not rewritten.
- Product-specific changes stay on governed integration branches and are reviewed before any default-branch merge.

## Reproducible bootstrap

```bash
git clone https://github.com/ingtrader21-spec/MediaMTX.git
cd MediaMTX
git remote add upstream https://github.com/bluenviron/mediamtx.git
git fetch origin --prune
git fetch upstream --prune
git checkout nabeel/integration
```

Before changing source, verify a clean tree with `git status --short --branch`. Never reset, clean, stash, force-push, or overwrite unknown local work.

## Licensing

The upstream license authority is preserved in `LICENSE` and any repository-specific third-party license directories/files. Codestra integration work does not remove or replace upstream license notices.

## Secrets and live effects

Credentials, stream keys, pairing secrets, tokens, and device identifiers must not be committed. Runtime secrets come from local environment/secret references. Live publishing or external-provider effects remain explicit opt-in operations and fail closed when required credentials or certification evidence are absent.

## NABEEL evidence contract

Completion evidence for NABEEL work must record:
1. exact Git SHA;
2. build/test results;
3. runtime health/readback;
4. credential/secret boundary;
5. rollback or recovery path;
6. any hardware or external-provider gate that remains unproven.

A Linear status alone is not completion evidence.
