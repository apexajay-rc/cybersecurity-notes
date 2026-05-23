# SMB Enumeration Notes

## Initial Nmap Enumeration

```bash
nmap -p445 --script=smb-enum-shares,smb-enum-users <TARGET-IP>
```

Purpose:

- enumerate SMB shares
- enumerate users

---

## Manual Enumeration

List available shares:

```bash
smbclient -L //<TARGET-IP> -N
```

Options:

| Option | Purpose |
|----------|----------|
| -L | List shares |
| -N | Null authentication |

---

## Enumeration Workflow

1. Identify SMB service
2. Enumerate shares
3. Test anonymous access
4. Enumerate users
5. Search for accessible files
6. Identify privilege escalation opportunities

---

## Notes

Automation can fail.

Validate results using multiple tools:

- Nmap NSE
- smbclient
- enum4linux
