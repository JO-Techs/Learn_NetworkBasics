# Module 15: Wireless Security and Encryption Protocols

## 📡 Introduction to Wireless Security
Wireless security is crucial to protect data transmission over Wi-Fi networks from unauthorized access, eavesdropping, and attacks. Unlike wired networks, wireless communications are more vulnerable due to their broadcast nature. This module explores wireless security threats and encryption protocols to secure wireless networks.

---

## 🚨 Common Wireless Security Threats

### 1️⃣ **Unauthorized Access & Rogue APs**
- Attackers set up rogue access points (APs) to trick users into connecting, allowing them to intercept data.
- Example: A hacker creates a fake Wi-Fi network called "Free_Public_WiFi" in an airport to steal login credentials.

### 2️⃣ **Eavesdropping & Packet Sniffing**
- Wireless data can be intercepted by attackers using packet sniffing tools like Wireshark.
- Example: An attacker captures unencrypted login credentials sent over an open Wi-Fi network.

### 3️⃣ **Denial-of-Service (DoS) Attacks**
- Attackers flood the wireless network with deauthentication frames, disconnecting users.
- Example: Using a tool like "MDK3" to launch a deauthentication attack on a corporate Wi-Fi network.

### 4️⃣ **Man-in-the-Middle (MITM) Attacks**
- Attackers intercept and manipulate traffic between a user and the network.
- Example: ARP spoofing on a public Wi-Fi network to redirect traffic through an attacker's device.

### 5️⃣ **Wi-Fi Protected Setup (WPS) Attacks**
- Exploiting vulnerabilities in WPS to retrieve Wi-Fi passwords using brute-force tools like "Reaver."
- Example: A hacker gains access to a home network by exploiting WPS vulnerabilities.

---

## 🔒 Wireless Encryption Protocols
Encryption protocols secure wireless communication by scrambling data to prevent unauthorized access.

### 🔹 **Wired Equivalent Privacy (WEP) (⚠️ Weak)**
- Uses RC4 encryption but is highly vulnerable due to weak key management.
- Can be cracked within minutes using tools like "aircrack-ng."

### 🔹 **Wi-Fi Protected Access (WPA) (🔄 Improved)**
- Introduced TKIP encryption, which improved security but is still vulnerable to certain attacks.

### 🔹 **Wi-Fi Protected Access 2 (WPA2) (🔐 Strong)**
- Uses AES encryption (CCMP mode) for better security.
- Vulnerable to brute-force and KRACK (Key Reinstallation Attack).

### 🔹 **Wi-Fi Protected Access 3 (WPA3) (🛡️ Strongest)**
- Uses Simultaneous Authentication of Equals (SAE) for protection against brute-force attacks.
- Provides forward secrecy and improved encryption.

---

## 🔧 Best Practices for Securing Wireless Networks

### ✅ **Use Strong Encryption**
- Always use WPA3 or WPA2 with AES encryption.
- Disable WEP and WPA-TKIP due to known vulnerabilities.

### ✅ **Change Default Credentials**
- Change the default SSID and router admin credentials.

### ✅ **Disable WPS**
- WPS is vulnerable to brute-force attacks; disable it in router settings.

### ✅ **Enable MAC Address Filtering**
- Restrict access to known devices by using MAC filtering.

### ✅ **Use VPN on Public Wi-Fi**
- Encrypt traffic using a VPN when accessing open networks.

### ✅ **Keep Firmware Updated**
- Regularly update router firmware to patch security vulnerabilities.

---

## 🛠️ Tools for Wireless Security Testing
- **Wireshark** - Packet sniffing tool to analyze wireless traffic.
- **Aircrack-ng** - Suite for testing WEP/WPA vulnerabilities.
- **Reaver** - WPS attack tool.
- **Kismet** - Wireless network detection and monitoring.
- **MDK3** - Deauthentication and DoS attack tool.

---

## 🏁 Conclusion
Wireless security is essential for protecting data against cyber threats. By implementing strong encryption, following best practices, and staying aware of potential attacks, individuals and organizations can secure their wireless networks effectively.

🚀 Stay safe, stay secure! 🔒
