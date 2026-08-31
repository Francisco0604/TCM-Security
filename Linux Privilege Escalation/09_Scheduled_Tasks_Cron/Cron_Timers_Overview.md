# 🛡️ Cron & Timers Overview

> **Course Track:** [Linux Privilege Escalation](../../README.md)  
> **Module:** [Scheduled tasks](./README.md)  
> **Topic Path:** `Linux Privilege Escalation > Scheduled tasks > Cron & Timers Overview`

---

## 🎯 Technical Overview & Objectives
This section covers the methodology, enumeration techniques, exploit mechanics, and defensive mitigations for **Cron & Timers Overview**.

---

## 🔬 Practical Notes, Commands & Proof of Exploit

My input
If get cron jobs which are executed every 5 mins or something try to put a malacious script in it and check if can escalate priv

Copied from meta
Cron
Cron is a time-based job scheduler in Linux that allows users to execute commands or scripts at specific intervals.
Key Features
1. Scheduled Tasks: Cron enables users to schedule tasks to run at specific times or intervals.1. Cron Daemon: The cron daemon runs in the background and checks for scheduled tasks.1. Crontab: Users can edit their crontab file to add, modify, or delete scheduled tasks.Crontab Syntax
The crontab syntax consists of five fields:
minute hour day month day_of_week command
Examples
1. Run a command every minute: * * * * * command1. Run a command every hour: 0 * * * * command1. Run a command daily at 2am: 0 2 * * * commandTimers
Timers are a systemd feature that allows users to schedule tasks to run at specific times or intervals.
Key Features
1. Systemd Integration: Timers are integrated with systemd, allowing for more flexibility and control.1. Persistent Timers: Timers can be set to run persistently, ensuring tasks are executed even if the system is rebooted.Examples
1. Create a timer file: sudo nano /etc/systemd/system/my_timer.timer1. Define the timer schedule: [Timer] OnUnitActiveSec=1hUse Cases
1. Automated Backups: Use cron or timers to schedule automated backups.1. System Maintenance: Schedule system maintenance tasks, such as disk cleanup or package updates.1. Report Generation: Use cron or timers to generate reports at specific intervals.Best Practices
1. Use Absolute Paths: Use absolute paths in cron jobs and timers to avoid issues.1. Log Output: Log output from cron jobs and timers for debugging and monitoring.1. Test Thoroughly: Test cron jobs and timers thoroughly to ensure they work as expected.


---

## 🛡️ Defensive Hardening & Remediation
- **Audit & Restrict Permissions:** Review `/etc/sudoers`, remove unnecessary SUID/SGID flags (`chmod u-s`), and enforce strict file ownership on configuration files.
- **Kernel Patching:** Regularly apply distribution security updates to mitigate known local privilege escalation (LPE) vulnerabilities.
- **Principle of Least Privilege:** Avoid running non-administrative daemon processes as `root` and isolate services using containers/namespaces.

---
[⬅ Back to Scheduled tasks](./README.md) • [🏠 Master Course Index](../README.md)
