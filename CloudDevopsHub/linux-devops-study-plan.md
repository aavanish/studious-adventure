# Linux for DevOps — 4-Week Focused Study Plan

**Goal:** Be interview-ready and job-confident on the Linux fundamentals that actually come up in DevOps roles — not "know all of Linux."

**Format:** Each week has a theory block (a few hours) + a hands-on scenario (do this yourself, don't just read). Use a free VM (VirtualBox, or a $5 DigitalOcean droplet, or WSL2) — reading commands isn't the same as typing them.

---

## Week 1 — File system, permissions, users

### Learn
- Filesystem Hierarchy Standard: what lives in `/etc`, `/var`, `/usr`, `/opt`, `/tmp`
- `chmod`, `chown`, `chgrp` — symbolic (`u+x`) and octal (`755`) notation
- Users, groups, `/etc/passwd`, `/etc/shadow`, `sudo` vs `su`
- Hard links vs symlinks, and why they matter for deployments

### Practice scenario
> You're deploying an app that needs to write logs to `/var/log/myapp/`, but only the `deploy` user and `myapp` service account should have write access; everyone else should read-only.

Build it: create the users/group, create the directory, set ownership and permissions so it actually enforces that — then verify by trying to write as a different user and watching it fail.

### Self-check
- [ ] Can explain the difference between `755` and `750` without a calculator
- [ ] Can explain what SUID/SGID do and give one real example (e.g. `passwd`)
- [ ] Can find "who owns this file and why can't user X write to it" in under a minute

---

## Week 2 — Processes, systemd, and services

### Learn
- `ps`, `top`/`htop`, `kill`, signals (`SIGTERM` vs `SIGKILL`)
- systemd unit files: `[Unit]`, `[Service]`, `[Install]` sections
- `systemctl status/start/stop/enable/restart`, `journalctl -u`, `journalctl -f`
- Runlevels/targets conceptually (you won't be quizzed deeply, but know what they are)

### Practice scenario
> You have a small Python or Node script that should run as a background service, restart automatically if it crashes, and start on boot.

Write the actual `.service` file, install it, kill the process manually and watch systemd restart it, then check `journalctl` to see the restart logged.

### Self-check
- [ ] Can write a working unit file from memory (not copy-paste)
- [ ] Can explain `Restart=on-failure` vs `Restart=always`
- [ ] Can debug "my service won't start" using `journalctl -u <service> -n 50`

---

## Week 3 — Networking basics + troubleshooting

### Learn
- `ss -tulnp` (what's listening on what port), `curl -v`, `dig`/`nslookup`
- Basic routing: `ip route`, default gateway concept
- SSH: key-based auth, `~/.ssh/config`, port forwarding (`-L`)
- Firewalls: `ufw` or `iptables` basics — allow/deny a port

### Practice scenario
> A teammate says "I deployed the app but I can't reach it on port 8080 from outside the server."

Simulate it: run a simple web server on a port, then deliberately misconfigure the firewall so it's blocked externally. Practice the actual diagnostic sequence: is it listening (`ss`)? Is it reachable locally (`curl localhost:8080`)? Is the firewall blocking it? Is a security group/cloud-level rule blocking it?

### Self-check
- [ ] Can list the diagnostic steps for "can't connect" in order, out loud, without notes
- [ ] Can set up SSH key auth and disable password login
- [ ] Can explain what a reverse proxy is and why you'd put nginx in front of an app

---

## Week 4 — Shell scripting, monitoring, and packages

### Learn
- Bash scripting: variables, conditionals, loops, exit codes, `$?`
- Text processing: `grep`, `awk`, `sed`, `jq` for JSON logs
- Disk/resource monitoring: `df -h`, `du -sh`, `free -h`, log rotation (`logrotate`)
- Package management: `apt`/`yum`, adding repos, checking installed versions

### Practice scenario
> Write a script that checks disk usage every hour, and if any partition is above 85% full, appends a warning to a log file and prints an alert message (pretend this would email/Slack in a real system).

This is one of the most common "show me you can script" interview asks. Make it actually robust: handle the case where `df` output format varies, use proper exit codes, add comments.

### Self-check
- [ ] Can write this script in under 15 minutes without looking anything up
- [ ] Can explain how you'd turn this into a cron job vs a systemd timer, and why you'd pick one over the other
- [ ] Can parse a JSON log line for a specific field using `jq` from memory

---

## After week 4: tie it together

Pick **one mini-project** that forces you to use everything above at once — this is what you'll actually talk about in interviews:

> Spin up a VM. Deploy a simple app as a systemd service, running as a dedicated non-root user with locked-down permissions. Put it behind a firewall rule that only allows your IP. Write a monitoring script that checks the service is alive and logs to a file. Document the whole thing in a README as if handing it to a teammate.

That project becomes your interview story: "I set up X, secured it with Y, and monitored it with Z" is exactly what a DevOps interviewer wants to hear — much stronger than reciting commands.

---

## Interview-prep note

Given your Capgemini background, frame your answers around **what you already did** plus **what you deliberately upskilled** — e.g. "I worked with Linux environments in production support at Capgemini, and over the past month I've gone deeper into systemd, scripting, and networking troubleshooting specifically to strengthen the DevOps side." That's a credible, honest narrative interviewers respond well to.
