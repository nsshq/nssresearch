# NSS research indicators

Indicator files for every published paper from NSS Research. TLP:CLEAR, shareable without restriction, CC BY 4.0.

## About NSS

NSS, the Nexus Sentinel Station, is a threat intelligence platform run by ALLITSYSTEMS LLC in Virginia, United States. It shows defenders the evidence behind every verdict: registration and certificate records, what a page served, the host type, and NSS's own first-seen time beside the first public listing. NSS Research publishes technical analyses of malicious infrastructure that NSS recorded or grouped, each with its full indicator list. Community accounts are open at no cost at https://nsshq.com.

## Papers

| Paper | Title | Published | Indicators | Read |
|---|---|---|---|---|
| [NSS-GB-01](NSS-GB-01-official-lookalike-names/) | Polish official and e-banking lookalike domains aimed at PKO business-banking users: technical analysis | 2026-11-13 | 595 | [nsshq.com](https://nsshq.com/research/official-lookalike-names) |
| [NSS-ZM-01](NSS-ZM-01-fake-zoom-update-remote-access/) | Fake Zoom update page installs a self-hosted ScreenConnect client: technical analysis | 2026-11-12 | 9 | [nsshq.com](https://nsshq.com/research/fake-zoom-update-remote-access) |
| [NSS-RH-01](NSS-RH-01-redirect-host-clusters/) | Lottery redirect names on a shared delivery network: technical analysis | 2026-11-11 | 319 | [nsshq.com](https://nsshq.com/research/redirect-host-clusters) |
| [NSS-OC-01](NSS-OC-01-linked-hosting-clusters/) | Linked hosting clusters and the purchase batches behind them: technical analysis | 2026-11-11 | 1770 | [nsshq.com](https://nsshq.com/research/linked-hosting-clusters) |
| [NSS-WA-01](NSS-WA-01-whatsapp-lookalike-kit/) | WhatsApp lookalike kit: technical analysis | 2026-11-10 | 52 | [nsshq.com](https://nsshq.com/research/whatsapp-lookalike-kit) |

## Licence and marking

Every file in this repository is marked **TLP:CLEAR**: disclosure is not limited, and the indicators may be shared freely, subject to standard copyright rules. The data is licensed under the Creative Commons Attribution 4.0 International licence (CC BY 4.0, see [LICENSE](LICENSE)). Credit "Nexus Sentinel Station (NSS)" and link to the paper the indicators come from.

## How to use the files

Each paper has its own folder with the same four files:

| File | Use it for | Values |
|---|---|---|
| `iocs.csv` | Spreadsheets, scripts and lookups. It is the list exactly as published on nsshq.com, with the context columns for that paper. | Live |
| `iocs.txt` | Reading, pasting into tickets and chat. One value per line under a `#` header. | Defanged |
| `stix2.1-bundle.json` | Threat intelligence platforms that read STIX 2.1. One report, its indicators, the NSS identity and the OASIS TLP:CLEAR marking. | Live, in patterns |
| `misp-event.json` | MISP instances: import it as a MISP event (JSON). Distribution is all communities; tags `tlp:clear` and `type:OSINT`. | Live |

Notes:

- **Defanged values** write dots as `[.]` and `http` as `hxxp`. Refang with `sed -e 's/\[\.\]/./g' -e 's/hxxp/http/' iocs.txt`.
- **Detection flag.** Not every indicator is a block rule. Each paper's README says which indicators carry the flag and why. A value without it is published as context or as a pivot.
- **Point in time.** Values were true when the paper was written. Names expire and addresses change hands, so check before you block, and use the dates in the CSV when you search old logs.
- **Shared addresses are left out on purpose.** Where a page sat on shared hosting or a delivery network, its addresses are not indicators.

## Corrections

If a value is wrong, write to **corrections@nsshq.com** with the paper id and the value. See [CONTRIBUTING.md](CONTRIBUTING.md). Security issues in NSS itself go to security@nsshq.com.
