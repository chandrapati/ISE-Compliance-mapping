# Cisco ISE Compliance Mapping Workshop Checklist

Use this checklist to prepare an ISE campus segmentation compliance workshop and produce actionable outputs.

## Pre-Workshop Inputs

- Target frameworks and audit drivers, such as PCI DSS, HIPAA, CMMC, NIST, SOC 2, ISO 27001, DORA, NIS2, NERC CIP, or CIS Controls.
- Current ISE deployment model, version, personas, node count, and licensing.
- Network access device inventory: switches, wireless controllers, VPN headends, firewalls, Meraki networks, and third-party NADs.
- RADIUS/TACACS+ coverage and sites not yet integrated with ISE.
- Identity sources: Active Directory, Entra ID, LDAP, certificate authorities, MDM/UEM, HR, contractor, and vendor systems.
- Endpoint sources: ISE profiling, MDM, EDR, CMDB, OT inventory, Cyber Vision, vulnerability scanners.
- Current VLAN, SGT, VN, ACL, dACL, and firewall zone taxonomy.
- Known regulated environments: CDE, ePHI, CUI, OT, privileged admin, production, guest/BYOD, vendor access.
- Logging destinations, retention requirements, and SIEM ownership.

## Discovery Questions

### Identity and Access

- Which user groups require differentiated campus access?
- Which privileged roles administer network devices or regulated systems?
- Which contractors, suppliers, vendors, and guests need access?
- Where is MFA required today, and where should Duo or another IdP enforce it?

### Device and Posture

- Which endpoint types are allowed, restricted, quarantined, or denied?
- Which devices cannot run 802.1X and must use MAB?
- Which devices need posture checks before sensitive access?
- Which source is authoritative for device compliance: ISE, MDM, EDR, CMDB, or another system?

### Segmentation and Enforcement

- Which access boundaries are enforced with VLANs, SGTs, SGACLs, dACLs, firewall rules, or SD-Access virtual networks?
- Which campus sites can enforce SGTs today?
- Which flows require firewall enforcement instead of access-layer enforcement?
- Which unsupported or unmanaged network areas need compensating controls?

### Evidence and Operations

- Which logs must be retained for audit evidence?
- Which reports must be produced monthly, quarterly, or per assessment?
- Which team owns policy exceptions and expired exceptions?
- Which SIEM, GRC, ticketing, and CMDB systems must receive evidence?

## Workshop Outputs

- Framework-to-campus segmentation map.
- ISE policy set and authorization profile inventory.
- Identity group, endpoint group, SGT, and network device group naming standards.
- Regulated access matrix by role, device type, site, posture, and destination.
- Product sufficiency matrix showing Cisco coverage and outside-product gaps.
- List of enforcement gaps by site, NAD type, unsupported endpoint, or missing telemetry.
- Evidence export plan: ISE reports, SIEM dashboards, GRC attachments, and review cadence.
- Exception handling workflow with owner, expiry date, compensating control, and review process.

## Minimum Evidence Package

- ISE policy set export or screenshots showing authorization logic.
- Endpoint and identity group inventory.
- Network device group and site inventory.
- SGT matrix or dACL/VLAN assignment map.
- RADIUS/TACACS+ authentication and authorization logs for sample access paths.
- Failed authentication, quarantine, and deny-event samples.
- pxGrid/SIEM integration confirmation where used.
- Change record for policy updates.
- Exception register and expiration review.

## Product Gap Review

For each framework, explicitly mark whether the requirement is handled by:

- ISE alone.
- ISE plus Cisco campus or security products.
- Cisco plus an external system of record.
- A non-Cisco product because Cisco is not deployed or not authoritative.
- A process or governance control outside product scope.

## Final Customer Prompt

The workshop is complete only when the customer can answer:

> Which identities, endpoint types, sites, posture states, and enforcement points define regulated campus access, and which systems prove that the controls operated as intended?
