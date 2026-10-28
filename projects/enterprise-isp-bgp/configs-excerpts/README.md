# Configuration excerpt inventory

Public excerpts are **selected sections** extracted from the user's CML Phase 13 file; they omit startup credentials, device-generated PKI material, banners and system boilerplate. They are not complete device configurations and cannot be pasted wholesale with any guarantee of correct behavior.

| Device | CML image | Configuration stored in source | Excerpt lines | Detected config features |
| --- | --- | --- | ---: | --- |
| RR1 | iosxrv9000 | Yes | 55 | OSPF, BGP, VPNv4 |
| RR2 | iosxrv9000 | Yes | 55 | OSPF, BGP, VPNv4 |
| P1 | csr1000v | Yes | 49 | OSPF, MPLS, LDP |
| P2 | csr1000v | Yes | 49 | OSPF, MPLS, LDP |
| PE1 | csr1000v | Yes | 83 | OSPF, BGP, VPNv4, MPLS, LDP, VRF, Route policy |
| PE2 | csr1000v | Yes | 93 | OSPF, BGP, VPNv4, MPLS, LDP, VRF, Route policy |
| PE3 | csr1000v | Yes | 66 | OSPF, BGP, VPNv4, MPLS, LDP, VRF |
| PE4 | csr1000v | Yes | 85 | OSPF, BGP, VPNv4, MPLS, LDP, VRF, Route policy |
| ASBR-A | csr1000v | Yes | 79 | OSPF, BGP, VPNv4, MPLS, LDP, VRF, Route policy |
| INET-A | frr | Yes | 5 | No listed routing features |
| PB2 | csr1000v | Yes | 85 | OSPF, BGP, VPNv4, MPLS, LDP, VRF, Route policy |
| CE-A1 | iosv | Yes | 13 | BGP |
| CE-B1 | iosv | Yes | 41 | BGP, Route policy |
| CE-B2 | iosv | Yes | 41 | BGP, Route policy |
| CE-C1 | iosv | Yes | 39 | BGP, Route policy |
| CE-D1 | iosv | Yes | 17 | BGP |
| CE-D2 | iosv | Yes | 29 | BGP, Route policy |
| CE-E1 | iosv | Yes | 13 | BGP |
| PB1 | csr1000v | Yes | 40 | OSPF, BGP, VPNv4, MPLS, LDP |
| INET-B | frr | Yes | 5 | No listed routing features |
| RS1 | frr | Yes | 8 | No listed routing features |
| INJ1 | frr | Yes | 5 | No listed routing features |
| CE-C2 | iosv | Yes | 39 | BGP, Route policy |
| RRB1 | iosv | Yes | 59 | OSPF, BGP, VPNv4 |
