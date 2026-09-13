# Gian Proxy Catalog

Public signed metadata Catalog for Gian Proxy and managed Runtime releases.

This repository owns only Catalog source, documentation, display assets, and
immutable `catalog-v1.<sequence>.0` Releases. Gian App and Proxy executables
remain in [`RichLogic/Gian`](https://github.com/RichLogic/Gian); approved
vendor Runtime assets may remain on their official immutable channels.

The production signing key is available only to GitHub Actions as the
write-only `GIAN_CATALOG_SIGNING_KEY_PEM` secret. This repository never stores,
prints, or generates that private key. Gian pins the matching public key in its
source tree and verifies every downloaded Catalog byte before activation.

## Publication

Run **Release Signed Gian Catalog** with:

- an exact 40-character certified Gian commit SHA;
- the next monotonic Catalog sequence;
- a reproducible ISO-8601 issue timestamp.

The workflow checks out that Gian revision for the compiler and trust policy,
verifies that every shipping entry has a certified Proxy/Runtime combination,
compiles and verifies the production signature, then publishes an immutable
Catalog Release. Documentation-only source cannot be published.
