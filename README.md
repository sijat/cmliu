📖 Project Introduction

edgetunnel is an edge computing tunnel decryption solution based on the Cloudflare Workers/Pages platform. It efficiently handles network traffic while providing a powerful management panel and flexible node configuration capabilities.

🖥️ Demo Site: https://EDT-Pages.github.io/admin

✨ Core Features

🛡️ Protocol Support: Supports mainstream protocols such as VLESS and Trojan with deep encryption integration.

📊 Management Panel: Built-in visual admin panel with real-time configuration editing, log viewing, and traffic statistics.

🛠️ Flexible Deployment: Fully compatible with CF Workers and CF Pages (GitHub / file upload).

🔄 Subscription System: Built-in automatic subscription generation and obfuscation conversion, compatible with major clients (Clash, Sing-box, Surge, etc.).

⚡ Performance Acceleration: Supports custom ProxyIP, SOCKS5/HTTP chained proxies, and preferred IP APIs to optimize latency.

🌐 Multi-Platform Support: Fully compatible with Windows, Android, iOS, macOS, and various router firmware.

💡 Quick Deployment

[!TIP]
📖 Detailed Illustrated Guide: edgetunnel Deployment Guide

[!WARNING]
⚠️ Error 1101 Issue: Video Explanation

⚙️ Workers Deployment
<details> <summary><code><strong>「 Workers Text Deployment Guide 」</strong></code></summary>

Deploy a CF Worker:

Create a new Worker in the CF Worker dashboard.

Paste the contents of worker.js
 into the Worker editor.

In the left Settings tab, select Variables > Add variable.
Set the variable name to ADMIN, and the value to your admin password, then click Save.

Bind a KV Namespace:

In the Bindings tab, select Add binding + > KV Namespace > Add binding, then choose an existing namespace or create a new one.

Set the Variable name to KV, then click Add binding.

Bind a Custom Domain to Workers:

In the Workers dashboard Triggers tab, click Add custom domain.

Enter a subdomain already delegated to Cloudflare DNS, e.g. vless.google.com, then click Add custom domain and wait for the certificate to activate.

Access the Admin Panel:

Visit https://vless.google.com/admin, enter the admin password to log in.

</details>
🛠 Pages Upload Deployment Highly Recommended!!! Illustrated Guide
<details> <summary><code><strong>「 Pages File Upload Deployment Guide 」</strong></code></summary>

Deploy CF Pages:

Download main.zip
 and don’t forget to Star the project!!!

In the CF Pages dashboard, select Upload assets, name your project, click Create project, upload main.zip, then click Deploy site.

After deployment, click Continue to site, go to Settings > Environment variables > Production, then Add variable.
Set ADMIN as the variable name and your admin password as the value, then click Save.

Return to the Deployments tab, click Create new deployment, re-upload main.zip, and click Save and deploy.

Bind a KV Namespace:

In Settings, select Bindings > + Add > KV Namespace, choose or create a namespace.

Set the variable name to KV, click Save, then redeploy.

Bind a CNAME Custom Domain to Pages: Video Tutorial

In the Pages dashboard Custom domains tab, click Set custom domain.

Enter your custom subdomain (do not use the root domain). Example:
If your domain is fuck.cloudns.biz, use lizi.fuck.cloudns.biz.

Follow CF instructions to add a CNAME record pointing lizi to edgetunnel.pages.dev, then click Activate domain.

Access the Admin Panel:

Visit https://lizi.fuck.cloudns.biz/admin, enter the admin password to log in.

</details>
🛠 Pages + GitHub Deployment
<details> <summary><code><strong>「 Pages + GitHub Text Deployment Guide 」</strong></code></summary>

Deploy CF Pages:

Fork this project on GitHub and Star it!!!

In the CF Pages dashboard, select Connect to Git, choose the edgetunnel project, then click Begin setup.

In the Build and deploy settings, select Environment variables (advanced) and add a variable.
Set ADMIN as the variable name and your admin password as the value, then click Save and deploy.

Bind a KV Namespace:

In Settings, select Bindings > + Add > KV Namespace, choose or create a namespace.

Set the variable name to KV, click Save, then redeploy.

Bind a CNAME Custom Domain to Pages: Video Tutorial

In the Pages dashboard Custom domains tab, click Set custom domain.

Enter your custom subdomain (do not use the root domain). Example:
If your domain is fuck.cloudns.biz, use lizi.fuck.cloudns.biz.

Follow CF instructions to add a CNAME record pointing lizi to edgetunnel.pages.dev, then click Activate domain.

Access the Admin Panel:

Visit https://lizi.fuck.cloudns.biz/admin, enter the admin password to log in.

</details>
🔑 Environment Variables
Variable	Required	Example	Description
ADMIN	✅	123456	Admin panel login password
KEY	❌	CMLiussss	Quick subscription path key, access /CMLiussss to fetch nodes
UUID	❌	90cd4a77-141a-43c9-991b-08263cfe9c10	Force a fixed UUID (UUIDv4 only)
HOST	❌	edt.pages.dev	Force fixed fake domain configurable via panel
PATH	❌	/	Force fixed fake path configurable via panel
PROXYIP	❌	proxyip.cmliussss.net:443	Global custom reverse proxy IP
URL	❌	https://cloudflare-error-page-3th.pages.dev	Default homepage disguise (URL or 1101)
GO2SOCKS5	❌	blog.cmliussss.com,*.ip111.cn,*google.com	Force SOCKS5 routing list (* for global, comma-separated)
🔧 Advanced Tips

This tool supports dynamically switching proxy modes via PATH routing:

PROXYIP examples

/proxyip=proxyip.cmliussss.net
/?proxyip=proxyip.cmliussss.net
/proxyip.cmliussss.net (only for domains starting with 'proxyip.')


SOCKS5 examples

/socks5=user:password@127.0.0.1:1080
/?socks5=user:password@127.0.0.1:1080
/socks://dXNlcjpwYXNzd29yZA==@127.0.0.1:1080 (global SOCKS5)
/socks5://user:password@127.0.0.1:1080 (global SOCKS5)


HTTP Proxy examples

/http=user:password@127.0.0.1:1080
/http://user:password@127.0.0.1:8080 (global SOCKS5)

💻 Client Compatibility
Platform	Recommended Clients	Notes
Windows	v2rayN, FlClash, mihomo-party, Clash Verge Rev	Fully supported
Android	ClashMetaForAndroid, FlClash, v2rayNG	Meta core recommended
iOS	Surge, Shadowrocket, Stash	Perfect compatibility
macOS	FlClash, mihomo-party, Clash Verge Rev, Surge	Fully compatible with M1/M2
⭐ Project Popularity

🙏 Special Thanks
💖 Sponsors – Providing cloud servers for the subscription conversion service

(unchanged list)

🛠 Open Source References

(unchanged list)

⚠️ Disclaimer

This project ("edgetunnel") is for educational, research, and personal security testing purposes only.

Users must strictly comply with local laws and regulations when downloading or using this project.

The author cmliu bears no responsibility for any misuse or consequences resulting from this project.

This project is not responsible for any direct or indirect damages caused by using the code.

It is recommended to remove all deployments related to this project within 24 hours after testing.

If you find this project helpful, please give it a Star 🌟 — it’s the greatest encouragement!
