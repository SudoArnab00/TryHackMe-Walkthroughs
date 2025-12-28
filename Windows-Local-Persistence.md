## Room : [Windows Local Persistence](https://tryhackme.com/room/windowslocalpersistence)

### Tampering with unprivileged accounts
`net localgroups` can be used to add unprivileged accounts to Admininstrators / Backup Operators groups for higher privilege or access

Example:
```
net localgroup administrators thmuser0 /add
net localgroup "Backup Operators" thmuser1 /add
net localgroup "Remote Management Users" thmuser1 /add
```

**Administrators** are master key groups
**Backup Operators** are key users (for data only) who need to capture/read/write ==everything / anything== when backing up ignoring ACLs (_Access Control Lists_) even protected files like SAM (_Security Accounts Manager_) database and System Hives

