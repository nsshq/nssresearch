# NSS-GR-01: A name generator behind 294 Aldi and Lidl look-alike .shop names: technical analysis

- **Published:** 2026-11-13
- **Marking:** TLP:CLEAR
- **Paper:** https://nsshq.com/research/aldi-lidl-lookalike-shop-names
- **PDF:** https://nsshq.com/research/files/nss-gr-01.pdf

## Summary

In nine hours from 17:15 UTC on 12 November 2026, NSS's certificate records logged 294 .shop names that put an Aldi or Lidl label in front of a generated shop name, such as lidldeals[.]kelmsfordgrocer[.]shop. 222 carry a Lidl label; the 2,043 names of this shape on public lists before then carried almost only Aldi labels. The 30 registrations NSS sampled were bought at one registrar between April and July 2026, eight within 10 seconds, and left unused until November. Two branded shop pages were live when NSS loaded them; three names from the 41-word grid served no page. On 13 November 284 of the 294 were on no list NSS holds; an update follows on 20 November.

## What NSS measured

- **294** brand names logged in nine hours from 17:15 UTC, 12 Nov 2026
- **222** with a Lidl label; 4 of 2,043 before
- **30 of 30** registrations read: Apr to Jul 2026, one registrar
- **284 of 294** on no list NSS holds, 13 Nov 2026, 15:27 UTC

## Files

| File | What it holds |
|---|---|
| `iocs.csv` | The published list exactly as on nsshq.com, 261 rows, with the context columns. Values are live, not defanged. |
| `iocs.txt` | One indicator per line, defanged. |
| `stix2.1-bundle.json` | STIX 2.1 bundle: the report, the 261 indicators, the NSS identity and the TLP:CLEAR marking. Patterns use live values. |
| `misp-event.json` | MISP event: 261 attributes plus a link to the paper. Values are live. |

Indicators: 261 domains.

## Detection flag

261 of 261 indicators carry the detection flag (`to_ids` in MISP, `malicious-activity` in STIX; the rest are `anomalous-activity`). Every name is flagged for detection: the paper offers the 261 Aldi and Lidl look-alike .shop names for blocking (a block on the registered name covers the brand name under it) and for looking back through DNS, web gateway and certificate logs. The delivery-network addresses the names used are not in the list and must not be blocked; nor must the grocers' own domains.

Read the paper's limits before acting on the list. Every value was true when the paper was written and is not re-checked here.

Corrections: corrections@nsshq.com. Licence: CC BY 4.0, credit Nexus Sentinel Station (NSS) and link to the paper.
