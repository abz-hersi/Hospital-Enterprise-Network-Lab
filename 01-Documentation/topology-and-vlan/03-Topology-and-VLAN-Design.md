\# Hospital Network — Topology \& VLAN Design



\## Network Topology



I decided to use two switches (SW1 and SW2), both connecting different hospital departments.



The switches are connected by two links, with a server connected to both switches.



The aim is to keep the network organised, separate departments and allow for redundancy later.



\## VLAN \& IP Addressing Plan



| VLAN | Department | Network | Planned Gateway |

|---|---|---|---|

| 10 | Management | 10.10.10.0/24 | 10.10.10.254 |

| 20 | Clinical (Doctors/Nurses) | 10.10.20.0/24 | 10.10.20.254 |

| 30 | Administration | 10.10.30.0/24 | 10.10.30.254 |

| 40 | Finance | 10.10.40.0/24 | 10.10.40.254 |

| 50 | IT | 10.10.50.0/24 | 10.10.50.254 |

| 60 | Servers | 10.10.60.0/24 | 10.10.60.254 |

| 70 | Medical Devices | 10.10.70.0/24 | 10.10.70.254 |

| 80 | Guest Wi-Fi | 10.10.80.0/24 | 10.10.80.254 |

| 90 | Staff Wi-Fi | 10.10.90.0/24 | 10.10.90.254 |



\## Why I Chose This Design



\- VLANs: Separate departments and reduce unnecessary broadcast traffic.

\- Two switches: Connect more devices and prepare for redundancy.

\- Separate Wi-Fi: Staff and guests have different access requirements.

\- Server VLAN: Keep important network services separate from users.

\- Security: ACLs and firewall rules will control access between networks.



\## Risks \& Troubleshooting



\- Wrong VLAN assignment can prevent devices reaching the right network.

\- Incorrect trunk configuration can stop VLAN traffic between switches.

\- The two switch links will need STP or EtherChannel configured correctly.

\- Both server connections need a proper dual-NIC design before being used together.

\- Guest Wi-Fi must be restricted from accessing internal hospital resources.



\## Project Status



Topology and IP addressing planned. Configuration, connectivity testing and redundancy verification are still to be completed.

