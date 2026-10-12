# CEISA References

Runtime master data for the ANC frontend.

## Files

- `manifest.json` lists the available reference datasets and their version.
- Each `*.json` file contains records with `code`, `name`, optional `documentCode`, and `isActive`.
- `kantor.json`, `jenis-identitas.json`, and `fasilitas-ppn.json` migrate the existing BC 4.0 frontend options. They contain only the options previously present in the application, not a complete official reference list.

## HS Code BTKI 2022

`hs-code.json` contains all 11,552 eight-digit codes from the `HS_Master` sheet of `HS_Code_BTKI_2022.xlsx`. Codes remain strings, including their leading zeros.

Fields preserve the source data: `code`, `name` (original Indonesian description), `descriptionEn`, `contextId`, `contextEn`, `formattedCode`, `chapter`, `heading`, `subheading`, `importDutyText`, `sourcePage`, `reviewNote`, `sequence`, and `isActive`.

For search and display, use `contextId` alongside `code`: many original descriptions are only "Lain-lain" or "Bibit" and require their parent context.

Source: the supplied workbook's extraction of PMK 26/PMK.010/2022, Lampiran III, PDF pages 230–673. The workbook reports OCR spelling errors and unresolved tariff reviews. Duty values are preserved as text without interpretation. `isActive: true` means enabled in this dataset, not verification of current regulatory validity. Subsequent regulatory amendments are not included.

## Publishing with GitHub Pages

Enable GitHub Pages from the `main` branch and the repository root. The frontend should use:

```env
VITE_MASTER_DATA_URL=https://agungks74.github.io/ceisa-references
```

After changing a dataset, update `manifest.json`'s `version`, commit, and push. Keep old codes as inactive instead of deleting them when historical documents may still reference them.

This repository contains public reference data only. Do not add credentials, API keys, or company-sensitive data.
