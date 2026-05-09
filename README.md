<p align="center">
<img width="598" height="244" alt="osticket lifecycle" src="https://github.com/user-attachments/assets/4e4f13e8-b0f8-4f06-9fd0-9abe2097762d" />
</p>

<h1>osTicket — Ticket Lifecycle: Creation, Assignment, and Resolution</h1>
This project demonstrates the full lifecycle of a help desk ticket inside osTicket — from submission by an end user, through triage and assignment by a help desk agent, to final resolution. It simulates real-world IT support scenarios using the roles, departments, and SLAs configured in the previous project.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines / Compute)
- Remote Desktop Protocol (RDP)
- Internet Information Services (IIS)
- osTicket v1.15.8

<h2>Operating System Used</h2>

- Windows 10 Pro (21H2)

<h2>High-Level Steps</h2>

1. Prepare department settings
2. Submit a ticket as an end user
3. Triage and assign the ticket as a help desk agent
4. Resolve the ticket as the assigned agent
5. Observe access control and ticket visibility rules

---

<h2>Step 1 — Prepare Department Settings</h2>

<p>
<img width="961" height="359" alt="image" src="https://github.com/user-attachments/assets/3e06ef7a-94bb-4bf7-85ff-058c9278e0fd" />
</p>
<p>
Before starting the ticket lifecycle, I made two changes in the Admin Panel. I promoted the <strong>SysAdmins</strong> department to a Top-Level Department, giving it visibility over all tickets. I also fully deleted the <strong>Maintenance</strong> department (not archived) to keep the environment clean for this demonstration.
</p>
<br />

---

<h2>Step 2 — Submit a Ticket as an End User</h2>

<p>
<img width="961" height="966" alt="image" src="https://github.com/user-attachments/assets/0203ec49-af33-409c-8bae-d412fbdf7b41" />
</p>
<p>
Logging in as end user <strong>Karen</strong>, I submitted a new ticket with the following details:

- <strong>Help Topic:</strong> Business Critical Outage
- <strong>Subject:</strong> Entire mobile/online banking system is down
- <strong>Description:</strong> Users across the organization are unable to access online or mobile banking services

This simulates a high-priority ticket coming in from a frustrated end user reporting a system-wide outage.
</p>
<br />

---

<h2>Step 3 — Triage the Ticket as Help Desk Agent John</h2>

<p>
<img width="960" height="184" alt="image" src="https://github.com/user-attachments/assets/0ae62e49-ab06-4d4a-b381-c5b5df64b797" />
</p>
<p>
Logging in as agent <strong>John</strong>, I opened the ticket and observed its default properties — no priority, no SLA, and no assigned agent. As first-line triage, I updated the ticket with the following:

| Property | Value |
|---|---|
| Priority | Emergency |
| SLA | Sev-A (1 hour, 24/7) |
| Department | SysAdmins |
| Assigned To | Jane |

After reassigning the ticket to the SysAdmins department, I attempted to view it again as John — the ticket was no longer visible, confirming that department-based access control is working correctly.
</p>
<br />

---

<h2>Step 4 — Resolve the Ticket as Agent Jane</h2>

<p>
<img width="1119" height="560" alt="image" src="https://github.com/user-attachments/assets/6c21bd30-e0d2-4ae2-8b75-2415610cdbca" />
</p>
<p>
Logging in as agent <strong>Jane</strong> (SysAdmins department), I could see the escalated ticket in my queue. I reviewed the issue, added internal notes documenting the troubleshooting steps taken, and posted a reply to the user confirming resolution. I then changed the ticket status to <strong>Resolved</strong>, closing it out.
</p>
<br />

---

<h2>Step 5 — Ticket Access Control Observations</h2>

<p>
This exercise demonstrated how osTicket enforces visibility rules based on department assignment. Key observations:

- Tickets assigned to SysAdmins were hidden from Support agents like John
- Only agents within the assigned department or with Supreme Admin role could view and modify escalated tickets
- SLA timers begin the moment a ticket is created, making fast triage critical for Sev-A tickets
</p>
<br />

---

<h2>Real-World Intake Note</h2>

<p>
In a real help desk environment, tickets do not always arrive through the web portal. They may come in through phone calls, emails, chat platforms like Slack or Teams, or even in-person requests. Regardless of how the issue is reported, <strong>every action taken should be logged as a ticket</strong>. This ensures accurate metrics for response time, resolution rate, and agent workload — all of which are critical for IT reporting and performance reviews.
</p>
<br />

---

<h2>Conclusion</h2>

This project completed the full osTicket workflow across all three repositories:

| Project | Focus |
|---|---|
| osticket-prereqs | Installation and environment setup |
| osticket-config | System configuration and helpdesk structure |
| osticket-lifecycle | Live ticket creation, triage, and resolution |

Together these projects demonstrate a complete IT help desk deployment from infrastructure to daily operations.
</p>
