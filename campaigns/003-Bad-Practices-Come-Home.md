# Bad Practices Come Home

## Requirements

Core Deck

## Overview

How do we respond when a user has been using an old compromised password...
everywhere? And how do we respond when brought in late to a response?


## Card Layout

### Scenario

*Initial Compromise*: Exploitable External Service

*Pivot & Escalate*: Creds exposed in Environment Variables

*C2 & Exfil*: HTTPS as Exfil

*Persistence*: Evil Firmware (Dependency)

NOTES:
We also allowed Server Analysis to find "Evil Firmware" as Evil firmware is
standing in for a prebaked dependency in various Java apps (eg. Elasticsearch)

STARTING CONDITION: "I'm not the cloud person". But only the first turn must
be done by whomever rolls the lowest D20.

### Established Procedures

1. Zeek/RITA Network Threat Hunting

2. Endpoint Analysis

3. Isolation

### Attack Details

A security responder has been phished and is embarassed about it happening.
The password that was phished/learned also happens to be old and used with
their account name in multiple locations - both personal to them and with the
organization.

## Things We Learnt

* The team took a much more hands on approaching 

* Asset Management/Inventory improvements - knowing what devices are important
* Understanding Tools - discussing what Zeek can log vs what it does log vs
  what does it log that it really does not need to log
* Azure and SIEM budgeting complications
* What is your company's threat model and what are your company's priorities
  on what to secure or monitor first?
