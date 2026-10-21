\# Hospital Network — Switching \& VLAN Configuration



\## 1. VLAN Configuration



I created 9 VLANs on SW1 and SW2 to separate the hospital departments and devices.



This helps organise the network, reduce broadcast traffic and allows us to control access between departments later.



I assigned each PC to its correct VLAN based on the network design.



\## 2. EtherChannel \& Trunking



I connected SW1 and SW2 using two physical links and configured EtherChannel with LACP.



\- SW1: LACP Active

\- SW2: LACP Passive

\- EtherChannel: Port-Channel 1

\- Trunk: VLANs 10–90



\*\*Why?\*\*



EtherChannel allows us to use both links together and provides redundancy if one link fails.



The trunk allows multiple VLANs to communicate across the two switches without mixing their traffic.



\*\*Verification:\*\* Checked EtherChannel and trunk status using:



\- `show etherchannel summary`

\- `show interfaces trunk`



\## 3. IP Addressing \& Connectivity



I assigned static IP addresses to the hospital PCs based on their VLAN subnets.



\*\*Tests completed:\*\*



\- Devices in the same VLAN communicated successfully across SW1 and SW2.

\- Communication between different VLANs failed because inter-VLAN routing hasn't been configured yet.



\## 4. Troubleshooting \& Risks



| Problem | What I would check |

|---|---|

| PC cannot reach another PC in the same VLAN | VLAN assignment, IP address and trunk |

| EtherChannel not working | LACP modes and physical interfaces |

| VLAN traffic not crossing switches | Allowed VLANs on the trunk |

| Different VLANs cannot communicate | Default gateway and inter-VLAN routing |



During testing, I also found a Clinical PC using an IP address from the Management subnet and corrected it to match VLAN 20.



\## 5. Current Progress



Completed:



\- VLAN creation and access-port assignments

\- EtherChannel and trunking

\- Static IP addressing

\- Same-VLAN connectivity testing



\*\*Next:\*\* Configure the Layer 3 gateways and inter-VLAN routing, then apply security policies to restrict unnecessary access between departments.

