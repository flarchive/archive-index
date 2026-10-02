# Exclusions

Packages listed here are **not archived**. The worker checks this list before
every archive step.

## How a package gets listed

- The package owner (verified as a maintainer of the package on Packagist or
  of its source repository) asks to be excluded. See
  [POLICY.md, section 8](POLICY.md#8-exclusions).
- The Maintainer excludes a package following a takedown decision. See
  [POLICY.md, section 9](POLICY.md#9-takedown-requests).

Listing stops **future** versions from being archived. Versions that were
already archived are only removed under the grounds in POLICY.md section 9.

## List

Vendor-level patterns (`vendor/*`) are supported next to exact package names.

| Package | Added | Reason category |
|---|---|---|
| `flarum/*` | 2026-10-02 | maintained by an organized group |
| `fof/*` | 2026-10-02 | maintained by an organized group |
| `0.1.x-dev/*` | 2026-10-02 | invalid vendor name (mirror) |

Reason categories: `owner request`, `copyright`, `license`, `harmful content`,
`personal data`, `maintained by an organized group`, `invalid vendor name (mirror)`.