# NABEEL outbound distribution

`scripts/nabeel-distribution.py` is the fail-closed outbound adapter for approved live destinations.

- destination configuration contains only secret **references** (`secret_env`), never stream keys;
- every destination has an explicit `enabled` flag;
- `status` reports readiness without revealing credentials;
- `run --dry-run` proves command construction with secrets redacted;
- an enabled destination with a missing secret exits non-zero and does not invoke FFmpeg.

Example:

```bash
scripts/nabeel-distribution.py --config docs/nabeel-destinations.example.json status
scripts/nabeel-distribution.py --config /secure/path/destinations.json run youtube --dry-run
```

Production/live publishing remains a separate explicit operation. A real private/unlisted destination test requires the corresponding credential to be supplied outside Git.
