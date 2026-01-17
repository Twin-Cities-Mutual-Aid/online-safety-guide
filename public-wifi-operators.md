---
title: The Small Business Guide to Securing Public Wifi
description: A practical guide for securing public Wifi networks, covering encryption, client isolation, DNS filtering, and maintenance.
---

## Securing Public Wifi

### Who is this for?

This guide is intended for operators of small business public Wifi networks—coffee shops, libraries, co-working spaces, and small offices—who want to provide connectivity to their guests without compromising their safety or the network's integrity.

### TL;DR: The 60-Second Security Checklist

If you only have five minutes,  **Post a sign**: "Public Wifi is never 100% safe" and then ensure these four settings are active on your router to prevent 99% of common attacks:

1.   **Enable Client Isolation:** Prevent guests from accessing each other's devices.
2.   **Set DNS to [Quad9](https://en.wikipedia.org/wiki/Quad9) (9.9.9.9):** Automatically block malware and phishing sites at the network level.
3.   **Disable WPS:** Turn off "[Wi-Fi Protected Setup](https://en.wikipedia.org/wiki/Wi-Fi_Protected_Setup)" to close a major security hole.
4.   **WPA2-AES or WPA3 Only:** Never use WEP or TKIP encryption.

### Highlights: What to do and Why

When setting up public Wifi networks, focus on these key outcomes:

*   **Ensure the encryption standard is modern.**
    *   *Goal:* Prevent attackers from easily cracking your network password.
    *   *Technical Detail:* Require a guest password so that traffic has at least some encryption over the air.
            Be sure to **Disable WPA1/WEP** and **Disable WPS (Wi-Fi Protected Setup).** These protocols are broken or easily exploited. **[WPA2](https://en.wikipedia.org/wiki/Wi-Fi_Protected_Access#WPA2)**, while standard, was released in 2004 and is aging; use **[WPA3](https://en.wikipedia.org/wiki/Wi-Fi_Protected_Access#WPA3)** if your hardware supports it, or strict WPA2-AES (Personal) at a minimum.

*   **Block known malicious sites and malware.**
    *   *Goal:* Prevent guests from inadvertently accessing sites known to host malware or phishing scams.
    *   *Technical Detail:* **Configure DNS Filtering.** Use a security-focused DNS provider like **[Quad9](https://en.wikipedia.org/wiki/Quad9) (9.9.9.9)** or **[OpenDNS Family Shield](https://en.wikipedia.org/wiki/OpenDNS)**. This automatically blocks access to dangerous domains.

*   **Keep guest devices separate.**
    *   *Goal:* Prevent a hacked laptop in your cafe from attacking the person sitting next to them.
    *   *Technical Detail:* **Enable Client Isolation (AP Isolation).** This prevents devices on the guest network from communicating directly with each other.

*   **Get agreement on Terms of Service.**
    *   *Goal:* Ensure users agree to your rules and prevent automated bots from using your bandwidth.
    *   *Technical Detail:* **Use a [Captive Portal](https://en.wikipedia.org/wiki/Captive_portal).** This page appears before internet access is granted.

*   **Share the speed fairly.**
    *   *Goal:* Prevent one person downloading a huge file from slowing down the internet for everyone else.
    *   *Technical Detail:* **Enable Rate Limiting.** This ensures fair bandwidth distribution.
    *   Consider adjusting DHCP lease timeouts to be shorter (hours not days).

### How to set this up

1.  **Router Interface:** Log in to your router's administrative interface (usually `192.168.1.1` or `10.0.0.1`).
2.  **Wireless Settings:** Look for "Security Mode" or "Authentication". Select "WPA2-PSK (AES)" or "WPA2/WPA3 Personal". Explicitly disable "WPA", "TKIP", and "WPS".
3.  **Guest Network:** Most modern routers have a "Guest Network" feature. Enable it. This often enables Client Isolation by default.
4.  **DNS Configuration:** Look for DNS settings specifically under **"DHCP Server"** or **"LAN Settings"** (not just the Internet/WAN settings). Set the primary DNS to **9.9.9.9** (Quad9) and the secondary to **149.112.112.112**. This ensures guest devices are handed the filtered DNS directly, rather than relying on your router to relay requests.

### Maintenance Schedule

*   **Quarterly:** Review router logs for unusual activity. Check for firmware updates for your access points and routers.
*   **Annually:**
    *   **Router Admin Password:** Ensure the administrative password is a long, complex passphrase (e.g., 20+ characters). **Do not** rotate this arbitrarily; only change it if a compromise is suspected or staff with access leaves (NIST guidance).
    *   **Guest Network Password:** While frequent rotation isn't required for security, consider rotating this quarterly or bi-annually if you notice loitering users or speed degradation. Alternatively, use a Captive Portal that rotates access codes automatically.
    *   Review settings to ensure they still meet current security standards (e.g., migration to WPA3).
