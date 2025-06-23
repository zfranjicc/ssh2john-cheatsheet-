# ssh2john-cheatsheet-
Commands for Key Attack SSH

# 🧨 SSH2John Cheat Sheet
Personal cheat sheet with ssh2john commands used in CTFs, pentesting, and red teaming.

---

## 🛠️ Basic Commands

| Command | Description |
|---------|-------------|
| `ssh2john [private_key_file] > [output_file]` | Extract hash from SSH private key to a file |
| `ssh2john id_rsa > id_rsa_hash.txt` | Extract hash from `id_rsa` to `id_rsa_hash.txt` |
| `python3 /usr/share/john/ssh2john.py id_rsa > id_rsa_hash.txt` | Use python script to extract hash (Kali Linux, TryHackMe) |
| `python3 /opt/john/ssh2john.py id_rsa > id_rsa_hash.txt` | Use python script on TryHackMe AttackBox |

---

## 🔐 Cracking the SSH Key Password

| Command | Description |
|---------|-------------|
| `john --wordlist=/usr/share/wordlists/rockyou.txt id_rsa_hash.txt` | Crack the extracted hash using John the Ripper with wordlist |

---

## 🎯 Practical Example

```bash
cd ~/John-the-Ripper-The-Basics/Task11/
python3 /opt/john/ssh2john.py id_rsa > id_rsa_hash.txt
john --wordlist=/usr/share/wordlists/rockyou.txt id_rsa_hash.txt
