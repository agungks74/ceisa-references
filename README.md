# CEISA References

Runtime master data for the ANC frontend.

## Files

- `manifest.json` lists the available reference datasets and their version.
- Each `*.json` file contains records with `code`, `name`, optional `documentCode`, and `isActive`.

## Publishing with GitHub Pages

Enable GitHub Pages from the `main` branch and the repository root. The frontend should use:

```env
VITE_MASTER_DATA_URL=https://agungks74.github.io/ceisa-references
```

After changing a dataset, update `manifest.json`'s `version`, commit, and push. Keep old codes as inactive instead of deleting them when historical documents may still reference them.

This repository contains public reference data only. Do not add credentials, API keys, or company-sensitive data.
