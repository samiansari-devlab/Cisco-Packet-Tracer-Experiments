# Experiment 07: Router Configuration Using GUI and CLI

## Aim

Set up and configure a router using both the graphical user interface (GUI) and command-line interface (CLI) in Cisco Packet Tracer.

## Network design

The main exercise connects two LANs through a router:

- LAN 1: `192.168.20.0/24`
- LAN 2: `192.168.10.0/24`

The router uses:
- GigabitEthernet 0/0/0: `192.168.20.1/24`
- GigabitEthernet 0/0/1: `192.168.10.1/24`

## PC addressing

| Devices | IP address range | Subnet mask | Default gateway |
|---|---|---|---|
| PC1–PC4 | 192.168.20.5–192.168.20.8 | 255.255.255.0 | 192.168.20.1 |
| PC5–PC8 | 192.168.10.5–192.168.10.8 | 255.255.255.0 | 192.168.10.1 |

## GUI procedure

1. Place eight PCs, two switches and one router.
2. Connect four PCs to each switch.
3. Connect the first switch to router interface GigabitEthernet 0/0/0 and the second switch to GigabitEthernet 0/0/1.
4. In the router Config tab, configure the two interface IP addresses listed above and turn both ports on.
5. Configure each PC's IP address, subnet mask and default gateway.
6. Use Simulation Mode and Add Simple PDU to send a packet from 192.168.20.5 to 192.168.10.5.
7. Verify delivery and test other PCs.

## CLI procedure

Enter the following commands on the router:

```text
enable
configure terminal

interface GigabitEthernet0/0/0
ip address 192.168.20.1 255.255.255.0
no shutdown
exit

interface GigabitEthernet0/0/1
ip address 192.168.10.1 255.255.255.0
no shutdown
exit

end
show ip interface brief
```

Configure the PCs with the same addressing plan as in the GUI procedure.

## Verification

From a PC in the first LAN, test a PC in the second LAN:

```text
ping 192.168.10.5
```

Alternatively, use Simulation Mode and Add Simple PDU.

## Additional task: third network

The assignment brief also describes adding a third network using an additional compatible router interface:

- Router interface: GigabitEthernet 0/0/2
- Router address intended by the PC addressing plan: `192.168.30.1/24`
- PC9: `192.168.30.5/24`, gateway `192.168.30.1`
- PC10: `192.168.30.6/24`, gateway `192.168.30.1`

**Check before implementation:** the supplied brief's interface-address line appears to omit the final octet (`192.168.30.`). The `192.168.30.1` value above is inferred from the PC gateway values, so confirm it with your instructor or lab sheet.

## Observation

- GUI configuration uses graphical interface options.
- CLI configuration uses router commands.
- Each LAN has a separate IPv4 subnet.
- PCs use the router interface on their own subnet as the default gateway.
- The router forwards packets between the two connected networks.

## Result

Router interfaces were configured using GUI and CLI, and communication between the two LANs was verified using Simple PDU and ping.

## Files

- Assignment brief: `Assignment-07.pdf`
- Packet Tracer project: add the original `.pkt` file here after saving it from Cisco Packet Tracer.
