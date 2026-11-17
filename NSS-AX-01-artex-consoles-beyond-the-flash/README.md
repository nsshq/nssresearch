# NSS-AX-01: 24 additional ARTEX consoles live on 14 November 2026, and the reseller layer behind them: a companion to the FBI FLASH

- **Published:** 2026-11-17
- **Marking:** TLP:CLEAR
- **Paper:** https://nsshq.com/research/artex-consoles-beyond-the-flash
- **PDF:** https://nsshq.com/research/files/nss-ax-01.pdf

## Summary

On 13 November 2026 the FBI published FLASH-20261113-001 on ARTEX, a framework public reporting ties to intrusions against finance and managed-service providers, with 24 addresses and one domain, and asked defenders for console and reseller indicators. NSS Research offers this paper in support of that request. All 25 FLASH indicators are corroborated here, each with the date it entered NSS's records. On 14 November NSS confirmed 24 additional ARTEX consoles active, and this edition takes the console fingerprint apart: the page identity and the certificate issuer that name the framework, the two-class structure NSS sees across the set, per-claim confidence, a dated timeline, and detection NSS validated against its own stored readings. It maps the reseller layer behind the FLASH's domain and records one apparent operator tie it tested and rejected. Under NSS's disclosure plan every console address stays held; the counts, the fingerprint and the detection are what ship here.

## What NSS measured

- **2** detection signatures NSS validated against its stored console readings: the page identity and the certificate issuer that name the framework

## Files

| File | What it holds |
|---|---|
| `iocs.csv` | The published list exactly as on nsshq.com, 22 rows, with the context columns. Values are live, not defanged. |
| `iocs.txt` | One indicator per line, defanged. |
| `stix2.1-bundle.json` | STIX 2.1 bundle: the report, the 22 indicators, the NSS identity and the TLP:CLEAR marking. Patterns use live values. |
| `misp-event.json` | MISP event: 22 attributes plus a link to the paper. Values are live. |

Indicators: 1 domain, 21 IP addresses.

## Detection flag

22 of 22 indicators carry the detection flag (`to_ids` in MISP, `malicious-activity` in STIX; the rest are `anomalous-activity`). Every indicator is flagged for detection: this file carries the 25 indicators of FBI FLASH-20261113-001 (24 addresses and one domain, less the three shared-provider addresses the FLASH itself marks transient) that NSS corroborates, each already published in the FLASH, for blocking at DNS and the egress gateway. Under NSS's disclosure plan every one of the 24 additional ARTEX consoles NSS confirmed active is held, so no console address is in this file; the console deliverable is the landing-page title and the framework-named certificate issuer fingerprint and the tested detection in the paper. Two addresses (85.11.167.52, 91.92.240.238) carry older unrelated listings; block them in the framework context noted.

Read the paper's limits before acting on the list. Every value was true when the paper was written and is not re-checked here.

Corrections: corrections@nsshq.com. Licence: CC BY 4.0, credit Nexus Sentinel Station (NSS) and link to the paper.
