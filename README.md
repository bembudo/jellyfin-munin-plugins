
## 📊 What It Does

Polls your Jellyfin server's `/Sessions` endpoint every 5 minutes and displays the number of unique users who are actively playing something.

---

## 🧰 Requirements

- Ruby (uses only built-in libraries; no gems required)
- Munin node
- Jellyfin server with an API key

---

## ⚙️ Installation

1. **Copy the plugin to Munin's plugin directory:**
   ```bash
   sudo cp jellyfin_active_clients /etc/munin/plugins/
   sudo chmod +x /etc/munin/plugins/jellyfin_active_clients
   ```

2. **Edit the script and set your server and API key:**
   ```ruby
   server_url = "http://localhost:8096"
   api_key = "YOUR_JELLYFIN_API_KEY"
   ```

3. **Restart the Munin node:**
   ```bash
   sudo systemctl restart munin-node
   ```

4. **Verify that it's working:**
   ```bash
   munin-run jellyfin_active_clients
   ```

---

## 🧪 Output Example

```text
active_users.value 1
```
This indicates that 1 unique Jellyfin user is currently playing something.
