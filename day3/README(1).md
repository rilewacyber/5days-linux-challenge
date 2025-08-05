
# 🗓️ Day 3: Processes and Services

Today’s focus was on understanding how Linux handles running processes and background services. I explored commands that help manage and monitor these elements.

---

## 📸 Screenshots & Explanations

### 🔹 Screenshot: `day3-1.png`
- **Topic:** Using the `ps` command.
- I opened Firefox and ran the command `ps`. Surprisingly, the PID for Firefox wasn’t visible, prompting deeper exploration.

---

### 🔹 Screenshot: `day3-2.png`
- **Topic:** Using `ps aux`.
- This command lists all running processes. Although very detailed, Firefox still didn’t show up as expected, which led me to use a more specific command.

---

### 🔹 Screenshot: `day3-4.png`
- **Topic:** `pgrep -a firefox` and Killing a Process.
- This command successfully listed the Firefox process and its PID.
- To terminate it, I ran `kill -9 <PID>`.
- **Note:** The `-9` flag sends a SIGKILL signal, forcefully terminating the process regardless of its state. It’s stronger than a normal kill and should be used with caution.

---

### 🔹 Screenshot: `day3-5.png`
- **Topic:** Using `top`.
- This command shows all active processes and resource usage.
- These update frequently and display running and sleeping processes.

---

### 🔹 Screenshot: `day3-6.png`
- **Topic:** Using `htop`.
- `htop` offers a more interactive and colorful interface than `top`.
- You can use `F9` to kill processes or `F10` to quit.

---

### 🔹 Screenshot: `day3-7.png`
- **Topic:** Viewing All Services.
- The command `systemctl` displays all available services on the system.
- This includes both active and inactive units.

---

### 🔹 Screenshot: `day3-8.png`
- **Topic:** Starting and Checking SSH.
- To start SSH: `sudo systemctl start ssh`
- To confirm it’s running: `sudo systemctl status ssh`

---

### 🔹 Screenshot: `day3-9.png`
- **Topic:** Nmap Port Scan.
- Ran `nmap localhost` to see open ports. Port 22 (SSH) appeared as open.
- **Security Note:** Always close unnecessary open ports to reduce attack surface.

---

### 🔹 Screenshot: `day3-11.png`
- **Topic:** Stopping SSH.
- Ran `sudo systemctl stop ssh` and confirmed it with `systemctl status` and `nmap -p22 localhost` to ensure port 22 was closed.

---

## 📚 Lesson Learned

Be cautious when using `kill -9`, and always monitor which services you start — especially SSH — as leaving ports open can introduce vulnerabilities. Nmap is a helpful way to verify what’s exposed.

