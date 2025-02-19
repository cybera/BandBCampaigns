# The Knowledge of Good and Evil

## Requirements

Core Deck 2.2 + Expansion

## Overview

What do you do when a supply chain attack takes out your organizational source of knowledge?
## Card Layout

### Scenario

*Initial Compromise*: Supply Chain Attack

*Pivot & Escalate*: Local Privilege Escalation

*C2 & Exfil*: Domain Fronting as C2 (fudged this a bit to be "utilize our externally exposed service/domain to run a VPN and Tor endpoint for illegitimate activity, as a profit motive")

*Persistence*: Malicious service

STARTING CONDITION: No specific starting condition was selected for this round.

*Injection(s):* Secrets leaked to Pastebin - played this off in game as "credentials of exploited server for other bad actors to use"

### Established Procedures

**Firewall Log Review, SIEM Log Analysis, Endpoint Analysis, Server Analysis**

### Attack Details

Slow/glitchy Confluence loads were the inciting incident, leading to a discovered supply chain compromise in a Confluence plugin. This had allowed the bad actors to take over the Confluence server and install a persistent service, with the aim of exposing a public Tor/VPN endpoint to other bad actors. This was exacerbated by the Cybera Wiki being the point of failure, as we were not able to isolate it from the internet during a critical period of use, and were not able to use it reliably enough to gain every piece of institutional information needed to respond effectively.


## Things We Learnt

* Linux server detection/monitoring in rSOC is lacking and would make detection and response to this type of attack very difficult if not impossible at this point
* The Wiki is a dependency for a lot of information that would assist in a response scenario and is assumed to always be available. Incident Response Plan should talk about where to go if Wiki is not available, because there are backups that aren't widely known
* Individual institutional knowledge is not equally distributed, making quick determinations challenging in an incident response scenario, especially for employees who have not been with Cybera for long.
* Our targets are higher value than what might be assumed - threats are real and should be taken seriously
* The Wiki is secret-free and that is a major success - good practice here helped this stay contained