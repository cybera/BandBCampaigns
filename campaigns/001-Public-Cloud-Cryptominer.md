# Public Cloud Cryptomining

## Requirements

Core Deck, Cloud Security/DenSecure

## Overview

Cybera runs a public cloud called the [Rapid Access
Cloud](https://www.cybera.ca/rapid-access-cloud/) - and as a public cloud we
also run some of our services on top of it as well as running the hardware
itself. We wanted to explore the very real chance of a user's instance being
compromised and how to manage the threats and risk that presents.

## Card Layout

### Scenario

*Initial Compromise*: Credentials Posted Publicly to a Code Repository

*Pivot & Escalate*: Query of Cloud APIs

*C2 & Exfil*: VM Access via Web Portal

*Persistence*: Application Shimming

NOTE: The Cryptominer inject was used as a starting condition.

### Established Procedures

1. Isolation


2. Permissions Audit

We chose this one and also helped the responders understand this particular
one also covered "cloud API access" to avoid confusion with other procedures.

3. Network Threat Hunting - Zeek/RITA

Chosen to reflect tools we have deployed

4. Server Analysis

### Attack Details

A "VIP" user with a near unlimited quota has posted their credentials to the
cloud to a public cloud repository. This has led to hundreds of new instances
being spun up to attempt to cryptomine leading to the first alert the team
gets - we are seeing load alerts across many of our hypervisors.

Unfortunately this "VIP" user still has access to see information via the
cloud's APIs of services internal to the company. Through luck and literary
tropes - a firewall misconfiguration means that the attacker can access things
that would normally not be accessible. Namely a public web portal to access
backups and the command line on an internal server. These are then downloaded by the attacker.

The attacker is also to ensure they stick around by altering the startup
commands of this particular web application

## Things We Learnt

* Jumping to conclusions, and rolling a 1 makes this game a lot of fun. Not so
  fun if the results actually happened.
* Firewalls are for all traffic - not just external IPs
* Scenarios where 3 of the 4 cards are flipped by Log Analysis procedures are
  a lot harder when your team is unable to understand (or read) the logs (meaning you rolled <10)

