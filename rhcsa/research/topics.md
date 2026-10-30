# Topics: RHCSA (EX200), beginner

Shaped by Red Hat's official EX200 study points (au.redhat.com/training/courses/ex200/, RHEL 10 era): hands-on exam, no internet, man pages allowed, everything must persist after reboot.

- T01 Exam format and how people prepare (hands-on, persistence, time, man pages, labs)
- T02 Essential tools: shell, redirection, grep/regex, ssh, tar/gzip, links, finding documentation (man, /usr/share/doc)
- T03 Standard permissions: ugo/rwx, chmod/chown, umask (default permissions)
- T04 Special permissions and ACLs: setuid, setgid, sticky bit, setfacl/getfacl
- T05 Users, groups and privileged access: useradd/usermod, password aging (chage), sudo/wheel
- T06 Software: dnf, RPM repositories (.repo files), Flatpak
- T07 Shell scripts: if/test, for loops, $1 $2, command output
- T08 Boot process and targets: systemctl set-default, rescue/emergency, GRUB edits
- T09 Interrupting boot to reset the root password (rd.break, init=/bin/bash, autorelabel)
- T10 Processes, tuning and logs: top/kill, nice, tuned profiles, journalctl, persistent journal
- T11 Services and scheduling: systemctl enable --now, cron, at, systemd timers
- T12 Local storage: GPT partitions, LVM (PV/VG/LV), extend, swap
- T13 File systems and mounting: mkfs (xfs/ext4/vfat), /etc/fstab by UUID, mount -a
- T14 Network file systems: NFS mounts, autofs (indirect maps, wildcards)
- T15 Networking: nmcli static IPv4/IPv6, hostname, name resolution
- T16 Firewall: firewalld zones, services, ports, --permanent and --reload
- T17 SELinux: modes, contexts, semanage fcontext + restorecon, booleans, port labels
- T18 SSH keys and time sync (chrony)
