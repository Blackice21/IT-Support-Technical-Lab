# Ethernet Connected But No Internet — Troubleshooting Steps

A quick IT-support style checklist for fixing an Ethernet connection that shows **connected** but has **no internet access**.

---

## 1. Check the Physical Connection

- Make sure the Ethernet cable is firmly plugged in on both ends
- Try a different Ethernet cable
- Try another port on the router or switch
- Check for link/activity lights on:
  - the Ethernet port on your PC
  - the router or switch port

---

## 2. Reboot Everything

### Restart the computer

Reboot the local machine first.

### Power-cycle the router/modem

1. Unplug the power cable
2. Wait 30 seconds
3. Plug it back in
4. Wait for the internet lights to stabilize
5. Test Ethernet again

---

## 3. Run Windows Network Troubleshooter

Open:

**Settings → Network & Internet → Troubleshoot**

or

Right-click the network icon in the taskbar → **Troubleshoot problems**

Allow Windows to scan and attempt automatic repair.

---

## 4. Disable / Re-enable the Ethernet Adapter

Open:

`Control Panel → Network and Sharing Center → Change adapter settings`

Then:

1. Right-click **Ethernet**
2. Click **Disable**
3. Wait a few seconds
4. Click **Enable**

This refreshes the adapter without rebooting.

---

## 5. Check IP Configuration

Open Command Prompt:

```cmd
ipconfig
```

Verify:

- IPv4 Address
- Subnet Mask
- Default Gateway
- DNS Servers

### Common Issue

If you see an address like:

```text
169.254.x.x
```

that usually means the machine did **not** receive an IP from DHCP.

---

## 6. Renew DHCP Lease

Request a fresh IP address from the router:

```cmd
ipconfig /release
ipconfig /renew
```

Then test connectivity again.

---

## 7. Test Connectivity with Ping

Use ping to determine where the failure is happening.

### Test local TCP/IP stack

```cmd
ping 127.0.0.1
```

---

### Test communication to the router

```cmd
ping <default-gateway-ip>
```

Example:

```cmd
ping 192.168.1.1
```

---

### Test internet access by IP

```cmd
ping 8.8.8.8
```

If this works, internet connectivity is present.

---

### Test DNS resolution

```cmd
ping google.com
```

If `8.8.8.8` works but `google.com` fails, the issue is likely DNS.

---

## 8. Change DNS Servers Manually

If DNS appears broken, manually configure DNS.

### Google DNS

```text
8.8.8.8
8.8.4.4
```

### Cloudflare DNS

```text
1.1.1.1
1.0.0.1
```

---

## 9. Reset Windows Network Stack

Run Command Prompt as **Administrator**:

```cmd
netsh winsock reset
```

```cmd
netsh int ip reset
```

```cmd
ipconfig /flushdns
```

Restart the PC after running these.

---

## 10. Update or Reinstall the Ethernet Driver

Open:

`Device Manager → Network adapters`

Then either:

### Update Driver

- Right-click Ethernet adapter
- Select **Update driver**

or

### Reinstall Driver

- Right-click Ethernet adapter
- Select **Uninstall device**
- Restart the computer

Windows should reinstall the driver automatically.

---

## 11. Perform a Full Network Reset

As a last resort:

Open:

**Settings → Network & Internet → Advanced network settings → Network reset**

This will:

- remove network adapters
- reinstall them
- reset all network configuration

---

# Recommended Troubleshooting Order

Most IT support follows this sequence:

```text
Cable
↓
Port
↓
Reboot
↓
Adapter
↓
IP Address
↓
DHCP
↓
DNS
↓
Driver
↓
Router / ISP
```
---

# Useful Commands Reference

## Show IP information

```cmd
ipconfig
```

## Release IP

```cmd
ipconfig /release
```

## Renew IP

```cmd
ipconfig /renew
```

## Flush DNS cache

```cmd
ipconfig /flushdns
```

## Reset Winsock

```cmd
netsh winsock reset
```

## Reset TCP/IP

```cmd
netsh int ip reset
```

## Ping localhost

```cmd
ping 127.0.0.1
```

## Ping Google DNS

```cmd
ping 8.8.8.8
```

## Ping domain name

```cmd
ping google.com
```
