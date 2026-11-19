# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added
- BeBee and Jobică as third/fourth sources. Both detail URLs derive from
  ANOFM ids; Jobică shortens long titles, so several title-slug variants are
  tried. JSON-LD `JobPosting` hiring organization is verified for each (#1).
- Generic JSON-LD parser handling plain objects, arrays and `@graph`, with
  posting date, salary, location and expiry date (#1).
- `_anofm_cif()` helper: ANOFM receives the raw CUI while Peviitor stores an
  8-digit id (#1).

### Changed
- Company identity set to OZALTIN INSAAT TICARET VE SANAYI ANONIM SIRKETI ANKARA SUCURSALA BUCURESTI (CUI `45642795`); repo links,
  config, docs and test fixtures rebranded (#1).
- Source identifier is now `mediere.anofm.ro, jobrapid.ro, bebee.com, jobica.ro` (#1).
- Stale-job scope covers all four source URL prefixes (#1).

### Fixed
- Mirror pages are decoded as UTF-8 so Romanian diacritics are preserved (#1).

## [1.0.0] - 2026-11-19

### Added
- Python scraper for **OZALTIN INSAAT TICARET VE SANAYI ANONIM SIRKETI ANKARA SUCURSALA BUCURESTI** (CUI `45642795`), reading jobs from ANOFM (`mediere.anofm.ro`).
- Publisher to peviitor v1 API: company upsert, job upload, stale-job delete.
- ANAF company validation with CUIScan fallback and cache.
- ANOFM job search mirroring the Node.js template.
- `validate_jobs.py` CLI for head/content URL validation.
- Unit, integration, e2e, and consistency tests.
- GitHub Actions workflows: `job-seeker-ro-spider`, `automation-testing`, deep-validate, recovery.
- GitHub Pages (`docs/`) with generated `jobs.md` and `company.json`.
- AI documentation under `ai/`.

### Fixed
- Location normalization keeps locality names such as `POROSCHIA`.
- Stale-job deletion is scoped to this scraper's URLs.
