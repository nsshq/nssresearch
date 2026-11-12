# NSS-WA-01: WhatsApp lookalike kit: technical analysis

- **Published:** 2026-11-10
- **Marking:** TLP:CLEAR
- **Paper:** https://nsshq.com/research/whatsapp-lookalike-kit
- **PDF:** https://nsshq.com/research/files/nss-wa-01.pdf

## Summary

Over three days in late October 2026, 51 domain names imitating WhatsApp were registered in three batches, each batch within a single minute. NSS recorded every one within 27 hours of its registration, tied the 51 together from public registration and hosting records, and read a copy of the WhatsApp sign-in page on 11 of them. This paper sets out what was observed, how the names were tied together, and what a defender can look for.

## What NSS measured

- **51** lookalike names in one kit
- **3** registration minutes for all 51
- **11** names where NSS read the sign-in copy
- **18 h** median from registration to first NSS record

## Files

| File | What it holds |
|---|---|
| `iocs.csv` | The published list exactly as on nsshq.com, 52 rows, with the context columns. Values are live, not defanged. |
| `iocs.txt` | One indicator per line, defanged. |
| `stix2.1-bundle.json` | STIX 2.1 bundle: the report, the 52 indicators, the NSS identity and the TLP:CLEAR marking. Patterns use live values. |
| `misp-event.json` | MISP event: 52 attributes plus a link to the paper. Values are live. |

Indicators: 52 domains.

## Detection flag

47 of 52 indicators carry the detection flag (`to_ids` in MISP, `malicious-activity` in STIX; the rest are `anomalous-activity`). The 47 names NSS rated High risk are flagged for detection. The four kit names never rated High risk and the relay label are published unflagged: the relay label is a pivot for finding sibling names, not a block rule, because the relay service has other customers.

Read the paper's limits before acting on the list. Every value was true when the paper was written and is not re-checked here.

Corrections: corrections@nsshq.com. Licence: CC BY 4.0, credit Nexus Sentinel Station (NSS) and link to the paper.
