# NSS-TK-01: Fake imToken download sites push an Android app that sends recovery phrases and private keys to one server: technical analysis

- **Published:** 2026-11-13
- **Marking:** TLP:CLEAR
- **Paper:** https://nsshq.com/research/fake-imtoken-download-sites
- **PDF:** https://nsshq.com/research/files/nss-tk-01.pdf

## Summary

Copies of imToken's Chinese website offer an Android app from outside the official store. It is not imToken. NSS downloaded it and read its code: it sends the recovery phrase of every wallet created or imported in it to pt888999[.]com, and private keys to api[.]quick-node[.]com, a name that imitates QuickNode, which is not involved. On 13 November 2026 both names pointed to one server. Block both domains, look for the package com[.]anonymous[.]wallet, and treat any wallet made in it as exposed. NSS recorded 53 of the look-alike names; 40 were on no threat list NSS takes in on 13 November.

## What NSS measured

- **1** server behind both names the app sends recovery phrases and private keys to
- **53** look-alike names NSS recorded from new registrations, 8 to 12 November
- **5** purchases of ten names each, every one inside 2 seconds
- **40 of 53** names on no threat list NSS takes in on 13 November

## Files

| File | What it holds |
|---|---|
| `iocs.csv` | The published list exactly as on nsshq.com, 75 rows, with the context columns. Values are live, not defanged. |
| `iocs.txt` | One indicator per line, defanged. |
| `stix2.1-bundle.json` | STIX 2.1 bundle: the report, the 75 indicators, the NSS identity and the TLP:CLEAR marking. Patterns use live values. |
| `misp-event.json` | MISP event: 75 attributes plus a link to the paper. Values are live. |

Indicators: 70 domains, 5 IP addresses.

## Detection flag

75 of 75 indicators carry the detection flag (`to_ids` in MISP, `malicious-activity` in STIX; the rest are `anomalous-activity`). Every indicator is flagged for detection: the paper offers the two names that receive recovery phrases and private keys, their registered domain, the forwarding domain and its shared host, the four forwarding addresses, the 62 download names and the address the receiving names used on 13 November 2026 for blocking. That address is an indicator as of that date, not an operator asset; block it only while the receiving names point to it.

Read the paper's limits before acting on the list. Every value was true when the paper was written and is not re-checked here.

Corrections: corrections@nsshq.com. Licence: CC BY 4.0, credit Nexus Sentinel Station (NSS) and link to the paper.
