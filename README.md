# 📅 Day 3 of Linux Challenge: Processes and Services

## 📸 Screenshot: day3-1.png
We started off by running the `ps` command after opening Firefox. While this command shows currently running processes by the user, it didn’t display the PID (Process ID) for Firefox.

---

## 📸 Screenshot: day3-2.png
Next, we ran `ps aux`, which displays all processes running on the system (including other users). Firefox still wasn’t listed clearly, which led us to a better approach.

---

## 📸 Screenshot: day3-4.png
We used the command `pgrep -a firefox` to find the exact PID for Firefox.  
To stop the process, we ran:

```bash
kill -9 [PID]
```

🔹 **Why use `-9`?**  
The `-9` flag sends the `SIGKILL` signal, which forcefully stops the process immediately. It’s a powerful option used when a process won’t close with normal methods.

---

## 📸 Screenshot: day3-5.png
To view all services running on the machine (including background ones), we used:

```bash
top
```

The output refreshes continuously and shows both active and sleeping processes.

---

## 📸 Screenshot: day3-6.png
For a more user-friendly, interactive version, we ran:

```bash
htop
```

It displays processes in color with an easy-to-navigate interface.  
- Use `F9` to kill a process  
- Use `F10` to quit the interface

---

## 📸 Screenshot: day3-7.png
We explored system services using:

```bash
systemctl
```

This command shows all services loaded on the system — including those that are active, inactive, or failed. These services are part of system-level operations.

---

## 📸 Screenshot: day3-8.png
To start the SSH service, we ran:

```bash
sudo systemctl start ssh
```

To confirm it's running:

```bash
sudo systemctl status ssh
```

If successful, the status will say **active (running)**.

---

## 📸 Screenshot: day3-9.png
To verify SSH is open and listening on the right port (22), we scanned the localhost using:

```bash
nmap localhost
```

You should see **port 22 open**, which means the SSH service is up.

⚠️ **Important:** Leaving port 22 open for too long is a security risk. Always close it if not in use.

---

## 📸 Screenshot: day3-11.png
To stop SSH:

```bash
sudo systemctl stop ssh
```

Confirm with:

```bash
sudo systemctl status ssh
```

Then scan again with:

```bash
nmap localhost
```

To double-check that port 22 is closed, run:

```bash
nmap -p22 localhost
```

---

### 💡 Summary & Lesson Learned
Today we learned how to:
- Monitor and kill running processes using `ps`, `pgrep`, `kill`
- View services dynamically with `top` and interactively with `htop`
- Start and stop system services with `systemctl`
- Securely manage ports using `nmap`

By combining these tools, we’ve taken another big step toward understanding how Linux handles internal processes and services.