# Description
  Exfiltrate wifi passwords, and sends it to your phone number via SMTP (gmail)

# Setup
  1. Create or use an existing app token gmail generated for you (as you can no longer use your normal password for auth).
  2. Replace %GMAIL_ACC% with your gmail account, %TOKEN% with the token gmail provides, %FROM% with your email, %SEND_TO% with the email you wish to send it to OR replace with your phone number.
  3. Save and move it to your flip 

# Send file to your phone
  Replace %SEND_TO% with <phoneNumber>@<smsgateway>
  Example:
     Sprint  - <phoneNumber>@messaging.sprintpcs.com
     AT&T    - <phoneNumber>@txt.att.net
     TMobile - <phoneNumber>@tmomail.net
     Verizon - <phoneNumber>@vtext.com

  * If your provider is NOT provided here, you can use https://freecarrierlookup.com to get exactly what it is, and how it's formatted.
