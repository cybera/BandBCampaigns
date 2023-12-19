# When Dependencies Attack

## Requirements

Core Deck, Cloud Security

## Overview

Dec. 10th and 11th, 2021 were a rather frustrating couple of dates as a major
vulnerability is an widely used Java library were released. The security
patches were incorrect initially requiring multiple patches to be applied.

For Cybera specifically it also proved to be very challenging as larger
systemic issues around vacation meant we had an atypically larger amount of
senior staff on vacation at that time.

So - how can we use the game to explore responding when shorthanded and
without any established procedures?

The cards specifically are designed to help guide the team through confirming
if we had an attack - and ideally through knowing if we did have an attack
where we have gaps in our posture.

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

**NONE**

If you're playing online - only select "Incident Management"

### Attack Details

Through multiple channels we have been alerted that a major security flaw with
Apache Log4J - a Java library used quite heavily by many Java based
applications or applications that leverage Java components to manage their
logging.

The timing of this could not be worse as we've been told that the size of the
hole means it's going to be exploited if it's not already being exploited in
the wild. Also all of our senior staff have just gone on vacation because
nobody took vacation due to the COVID waves during the summer.

The information is only that there is a major vulnerability and patches will
be rolling out in the coming days - how do we know if we're already
compromised or are being compromised?

How do we deal with a lot of overly confident information being posted online
that isn't helpful?

STARTING CONDITION: "I'm not the cloud person" - everyone roll a D20. However
it will only be the first turn.

This is to capture the confusion that resulted when this vulnerability was
first announced of folks thinking Apache Log4J was related to the Apache HTTP
server. This was evident in many social media posts and discussion forums.


## Things We Learnt

* Asset Management/Inventory improvements - knowing what devices are important
* Understanding Tools - discussing what Zeek can log vs what it does log vs
  what does it log that it really does not need to log
* Azure and SIEM budgeting complications
* What is your company's threat model and what are your company's priorities
  on what to secure or monitor first?
