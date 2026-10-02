# Flarchive
### Extension Archive for Flarum

A permanent, read-only archive of released versions of community extensions
for Flarum, so that they are not lost when an author deletes a repository,
rewrites a tag, or abandons a package.

> **Not affiliated with the Flarum Foundation or the Flarum project.**
> This is an independent community project. Archived code is third-party,
> unreviewed, and provided as is. Read [DISCLAIMER.md](DISCLAIMER.md) before
> using anything from the archive.

## How it works

1. New releases of `flarum-extension` packages are discovered through the
   Packagist metadata API.
2. If the tagged version declares an OSI-approved license, its source is
   forked and tagged as `archive/vX.Y.Z`. Otherwise only metadata is
   recorded and **no code is copied**.
3. Every version is recorded in the manifest in this repository.
4. Archived tags are protected: they are never modified or deleted by the
   archive (the only exception is a takedown, see [POLICY.md](POLICY.md)).

Only released, tagged versions are archived. Development versions are not.

## What this archive is not

- It is **not a package source**. Nothing is published on Packagist or any
  other index from here.
- It does **not** maintain, support, or endorse archived extensions.
- It does not guarantee completeness.

If an upstream extension disappears and you want to continue it, you may fork
the archived repository into your own account and publish it yourself under
the terms of its license. You are then the publisher and are solely
responsible for it.

## Repository layout

| Path | Content |
|---|---|
| `POLICY.md` | Scope, license gate, immutability, takedown and exclusion rules |
| `DISCLAIMER.md` | Disclaimers and limitation of liability |
| `EXCLUSIONS.md` | Packages excluded from archiving |
| `packages/{vendor}__{package}.json` | Append-only manifest, one file per package |

## Manifest format

```json
{
  "package": "vendor/package",
  "upstream": "https://github.com/vendor/package",
  "versions": [
    {
      "version": "1.2.0",
      "tag": "archive/v1.2.0",
      "commit": "0123456789abcdef0123456789abcdef01234567",
      "released": "2026-01-15",
      "archived": "2026-10-03",
      "license": "MIT",
      "source": "archived",
      "status": "ok"
    }
  ]
}
```

- `source`: `archived` (source copied) or `metadata-only` (license did not
  allow copying).
- `status`: `ok`, `diverged` (upstream tag now points elsewhere), `flagged`,
  or `removed` (takedown; only a general reason category is kept).

Entries are only ever appended.

## Reports, takedowns, and exclusions

If something here infringes your rights, contains malicious code, or exposes
personal data, or if you are a package owner who wants to be excluded from
future archiving, follow [POLICY.md](POLICY.md).

Contact: `mysuperuser01@gmail.com`
