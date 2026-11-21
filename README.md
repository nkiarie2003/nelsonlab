# NelsonLab

Home lab I built to practise 1st line IT support. Windows Server, Windows 11, Microsoft 365, Intune and Jira, all running in VirtualBox.

Videos:
- Lab walkthrough: https://youtu.be/1J6hfjl-TAc
- Jira tickets: https://youtu.be/1tqk1oRCJkA

## Setup

- DC01: Windows Server 2025 domain controller (AD, DNS, DHCP, file shares, print server, NAT, Entra Connect)
- PC01: Windows 11, joined to the domain, managed with Group Policy
- PC02: Windows 11, set up with Autopilot and managed with Intune
- Microsoft 365 Business Premium trial tenant

## What I did

- Created OUs, users and security groups for Finance, Sales and IT
- Group Policy for mapped drives, printer, Remote Desktop, login banner and blocking Control Panel
- DHCP scope and printer reservation, DNS records
- Synced users to Entra ID with Entra Connect
- MFA with Conditional Access and a break-glass admin account
- Registered PC02 with Autopilot and enrolled it into Intune
- Compliance policy, BitLocker and Defender policies, Office deployed through Intune
- Logged and resolved 43 practice tickets in Jira (accounts, permissions, network, printers, M365, security)

## Screenshots

Everything is in the screenshots folder, split by machine and portal.

## Notes

- Tickets are scenarios I wrote myself and worked through in the lab.
- PC01 couldn't use BitLocker because the evaluation image didn't include it, so encryption was done on PC02 through Intune instead.
