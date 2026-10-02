# Archive Policy

**Extension Archive for Flarum** (the "Archive")

Last updated: 2026-10-02

This document defines what the Archive does, what it does not do, and how
requests such as takedowns and exclusions are handled. The Archive is run by a
single maintainer (the "Maintainer"), who makes all decisions described here.
See also [DISCLAIMER.md](DISCLAIMER.md) and [EXCLUSIONS.md](EXCLUSIONS.md).

---

## 1. Purpose

Community extensions for Flarum are published by individuals. When an author
deletes a repository, rewrites a tag, or abandons a package, released versions
can disappear and sites depending on them can break or lose the ability to
audit what they ran.

The Archive keeps a **permanent, read-only copy of released extension
versions** so that this history is not lost. Nothing more.

## 2. Independence and trademark

- The Archive is an independent, community-run project. It is **not
  affiliated with, endorsed by, or sponsored by the Flarum Foundation** or the
  Flarum project.
- The Archive follows the Flarum Foundation's
  [Legal & Branding guidelines](https://flarum.org/foundation/legal):
  "Flarum" is referenced only to describe what the Archive relates to (for
  example, "for Flarum"), never as the name of an account, company, or
  product, and the Flarum logo is not used as the Archive's own.
- The Archive's domain does not contain the trademarked name.

## 3. What is archived

- **Discovery:** packages on [Packagist](https://packagist.org) of type
  `flarum-extension`, found through the Packagist metadata/changes API.
- **Versions:** released, tagged versions only. Development branches and
  development versions (`dev-*`) are not archived.
- **Scope of copy:** the source code at the tagged commit, together with its
  full license and copyright notices, exactly as published by the author.
- **Quality:** best effort ("good enough, not perfect"). The Archive may miss
  a release, be delayed, or fail to archive a package, and makes no promise of
  completeness.

## 4. License gate

The Archive only copies source code that its license allows to be copied and
redistributed. The decision is made **per version**, using the license
declared in the `composer.json` of the tagged commit:

| License status of the tagged version | What the Archive does |
|---|---|
| A license identifier (SPDX) that is OSI-approved | Source is forked/copied and tagged; manifest entry recorded |
| No license, `proprietary`, unreadable, or non-OSI | **Metadata only** (package, version, commit SHA, date, declared license). **No source code is copied.** |

Additional rules:

- If a package later adds or changes its license, only versions whose own
  tagged `composer.json` declares a qualifying license are archived with
  source. Versions already archived are not re-evaluated retroactively, except
  through the takedown process in section 9.
- The Archive does not verify that the declared license is accurate and does
  not provide legal advice. A wrongly declared license is handled through
  section 9.

## 5. Immutability

- Archived versions are stored as tags named `archive/vX.Y.Z` in the
  Archive's repositories. Tag deletion and force-pushes are blocked by
  organization-level rules.
- Once archived, a version is **never modified or removed by the Archive**,
  with the sole exception of the cases in sections 8 and 9.
- If the upstream author later moves, deletes, or re-creates a tag so that it
  points to a different commit, the Archive keeps the original archived commit
  and records the divergence in the manifest. The Archive does not follow the
  rewritten tag.

## 6. Read-only; not a distribution channel

- The Archive does not modify code, does not add commits of its own to
  archived repositories, does not publish releases, and does **not register
  anything on Packagist or any other package index**.
- Issues, pull requests, and discussions are disabled on archived
  repositories. Archived code is not supported or maintained.
- The Archive does not use, run, sell, or provide any archived extension.

## 7. Reuse by third parties

Anyone may use archived code only under the terms of the license of that code.
If an upstream extension has been deleted and a developer wants to continue
it, they may fork the Archive's repository into their own account and publish
it themselves, in line with the license. In that case:

- the developer is the publisher and is solely responsible for that
  publication, including its quality, security, naming, and license
  compliance;
- the Archive does not endorse, support, or take part in the continuation;
- continuing an abandoned extension is a separate process and is not part of
  the Archive.

## 8. Exclusions

Authors and rights holders may ask that their package be excluded.

- **Future versions:** a verified request from the package's owner to stop
  archiving it is always honored. The package is listed in
  [EXCLUSIONS.md](EXCLUSIONS.md) and no further versions are archived.
- **Already archived versions:** these are kept, because the license on them
  already permitted copying, unless one of the grounds in section 9 applies
  (legal claim, malicious content, personal data, or a license that did not
  permit archiving).
- Exclusions apply to code copies. The Archive may keep minimal factual
  metadata (package name, version numbers, dates) in the manifest.

## 9. Takedown requests

The Archive may receive requests concerning copyright or license violations,
malicious or harmful code, or personal data.

**How to submit:** email the contact address in section 12 with:

1. the package and version(s) concerned and the repository URL;
2. who you are and, for copyright or license claims, your relationship to the
   rights holder;
3. the specific reason (what right is infringed, what is harmful, or what
   personal data is included);
4. a way to contact you.

**What happens:**

1. The Maintainer acknowledges the request as soon as reasonably possible.
2. While the request is reviewed, the affected repository or tag may be made
   temporarily unavailable.
3. If the request is judged legitimate, the affected content is removed. If
   it is not, access is restored and the requester is told why.
4. The manifest keeps a minimal record marking the version as removed, with
   only a general reason category (for example "copyright", "license",
   "harmful content", "personal data"). The text of the request and the
   requester's identity are not published.
5. A package owner who disagrees with a removal or flagging decision can
   reply to the same email thread to contest it.

This process is separate from, and in addition to, any notices submitted
directly to GitHub under GitHub's own policies, which the Archive also
follows.

This is the only process through which archived code is removed.

## 10. Security and malicious code

The Archive does not review, scan, or vouch for the code it stores. An
archived version may contain bugs, vulnerabilities, or malicious code that
was present in the original release. If you find such a case, report it
using section 9. The Archive may flag a version in the manifest, remove it, or
both. See [DISCLAIMER.md](DISCLAIMER.md).

## 11. Changes to this policy

The Maintainer may update this policy. Changes are tracked in this
repository's Git history. Updates do not weaken the immutability rule in
section 5 except to add a removal ground that is legally required.

## 12. Contact

- Email: `mysuperuser01@gmail.com`
- Maintainer: `@huseyinfiliz`