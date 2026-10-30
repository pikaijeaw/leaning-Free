# Lesson 8. Timers That Fire

**Listen:** timers-that-fire.mp3 (2 min)

**The idea, in three lines**
- A systemd timer is two units with the same name: `backup.service` says what to run, `backup.timer` says when.
- Enable the `.timer`, not the `.service`. If `systemctl list-timers` shows NEXT as `n/a`, the timer is loaded but not armed and the job never fires.
- `Persistent=true` in the timer runs a missed job once after the next boot; cron would simply skip it.

**Impact:** scheduled jobs you set up actually run, survive a reboot, and log to the journal where you can prove it.

**Who says it:** 3 of the 7 pages on scheduling teach this; none disagree. Soft split on cron: centron frames timers as its replacement, while adminschoice and cronuru keep cron for simple one-line jobs. Red Hat's objectives list at, cron and systemd timer units, so practise all three.

**Try it** · Quick Win · 10 min
On a practice VM (Rocky Linux, AlmaLinux or RHEL), run `sudo -i` first so every command below runs as root:
> **1.** Create /etc/systemd/system/hello.service:
> ```
> [Unit]
> Description=Say hello
>
> [Service]
> Type=oneshot
> ExecStart=/usr/bin/echo hello
> ```
> **2.** Create /etc/systemd/system/hello.timer:
> ```
> [Unit]
> Description=Say hello every minute
>
> [Timer]
> OnCalendar=minutely
> Persistent=true
>
> [Install]
> WantedBy=timers.target
> ```
> **3.** `systemctl daemon-reload`, then `systemctl enable hello.timer`, then `systemctl start hello.timer`
> **4.** `systemctl list-timers`. The hello.timer row shows a real time under NEXT, not `n/a`.
> **5.** Wait a minute or two, then `journalctl -u hello.service`. You'll see `hello`.
> **6.** Clean up: `systemctl disable hello.timer`, `systemctl stop hello.timer`, delete both files, `systemctl daemon-reload`.

Notice the service has no [Install] section: there's nothing to enable on it.

No VM yet? On paper, write both files and circle the one you enable.

**Rule to keep**
Enable the .timer, never the .service.

**Skip** · no cost, no catch-up. Lesson 9 is just lesson 9.

**Go deeper (optional)**
- Timers step by step, including the n/a trap: https://www.centron.de/tutorials/systemd-timers-instead-of-cron
- When to keep cron, and Persistent=true: https://adminschoice.com/systemd-timers-vs-cron/
- OnCalendar syntax and checking it: https://cronuru.com/guides/systemd-timers
