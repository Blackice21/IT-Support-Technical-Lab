# Wi-Fi Connected But No Internet — Troubleshooting Steps

A step-by-step IT support workflow for troubleshooting the issue:

> **"Wi-Fi connected but no internet. Need help!"**

This guide covers a common issue where:

- the device shows connected to Wi-Fi
- signal bars are visible
- but websites and apps cannot reach the internet

---

# Initial Ticket

## Reported Issue

```text
Wi-Fi connected but no internet. Need help!
```

This tells us:

✅ Wireless connection exists  
❌ Internet access is failing

Meaning the machine is likely connected to the router—but something is failing beyond that.

---

# 1. Gather Information

Before changing anything, ask:

- Can other devices use the Wi-Fi?
- Is only this device affected?
- Did this just start happening?
- Did anything recently change?
  - Windows update
  - router reboot
  - moved rooms
  - VPN enabled
  - password changed

---

# 2. Confirm Wi-Fi Connection

Verify:

- Wi-Fi is enabled
- Airplane mode is OFF
- Connected to the correct SSID
- Signal strength is good

Check:

```text
Taskbar → Wi-Fi icon
```

---

## Verify internet status

Open browser and test:

```text
google.com
youtube.com
```

If pages do not load but Wi-Fi shows connected:

continue troubleshooting.

---

# 3. Test Another Device on the Same Wi-Fi

Connect another device:

Examples:

- phone
- tablet
- another laptop

---

## If other devices also fail

Likely issue:

- router
- modem
- ISP outage

---

## If other devices work

Likely issue:

- local device only
- DNS
- DHCP
- wireless adapter
- saved Wi-Fi profile

---

# 4. Forget and Reconnect to Wi-Fi

A very common fix.

Open:

```text
Settings → Network & Internet → Wi-Fi → Manage Known Networks
```

Then:

1. Select current Wi-Fi
2. Click **Forget**
3. Reconnect manually
4. Enter password again

This refreshes the wireless profile.

---

# 5. Toggle Wi-Fi Off and Back On

Quick adapter refresh.

Steps:

- turn Wi-Fi OFF
- wait 5–10 seconds
- turn Wi-Fi back ON
- reconnect

---

# 6. Restart the Computer

Reboot the machine and test again.

This clears temporary adapter or software/network stack issues.

---

# 7. Reboot Router / Modem

Power-cycle:

1. Unplug router/modem
2. Wait 30 seconds
3. Plug back in
4. Wait until all lights stabilize
5. Reconnect Wi-Fi
6. Test internet

---

# 8. Check IP Address

Open Command Prompt:

```cmd
ipconfig
```

Check:

- IPv4 Address
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
- router did not hand out an IP address

---

# 9. Renew DHCP Lease

Request a fresh IP from the router.

Run:

```cmd
ipconfig /release
```

```cmd
ipconfig /renew
```

Then reconnect/test again.

---

# 10. Run Ping Tests

Use ping to isolate where communication breaks.

---

## Test local TCP/IP stack

```cmd
ping 127.0.0.1
```

Confirms local networking is functioning.

---

## Test connection to router

```cmd
ping <default-gateway-ip>
```

Example:

```cmd
ping 192.168.1.1
```

If this fails:
problem is between device and router.

---

## Test internet by IP

```cmd
ping 8.8.8.8
```

If this succeeds:
internet works.

---

## Test DNS resolution

```cmd
ping google.com
```

---

## Common Result

If:

```text
ping 8.8.8.8 = works
ping google.com = fails
```

then the issue is usually **DNS**.

---

# 11. Change DNS Servers

Manually set DNS.

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

Then reconnect and test.

---

# 12. Run Windows Network Troubleshooter

Open:

```text
Settings → Network & Internet → Troubleshoot
```

or

```text
Right-click Wi-Fi icon → Troubleshoot problems
```

Let Windows attempt automatic repair.

---

# 13. Disable / Re-enable Wi-Fi Adapter

Open:

```text
Control Panel → Network Connections
```

Then:

- right-click Wi-Fi adapter
- Disable
- wait a few seconds
- Enable

This refreshes the adapter.

---

# 14. Reset Windows Network Stack

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

# 15. Update or Reinstall Wireless Driver

Open:

```text
Device Manager → Network adapters
```

Then either:

---

## Update Driver

- Right-click wireless adapter
- Update driver

---

## Reinstall Driver

- Right-click adapter
- Uninstall device
- Reboot

Windows will usually reinstall automatically.

---

# 16. Full Network Reset (Last Resort)

Open:

```text
Settings → Network & Internet → Advanced network settings → Network reset
```

This will:

- remove all network adapters
- reinstall networking components
- reset Wi-Fi/network configuration

---

# Troubleshooting Flow Summary

Typical IT workflow:

```text
Confirm Wi-Fi connection
↓
Check other devices
↓
Forget/reconnect Wi-Fi
↓
Toggle Wi-Fi
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
Full network reset
↓
Escalate to ISP/router issue
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
