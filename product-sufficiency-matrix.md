# Cisco ISE Product Sufficiency Matrix

This matrix calls out where Cisco products can usually satisfy the campus segmentation evidence need and where non-Cisco tools are commonly required.

## How To Read This

- **ISE sufficient** means ISE plus existing network access devices can usually provide the core evidence or enforcement for that control area.
- **Cisco portfolio needed** means ISE should be paired with other Cisco products for complete technical coverage.
- **Outside product likely needed** means the requirement usually lives outside campus segmentation or requires a dedicated third-party system.

## Product Coverage Matrix

| Control / evidence area | ISE sufficient? | Cisco products that can suffice | When outside products may be needed |
|---|---:|---|---|
| 802.1X/MAB network admission | Yes | ISE, Catalyst switches, wireless LAN controllers, Meraki access | Third-party switches that lack needed RADIUS attributes, dACL, VLAN, or SGT support |
| Role-based campus segmentation | Usually | ISE, TrustSec/SGT, Catalyst Center, SD-Access, Catalyst 9000, Secure Firewall | Non-Cisco fabrics, legacy switching, or environments standardized on other NAC/segmentation platforms |
| Guest and BYOD access | Yes | ISE guest portal, sponsor portal, BYOD onboarding, wireless infrastructure | Guest identity proofing, legal consent management, or marketing systems outside ISE |
| Device profiling and IoT classification | Usually | ISE profiling, AI Endpoint Analytics, Catalyst Center, Cyber Vision for OT | Dedicated IoT/OT inventory such as Claroty or Nozomi when Cyber Vision is not deployed or coverage is incomplete |
| Endpoint posture before access | Usually | ISE posture, Cisco Secure Client, Duo Device Health, Secure Endpoint | Microsoft Intune, Jamf, CrowdStrike, SentinelOne, or Defender when they are the authoritative device compliance source |
| Privileged network device administration | Yes | ISE TACACS+, command sets, device admin policy | PAM vault/session recording such as CyberArk, BeyondTrust, or Delinea for privileged account governance |
| MFA for sensitive access | Cisco portfolio needed | Duo, ISE, Secure Client, VPN/firewall integrations | Okta, Entra ID, Ping, or other enterprise IdP when already standardized |
| Firewall enforcement for campus-to-data-center/cloud | Cisco portfolio needed | Secure Firewall, ISE pxGrid, SGT/SGACL, SD-Access transit | Palo Alto, Fortinet, Check Point, or cloud-native firewalls where those are the existing enforcement points |
| Flow analytics and anomaly detection | Cisco portfolio needed | Secure Network Analytics, Splunk, XDR, Catalyst Center Assurance | QRadar, Elastic, Datadog, or other SIEM/NDR platforms if they are the enterprise system of record |
| Vulnerability management evidence | No | Cisco Vulnerability Management where licensed, Secure Endpoint context | Tenable, Qualys, Rapid7, Wiz, Prisma Cloud, or ServiceNow Vulnerability Response |
| Asset inventory / CMDB reconciliation | No | Catalyst Center inventory, ISE endpoints, Meraki dashboard, Cyber Vision | ServiceNow CMDB, Device42, Lansweeper, Axonius, or enterprise asset inventory |
| GRC evidence workflow | No | Splunk dashboards can support evidence views | ServiceNow GRC, Archer, AuditBoard, Drata, Vanta, OneTrust |
| Privacy / data classification | No | ISE can consume groups and tag access boundaries | Microsoft Purview, BigID, OneTrust, Collibra, data discovery/DLP platforms |
| Endpoint malware / EDR | No | Secure Endpoint, XDR | CrowdStrike, SentinelOne, Microsoft Defender, Palo Alto Cortex |
| DNS / internet access control | Cisco portfolio needed | Umbrella, Secure Access, Secure Firewall | Zscaler, Netskope, Palo Alto Prisma Access, Cloudflare Zero Trust |
| Backup and recovery | No | Not an ISE function | Veeam, Cohesity, Rubrik, Commvault, cloud-native backup |
| Certificate lifecycle and PKI | Partial | ISE internal CA for BYOD use cases, Cisco platform cert management | DigiCert, Venafi, Keyfactor, Microsoft AD CS, enterprise HSM/PKI |
| Cryptographic module validation | No | FIPS-capable Cisco platforms where configured | Thales, Entrust, cloud KMS/HSM, validated crypto libraries and governance |
| OT/ICS segmentation | Cisco portfolio needed | ISE for IT-side access, Cyber Vision, Secure Firewall, Industrial Ethernet switching | Claroty, Nozomi, Dragos, data diodes, OT firewalls, safety-system controls |
| Regulatory reporting and audit packets | No | Splunk and XDR can provide supporting evidence | GRC, legal, regulatory workflow, and assessor portals |

## Cisco Product Fit By Use Case

| Use case | Primary Cisco fit | Notes |
|---|---|---|
| NAC and identity-aware authorization | ISE | Core policy decision point for RADIUS/TACACS+ campus access |
| Campus fabric segmentation | Catalyst Center and SD-Access | Provides scalable SGT/VN-based segmentation when deployed |
| Non-fabric SGT enforcement | Catalyst switches, wireless, Secure Firewall | Useful for phased TrustSec adoption |
| Device admin compliance | ISE TACACS+ | Covers administrator authorization and command control |
| Remote access context | Secure Client, Secure Firewall, Duo, ISE | Useful for VPN and posture-aware access |
| OT visibility | Cyber Vision | Pair with ISE only where OT devices interact with IT access boundaries |
| SIEM and investigation | Splunk, XDR | Needed when audit retention and correlation go beyond ISE logs |
| Internet/SaaS controls | Umbrella and Secure Access | ISE does not control SaaS or public internet access by itself |

## Practical Guidance

ISE is strongest when the requirement says: identify the user or device, decide whether it should be on the network, assign the right role/segment, and produce an access decision log.

ISE is usually insufficient by itself when the requirement says: prove governance, retain enterprise audit evidence, classify sensitive data, manage vulnerability SLAs, perform endpoint malware response, run backups, manage legal obligations, or certify cryptographic modules.
