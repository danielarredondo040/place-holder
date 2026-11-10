# Problem Coworker: Help Desk Training Simulator

A browser-based simulator for practicing Tier 1 help desk troubleshooting. Fictional coworkers submit network tickets, you chat with them to gather information, troubleshoot their PC from a simulated Windows Command Prompt, fix the problem, and write up the ticket.

I built this to practice for help desk work while studying for CompTIA A+.

## What it does

- **Ticket queue**: 7 tickets, numbered 1 to 7, each with a status, priority and alert level, styled after a real web help desk.
- **Messages**: chat with the user who opened the ticket. They are not technical, so you have to ask good questions (When did it start? Did anything change? Is anyone else affected?).
- **Command Prompt**: a simulated `cmd.exe` on the user's PC. Output matches the hidden problem and changes once you actually fix it.
- **Resolve**: write the root cause, work notes for the next technician, and a plain-language message to the user. You then get feedback on method, communication and documentation.
- **Reports**: scores, root causes found, and average time to resolve.

## The tickets

| # | Symptom | What you are practicing |
|---|---------|-------------------------|
| 1 | Internet completely down | Spotting a disabled network adapter |
| 2 | Websites won't load, icon says connected | Telling DNS problems apart from connectivity problems |
| 3 | Yellow triangle after docking a laptop | Recognizing a 169.254 (APIPA) address and renewing DHCP |
| 4 | Shared drive works, internet doesn't | Finding a wrong default gateway on a static IP |
| 5 | Only Outlook on the web fails | Finding a bad hosts file entry |
| 6 | Browsers fail, Teams still works | Finding a dead manual proxy |
| 7 | No internet after the desk was moved | Recognizing "Media disconnected" and walking the user through a physical fix |

## Supported commands

`ipconfig`, `ipconfig /all`, `ipconfig /release`, `ipconfig /renew`, `ipconfig /flushdns`, `ping`, `nslookup`, `tracert`, `netsh interface show interface`, `netsh interface set interface "Ethernet" enable`, `netsh interface ip set dns "Ethernet" dhcp`, `netsh interface ip set address "Ethernet" dhcp`, `type` and `notepad` on the hosts file, `reg query` on Internet Settings, `start ms-settings:network-proxy`, `start https://<site>`, `hostname`, `whoami`, `getmac`, `cls`. Type `help` in the console for the list.

## How to run it

Open `index.html` in any browser. No install needed.

The full version, where Claude plays the coworkers and grades your tickets, runs as a Claude artifact. Opened as a plain file, the coworkers use simple scripted replies and you grade yourself against the real cause.

## Skills shown

- Layered network troubleshooting: local config, gateway, external IP, DNS, application
- Windows networking tools: ipconfig, ping, nslookup, tracert, netsh
- Ticket documentation: root cause, work notes, user communication
- Asking non-technical users the right questions

## Related

- [`docs/video-plan.md`](docs/video-plan.md): the help desk videos I'm making for my portfolio
- [`docs/break-fix-labs.md`](docs/break-fix-labs.md): problems I break on purpose in a Windows VM and then fix on camera
