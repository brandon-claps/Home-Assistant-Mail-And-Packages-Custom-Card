{% if prerelease %}

### This is a pre-release version

It may contain bugs. Please review open issues and submit new issues to the [GitHub issue tracker](https://github.com/moralmunky/Home-Assistant-Mail-And-Packages-Custom-Card/issues).

{% endif %}

{% if installed %}

## Changes as compared to the installed version:

### Breaking Changes

{% if version_installed.replace("v", "").replace(".","") | int < 100  %}
This is a major rewrite. Remove the current card from your dashboard and add a new card from the card picker.
- Migrated from lit-element 2.x to Lit 3.x
- Config keys normalized to lowercase (backward compatible with old uppercase keys)
{% endif %}

### Changes

{% if version_installed.replace("v", "").replace(".","") | int < 100  %}

- **New: Package Tracker card** (`custom:mailandpackages-tracker`) — Full-page tracking dashboard with Package Registry integration
- Added 5 new carriers: Australia Post, Poczta Polska, InPost, DPD, GLS (13 total)
- Package Registry service call buttons: Add Package, Mark Delivered, Clear, Clear All Delivered
- Status-grouped display with collapsible sections
- Expandable package detail rows with carrier links
- Null-safety for all entity state access (no more crashes when sensors are missing)
- Data-driven carrier rendering (centralized carrier definitions)
- Modernized tech stack: Lit 3.x, TypeScript 5.x, Rollup 4.x

{% endif %}

---

{% endif %}

![GitHub release (latest by date)](https://img.shields.io/github/v/release/moralmunky/Home-Assistant-Mail-And-Packages-Custom-Card)
[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/custom-components/hacs)

Custom Lovelace cards for the [Mail and Packages integration](https://github.com/moralmunky/Home-Assistant-Mail-And-Packages).

**Two cards in one bundle:**

1. **Mail and Packages** — Summary card with carrier icons, package counts, and camera feeds
2. **Package Tracker** — Full-page tracking dashboard showing individual packages from the Package Registry

### 13 Supported Carriers

USPS, UPS, FedEx, Amazon, DHL, Canada Post, Hermes, Royal Mail, Australia Post, Poczta Polska, InPost, DPD, GLS

### Package Tracker Features

- Packages grouped by status: Out for Delivery, In Transit, Detected, Delivered
- Expandable detail rows with full metadata
- Service call buttons: Add Package, Mark Delivered, Clear, Clear All Delivered
- Best used in Panel mode for a full-page experience
- Requires Package Registry enabled in the integration
