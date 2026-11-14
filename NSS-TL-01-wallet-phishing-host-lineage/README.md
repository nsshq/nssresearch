# NSS-TL-01: One wallet-phishing operator, six servers in three weeks: followed by the names it carried host to host

- **Published:** 2026-11-14
- **Marking:** TLP:CLEAR
- **Paper:** https://nsshq.com/research/wallet-phishing-host-lineage
- **PDF:** https://nsshq.com/research/files/nss-tl-01.pdf

## Summary

Twenty-four names moved with one wallet-phishing operation across six servers between 27 October and 14 November 2026, the stretch NSS's own resolution record covers; six of them went the whole way from the first server NSS recorded to the sixth, the server behind NSS-TK-01, the fake imToken download sites. Twenty-two of the moved names sat behind the operation's forwarding layer, each keeping its own label while the address behind it changed. The operation's oldest names were bought in July and on lists from August. Of the 104 names NSS saw on the six servers, 34 were on a threat list NSS takes in on 14 November; the 43 names that first appeared on the current server were on none.

## What NSS measured

- **24** names that moved from an earlier server to a later one; six went the whole way from the first to the sixth
- **6** servers used by one operation between 27 October and 14 November 2026, in NSS's record
- **104** names NSS saw on the six servers; 62 first recorded by NSS's own sensors
- **0 of 43** names new on the current server that were on a threat list NSS takes in on 14 November; 41 of them were registered 8 to 13 November

## Files

| File | What it holds |
|---|---|
| `iocs.csv` | The published list exactly as on nsshq.com, 116 rows, with the context columns. Values are live, not defanged. |
| `iocs.txt` | One indicator per line, defanged. |
| `stix2.1-bundle.json` | STIX 2.1 bundle: the report, the 116 indicators, the NSS identity and the TLP:CLEAR marking. Patterns use live values. |
| `misp-event.json` | MISP event: 116 attributes plus a link to the paper. Values are live. |

Indicators: 6 IP addresses, 110 domains.

## Detection flag

114 of 116 indicators carry the detection flag (`to_ids` in MISP, `malicious-activity` in STIX; the rest are `anomalous-activity`). 114 of the 116 indicators are flagged for detection: the paper offers the forwarding apex and its labels, the four later servers NSS classes dedicated to the operation, the 24 moved names, the other names seen on the six servers and the four fake-software download names in the same forwarding layer for blocking. The first two servers, idle since 31 October and 6 November 2026, are published unflagged: the paper says to alert on them, not block, because NSS cannot say they are still the operator's.

Read the paper's limits before acting on the list. Every value was true when the paper was written and is not re-checked here.

Corrections: corrections@nsshq.com. Licence: CC BY 4.0, credit Nexus Sentinel Station (NSS) and link to the paper.
