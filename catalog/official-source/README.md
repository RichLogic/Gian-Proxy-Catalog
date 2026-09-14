# Official Catalog source

Authoritative source for signed `catalog-v1.*` Releases managed in this
repository. Catalog metadata remains separate from App and executable Proxy
assets in `RichLogic/Gian`. This tree describes the currently visible official
Proxies:

| Plugin ID | Product name | Version |
|---|---|---|
| `claude` | Claude Code | 0.2.4 |
| `codex` | Codex | 0.2.16 |
| `kimi` | Kimi Code | 0.2.10 |
| `ai.deepseek.harness` | DeepSeek Harness | 0.1.6 |
| `com.zhipu.zcode` | ZCode | 0.1.1 |

`io.gian.fixture` and `grok` are not official Catalog source entries.
`grok` remains a shipped executor but is hidden from the product surface.

This checked-in source remains **documentation-only** until independently
certified immutable Proxy releases exist. Stable artifact coordinates are added
only from `scripts/prepare-catalog-coordinate.mjs` output bound to those exact
public bytes in `RichLogic/Gian`. The compiler must not invent GitHub URLs,
sentinel hashes, or sizes. See
the publication workflow in the repository root README.

## Production trust root

The production Host pins public key
`8721796e6bdf8798804745396bd2181cd999f261d077f09a6fdaa180091344df`
(`keyId` `gian-official-catalog-2026-09`). The matching private key is
stored only as the protected `RichLogic/Gian-Proxy-Catalog` Actions secret
`GIAN_CATALOG_SIGNING_KEY_PEM`. The repository cannot export or print it.
Do not generate, print, download, or commit a replacement production key from
this source tree. Key rotation requires an explicit Gian trust-root update.
