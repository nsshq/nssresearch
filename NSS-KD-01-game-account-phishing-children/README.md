# NSS-KD-01: Phishing aimed at children and their families: 188 look-alike names in six sets

- **Published:** 2026-11-16
- **Marking:** TLP:CLEAR
- **Paper:** https://nsshq.com/research/game-account-phishing-children
- **PDF:** https://nsshq.com/research/files/nss-kd-01.pdf

## Summary

Between 27 October and 16 November 2026 NSS recorded 188 new web names built to take children's and teenagers' game accounts, and through those accounts their families' money, devices and social accounts. The largest single piece is one server that answered for 40 names written for Russian speakers: Roblox sign-in and "Robux" names, a Brawl Stars gem store, Roblox script sites, look-alikes of the VK social network, a voting lure and a shopping look-alike, most of them each on a DNS account of its own. Beside it sit a Fortnite "locker worth" checker server whose newest 39 names were almost all unlisted, Roblox link names bought in four bursts, staged Mobile Legends "support" names and Minecraft "creator" invitations. On 16 November 161 of the 188 were on no threat list NSS takes in. This paper gives every name, takes apart the anti-bot gate that keeps the Fortnite checker off blocklists, and sets out what parents, schools and platform teams can do.

## What NSS measured

- **12** Fortnite checker names on one server run the same anti-bot gate; NSS took the gate apart, captured the kit read-only and ships tested detection

## Files

| File | What it holds |
|---|---|
| `iocs.csv` | The published list exactly as on nsshq.com, 192 rows, with the context columns. Values are live, not defanged. |
| `iocs.txt` | One indicator per line, defanged. |
| `stix2.1-bundle.json` | STIX 2.1 bundle: the report, the 192 indicators, the NSS identity and the TLP:CLEAR marking. Patterns use live values. |
| `misp-event.json` | MISP event: 192 attributes plus a link to the paper. Values are live. |

Indicators: 2 IP addresses, 190 domains.

## Detection flag

190 of 192 indicators carry the detection flag (`to_ids` in MISP, `malicious-activity` in STIX; the rest are `anomalous-activity`). The names and the two servers are flagged for detection: the paper offers the 188 look-alike names for blocking and for searching mail, web and DNS logs, and the two servers 87.120.104.209 and 193.187.110.18 as the choke points behind the live names. Many names were staged and not yet serving a page when NSS recorded them, so treat the list as both a block set for the active names and a watch set for the rest. The two listed context names of the Roblox link set are published unflagged as a pivot. The delivery-network addresses some names used are not in the list and must not be blocked.

Read the paper's limits before acting on the list. Every value was true when the paper was written and is not re-checked here.

Corrections: corrections@nsshq.com. Licence: CC BY 4.0, credit Nexus Sentinel Station (NSS) and link to the paper.
