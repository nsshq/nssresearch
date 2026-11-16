# NSS-ZM-01: Fake Zoom update page installs a self-hosted ScreenConnect client: technical analysis

- **Published:** 2026-11-12
- **Marking:** TLP:CLEAR
- **Paper:** https://nsshq.com/research/fake-zoom-update-remote-access
- **PDF:** https://nsshq.com/research/files/nss-zm-01.pdf

## Summary

A page made to look like a Zoom meeting tells the visitor their app is out of date and offers an update. The update is a ScreenConnect remote-access client set to call a server its sender runs; whoever runs it hands over control of their computer. NSS's own sensors picked up the page; NSS captured it, read the installer and traced it to that server within 23 hours of the page's registration. The server's domain was registered 63 days before the lure. None of the nine indicators was on any list NSS holds on 12 November 2026.

## What NSS measured

- **0** of the 9 indicators on any list NSS holds
- **23 h** from lure registration to its server and file hash
- **1** server behind the download portal and the relay
- **63 days** by which the connect-back domain is older than the lure

## Files

| File | What it holds |
|---|---|
| `iocs.csv` | The published list exactly as on nsshq.com, 9 rows, with the context columns. Values are live, not defanged. |
| `iocs.txt` | One indicator per line, defanged. |
| `stix2.1-bundle.json` | STIX 2.1 bundle: the report, the 9 indicators, the NSS identity and the TLP:CLEAR marking. Patterns use live values. |
| `misp-event.json` | MISP event: 9 attributes plus a link to the paper. Values are live. |

Indicators: 5 domains, 1 URL, 1 IP address, 1 SHA-256 hash, 1 MD5 hash.

## Detection flag

9 of 9 indicators carry the detection flag (`to_ids` in MISP, `malicious-activity` in STIX; the rest are `anomalous-activity`). All nine indicators are the operator's lure, download, connect-back, server and installer. Every one is flagged for detection.

Read the paper's limits before acting on the list. Every value was true when the paper was written and is not re-checked here.

Corrections: corrections@nsshq.com. Licence: CC BY 4.0, credit Nexus Sentinel Station (NSS) and link to the paper.
