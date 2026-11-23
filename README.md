# Lab 12.2.2: Examine NAT on a Wireless Router

## Objective
Verify Network Address Translation (NAT) behavior at the Wireless Router using a periodic HTTP PDU from `PC1` to `ciscolearn.nat.com`.

## Network & Test Parameters
- **Source Host (`PC1`):** `192.168.1.101` (LAN side of Wireless Router: `192.168.1.1`)
- **Wireless Router WAN IP:** `209.165.200.227`
- **Destination Server (`ciscolearn.nat.com`):** `209.165.200.228`
- **Protocol / Ports:** HTTP / TCP Source Port `1000`, Destination Port `80`
- **Simulation Mode:** Periodic (`120` s interval), Event List filtered to `HTTP, TCP`

## Key Observations & NAT Verification
- **At `PC1` (Outbound):** Layer 3 source IP is `192.168.1.101` and destination IP is `209.165.200.228` (TCP `1000` -> `80`).
- **At `Switch0`:** Layer 2 switching forwards frames by MAC address without modifying Layer 3 IP addresses.
- **At `Wireless Router`:** Translates the private LAN source IP (`192.168.1.101`) to the public WAN IP (`209.165.200.227`) for outbound traffic toward `209.165.200.228`, and maps return traffic back to `192.168.1.101`.
- **Lab Status:** Verified complete via **Check Results**.

## Files in this Branch
- `Packet_Tracer_..._Completed.pka` - Completed Packet Tracer simulation
- `NAT_Topology.jpg` - Topology diagram

## Author & Peer Review
- **Author:** Chukwuemeka Nze
- **Branch:** `Chukwuemeka-NAT`
- **Verified by:** Chukwuemeka Nze
- **Questions / Edge Cases to Discuss:** Open for study group discussion