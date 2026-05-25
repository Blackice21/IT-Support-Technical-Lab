# DNS Not Resolving — Troubleshooting Steps

A step-by-step IT support workflow for troubleshooting the issue:

> **"DNS isn’t resolving."**  
> or  
> **"Internet works, but websites won’t load by name."**

This guide covers how IT support would diagnose a DNS resolution issue when a device has network connectivity but domain names are failing to resolve.

---

# Initial Ticket

## Reported Issue

```text
User reports:
"my internet works but websites wont load"
```

Common symptoms include:

- Internet appears connected
- Browser shows:
  - **DNS_PROBE_FINISHED_NXDOMAIN**
  - **Server IP address could not be found**
  - **This site can’t be reached**
- Websites fail by hostname
- Some applications fail to connect
- Pinging IP addresses works
- Pinging domain names fails

---

# 1. Gather Information

Start by asking:

- Are you on **Wi-Fi or Ethernet**?
- Is only one device affected?
- Can other users browse websites normally?
- Does the issue affect all websites or just one?
- Did anything recently change?
  - router reboot
  - VPN connection
  - DNS settings modified
  - Windows update
  - browser update

---

# 2. Confirm Internet Connectivity

First determine whether internet access exists at all.

Open Command Prompt:

```cmd
ping 8.8.8.8
```

---

## If ping succeeds

Internet is reachable.

DNS is likely the issue.

---

## If ping fails

Likely:

- no internet
- routing issue
- gateway issue
- ISP issue

Troubleshoot connectivity first.

---

# 3. Test DNS Resolution

Test domain name resolution:

```cmd
ping google.com
```

---

## Common Result

```text
ping 8.8.8.8 → works
ping google.com → fails
```

This strongly points to DNS failure.

---

# 4. Check IP Configuration

Run:

```cmd
ipconfig
```

Review:

- IPv4 Address
- Default Gateway
- DNS Servers

Example:

```text
DNS Servers . . . . . : 192.168.1.1
```

or

```text
DNS Servers . . . . . : 8.8.8.8
```

Look for:

- missing DNS server
- incorrect DNS server
- unreachable DNS server

---

# 5. Flush DNS Cache

Most common first fix.

Open Command Prompt as Administrator:

```cmd
ipconfig /flushdns
```

This clears locally cached DNS records.

Expected output:

```text
Successfully flushed the DNS Resolver Cache
```

---

# 6. Test Name Resolution Again

Retry:

```cmd
ping google.com
```

Or open browser and test:

```text
google.com
youtube.com
microsoft.com
```

---

# 7. Use nslookup

Check DNS directly.

Run:

```cmd
nslookup google.com
```

Example working output:

```text
Server:  dns.google
Address: 8.8.8.8

Name: google.com
Address: <resolved IP>
```

---

## If nslookup fails

Examples:

```text
DNS request timed out
```

or

```text
Non-existent domain
```

Likely DNS server issue.

---

# 8. Change DNS Servers Manually

Very common fix.

Open:

```text
Control Panel → Network Connections
→ Adapter Properties
→ Internet Protocol Version 4 (TCP/IPv4)
```

Then manually configure DNS.

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

Apply settings and reconnect.

---

# 9. Disable / Re-enable Network Adapter

Open:

```text
Control Panel → Network Connections
```

Then:

- Right-click active adapter
- Disable
- Wait a few seconds
- Enable

This refreshes the adapter and DNS configuration.

---

# 10. Release and Renew IP Address

Refresh DHCP and DNS lease:

```cmd
ipconfig /release
```

Then:

```cmd
ipconfig /renew
```

Then test again.

---

# 11. Reset Winsock and TCP/IP Stack

Open Command Prompt as Administrator:

```cmd
netsh winsock reset
```

Then:

```cmd
netsh int ip reset
```

Restart afterward.

---

# 12. Restart Router / Modem

Power-cycle:

1. Unplug router/modem
2. Wait 30 seconds
3. Plug back in
4. Wait until fully online
5. Reconnect
6. Retest DNS

Many home routers also act as DNS forwarders, so rebooting can clear DNS forwarding issues.

---

# 13. Check Browser or Application

Sometimes DNS works system-wide but fails in one browser.

Test:

- Chrome
- Edge
- Firefox

Or test:

```text
google.com
```

in another browser.

---

# 14. Check VPN or Proxy Settings

DNS failures are often caused by VPN/proxy misconfiguration.

Check:

```text
Settings → Network & Internet → Proxy
```

Also temporarily disconnect:

- VPN client
- Zscaler
- Cisco AnyConnect
- Tailscale
- WireGuard

Then test again.

---

# 15. Restart DNS Client Service (Optional)

Open:

```text
services.msc
```

Find:

```text
DNS Client
```

Then:

- Restart service

or from command line:

```cmd
net stop dnscache
net start dnscache
```

---

# 16. Full Network Reset (Last Resort)

Open:

```text
Settings → Network & Internet
→ Advanced network settings
→ Network reset
```

This resets:

- network adapters
- DNS settings
- TCP/IP settings

Then reboot.

---

# Troubleshooting Flow Summary

Typical IT workflow:

```text
Gather information
↓
Test internet by IP
↓
Test domain name resolution
↓
Check ipconfig
↓
Flush DNS cache
↓
Use nslookup
↓
Change DNS server
↓
Reset adapter
↓
Renew IP
↓
Reset Winsock/TCP-IP
↓
Reboot router
↓
Check browser
↓
Check VPN/proxy
↓
Restart DNS Client
↓
Full network reset
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

## Test internet connectivity

```cmd
ping 8.8.8.8
```

---

## Test DNS resolution

```cmd
ping google.com
```

---

## Query DNS directly

```cmd
nslookup google.com
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

## Restart DNS cache service

```cmd
net stop dnscache
net start dnscache
```

---
