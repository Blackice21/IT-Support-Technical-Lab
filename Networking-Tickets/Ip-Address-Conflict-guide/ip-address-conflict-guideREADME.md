# IP Address Conflict — Troubleshooting Steps

A step-by-step IT support workflow for troubleshooting the issue:

> **"IP address conflict detected."**  
> or  
> **Another device on the network is using the same IP address.**

This guide covers how IT support would diagnose and fix an IP address conflict on a local network.

---

# Initial Ticket

## Reported Issue

```text
User reports:
"I get this message saying "Another device on the network is using the same IP address." I need help."
```

Common symptoms include:

- Popup saying:
  - **"Windows has detected an IP address conflict"**
- Internet disconnects randomly
- Network access drops intermittently
- Can’t reach internal resources
- Limited connectivity warning
- Device repeatedly disconnects and reconnects

---

# 1. Gather Information

Before changing anything, ask:

- Is the issue happening on one device or multiple?
- Are they on Wi-Fi or Ethernet?
- Did this start recently?
- Was anything changed recently?
  - router reboot
  - static IP configured
  - printer installed
  - new device added
  - VPN used

---

# 2. Check Current IP Configuration

Open Command Prompt:

```cmd
ipconfig
```

Review:

- IPv4 Address
- Subnet Mask
- Default Gateway
- DNS Servers

Example:

```text
IPv4 Address . . . . . : 192.168.1.25
Subnet Mask  . . . . . : 255.255.255.0
Default Gateway . . .  : 192.168.1.1
```

---

# 3. Determine Whether IP Is Static or DHCP

Check whether the machine is using:

- **DHCP** (automatic address assignment)
or
- **Static IP** (manually assigned)

Open:

```text
Control Panel → Network Connections
→ Adapter Properties
→ Internet Protocol Version 4 (TCP/IPv4)
```

Then verify whether:

- **Obtain an IP address automatically** is selected
or
- a manual IP is entered

---

# 4. Release and Renew the IP Address

Most common quick fix.

Open Command Prompt:

```cmd
ipconfig /release
```

Then:

```cmd
ipconfig /renew
```

This requests a new IP from DHCP.

---

# 5. Check If Another Device Is Using the Same IP

Try pinging the IP:

```cmd
ping <conflicting-ip>
```

Example:

```cmd
ping 192.168.1.25
```

Then compare device MAC addresses.

---

# 6. Check ARP Table

Use ARP to see what MAC address owns the IP.

Run:

```cmd
arp -a
```

Example output:

```text
192.168.1.25   aa-bb-cc-dd-ee-ff
```

Compare this to:

- your machine’s MAC address
- another host on the network

This helps identify the duplicate device.

---

# 7. Restart the Device

Simple but often effective.

Restart the computer and reconnect to the network.

This can force DHCP to assign a different address.

---

# 8. Reboot Router / DHCP Server

Power-cycle:

1. Unplug router/modem
2. Wait 30 seconds
3. Plug it back in
4. Wait until fully online

Then reconnect the device.

This refreshes DHCP leases.

---

# 9. Look for Static IP Devices

Check the network for devices using manual IPs:

Common examples:

- printers
- servers
- cameras
- NAS devices
- access points

These often cause duplicate IP issues if configured inside the DHCP pool.

---

# 10. Verify DHCP Scope on Router

If managing the router:

Check:

- DHCP start range
- DHCP end range
- DHCP reservations

Example:

```text
192.168.1.100 - 192.168.1.200
```

Make sure manually assigned IPs are **outside** that pool.

Example safe static IP:

```text
192.168.1.10
```

---

# 11. Assign a New Static IP (if needed)

If static addressing is required:

Manually assign a different unused address. usually only applies to servers.

Example:

```text
IP Address:      192.168.1.50
Subnet Mask:     255.255.255.0
Gateway:         192.168.1.1
DNS:             8.8.8.8
```

---

# 12. Disable / Re-enable Network Adapter

Open:

```text
Control Panel → Network Connections
```

Then:

- right-click adapter
- Disable
- wait a few seconds
- Enable

This refreshes the adapter and DHCP request.

---

# 13. Flush Network Cache

Open Command Prompt as Administrator:

```cmd
ipconfig /flushdns
```

Then:

```cmd
netsh winsock reset
```

Then:

```cmd
netsh int ip reset
```

Restart the computer afterward.

---

# 14. Check Router for DHCP Reservation Conflicts

If the router supports DHCP reservations:

Check for:

- duplicate reservations
- overlapping static IPs
- stale DHCP leases

Sometimes clearing old DHCP leases resolves the issue.

---

# 15. Test Connectivity Again

After changes:

Run:

```cmd
ipconfig
```

Then:

```cmd
ping 127.0.0.1
```

Then:

```cmd
ping <default-gateway>
```

Example:

```cmd
ping 192.168.1.1
```

Then:

```cmd
ping 8.8.8.8
```

Then:

```cmd
ping google.com
```

---

# Troubleshooting Flow Summary

Typical IT-support workflow:

```text
Gather information
↓
Check current IP address
↓
Determine DHCP vs static
↓
Release / renew IP
↓
Check ARP table
↓
Identify duplicate device
↓
Reboot PC
↓
Reboot router
↓
Verify DHCP scope
↓
Move static IP if needed
↓
Reset adapter
↓
Clear DHCP lease conflict
↓
Retest connectivity
```

---

# Useful Commands Reference

## Show IP configuration

```cmd
ipconfig
```

---

## Release IP

```cmd
ipconfig /release
```

---

## Renew IP

```cmd
ipconfig /renew
```

---

## Show ARP table

```cmd
arp -a
```

---

## Flush DNS cache

```cmd
ipconfig /flushdns
```

---

## Reset Winsock

```cmd
netsh winsock reset
```

---

## Reset TCP/IP stack

```cmd
netsh int ip reset
```

---

## Ping localhost

```cmd
ping 127.0.0.1
```

---

## Ping router

```cmd
ping 192.168.1.1
```

---

## Ping internet

```cmd
ping 8.8.8.8
```

---

## Test DNS resolution

```cmd
ping google.com
```

---
