# Slow Internet — Troubleshooting Steps

A step-by-step IT support workflow for troubleshooting the issue:

> **"Internet is really slow."**  
> or  
> **"My connection works, but everything is loading slowly."**

This guide covers how IT support would diagnose slow internet performance on Wi-Fi or Ethernet.

---

# Initial Ticket

## Reported Issue

```text
User reports:
"my internet is working... but its REALLY slow. pages take forever to load. please fix."
```

Common symptoms include:

- websites take a long time to load
- downloads are slow
- buffering on YouTube/Netflix
- Teams or Zoom lagging
- file uploads taking too long
- pages eventually load, but slowly
- intermittent pauses while browsing

---

# 1. Gather Information

Before troubleshooting, ask:

- Are you on **Wi-Fi or Ethernet**?
- Is the issue happening on one device or multiple?
- When did it start?
- Is it:
  - constant
  - intermittent
  - only at certain times of day
- Are:
  - downloads slow?
  - browsing slow?
  - video calls lagging?
  - streaming buffering?

Also ask:

- Has anything changed recently?
  - moved rooms
  - rebooted router
  - VPN enabled
  - software update
  - new device on network

---

# 2. Test Another Device

Check another device on the same network:

Examples:

- phone
- laptop
- tablet

---

## If multiple devices are slow

Likely:

- router issue
- ISP issue
- bandwidth saturation
- wireless interference

---

## If only one device is slow

Likely:

- local PC issue
- adapter issue
- driver issue
- software using bandwidth

---

# 3. Run a Speed Test

Measure actual performance.

Use:

```text
speedtest.net
```

or

```text
fast.com
```

Check:

- Download speed
- Upload speed
- Ping / Latency

Compare results to expected ISP speeds.

---

# 4. Determine Wi-Fi vs Ethernet

If using Wi-Fi:

Test the same device over Ethernet if possible.

---

## If Ethernet is faster

Likely:

- weak Wi-Fi signal
- interference
- access point issue

---

## If both are slow

Likely:

- ISP
- router
- modem
- device issue

---

# 5. Check Signal Strength (Wi-Fi)

If wireless:

Verify:

- number of bars
- distance from router
- walls or obstacles
- interference nearby

Common interference sources:

- microwaves
- Bluetooth
- neighboring Wi-Fi
- cordless phones
- thick walls

---

# 6. Reboot Computer

Restart the local device.

This clears:

- stuck processes
- memory issues
- temporary adapter issues

---

# 7. Reboot Router / Modem

Power-cycle:

1. Unplug router/modem
2. Wait 30 seconds
3. Plug back in
4. Wait for internet lights to stabilize
5. Reconnect and test again

---

# 8. Check Network Usage

Slow internet may be bandwidth saturation.

Open:

```text
Task Manager → Performance
```

or

```text
Task Manager → Processes
```

Look for apps using bandwidth:

Examples:

- Windows Update
- OneDrive sync
- Dropbox
- Steam downloads
- browser downloads
- backup software
- cloud sync

---

# 9. Check IP Configuration

Open Command Prompt:

```cmd
ipconfig
```

Verify:

- valid IPv4 address
- default gateway
- DNS servers

---

# 10. Ping Test Latency

Check latency and packet loss.

---

## Ping router

```cmd
ping <default-gateway-ip>
```

Example:

```cmd
ping 192.168.1.1
```

---

## Ping public DNS

```cmd
ping 8.8.8.8
```

Watch for:

- high latency
- spikes
- packet loss

---

## Test DNS resolution

```cmd
ping google.com
```

---

# 11. Change DNS Servers

If browsing feels slow but internet works, DNS lookup delays may be the cause.

Set DNS manually.

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

# 12. Disable VPN / Proxy

VPNs commonly reduce speed.

Temporarily disconnect:

- VPN client
- AnyConnect
- WireGuard
- Tailscale
- Zscaler

Then retest speed.

Also check:

```text
Settings → Network & Internet → Proxy
```

---

# 13. Disable / Re-enable Network Adapter

Open:

```text
Control Panel → Network Connections
```

Then:

- right-click active adapter
- Disable
- wait a few seconds
- Enable

---

# 14. Update or Reinstall Network Driver

Open:

```text
Device Manager → Network adapters
```

Then:

---

## Update Driver

- Right-click adapter
- Update driver

---

## Reinstall Driver

- Uninstall device
- Reboot

---

# 15. Flush DNS / Reset Network Stack

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

Restart afterward.

---

# 16. Check Router Placement (Wi-Fi)

If wireless:

Verify router is:

- elevated
- centrally located
- away from walls
- away from metal objects
- away from electronics causing interference

---

# 17. Check for ISP Issues

If everything local looks normal:

Check:

- ISP outage page
- modem status lights
- ISP mobile app
- neighborhood outage reports

---

# 18. Escalate if Needed

If slow speed persists after troubleshooting:

Escalate to:

- ISP
- networking team
- router replacement
- access point replacement

---

# Troubleshooting Flow Summary

Typical IT workflow:

```text
Gather information
↓
Test another device
↓
Run speed test
↓
Compare Wi-Fi vs Ethernet
↓
Check signal strength
↓
Restart PC
↓
Restart router
↓
Check bandwidth usage
↓
Ping test latency
↓
DNS troubleshooting
↓
Disable VPN/proxy
↓
Reset adapter
↓
Update driver
↓
Reset network stack
↓
Check router placement
↓
Check ISP outage
↓
Escalate if needed
```

---

# Useful Commands Reference

## Show IP configuration

```cmd
ipconfig
```

---

## Flush DNS cache

```cmd
ipconfig /flushdns
```

---

## Ping router

```cmd
ping 192.168.1.1
```

---

## Ping public internet

```cmd
ping 8.8.8.8
```

---

## Test DNS resolution

```cmd
ping google.com
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

# Useful Websites

## Speed Test

```text
https://www.speedtest.net
```

---

## Fast.com

```text
https://fast.com
```

---
