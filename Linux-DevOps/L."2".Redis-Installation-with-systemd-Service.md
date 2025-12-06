
## Manual Redis Installation & systemd Service Setup on RHEL 9 / AlmaLinux 9

This guide explains how to **manually install Redis from source** and configure it as a **systemd service** on RHEL 9 or compatible distributions.

---

### 📦 Step 1: Install Build Tools and Dependencies

```bash
sudo dnf groupinstall "Development Tools" -y
sudo dnf install gcc make jemalloc-devel tcl -y
```

---

### 🚀 Step 2: Download and Compile Redis

```bash
cd /usr/local/src
sudo curl -O https://download.redis.io/releases/redis-7.2.4.tar.gz
sudo tar xzf redis-7.2.4.tar.gz
cd redis-7.2.4
sudo make
sudo make install
```

This installs Redis binaries like:
- `/usr/local/bin/redis-server`
- `/usr/local/bin/redis-cli`

---

### 👤 Step 3: Create Redis User and Directories

```bash
sudo useradd -r -s /sbin/nologin redis
sudo mkdir -p /etc/redis /var/lib/redis
sudo chown redis:redis /var/lib/redis
sudo chmod 770 /var/lib/redis
```

---

### ⚙️ Step 4: Copy and Edit Redis Configuration

```bash
sudo cp redis.conf /etc/redis/
sudo nano /etc/redis/redis.conf
```

Modify or verify the following lines in `/etc/redis/redis.conf`:

```conf
supervised systemd
dir /var/lib/redis
```

---

### 🛠 Step 5: Create the systemd Service File

```bash
sudo nano /etc/systemd/system/redis.service
```

Paste the following content:

```ini
[Unit]
Description=Redis In-Memory Data Store
After=network.target

[Service]
User=redis
Group=redis
ExecStart=/usr/local/bin/redis-server /etc/redis/redis.conf
ExecStop=/usr/local/bin/redis-cli shutdown
Restart=always

ProtectSystem=full
ProtectHome=true
NoNewPrivileges=true
PrivateTmp=true

[Install]
WantedBy=multi-user.target
```

---

### 🔁 Step 6: Enable and Start Redis Service

```bash
sudo systemctl daemon-reload
sudo systemctl enable redis
sudo systemctl start redis
```

---

### ✅ Step 7: Test and Verify

Check if Redis is running:

```bash
systemctl status redis
```

Test Redis CLI:

```bash
redis-cli ping
# Output: PONG
```

Check logs:

```bash
journalctl -u redis
```

---

### 📋 Commands Summary

| Task              | Command                      |
|-------------------|------------------------------|
| Start Redis       | `systemctl start redis`      |
| Stop Redis        | `systemctl stop redis`       |
| Enable on boot    | `systemctl enable redis`     |
| Check Status      | `systemctl status redis`     |
| View Logs         | `journalctl -u redis`        |

---

### 🧠 Notes

- This process is ideal for manually installed Redis (e.g., from source).
- Adjust paths if Redis is installed elsewhere.
- Redis config must have `supervised systemd`.

---

Happy hacking! 🚀

