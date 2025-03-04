# Cyber-Alert-Triage
Yo, I’m Raj—Master’s in Info Systems and Security, cyber analyst soul. 
This project’s a no-code way to play analyst: triaging fake alerts like I’m on the job.
I use free tools to sort threats from noise—hands-on, no scripts needed!


What’s the Big Idea?

Analysts get slammed with alerts—“Port scan!” “Login fail!”—most are junk.
I fake some alerts, use tools to check ‘em, and decide what’s hot. 
It’s practice for the real gig, no coding required.


How I Made It Happen

Here’s my simple flow, like I’m at my desk:

1. Make Fake Alerts: Wrote pretend logs—like “10 logins failed” or “Port 445 hit 50 times.”
   Example: “User: raj, 5 fails” vs. “Port 22, 100 hits.”

2. Check with Tools: Used Wireshark to fake network hits, Event Viewer for login stuff—see what’s up.
   Example: Wireshark showed tons of port 22 traffic—sketchy!

3. Sort ‘Em: Ranked alerts—high (attacks), low (normal), based on what I saw.
   Example: “100 port hits = High. 5 login fails = Low.”

4. Log It: Wrote my calls in a text file—like a mini report.
   Example: “High: Port 22 attack. Low: Raj forgot password.”

Stuff You’ll Need

Wireshark: Free from wireshark.org—sees network stuff.
Event Viewer: Built into Windows—no download.
Notepad: Your computer’s got it—logs your calls.
Your PC: Just your machine, no extras.

Let’s Do It—Step by Step with Commands

1. Get Tools:
   - Wireshark: wireshark.org, download, install—easy setup.
   - Event Viewer/Notepad: Already on Windows (Mac folks, use Activity Monitor instead).

2. Set Up Folder: You’re in RajCyberAIProjects/CyberAlertTriage—sweet!
   Command: “cd RajCyberAIProjects\CyberAlertTriage” (Windows)
   or
   “cd RajCyberAIProjects/CyberAlertTriage” (Mac)
   if you’re moving around.

4. Fake Alerts: In Notepad, save as “alerts.txt” here:
User: raj, 5 login fails, 10:00 AM
Port 22, 100 hits, 10:05 AM
Port 80, 3 hits, 10:10 AM


5. Check Network: Open Wireshark, pick your Wi-Fi,
6.  hit “Start.” Click around a bit (fake traffic),
7.   stop after a minute.
   Filter: Type “tcp.port == 22” in the filter bar,
hit enter—see if it’s busy. Save as “network.txt” (File > Export Objects > Text).

9. Check Logins: Windows: Search “Event Viewer,” open it, go to “Windows Logs >
10. Security.” Look for failed logins.
   Example: “Event ID 4625”—login fail. Note it in “alerts.txt.”

11. Triage: Open “alerts.txt,” add your calls:
   Example: “Port 22, 100 hits—High (attack?). User: raj, 5 fails—Low (me messing up).”

Bumps in the Road

No Traffic: Wireshark’s quiet? Surf more to stir it up.
Event Viewer Empty: Try failing a login yourself—lock your PC wrong a few times.
Overthinking: Keep it simple—high = lots, low = little.

Why I Love It

It’s analyst practice without code—feels like the real deal. Shows my triage game!

Snap Wireshark’s “tcp.port == 22” filter with hits—save as “screenshot.
