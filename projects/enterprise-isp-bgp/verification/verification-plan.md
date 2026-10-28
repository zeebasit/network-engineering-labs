# Verification plan — collect evidence before claiming working state

This is a **test plan**, not a record of successful tests. Commands are examples and may vary by image/version. Preserve the topology/OS compatibility context with each test result.

| Component | Example command(s) | Evidence to capture | Status |
| --- | --- | --- | --- |
| OSPF adjacencies | `show ip ospf neighbor` (IOS XE), `show ospf neighbor` (IOS XR) | All intended neighbors Full; correct interfaces and areas | Not tested in supplied evidence |
| OSPF reachability | `show ip route ospf`, `show route ospf` | Provider loopbacks and core endpoints reachable | Not tested |
| MPLS LDP | `show mpls ldp neighbor`, `show mpls forwarding-table` | Expected LDP neighbors and usable labels | Not tested |
| BGP RR sessions | `show bgp vpnv4 unicast summary` (platform-dependent) | Route reflector and PE sessions Established | Not tested |
| Customer VRF | `show ip route vrf CUST-C`, `show bgp vpnv4 unicast vrf CUST-C` | Expected VPN routes; isolated tables | Not tested |
| VPN reachability | VRF-aware ping and traceroute between CEs | Reachability and intended transport labels | Not tested |
| Inter-AS CUST-C | `show ip bgp vpnv4 vrf CUST-C summary` (or platform equivalent) | VRF eBGP adjacency and prefix exchange | Not tested |
| BGP policies | `show ip bgp` with targeted prefix and neighbor advertised/received routes | Observed LOCAL_PREF / AS_PATH changes and denied prefixes | Not tested |
| Failover | Shutdown a selected redundant link, re-run BGP and path checks | Convergence, alternate path, and restoration | Not tested |

### Suggested evidence naming

Store sanitized future outputs in `verification/evidence/` as `RR1-bgp-vpnv4-summary.txt`, `PE1-mpls-forwarding.txt`, `PE1-cust-a-routes.txt`, etc. Do **not** invent or manually fabricate outputs. Record device name, date, platform version, test conditions, observed result, and expected result.
