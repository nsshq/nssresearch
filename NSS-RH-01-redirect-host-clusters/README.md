# NSS-RH-01: Lottery redirect names on a shared delivery network: technical analysis

- **Published:** 2026-11-11
- **Marking:** TLP:CLEAR
- **Paper:** https://nsshq.com/research/redirect-host-clusters
- **PDF:** https://nsshq.com/research/files/nss-rh-01.pdf

## Summary

Two address blocks on two different networks answer for the same 319 throwaway names, and the names open Chinese-language lottery and betting pages. NSS recorded 100 of those names itself, a median of 21 minutes after their certificates appeared, and none of the 100 is on any list NSS holds. This paper sets out what ties the names together, why the two blocks are a shared delivery network and not one operator's servers, and what a defender can look for.

## What NSS measured

- **319** names answering from the two blocks
- **100** recorded by NSS and on no list NSS holds
- **21 min** median from certificate log to NSS record
- **13** purchase batches holding 140 registered names

## Files

| File | What it holds |
|---|---|
| `iocs.csv` | The published list exactly as on nsshq.com, 319 rows, with the context columns. Values are live, not defanged. |
| `iocs.txt` | One indicator per line, defanged. |
| `stix2.1-bundle.json` | STIX 2.1 bundle: the report, the 319 indicators, the NSS identity and the TLP:CLEAR marking. Patterns use live values. |
| `misp-event.json` | MISP event: 319 attributes plus a link to the paper. Values are live. |

Indicators: 319 domains.

## Detection flag

0 of 319 indicators carry the detection flag (`to_ids` in MISP, `malicious-activity` in STIX; the rest are `anomalous-activity`). No name is flagged for detection. The paper records lottery and betting pages behind throwaway names, does not rule on their lawfulness, and offers the list for policy that restricts gambling sites and for looking back through logs.

Read the paper's limits before acting on the list. Every value was true when the paper was written and is not re-checked here.

Corrections: corrections@nsshq.com. Licence: CC BY 4.0, credit Nexus Sentinel Station (NSS) and link to the paper.
