# Inter-VLAN Routing Project (Router-on-a-Stick)

## 📌 Overview
This project demonstrates how to enable communication between different broadcast domains (VLAN 10 and VLAN 20) using a single physical router interface. This method, commonly known as **"Router-on-a-Stick,"** provides an efficient solution for network segmentation without requiring multiple physical ports on the router.

## 🛠️ Technical Specifications
*   **Router:** Cisco ISR 1941
*   **Switch:** Cisco Catalyst 2960
*   **Encapsulation Protocol:** IEEE 802.1Q
*   **IP Addressing Schema:** 
    *   **VLAN 10 (Finance):** `192.168.10.0/24`
    *   **VLAN 20 (IT):** `192.168.20.0/24`

## 🚀 Key Learnings & Implementation
1.  **VLAN Segmentation:** Implemented to separate traffic between departments, improving security and reducing broadcast traffic.
2.  **Trunking Configuration:** Configured the switchport connected to the router as a **Trunk Link** to allow multiple VLAN tags to pass through.
3.  **Logical Sub-interfaces:** Created virtual sub-interfaces on the router's physical port to act as the **Default Gateway** for each specific VLAN.

## 🔍 Verification Steps
To ensure the configuration is successful, the following tests were performed:
- **ICMP Connectivity:** Executed a `ping` from a host in VLAN 10 to a host in VLAN 20 (**Success**).
- **Routing Table Check:** Ran `show ip route` on the router to verify that both sub-nets are recognized as directly connected via sub-interfaces.
- **Trunk Verification:** Ran `show interface trunk` on the switch to confirm that the uplink port is correctly identifying and carrying VLAN 10 and 20.

## 📂 How to Use
1. Download the `.pkt` (Cisco Packet Tracer) file from this repository.
2. Open the file using **Cisco Packet Tracer v8.2** or newer.
3. You can also view the full CLI commands in the `/config-files` directory.
