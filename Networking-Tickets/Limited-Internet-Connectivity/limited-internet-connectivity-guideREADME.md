# Limited Internet Connectivity — Troubleshooting Steps

A step-by-step IT support workflow for troubleshooting the issue:

> **"Limited internet connectivity."**  
> or  
> **"Connected, but internet access is limited."**

This guide covers how IT support would diagnose a machine that appears connected to the network, but has partial or unstable internet access.

---

# Initial Ticket

## Reported Issue

```text
User reports:
"my internet isn't working. it says limited connectivity please fix"
```

Common symptoms include:

- Wi-Fi or Ethernet shows **Connected**
- Network icon shows:
  - **No Internet**
  - **Limited**
  - **Connected, secured — No internet**
- Some websites load, others don’t
- Teams/Zoom disconnects intermittently
- Slow or unstable browsing
- Internal network may work while internet fails

---

# 1. Gather Information

Start with basic questions:

- Are you on **Wi-Fi or Ethernet**?
- Is only one device affected?
- Can other users get online?
- Is the issue constant or intermittent?
- Did anything recently change?
  - moved location
  - router reboot
  - software update
  - VPN connection
  - docking station change

---

# 2. Confirm Network Status

Check whether the machine is connected.

Verify:

- Wi-Fi connected to correct SSID  
or
- Ethernet plugged in with link lights

Then check the Windows network icon for:

```text
Connected
Limited
No Internet
Secured, No Internet
```

---

# 3. Test Another Device on the Same Network

Use another device:

- phone
- tablet
- laptop

---

## If multiple devices fail

Likely issue:

- router
- modem
- ISP

---

## If only one device fails

Likely issue:

- local adapter
- DHCP
- DNS
- driver
- VPN/proxy

---

# 4. Check IP Configuration

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

This usually means:

- DHCP failed
- device did not receive an IP lease

---

# 5. Release and Renew IP Address

Refresh DHCP lease:

```cmd
ipconfig /release
```

Then:

```cmd
ipconfig /renew
```

Then retest.

---

# 6. Run Connectivity Tests with Ping

---

## Test local stack

```cmd
ping 127.0.0.1
```

Verifies TCP/IP stack.

---

## Test gateway

```cmd
ping <default-gateway-ip>
```

Example:

```cmd
ping 192.168.1.1
```

Verifies communication with router.

---

## Test internet by IP

```cmd
ping 8.8.8.8
```

Verifies raw internet access.

---

## Test DNS

```cmd
ping google.com
```

---

## Common Result

If:

```text
8.8.8.8 works
google.com fails
```

Likely a **DNS issue**.

---

# 7. Change DNS Servers

If DNS is suspected, manually set DNS.

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

Reconnect and test again.

---

# 8. Disable / Re-enable Network Adapter

Open:

```text
Control Panel → Network Connections
```

Then:

- Right-click active adapter
- Disable
- Wait a few seconds
- Enable

This forces a fresh adapter reset.

---

# 9. Restart the Computer

Reboot the machine and test again.

Often resolves temporary DHCP, adapter, or cached routing issues.

---

# 10. Reboot Router / Modem

Power-cycle network equipment:

1. Unplug router/modem
2. Wait 30 seconds
3. Plug back in
4. Wait until internet lights stabilize
5. Reconnect
6. Retest internet

---

# 11. Flush DNS Cache

Open Command Prompt as Administrator:

```cmd
ipconfig /flushdns
```

This clears cached DNS records.

---

# 12. Reset Network Stack

Run:

```cmd
netsh winsock reset
```

Then:

```cmd
netsh int ip reset
```

Restart afterward.

---

# 13. Check for VPN or Proxy Issues

Limited internet is often caused by VPN or proxy settings.

Check:

```text
Settings → Network & Internet → Proxy
```

Verify:

- Proxy disabled (unless required)
- VPN disconnected for testing

Temporarily disable and retest.

---

# 14. Update or Reinstall Network Driver

Open:

```text
Device Manager → Network adapters
```

Then either:

---

## Update Driver

- Right-click adapter
- Update driver

---

## Reinstall Driver

- Right-click adapter
- Uninstall device
- Reboot

Windows should reinstall automatically.

---

# 15. Full Network Reset (Last Resort)

Open:

```text
Settings → Network & Internet → Advanced network settings → Network reset
```

This will:

- remove adapters
- reinstall network components
- reset networking back to default

---

# Troubleshooting Flow Summary

Typical IT workflow:

```text
Gather information
↓
Confirm connected status
↓
Test another device
↓
Check IP address
↓
Renew DHCP
↓
Ping tests
↓
DNS troubleshooting
↓
Reset adapter
↓
Restart PC
↓
Restart router
↓
Flush DNS
↓
Reset network stack
↓
Check VPN/proxy
↓
Driver reinstall
↓
Full network reset
↓
Escalate ISP/router issue
```

---

# Useful Commands Reference

## Show IP configuration

```cmd
ipconfig
```

---

## Release DHCP lease

```cmd
ipconfig /release
```

---

## Renew DHCP lease

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

## Ping internet by IP

```cmd
ping 8.8.8.8
```

---

## Test DNS resolution

```cmd
ping google.com
```

---
