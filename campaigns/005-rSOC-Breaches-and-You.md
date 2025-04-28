# Roles
## Person who reported - Incoming alert, reported by the system
## Incident Coordinator - Micheal
## Incident Handler - Kolby then Angelina
## Incident Scribe - Gabriel

# Notes
This incident was mistakenly made too rSOC focussed with not enough Cybera internal work. First attempt at using the IRP instead of Backdoors and Breaches. Will have to improve this next time to be more meaningful to the internal team, not just the rSOC analysts.

# Incident
- Analyst sees alerts for log silence from log sources for Wild Rose University (whose motto is "Totally a real school") at 2:30 AM MST
	- Log silence started at 2:15 AM upon investigation
- Wild Rose University is an rSOC client, is running 4 physical LCA appliances
- WRU has 5,000 students and 500 endpoints
- Windows servers and endpoints, some linux servers, Cisco switching infrastructure, Cisco APs
- No reported incidents from WRU


# Details
- This is the "early stage" of a persistent access attack. 
- CVE used for privilege escalation:
	- https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-29810 (from April 8)
- Silent log sources are:
	- Windows based only
	- UEBA only (login auditing)
	- Logs were cleared continuously for 15 minutes to hide an account creation from UEBA
- Someone was exploited at WRU and through use of privilege escalation was able to be escalated to a domain admin during this 15 minute time period
	- The goal of the attack was to establish persistence by creating a domain admin account
	- Attack came from a BYO laptop that is unmanaged/unlogged, but was connected to the internal trusted network
		- Thought to be a previous exploit downloaded through a pirated game
	- Windows DCs are susceptible to the CVE
- The logs appear to come back and start flowing after 15 minute blank window
- Network traffic is 10% higher than normal (this is a false positive)
- Minor endpoint incidents from the last 24 hours for WRU (credential stuffing, also a false positive)
- 3 of the 4 LCA appliances are responsive to management commands
	- 1 of the 4 is down for an unrelated reason (networking misconfiguration that we missed that means it is ingesting no logs but reporting fine to management)
	- Incorrect VLAN on WRU side
	- This is a red herring
- There are no internal Cybera breaches as a part of this tabletop, it is solely to focus on the boundry between rSOC and Cybera, and at what point do we examine Cybera provided or Cybera internal systems in a member compromise?

# Discussion Points
- How often do our tools receive new CVE definitions? (Exabeam, Logscale, XSOAR)
- Do we track vulnerable servers/endpoints? Where does our involvement begin/end?
- How sensitive are our log silence alerts? Are they endpoint specific? Should they be tuned or are they where they need to be?
- How did it feel to follow the IRP? Where did you feel like it helped? Where did it feel more "forced?"
- Does Cybera take any steps to look at our own systems after a compromise?
