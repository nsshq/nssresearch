# NSS-GB-01: Polish official and e-banking lookalike domains aimed at PKO business-banking users: technical analysis

- **Published:** 2026-11-13
- **Marking:** TLP:CLEAR
- **Paper:** https://nsshq.com/research/official-lookalike-names
- **PDF:** https://nsshq.com/research/files/nss-gb-01.pdf

## Summary

From 23 October to 5 November 2026, 19 domains built on Polish words for the authorities, the government, a company and electronic banking carried 576 one-time phishing links aimed at PKO Bank Polski's business-banking customers. Every name came from public lists and the domains are now down. NSS adds the one link format that ties them, a log search to find who received a link, and a correction to NSS's own earlier record.

## What NSS measured

- **19** registered domains
- **576** one-time links, 574 codes used once
- **1** link format, search pattern in findings
- **0 of 19** domains resolving on 13 Nov 2026

## Files

| File | What it holds |
|---|---|
| `iocs.csv` | The published list exactly as on nsshq.com, 595 rows, with the context columns. Values are live, not defanged. |
| `iocs.txt` | One indicator per line, defanged. |
| `stix2.1-bundle.json` | STIX 2.1 bundle: the report, the 595 indicators, the NSS identity and the TLP:CLEAR marking. Patterns use live values. |
| `misp-event.json` | MISP event: 595 attributes plus a link to the paper. Values are live. |

Indicators: 595 domains.

## Detection flag

595 of 595 indicators carry the detection flag (`to_ids` in MISP, `malicious-activity` in STIX; the rest are `anomalous-activity`). Every name is flagged for detection: the paper offers the 19 registered domains for blocking (a block on a domain covers every link name under it) and the 576 link names for searching mail and web logs from 23 October 2026 on. The names come from public warning lists; NSS's work is the link format that ties them. The addresses the names used are not in the list.

Read the paper's limits before acting on the list. Every value was true when the paper was written and is not re-checked here.

Corrections: corrections@nsshq.com. Licence: CC BY 4.0, credit Nexus Sentinel Station (NSS) and link to the paper.
