# VPN Monitor — demo

A demo build of a monitoring panel I wrote and run in production for an L2TP/IPsec
VPN service: connection state, per-client session history, uptime, traffic counters,
detection of channel switching between wired and LTE, and log review.

**All data in this demo is synthetic.** Client names, IP addresses, session history
and logs are generated — no real subscriber data is present anywhere in this build.
Every action that would change state (enabling or disabling a client, running a
command on a device, adding clients) is disabled and returns a "demo mode" response.

**Live demo:** https://sashaptiza.github.io/vpn-monitor-demo/

## What it does

- Real-time view of who is connected, on which interface, from which external address
- Per-client session statistics: uptime over 24 hours and 7 days, reconnects,
  average and longest session, 24-hour timeline
- Detection of clients switching between wired and mobile channels — in practice the
  usual cause of disconnects that look random from the server side
- Interface traffic counters
- Service state for xl2tpd and strongSwan
- Log review, with an AI-assisted explanation of what the log actually means

## Stack

Python / Flask on Ubuntu, single-page vanilla JS front end, nginx, token
authentication over HTTPS only. Built and operated by one person — the same person
who gets called when it breaks at 2am.

---

Oleksandr Zhuravel — network engineer, WISP operator since 2014.
Lubny, Ukraine.
