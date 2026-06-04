+++
date = '2026-05-14T21:49:58+05:30'
draft = false
title = 'Finding LAN Devices'
categories = ["Linux", "Raspberry Pi", "SSH"]
tags = ["linux", "ssh", "network"]
+++

## Finding Devices on Your Local Network in Linux

Sometimes you need to find:

- your Raspberry Pi
- another computer on the LAN
- a phone
- a smart TV
- a server
- an unknown device connected to your router

Linux provides several useful commands for exploring your local network.

---

## Viewing Network Interfaces

The first thing you usually want to know is:

- your IP address
- your subnet
- your network interface name

Use:

```bash
ip addr
```

Example output:

```text
2: wlan0: <BROADCAST,MULTICAST,UP,LOWER_UP>
    inet 192.168.1.23/24
```

This tells us:

- interface name: `wlan0`
- local IP address: `192.168.1.23`
- subnet mask: `/24`

A `/24` subnet usually means the network range is:

```text
192.168.1.0/24
```

---

## Understanding the Subnet

If your machine has:

```text
192.168.1.23/24
```

then:

- network address: `192.168.1.0`
- possible devices: `192.168.1.1` → `192.168.1.254`

Usually:

- `.1` is the router
- other devices receive addresses dynamically via DHCP

---

## Viewing Known Devices with `ip neigh`

Linux maintains a neighbor table containing devices your machine has recently communicated with.

View it using:

```bash
ip neigh
```

Example:

```text
192.168.1.1 dev wlan0 lladdr 34:60:f9:aa:bb:cc REACHABLE
192.168.1.5 dev wlan0 lladdr 11:22:33:44:55:66 STALE
```

Explanation:

- `192.168.1.1` → device IP address
- `wlan0` → network interface
- `lladdr` → MAC address
- `REACHABLE` → device recently responded
- `STALE` → entry exists but has not been contacted recently

This command is useful for quickly seeing devices already known to the system.

---

## Using `arp -a`

Older systems often use:

```bash
arp -a
```

Example:

```text
router (192.168.1.1) at 34:60:f9:aa:bb:cc [ether] on wlan0
```

This shows similar information to `ip neigh`.

`ip neigh` is considered the modern replacement.

---

## Scanning the Entire Network with `nmap`

`nmap` is one of the most useful network scanning tools available.

Install it:

### Arch / Artix

```bash
sudo pacman -S nmap
```

### Debian / Ubuntu

```bash
sudo apt install nmap
```

---

## Ping Scan with `nmap -sn`

To discover active devices on your network:

```bash
nmap -sn 192.168.1.0/24
```

Explanation:

- `-sn` means:
  - host discovery only
  - no port scanning

Sometimes `nmap` can also identify the device vendor:

---

## Raspberry Pi USB Gadget Networking

If SSH over USB is enabled on a Raspberry Pi, plugging it into a Linux computer may create a USB network interface.

Check interfaces:

```bash
ip addr
```

You may see:

- `usb0`
- `enx...`

Typical addresses:

| Device       | IP          |
| ------------ | ----------- |
| Host PC      | 192.168.7.1 |
| Raspberry Pi | 192.168.7.2 |

Connect using:

```bash
ssh pi@192.168.7.2
```

or:

```bash
ssh username@raspberrypi.local
```

---

## Discovering `.local` Hostnames with Avahi

Linux systems can use mDNS (multicast DNS) for hostname discovery.

Install:

### Arch / Artix

```bash
sudo pacman -S avahi nss-mdns
```

Start the service:

```bash
sudo systemctl enable --now avahi-daemon
```

Browse devices:

```bash
avahi-browse -at
```

This may show:

- Raspberry Pis
- printers
- Linux machines
- smart devices

---

## Useful One-Liners

### Show only IPv4 addresses

```bash
ip -4 addr
```

### Show routing table

```bash
ip route
```

### View active listening ports

```bash
ss -tulpn
```

### Ping a device

```bash
ping 192.168.1.1
```

---

