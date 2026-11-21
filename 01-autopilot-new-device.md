# KB01: Setting up a new device with Autopilot

Use this when a new starter needs a laptop set up through Intune.

## Before you start
- Device has TPM 2.0 (check in PowerShell as admin: `get-tpm`)
- Device is connected to the internet
- User has an account and a Microsoft 365 licence

## Steps
1. On the device, open PowerShell as admin and get the hardware hash:
   ```
   Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
   Install-Script -Name Get-WindowsAutopilotInfo -Force
   Get-WindowsAutopilotInfo -OutputFile C:\autopilot.csv
   ```
2. In Intune go to Devices > Enrollment > Windows Autopilot > Devices > Import and upload the CSV.
3. Wait for the device to show up, then check it has a deployment profile assigned.
4. Reset the device to first-time setup:
   ```
   C:\Windows\System32\Sysprep\sysprep.exe /oobe /reboot
   ```
5. When it restarts it should say "Let's set things up for your work or school". The user signs in with their work email and sets a PIN.
6. In Intune check the device shows as Compliant with the right primary user.

## Common problems
- "Running scripts is disabled": run the Set-ExecutionPolicy line first.
- `sysprep` not recognised: use the full path in step 4.
- Normal Windows setup appears instead of the work screen: the device isn't registered or has no profile yet. Check step 3.
