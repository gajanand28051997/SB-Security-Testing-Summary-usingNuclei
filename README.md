### ✅ **Security Testing Summary using Nuclei**

We conducted a **security assessment** of the website using [**Nuclei**](https://github.com/projectdiscovery/nuclei) across key risk categories. The goal was to identify common vulnerabilities, misconfigurations, and exposed assets.

---

#### 🔍 **Scan Coverage**

The following tests were performed using Nuclei’s latest community templates:

| Category                     | Tags Used                | Description                                                |
| ---------------------------- | ------------------------ | ---------------------------------------------------------- |
| 🔥 CVEs & Vulnerabilities    | `cve`, `vulnerabilities` | Known security flaws in PHP, Yii2, Apache, WordPress, etc. |
| 📁 Exposed Files & Secrets   | `exposure`, `file`       | Public `.env`, `.git`, backups, config files, etc.         |
| ⚙️ Misconfigurations         | `misconfig`              | HTTP methods, default pages, trace, etc.                   |
| 🛡 SSL/TLS Configuration     | `ssl`                    | HSTS, weak ciphers, TLS versions                           |
| ☁️ Cloudflare Origin Checks  | `cloud`                  | Leaked real IPs behind Cloudflare                          |
| 🌐 DNS Issues                | `dns`                    | Zone transfers, misconfigurations, takeover risks          |
| 🧠 Info Disclosure / Headers | `info`, `headless`       | Missing headers, tech stack leaks                          |

---

#### ⚠️ **Important Notes**

* 🔐 **Authentication not used during scan**:
  All scans were performed without login credentials. Therefore:

  * Authenticated areas (e.g., user dashboard, admin panel) were **not scanned**.
  * Business logic flaws, access control issues, or internal-only pages were **not evaluated**.

---

#### 📊 **Key Findings**

* ✅ No critical or high-risk CVEs detected in public surface.
* ⚠️ Low-severity issues in SSL/TLS:

  * Possibly weak cipher support or missing HSTS.
* ⚠️ Exposed information found:

  * Google OAuth Client ID publicly accessible.
  * Possible exposed environment keys (`.env` content).

---
