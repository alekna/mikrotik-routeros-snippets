# Mikrotik RouterOS snippets
## DoH
```
/ip dns set servers=1.1.1.1,1.0.0.1
/system ntp client set enabled=yes server-dns-names=time.cloudflare.com
/tool fetch https://cacerts.digicert.com/DigiCertGlobalRootCA.crt
/certificate import file-name=DigiCertGlobalRootCA.crt passphrase=""
/ip dns set use-doh-server=https://1.1.1.1/dns-query verify-doh-cert=yes
/ip dns set servers=""
```
Servers:
* 1.1.1.1
* 1.1.1.2 - Malware Blocking Only
* 1.1.1.3 - Malware and Adult Content Blocking Together
