# NSS-BK-01: Numbered bank "auth gateways": one generator, 18 brands, an empty page for anyone without the link

- **Published:** 2026-11-18
- **Marking:** TLP:CLEAR
- **Paper:** https://nsshq.com/research/numbered-bank-auth-gateways
- **PDF:** https://nsshq.com/research/files/nss-bk-01.pdf

## Summary

Between 27 October and 16 November 2026 one generator bought 48 names such as 42708-fifth-third-auth-gateway[.]icu, 46208-capone-auth-gateway[.]icu and 94709-citi-auth-gateway[.]credit: a number, a bank or carrier and a word like "auth gateway" or "identity verif", on cheap domain endings. Every one of them uses the same DNS service, and on 16 November 47 resolved to a pool of 13 small rented servers where names of different banks share the same address. 15 of the 21 names NSS tried answered with an empty page at the root, consistent with content served only on the message link; one led to a picture puzzle. On 16 November none of the 48 was on a threat list NSS takes in. Read again two days later, 44 of the 48 still answered on the same 13 servers, three had gone to a registry hold, still none was on a list, and the generator had bought six more names, two of them in a shape that reads as a credit union's own fraud-prevention line.

## What NSS measured

- **48** names from one generator, bought 27 October to 16 November 2026, all on one DNS service
- **18** brands read from the names: 16 US banks, credit unions and fintechs and two mobile carriers
- **13** small rented servers holding 47 of the names on 16 November; names of different banks share them
- **0 of 54** names on any threat list NSS takes in, on 16 and 18 November 2026: the 48 measured, plus six found later

## Files

| File | What it holds |
|---|---|
| `iocs.csv` | The published list exactly as on nsshq.com, 54 rows, with the context columns. Values are live, not defanged. |
| `iocs.txt` | One indicator per line, defanged. |
| `stix2.1-bundle.json` | STIX 2.1 bundle: the report, the 54 indicators, the NSS identity and the TLP:CLEAR marking. Patterns use live values. |
| `misp-event.json` | MISP event: 54 attributes plus a link to the paper. Values are live. |

Indicators: 54 domains.

## Detection flag

54 of 54 indicators carry the detection flag (`to_ids` in MISP, `malicious-activity` in STIX; the rest are `anomalous-activity`). Every name is flagged for detection: the paper offers all 54 look-alike names for blocking, the 48 of the measured set and the six the 18 November re-check added. The 13 server addresses are not in this list: the paper says to watch them, not block them, and they stay in the JSON file's separate watch section.

Read the paper's limits before acting on the list. Every value was true when the paper was written and is not re-checked here.

Corrections: corrections@nsshq.com. Licence: CC BY 4.0, credit Nexus Sentinel Station (NSS) and link to the paper.
