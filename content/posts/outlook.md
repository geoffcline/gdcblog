---
title: "Outlook Rules"
date: 2020-08-19T21:32:07Z
draft: false
---

## Theory
Personally, I use three categories of emails.

1. External - emails not from an Amazon domain
2. Indirect- emails sent to lots of people, not just me
3. Inbox - emails that don't match either of the previous two rules

I would ideally like to add an additional category -- automated (e.g., slack notifications, ticket notifications). However, these emails are often internal and sent only to me. I haven't found a good way to identify these emails using Outlook rules. 

## Indirect Emails

In short: emails where you aren't in the "to" line. For example, emails sent to mailing lists you are a member of.


- To: fmulder@fbi.gov, dscully@fbi.gov 
    -  ✅ direct


- To: xfiles-team@fbi.gov
    - ❌ indirect  
    - this group could include fmulder@fbi.gov, but it's *indirectly* sent to that address

## Sent to *only* me

Some people go a step further. They filter messages sent to more than one person. This rule can be helpful to tame an overflowing mailbox, or identify priority emails. 

- To: fmulder@fbi.gov, end of list
    - ✅ single recepient, sent only to you


- To: fmulder@fbi.gov, dscully@fbi.gov 
    - ❌ multiple recepients 


## Internal Groups

You can create outlook rules based on internal ANT groups, instead of individually specifiying users. In other words, you can use existing groups on permissions.amazon.com to automate your outlook rules. 

Note this only works with groups on permissions.amazon.com of the "ANT" type. 

When you use groups in Outlook rules, they don't require the *entire* group, but just a *single* member. 

- xfiles-team
    - fmulder@fbi.gov, dscully@fbi.gov


- from: fmulder@fbi.gov
    - to: wskinner@fbi.gov
    - ✅ triggers a rule based on messages from "xfiles-team"

## External Emails

Luckily at Amazon, external messages include the "[EXTERNAL]...." prefix in the subject line, making them a bit easier to handle. Configure your outlook rules to look for this prefix in the subject line. 

I add an exception: don't filter external messages if the sender is in my personal outlook address book. The key here is to get in the habit of adding external people you communicate with to your address book. 

Notably, this rule is *client only*. Meaning, it *doesn't* execute on the email sever as messages are received. Instead, the outlook desktop app executes this rule. The outcome is that these rules don't work when you are on a mobile device and don't have the desktop app open anywhere. 

### Server Proccessing Possible?

Determining if an email is sent from a member of an *internal* group is possible in a traditional server executed rule.

Is a server rule possible for groups of *external* users? We can't add these people to ANT groups -- then it would be to grant internal permissions to external users. 

What we need is a "distribution list" or "public group" that the exchange server can programatically access. However, I haven't been able to find a way to create this at Amazon. Microsoft's documentation is unhelpful on this. They have very fluid definitions of teams, groups, and lists. 

## Further Topics?

### notifications
- desktop
- mobile
- rules that skip inbox don't trigger desktop notifications
- research what happens on mobile

### calendar
- move to other calendar
- categories, but don't work on mobile
- mobile works for multiple calendars
- share your calendar

### mobile email clients
- advantages of VMware boxer
- similar to iOS outlook
- single app for exchange email, calendar, and contacts
- better way to search contacts on mobile
- understanding of multiple calendars
- better email management
- keep Amazon content seperate