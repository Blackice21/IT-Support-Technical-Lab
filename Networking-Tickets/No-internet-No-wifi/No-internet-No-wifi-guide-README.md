# No Internet (Wi-Fi) — Troubleshooting Steps

A step-by-step IT support workflow for troubleshooting a vague help desk ticket like:

> **"No internet — can you fix this?"**

This guide focuses on **Wi-Fi troubleshooting** and follows a practical IT-support style diagnostic process.

---

# Initial Ticket

## Reported Issue

```text
User reports: "No internet"
```

At this stage the ticket is vague, so first gather information before jumping into fixes.

---

# 1. Gather Basic Information

Ask the user:

- Are you on **Wi-Fi or Ethernet**?
- Is **only this device** affected?
- Are other users/devices able to access the internet?
- When did it stop working?
- Did anything change recently?
  - reboot
  - update
  - moved location
  - router reboot
  - power outage

---

# 2. Confirm Wi-Fi Connection Status

Check whether the machine is connected to Wi-Fi.

Verify:

- Wi-Fi is turned **On**
- Airplane mode is **Off**
- Connected to the correct SSID
- Signal strength is present

Check:

```text
Taskbar → Wi-Fi icon
```

---

# 3. Verify Other Devices

Test another device on the same Wi-Fi:

Examples:

- phone
- tablet
- second laptop

### Outcomes

## If other devices also fail
Likely:
- router issue
- modem issue
- ISP outage

## If only one device fails
Likely:
- local machine issue
- Wi-Fi adapter issue
- DNS issue
- bad saved network profile

---

# 4. Forget and Reconnect to Wi-Fi

A very common fix.

Steps:

```text
Settings → Network & Internet → Wi-Fi → Manage Known Networks
```

Then:

1. Select the Wi-Fi network
2. Click **Forget**
3. Reconnect
4. Re-enter Wi-Fi password

This rebuilds the saved wireless profile.

---

# 5. Reboot the Computer

Restart the local machine and test again.

This clears temporary adapter issues and cached networking problems.

---

# 6. Reboot Router / Modem

Power-cycle network equipment:

1. Unplug router/modem
2. Wait 30 seconds
3. Plug back in
4. Wait until lights stabilize
5. Reconnect Wi-Fi
6. Test internet access

---

# 7. Check IP Configuration

Open Command Prompt:

```cmd
ipconfig
```

Verify:

- IPv4 Address
- Subnet Mask
- Default Gateway
- DNS Servers

---

## Common Problem

If you see:

```text
169.254.x.x
```

that usually means:

- DHCP failed
- router did not assign an IP address

---

# 8. Renew DHCP Lease

Request a fresh IP from the router.

Run:

```cmd
ipconfig /release
ipconfig /renew
```

Then test internet again.

---

# 9. Test Connectivity with Ping

Ping helps determine where the failure is happening.

---

## Test local TCP/IP stack

```cmd
ping 127.0.0.1
```

Confirms networking stack is working locally.

---

## Test communication to router

```cmd
ping <default-gateway-ip>
```

Example:

```cmd
ping 192.168.1.1
```

Tests connectivity to the router.

---

## Test internet access by IP

```cmd
ping 8.8.8.8
```

If successful:
internet is reachable.

---

## Test DNS resolution

```cmd
ping google.com
```

If this fails while `8.8.8.8` succeeds:

DNS is likely the problem.

---

# 10. Change DNS Servers Manually

If internet works by IP but not by hostname:

configure DNS manually.

---

## Google DNS

```text
8.8.8.8
8.8.4.4
```

---

## Cloudflare DNS

```text
1.1.1.1
1.0.0.1
```

---

# 11. Run Windows Network Troubleshooter

Open:

```text
Settings → Network & Internet → Troubleshoot
```

or

```text
Right-click Wi-Fi icon → Troubleshoot problems
```

Allow Windows to diagnose automatically.

---

# 12. Disable / Re-enable Wi-Fi Adapter

Open:

```text
Control Panel → Network Connections
```

Then:

- Right-click Wi-Fi adapter
- Disable
- Wait a few seconds
- Enable

This refreshes the adapter.

---

# 13. Reset Network Stack

Open Command Prompt as **Administrator**:

```cmd
netsh winsock reset
```

```cmd
netsh int ip reset
```

```cmd
ipconfig /flushdns
```

Restart afterward.

---

# 14. Update or Reinstall Wi-Fi Driver

Open:

```text
Device Manager → Network adapters
```

Then either:

## Update Driver

- Right-click wireless adapter
- Select **Update driver**

or

## Reinstall Driver

- Right-click adapter
- Select **Uninstall device**
- Reboot

Windows should reinstall automatically.

---

# 15. Perform Full Network Reset (Last Resort)

Open:

```text
Settings → Network & Internet → Advanced network settings → Network reset
```

This will:

- remove network adapters
- reinstall networking components
- reset network settings back to default

---

# Troubleshooting Flow Summary

Typical IT-support workflow:

```text
Gather info
↓
Confirm Wi-Fi connection
↓
Test another device
↓
Reconnect to Wi-Fi
↓
Reboot PC
↓
Reboot router
↓
Check IP address
↓
Renew DHCP
↓
Ping tests
↓
DNS troubleshooting
↓
Adapter reset
↓
Driver reinstall
↓
Network reset
↓
Escalate to ISP/router issue
```

---

# Useful Commands Reference

## Show network configuration

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

## Reset TCP/IP

```cmd
netsh int ip reset
```

---

## Test localhost

```cmd
ping 127.0.0.1
```

---

## Test internet by IP

```cmd
ping 8.8.8.8
```

---

## Test DNS resolution

```cmd
ping google.com
```

---
