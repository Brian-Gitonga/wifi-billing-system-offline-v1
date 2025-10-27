# Qtro ISP - MikroTik Hotspot Management System

![Version](https://img.shields.io/badge/version-1.00-blue.svg)
![License](https://img.shields.io/badge/license-GPLv2-green.svg)
![PHP](https://img.shields.io/badge/PHP-5.6%2B-purple.svg)

## 📋 Overview

**Qtro ISP** is a powerful web-based management system designed for managing MikroTik routers and generating WiFi vouchers for hotspot services. This application allows ISP operators and hotspot providers to easily manage their MikroTik infrastructure through an intuitive web interface.

### Key Features

- ✅ **Multi-Router Management** - Add and manage multiple MikroTik routers from a single interface
- 🎫 **WiFi Voucher Generation** - Create and print customizable WiFi vouchers with QR codes
- 👥 **Hotspot User Management** - Create, edit, and monitor hotspot users
- 📊 **Real-time Monitoring** - Monitor active connections, traffic, and system resources
- 💰 **Sales & Reporting** - Track sales, generate reports, and export data
- 🎨 **Customizable Voucher Templates** - Design your own voucher templates with logo support
- 🌐 **Multi-language Support** - Available in multiple languages
- 🎨 **Multiple Themes** - Choose from various themes including dark mode
- 📱 **Responsive Design** - Works on desktop, tablet, and mobile devices

---

## 🚀 Installation Guide

Since this application requires a PHP server and there is **no dedicated server setup**, you'll need to install a local PHP server environment on your computer.

### Prerequisites

- Windows, macOS, or Linux operating system
- At least 100MB of free disk space
- MikroTik router with API enabled
- Network access to your MikroTik router

### Step 1: Download and Install XAMPP

**XAMPP** is a free and easy-to-install PHP development environment that includes Apache web server, PHP, and MySQL.

1. **Download XAMPP:**
   - Visit: [https://www.apachefriends.org/](https://www.apachefriends.org/)
   - Download the version for your operating system (Windows/Mac/Linux)
   - Recommended: PHP 7.4 or higher

2. **Install XAMPP:**
   - Run the downloaded installer
   - Follow the installation wizard
   - Install to default location (e.g., `C:\xampp` on Windows)
   - Select at minimum: Apache and PHP components

3. **Start XAMPP:**
   - Open XAMPP Control Panel
   - Click "Start" next to **Apache**
   - Wait until Apache shows "Running" status

### Step 2: Install Qtro ISP

1. **Extract Qtro ISP files:**
   - Extract the Qtro ISP package
   - Copy the `mikhmon` folder to XAMPP's `htdocs` directory
     - Windows: `C:\xampp\htdocs\`
     - Mac: `/Applications/XAMPP/htdocs/`
     - Linux: `/opt/lampp/htdocs/`

2. **Set Permissions (Linux/Mac only):**
   ```bash
   chmod -R 755 /opt/lampp/htdocs/mikhmon
   chmod -R 777 /opt/lampp/htdocs/mikhmon/include
   ```

### Step 3: Access Qtro ISP

1. **Open your web browser**
2. **Navigate to:**
   ```
   http://localhost/mikhmon/admin.php
   ```

3. **Default Login Credentials:**
   - **Username:** `qtro_isp`
   - **Password:** `icel`
   
   ⚠️ **Important:** Change these credentials immediately after first login!

---

## ⚙️ Configuration Guide

### Adding Your First Router

1. **Login to Qtro ISP** using the default credentials

2. **Navigate to Sessions/Settings:**
   - Click on the **Settings** icon or menu
   - Click **"Add New Router"** or similar option

3. **Configure Router Connection:**
   
   Fill in the following information:
   
   | Field | Description | Example |
   |-------|-------------|---------|
   | **Session Name** | A friendly name for this router | `MyHotspot` or `Office-Router` |
   | **IP MikroTik** | IP address of your MikroTik router | `192.168.88.1` or `10.5.50.1` |
   | **Username** | MikroTik admin username | `admin` |
   | **Password** | MikroTik admin password | Your router password |
   | **Hotspot Name** | Name of your hotspot service | `MyWiFi Hotspot` |
   | **DNS Name** | DNS name for hotspot | `mywifi.local` |
   | **Currency** | Currency symbol for pricing | `$`, `Rp`, `KSh`, etc. |

4. **Enable MikroTik API:**
   
   Before connecting, ensure the API is enabled on your MikroTik router:
   
   - Login to your MikroTik router (via Winbox or WebFig)
   - Go to **IP → Services**
   - Find **API** service
   - Ensure it's **enabled** and note the port (default: 8728)
   - If disabled, double-click and check "Enabled"

5. **Test Connection:**
   - Click **"Save"** or **"Connect"**
   - If successful, you'll see **"Connected"** status in green
   - If failed, verify:
     - Router IP is correct and reachable
     - Username and password are correct
     - API service is enabled on MikroTik
     - No firewall blocking port 8728

---

## 🎫 Generating WiFi Vouchers

### Quick Start Guide

1. **Select Your Router Session:**
   - From the dashboard, select the router session you configured

2. **Create User Profiles (Optional but Recommended):**
   - Go to **Hotspot → User Profiles**
   - Click **"Add Profile"**
   - Configure:
     - Profile name (e.g., `1Hour`, `1Day`, `1Week`)
     - Speed limit (e.g., `2M/2M` for 2Mbps)
     - Session timeout
     - Data limit (optional)
   - Click **Save**

3. **Generate Vouchers:**
   - Go to **Hotspot → Generate Vouchers** or **Voucher** menu
   - Select or configure:
     - **User Profile:** Choose from your created profiles
     - **Number of Vouchers:** How many vouchers to generate
     - **Prefix:** Optional prefix for usernames
     - **Character Length:** Length of random password
     - **Validity:** How long the voucher is valid
   - Click **"Generate"**

4. **Print Vouchers:**
   - After generation, click **"Print"** or **"Preview"**
   - Vouchers will include:
     - Username and Password
     - QR Code for easy connection
     - Validity period
     - Your custom logo (if uploaded)
   - Print directly or save as PDF

### Customizing Voucher Templates

1. **Go to Voucher Template Editor:**
   - Navigate to **Voucher → Template Editor**

2. **Customize Design:**
   - Edit HTML/CSS template
   - Add your logo
   - Adjust colors, fonts, and layout
   - Preview changes in real-time

3. **Upload Logo:**
   - Go to **Settings → Upload Logo**
   - Upload your company logo (PNG recommended)
   - Logo will appear on all vouchers

---

## 📱 Main Features Explained

### 1. Dashboard
- Real-time system resource monitoring
- Active users count
- Traffic statistics
- Quick access to common functions

### 2. Hotspot Management
- **Users:** Add, edit, delete, and monitor hotspot users
- **Active Users:** View currently connected users
- **User Profiles:** Create reusable user profiles with speed/time limits

### 3. PPP Management
- Manage PPPoE, PPTP, L2TP connections
- Create PPP secrets and profiles
- Monitor active PPP sessions

### 4. Voucher System
- Generate bulk vouchers
- Customizable templates
- QR code generation
- Print-ready format

### 5. Reports
- User logs and history
- Sales reports
- Data usage reports
- Export to CSV/Excel

### 6. Traffic Monitor
- Real-time traffic graphs
- Interface monitoring
- Bandwidth usage statistics

### 7. Network Tools
- DHCP lease management
- ARP table viewer
- System resource monitor

---

## 🔧 Troubleshooting

### Cannot Access Qtro ISP

**Problem:** Browser shows "This site can't be reached"

**Solutions:**
- Ensure XAMPP Apache is running (green in XAMPP Control Panel)
- Check the URL: `http://localhost/mikhmon/admin.php`
- Try `http://127.0.0.1/mikhmon/admin.php`
- Restart Apache from XAMPP Control Panel

### Cannot Connect to MikroTik Router

**Problem:** Shows "Not Connected" in red

**Solutions:**
1. **Verify Router IP:**
   - Ping the router: `ping 192.168.88.1`
   - Ensure your computer can reach the router

2. **Check API Service:**
   - Login to MikroTik
   - Go to IP → Services
   - Enable API service (port 8728)

3. **Verify Credentials:**
   - Double-check username and password
   - Try logging in via Winbox with same credentials

4. **Firewall Rules:**
   - Check if MikroTik firewall blocks API port
   - Temporarily disable firewall to test

### Vouchers Not Generating

**Problem:** Error when generating vouchers

**Solutions:**
- Ensure you're connected to the router
- Check if user profile exists
- Verify hotspot server is configured on MikroTik
- Check PHP error logs in `xampp/apache/logs/error.log`

---

## 🔒 Security Recommendations

1. **Change Default Password:**
   - Go to **Settings → Admin Settings**
   - Change default username and password immediately

2. **Secure Your MikroTik:**
   - Use strong passwords
   - Limit API access to trusted IPs
   - Keep RouterOS updated

3. **XAMPP Security:**
   - Don't expose XAMPP to the internet
   - Use only on local network
   - For production, use proper web hosting

4. **Regular Backups:**
   - Backup `mikhmon/include/config.php` regularly
   - Export user data periodically

---

## 📞 Support & Resources

- **Original Author:** Laksamadi Guko
- **License:** https://qtroispman.co.ke
- **API Library:** [routeros-api](https://github.com/BenMenking/routeros-api)
- **Website:** https://qtroispman.co.ke

---

## 📝 System Requirements

### Minimum Requirements:
- **PHP:** 5.6 or higher (7.4+ recommended)
- **Web Server:** Apache 2.4+
- **Browser:** Modern browser (Chrome, Firefox, Safari, Edge)
- **MikroTik RouterOS:** 6.x or higher
- **RAM:** 512MB minimum
- **Disk Space:** 100MB

### Recommended:
- **PHP:** 7.4 or 8.0
- **RAM:** 1GB or more
- **SSD Storage** for better performance

---

## 🎯 Quick Tips

- **Backup Regularly:** Always backup your configuration before making changes
- **Test First:** Test voucher generation with small batches first
- **Monitor Resources:** Keep an eye on router CPU and memory usage
- **Update Profiles:** Create different profiles for different customer tiers
- **Use QR Codes:** Enable QR codes for easier customer connection
- **Custom Branding:** Upload your logo for professional-looking vouchers

---

## 📄 License

This project is licensed under the GNU General Public License v2.0 (GPLv2).

Copyright © 2025 Brian Gitonga Mwiti

---

**Enjoy using Qtro ISP! 🚀**

For questions and support, please refer to the official documentation or community forums.

