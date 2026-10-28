# Design notes and technical audit

## Source and snapshot integrity

Source: `Master_Enterprise_ISP_BGP_Lab_-_24_Nodes_Phase_13.yaml` (user-supplied CML export). **24 nodes, 28 links.** This is not asserted to be the final state of the complete research lab.

CML devices by image definition: iosxrv9000: 2, csr1000v: 9, frr: 4, iosv: 9.

VRFs observed in this snapshot:

| VRF | Nodes defining it |
| --- | --- |
| CUST-A | PE1 |
| CUST-B | PE1, PE2 |
| CUST-C | PE3, ASBR-A, PB2 |
| CUST-D | PE2, PE4 |
| CUST-E | PE4 |

## Control plane

- IOS XR RR1 and RR2 contain vpnv4 route-reflector-client policies. This documents intent and configuration, **not live reflected routes**.
- PE1–PE4 and ASBR-A have OSPF/MPLS LDP and MP-BGP configuration blocks. Session state requires `show` outputs.
- The ASBR-A to PB2 connection in this file appears to be **VRF-based IPv4 eBGP** between different autonomous systems for CUST-C, not an MP-BGP VPNv4 ASBR peering. Do not label this as a proven Inter-AS Option B or Option C deployment.
- Customer B route policies and customer D path-preference examples exist. Correct policy outcomes are not verified by stored outputs.
- Internet-related FRR nodes are present, but the embedded configuration is sparse. Avoid claiming verified Internet routing for them.

## Verification still required

No CLI verification output, successful reachability tests, path-tracing, link-failure tests, or screenshots of converged protocol state were supplied in this phase snapshot. The presence of a command in a saved configuration does not establish its operational state.

## Public-release security process

Raw source configuration **was not** copied into the public package. The original export contains IOS XR local-account password hashes and device-generated PKI/certificate material. Public CML YAML deliberately removes all node configurations; config excerpt files use an allowlist of network-design sections and a second credential-pattern scan. There is no claim that these excerpts are fully runnable.

Before any future public release of full configurations, independently inspect those files for credentials, SSH keys, PKI material, public IP addresses, private operational data, and proprietary content. Ensure public-sharing rights and software license obligations are satisfied.
