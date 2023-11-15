# Google Workspace

## Requirements

Core Deck, Cloud Security/DenSecure

## Overview

In this scenario we want to explore what could happen if someone's credentials
got stolen - how could we respond or even know if an employee's credentials
were being used with our Google Workspace?

## Card Layout

### Scenario

*Initial Compromise*: Credential Stuffing

*Pivot & Escalate*: New Service Creation

*C2 & Exfil*: Gmail as C2

*Persistence*: Malicious Browser Plugins

### Established Procedures

1. Endpoint Analysis

Chosen to reflect that Cybera has MDM deployed on our machines, and also has
experience among staff on investigating malware or evaluating end user
machines.

2. Network Threat Hunting - Zeek/RITA Analysis

Chosen to reflect tools we have deployed

3. SIEM Log Analysis

Chosen to reflect tools we have deployed

4. Permissions Audit

Chosen to reflect the relative straight forward nature of Google Workspace and
to investigate if this is something 

### Attack Details

The attacker used reused credentials from another website to get access to an
employee's G Suite login and then was able to pivot by creating a new service
or application within Google Workspace. They then used Gmail to exfiltrate
data (good ol' email) and used Workspace's managed Chrome features to install
malicious browser plugins on different user's browsers.

## Things We Learnt

* Understanding how Google Workspace is used in an organization
* Understanding what logs are most relevant (eg. password changes, resets)
* Understanding limitations of non profit licensing versus enterprise
  licensing with Google
* macOS Internals - launchd, MDM, browser management
