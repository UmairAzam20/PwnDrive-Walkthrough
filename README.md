# PwnDrive-Walkthrough
Penetration testing walkthrough for PwnDrive machine
# PwnDrive - 10.150.150.11 Walkthrough

## 📋 Machine Information
- **Target IP:** 10.150.150.11
- **OS:** Windows Server 2008 R2
- **Difficulty:** Easy
- **Goal:** Capture the flag

## 🔍 Reconnaissance

First, I scanned the target to find open ports:

```bash
nmap -sV -sC -Pn 10.150.150.11 -oN pwndrive_scan.txt

PORT      STATE SERVICE       VERSION
21/tcp    open  ftp           Xlight ftpd 3.9
80/tcp    open  http          Apache 2.4.46
443/tcp   open  ssl/http      Apache 2.4.46
445/tcp   open  microsoft-ds  Windows Server 2008 R2
1433/tcp  open  ms-sql-s      SQL Server 2012
3306/tcp  open  mysql         MariaDB 10.4.14
3389/tcp  open  ms-wbt-server Microsoft Terminal Service

## 🕵️ Enumeration
I ran directory brute-forcing on port 80:
