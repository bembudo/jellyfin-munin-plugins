# Munin Plugin: Jellyfin Active Clients

This is a Munin plugin written in Ruby that tracks the number of unique active Jellyfin clients currently playing media.

## 📊 What It Does

Polls your Jellyfin server's `/Sessions` endpoint every 5 minutes and displays the number of unique users who are actively playing something.

## 🧰 Requirements

- Ruby (built-in libraries only; no gems required)
- Munin node
- Jellyfin server with API key

## ⚙️ Installation

1. Copy the plugin to Munin's plugin directory:
   ```bash
   sudo cp jellyfin_active_clients /etc/munin/plugins/
   sudo chmod +x /etc/munin/plugins/jellyfin_active_clients
```

2. Edit the script and set:
 
    ruby
 
    CopyEdit
 
```
     server_url = "http://localhost:8096 
     api_key = "YOUR_JELLYFIN_API_KEY
```
 
3. Restart the Munin node:
 
    CopyEdit
 
```
    sudo systemctl restart munin-node
```
 
4. Verify:
 
    CopyEdit
 
```
    munin-run jellyfin_active_clients
```
 

## 🧪 Output Example

`active_users.value 1`
