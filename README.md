Cyber-Alert-Triage
Every SOC analyst deals with the same problem — too many alerts, not enough time, and most of them are noise. This project is my hands-on way of practicing exactly that: taking a pile of alerts and figuring out what actually matters.

No complex code. Just the mindset and tools that make a real analyst useful.

Why I Built This
Working as a Cybersecurity Analyst, I learned fast that the hardest skill is not detecting threats — it is knowing which ones to act on first. Alert fatigue is real. This project simulates that pressure in a controlled way so I could sharpen my triage thinking outside of work hours.


What It Does
Simulates a small alert queue — the kind you would see in a real SOC environment — and walks through how to investigate, prioritize, and document each one using free tools anyone can access.


Tools Used
Wireshark — network traffic capture and analysis
Windows Event Viewer — login and system event monitoring
Notepad / any text editor — incident logging and documentation


The Triage Process
Step 1 — Create the Alert Queue
Built a simple alerts.txt file to simulate incoming alerts:
User: raj, 5 login failures, 10:00 AM
Port 22, 100 connection attempts, 10:05 AM
Port 80, 3 requests, 10:10 AM
These represent the kind of events that would come through a SIEM in a real environment.


Step 2 — Investigate Network Activity
Opened Wireshark, started a capture on the active interface, then filtered for suspicious traffic: tcp.port == 22
High volume on Port 22 in a short window is a red flag — could indicate brute force or unauthorized SSH attempts.
Exported findings to network.txt for documentation.


Step 3 — Check Authentication Events
Opened Windows Event Viewer → Windows Logs → Security
Looked for Event ID 4625 — failed login attempts. Cross-referenced timestamps with the alert queue to see if login failures correlated with the network activity.


Step 4 — Prioritize and Document
Updated alerts.txt with triage decisions:
Port 22 — 100 hits in 60 seconds — HIGH (potential brute force, escalate)
Port 80 — 3 hits — LOW (normal web traffic, monitor only)
User: raj — 5 login fails — LOW (user error, no escalation needed)
This mirrors the documentation process I follow professionally — clear, concise, and actionable for whoever picks it up next.


What I Learned
How to separate genuine threats from background noise quickly
The importance of correlating multiple data sources before making a call

How to document triage decisions clearly so the next analyst understands your reasoning
That 90% of alerts are low priority — but that 10% matters a lot.

How to Run It Yourself
Download Wireshark from wireshark.org
Create an alerts.txt file with your simulated events
Run a Wireshark capture and apply port filters
Open Event Viewer and review Security logs
Document your triage calls and reasoning
No coding required. Just your machine and your analytical thinking.

€cho_Connect_with_me:LinkedIn: linkedin.com/in/rajesh-rathlavathu23
Portfolio: Richierich69696.github.io
GitHub: github.com/Richierich69696
