---
title: OWASP ZAP Scanner
category: Scanners
chapter: 3
order: 1
---


The OWASP Zed Attack Proxy (ZAP) is one of the world’s most popular free security tools and is actively maintained by hundreds of international volunteers*. It can help you automatically find security vulnerabilities in your web applications while you are developing and testing your applications. Its also a great tool for experienced pentesters to use for manual security testing.

![ZAP Scanner](/images/screenshots/owaspzap.png)

Archery has in built plugin for OWASP Zed Attack Proxy (ZAP) Scanner and you can utilize to perform automated way scanning on your web applications.

### ZAP Running in Daemon Mode

ZAP Scanner path

```bash
# Windows

C:\Program Files\OWASP\Zed Attack Proxy

# Linux

/usr/share/zaproxy/

# Mac OS

/Applications/OWASP\ ZAP.app/Contents/Java/

```

You can run ZAP scanner in daemon mode and configure into Archery ZAP setting module.

```bash
# Windows

zap.bat -daemon -host 0.0.0.0 -port 8080 -config api.disablekey=true -config api.addrs.addr.name=.* -config api.addrs.addr.regex=true

# Others

zap.sh -daemon -host 0.0.0.0 -port 8080 -config api.disablekey=true -config api.addrs.addr.name=.* -config api.addrs.addr.regex=true
```

Archery uses ZAP Scanner API in order to trigger scans in ZAP. If you run ZAP in daemon mode, the ZAP API end points are exposed on your localhost `127.0.0.1` or your system IP.

You can test by accessing ``` http://127.0.0.1:8080/ ``` OR ``` http://your-system-IP:8080/ ```

![ZAP Scanner](/images/screenshots/zap_api.png)

### Configure ZAP in Archery

Steps in Archery :
 - Go to Settings
 - Edit ZAP Setting

 ![ZAP Scanner](/images/screenshots/edit_zap.png)

 - Leave ZAP API Key blank if you are running ZAP daemon mode with `-config api.disablekey=true`
 - Fill ZAP API host as localhost `127.0.0.1` or `YOUR-SYSTEM-IP`
 - Fill ZAP Port as `8080`

 ![ZAP Scanner](/images/screenshots/zap_api_fill.png)

 - Now you can launch a scan from Domain scan.

