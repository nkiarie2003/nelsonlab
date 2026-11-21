# KB02: Device showing non-compliant in Intune

A non-compliant device can be blocked from email, Teams and SharePoint, so treat it as a priority.

## Steps
1. In Intune go to Devices > All devices and open the device.
2. Click Device compliance and open the policy that's failing.
3. Check which setting failed (for example firewall, antivirus, BitLocker).
4. Fix that setting on the device. For a disabled firewall: Windows Security > Firewall & network protection > turn it on for all three networks.
5. Back in Intune click Sync on the device page. You can also sync from the device: Settings > Accounts > Access work or school > Info > Sync.
6. Refresh the compliance page until it shows Compliant.

## Notes
- The status doesn't update straight away. It can take a few minutes after a sync, sometimes longer.
- Tell the user it's fixed once Intune shows Compliant, not before.
- If the setting keeps turning itself off, check whether the user has admin rights or software that changes it.
