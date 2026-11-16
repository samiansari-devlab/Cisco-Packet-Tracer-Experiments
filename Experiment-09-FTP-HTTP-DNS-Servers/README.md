# Experiment 09: FTP, HTTP and DNS Server Configuration

## Aim

Configure FTP, HTTP and DNS services in Cisco Packet Tracer and test access from a client PC.

## Devices and addressing plan

The assignment workspace shows one switch, three servers, two PCs and one laptop connected to the switch using copper straight-through cables.

| Device | IPv4 address |
|---|---|
| FTP Server | 192.168.1.1 |
| HTTP Server | 192.168.1.2 |
| DNS Server | 192.168.1.3 |
| PC0 | 192.168.1.4 |
| PC1 | 192.168.1.5 |
| Laptop0 | 192.168.1.6 |

Subnet mask for all devices: `255.255.255.0`.

## Configuration procedure

### 1. Build the topology

1. Place one switch, three servers, two PCs and one laptop.
2. Connect every device to the switch using copper straight-through cables.

### 2. Configure FTP Server

1. Open the FTP Server and select Services → FTP.
2. Turn FTP service ON.
3. Create an FTP username and password as required by the lab instructions.

### 3. Configure HTTP Server

1. Open the HTTP Server and select Services → HTTP.
2. Turn HTTP service ON.
3. The provided lab screenshot shows both HTTP and HTTPS enabled.
4. Ensure the website has an `index.html` page.

### 4. Configure DNS Server

1. Open the DNS Server and select Services → DNS.
2. Turn DNS service ON.
3. Add the website record:

| Name | Address |
|---|---|
| www.sami.com | 192.168.1.2 |

### 5. Configure client IP settings

On PC0, PC1 and Laptop0, open Desktop → IP Configuration and enter the corresponding IP address from the addressing table, subnet mask `255.255.255.0`, and DNS server `192.168.1.3`.

## Verification

### HTTP test

On PC0, open Desktop → Web Browser and visit:

```text
http://www.sami.com
```

### FTP test

On PC0, open Desktop → Command Prompt and run:

```text
ftp 192.168.1.1
```

Enter the FTP username and password created on the FTP server.

### DNS test

On PC0, open Command Prompt and run:

```text
ping www.sami.com
```

The name should resolve to `192.168.1.2`.

## Troubleshooting notes

- Check that all devices have the correct IP address and subnet mask.
- Check that PC0 uses DNS server `192.168.1.3`.
- Check that DNS service is ON and the record is spelled exactly `www.sami.com`.
- The lab screenshot's DNS record is `www.sami.com`; do not enter `www.samy.com`.
- Check that HTTP and FTP services are ON on their respective servers.

## Result

FTP, HTTP and DNS services are configured in the Packet Tracer topology and tested from the client PC.

## Files to add

Add the original Packet Tracer project (`.pkt`), assignment PDF and screenshots to this folder when available.
