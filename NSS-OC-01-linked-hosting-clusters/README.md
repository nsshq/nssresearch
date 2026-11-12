# NSS-OC-01: Linked hosting clusters and the purchase batches behind them: technical analysis

- **Published:** 2026-11-11
- **Marking:** TLP:CLEAR
- **Paper:** https://nsshq.com/research/linked-hosting-clusters
- **PDF:** https://nsshq.com/research/files/nss-oc-01.pdf

## Summary

Public warning lists carry more than 1,800 shop-style domain names that point at one hosting network. A list says a name is bad; it does not say which names belong together. NSS read the public registration record of every name and found that 1,770 of them were bought in 98 batches, each batch within seconds, and that those batches tie nine hosts in six address blocks into three groups. This paper sets out what was measured, what it does and does not prove, and what a defender can look for.

## What NSS measured

- **1,770** names tied to a group by a purchase batch
- **98** purchase batches, April to November 2026
- **46 s** median time from first to last name in a batch
- **53** batches that span two address blocks

## Files

| File | What it holds |
|---|---|
| `iocs.csv` | The published list exactly as on nsshq.com, 1770 rows, with the context columns. Values are live, not defanged. |
| `iocs.txt` | One indicator per line, defanged. |
| `stix2.1-bundle.json` | STIX 2.1 bundle: the report, the 1770 indicators, the NSS identity and the TLP:CLEAR marking. Patterns use live values. |
| `misp-event.json` | MISP event: 1770 attributes plus a link to the paper. Values are live. |

Indicators: 1770 domains.

## Detection flag

1770 of 1770 indicators carry the detection flag (`to_ids` in MISP, `malicious-activity` in STIX; the rest are `anomalous-activity`). Every name is flagged for detection: the paper offers the list for blocking and for looking back through logs. The names come from public warning lists that call them fake shops; NSS's work is the grouping by purchase batch.

Read the paper's limits before acting on the list. Every value was true when the paper was written and is not re-checked here.

Corrections: corrections@nsshq.com. Licence: CC BY 4.0, credit Nexus Sentinel Station (NSS) and link to the paper.
