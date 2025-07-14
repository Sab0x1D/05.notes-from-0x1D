# VPN Status Checker

This is a lightweight GUI tool that helps you verify if your internet traffic is routed through a VPN or not — based on your real ISP identity.

No IP leaks, no DNS analysis — just a simple, user-defined check powered by [ipinfo.io](https://ipinfo.io/json).

---

## Features

✅ Shows your current external IP, ISP, and geolocation  
✅ Detects VPN usage by comparing your current ISP against your real one  
✅ Auto-refreshes every 2 minutes  
✅ Quick "Refresh Network" button (flush + renew IP)  
✅ Configurable ⚙️ **Settings** window to set your known ISP  
✅ Works silently — no console window  
✅ First-launch popup guides the user through setup

---

## How It Works

1. At first run, you’ll be asked to visit [ipinfo.io](https://ipinfo.io/json)
2. Copy the value of the `org` field (e.g., `AS136787 PacketHub S.A.` or `AS25697 Lightwave Networks`)
3. Paste it into **Settings > Real ISP**
4. The tool will monitor your current IP's ISP:
   - If it **matches your real ISP** → ❌ VPN is **not active**
   - If it **differs from your real ISP** → ✅ VPN is **active**

---
