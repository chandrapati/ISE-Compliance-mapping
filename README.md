# Cisco ISE Compliance Mapping

![Visitors](https://visitor-badge.laobi.icu/badge?page_id=chandrapati.ISE-Compliance-mapping&left_text=visitors)

Customer-facing scope and product mapping patterns for Cisco Identity Services Engine
(ISE), Cisco Secure Workload (CSW), campus segmentation, workload segmentation,
and compliance workshops.

This repository adapts the scope-design style from the Cisco Secure Workload
compliance mapping work to the campus network and connects it to workload
segmentation. It focuses on how Cisco ISE, 802.1X/MAB, TrustSec Security Group
Tags (SGTs), downloadable ACLs, posture, pxGrid, campus enforcement points, CSW
scopes, workload labels, ADM workspaces, and workload policies can support
compliance evidence and segmentation design.

## What This Repo Provides

- `framework-scope-design.md` - framework-by-framework campus and workload
  segmentation mapping for ISE and CSW.
- `product-sufficiency-matrix.md` - where Cisco products are enough, where
  additional Cisco products are needed, and where outside products may be needed.
- `workshop-checklist.md` - practical discovery questions and workshop
  outputs for an ISE compliance mapping session.

## Primary Cisco Products In Scope

- Cisco Identity Services Engine (ISE)
- Cisco Secure Workload (CSW)
- Cisco Catalyst Center / SD-Access
- Cisco Catalyst switches, wireless controllers, and access points
- Cisco TrustSec / SGT-aware enforcement
- Cisco Secure Firewall
- Cisco Secure Network Analytics
- Cisco Cyber Vision for OT visibility
- Cisco Duo for MFA/device trust
- Cisco Secure Client / AnyConnect posture and remote access
- Cisco Secure Endpoint, Umbrella, XDR, and Splunk where needed for adjacent
  endpoint, DNS, investigation, and SIEM use cases

## Positioning

ISE is strongest for identity-aware access control, campus segmentation,
network admission control, device profiling, guest/BYOD control, posture signals,
and SGT-based policy. CSW is strongest for workload inventory, application scope
design, workload-to-workload flow evidence, ADM-driven policy design, and
application segmentation enforcement. Neither product is a complete compliance
platform by itself.

For most frameworks, ISE supplies technical evidence for network access,
segmentation, authentication, authorization, and device classification. CSW
supplies technical evidence for workload scope, observed application flows,
segmentation policy, workload inventory, process/package context, and application
dependency review. They should be paired with authoritative inventory, identity
governance, vulnerability management, endpoint protection, SIEM, GRC, backup,
privacy, and audit workflows as required by the specific framework.

## Important Caveat

These mappings are planning accelerators, not compliance certifications. Validate
final scope, evidence, and product sufficiency with the customer's architecture
owners, compliance team, and assessor.
