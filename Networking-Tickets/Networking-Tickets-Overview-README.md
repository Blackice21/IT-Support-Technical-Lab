# Networking Troubleshooting (Help Desk)

A collection of practical help desk troubleshooting guides for diagnosing and fixing common **network connectivity issues** on Windows systems.

This folder focuses on real-world networking tickets such as:

- DNS not resolving
- Ethernet connected but no internet
- IP address conflict
- Limited internet connectivity
- No internet connectivity
- Slow internet
- Wi-Fi connected but no internet

---

# Goal

The goal of these notes is to provide a simple, repeatable workflow for troubleshooting common networking issues in a help desk environment.

These guides are meant to help with:

- gathering information from the user
- isolating whether the issue is device, network, or ISP related
- testing connectivity step-by-step
- applying common fixes in a logical order
- documenting troubleshooting clearly

---

# Common Networking Tickets

## DNS Not Resolving
Troubleshooting name resolution failures where websites fail to load by hostname but internet may still work.

---

## Ethernet Connected But No Internet
Diagnosing wired connections that show connected but cannot reach the internet.

---

## IP Address Conflict
Fixing duplicate IP issues causing network disconnects or limited access.

---

## Limited Internet Connectivity
Troubleshooting devices that connect to the network but have partial or unstable internet access.

---

## No Internet Connectivity
General end-to-end workflow for machines with no internet access at all.

---

## Slow Internet
Troubleshooting slow browsing, buffering, high latency, and poor connection performance.

---

## Wi-Fi Connected But No Internet
Diagnosing wireless connections that appear connected but cannot access websites or online services.

---

# General Networking Troubleshooting Workflow

Most networking tickets follow this process:

```text
Gather information
↓
Identify Wi-Fi or Ethernet
↓
Test another device
↓
Check IP configuration
↓
Run ping tests
↓
Check DNS
↓
Renew DHCP lease
↓
Reset adapter
↓
Restart PC
↓
Restart router/modem
↓
Test again
↓
Escalate if needed
```

---

# Common Commands Used

## Show IP configuration

```cmd
ipconfig
```

## Release IP address

```cmd
ipconfig /release
```

## Renew IP address

```cmd
ipconfig /renew
```

## Flush DNS cache

```cmd
ipconfig /flushdns
```

## Ping test

```cmd
ping 8.8.8.8
```

## Test DNS resolution

```cmd
ping google.com
```

## DNS lookup

```cmd
nslookup google.com
```

## Reset Winsock

```cmd
netsh winsock reset
```

## Reset TCP/IP stack

```cmd
netsh int ip reset
```

---

# Folder Structure

```text
networking/
│
├── README.md
├── dns-not-resolving.md
├── ethernet-connected-no-internet.md
├── ip-address-conflict.md
├── limited-internet-connectivity.md
├── no-internet-connectivity.md
├── slow-internet.md
└── wifi-connected-no-internet.md
```

---

# Notes

Most networking issues can usually be narrowed down to one of these areas:

```text
Physical Connection
IP Addressing / DHCP
DNS
Adapter / Driver
Router / ISP
```

Finding **where communication breaks** is usually the fastest way to solve the ticket.

---
