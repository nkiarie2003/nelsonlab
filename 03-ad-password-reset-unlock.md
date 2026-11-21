# KB03: Resetting a password or unlocking an account in AD

## Before you do anything
Confirm it's actually the user. Never reset a password because someone else asked for it, even a manager. If they need access to files, that goes through approval instead.

## Unlock an account
1. Open Active Directory Users and Computers.
2. Find the user, right-click > Properties > Account tab.
3. Tick "Unlock account" and click OK.

## Reset a password
1. Right-click the user > Reset Password.
2. Enter a temporary password.
3. Tick "User must change password at next logon".
4. Tick "Unlock the user's account" if it's locked.
5. Give the temporary password to the user directly, not by email to someone else.

## If they keep getting locked out
Repeated lockouts usually mean an old password is saved somewhere and keeps trying to sign in. Check:
- Phone email apps
- Saved credentials in Credential Manager
- Mapped drives or apps signed in with the old password

Clear the old password, then unlock the account again.
