# Arch Linux Full Security Inspection

This guide provides a structured approach to performing a full security inspection on an Arch Linux system.

---

## 1. Update and Verify System Integrity

1. **Update your system:**

```bash
sudo pacman -Syu
```

2. **Check for orphaned packages (unused dependencies):**

```bash
pacman -Qdt
```

Remove them if unnecessary:

```bash
sudo pacman -Rns $(pacman -Qdtq)
```

3. **Verify package integrity with pacman:**

```bash
sudo pacman -Qk
```

This checks if files installed by packages are missing or modified.

---

## 2. Security Tools to Install

* **Lynis (general security auditing):**

```bash
sudo pacman -S lynis
sudo lynis audit system
```

* **Chkrootkit (rootkit scanner):**

```bash
sudo pacman -S chkrootkit
sudo chkrootkit
```

* **Rkhunter (rootkit & malware scan):**

```bash
sudo pacman -S rkhunter
sudo rkhunter --update
sudo rkhunter --check
```

* **ClamAV (antivirus):**

```bash
sudo pacman -S clamav
sudo freshclam
sudo clamscan -r --bell -i /
```

---

## 3. System Configuration & Hardening

1. **Check open ports:**

```bash
ss -tulpn
```

2. **Firewall setup (ufw):**

```bash
sudo pacman -S ufw
sudo systemctl enable --now ufw
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
```

3. **Fail2ban (brute force protection):**

```bash
sudo pacman -S fail2ban
sudo systemctl enable --now fail2ban
```

4. **Check SUID/SGID binaries (potential privilege escalation risks):**

```bash
find / -perm -4000 -o -perm -2000 -type f 2>/dev/null
```

5. **Audit users and groups:**

```bash
cat /etc/passwd
cat /etc/group
```

6. **Check system logs for anomalies:**

```bash
journalctl -p err -b
```

---

## 4. Intrusion Detection & Monitoring

* **Auditd (audit framework):**

```bash
sudo pacman -S audit
sudo systemctl enable --now auditd
ausearch -m avc,user_avc,selinux
```

* **Tripwire (file integrity checker):**

```bash
yay -S tripwire
```

* **Check last logins & failed attempts:**

```bash
last -a
lastb
```

---

## 5. Optional Extras

* **Kernel hardening:** Install `linux-hardened` kernel:

```bash
sudo pacman -S linux-hardened
```

* **Enable AppArmor or SELinux** for Mandatory Access Controls (MAC).
* **Encrypt sensitive partitions** with LUKS if not already.

---

Follow this guide step by step to perform a comprehensive security audit of your Arch Linux system.
