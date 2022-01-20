<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/jetkai/proxy-list?style=flat&logo=github
[contributors-url]: https://github.com/jetkai/proxy-list/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/jetkai/proxy-list?style=flat&logo=github
[forks-url]: https://github.com/jetkai/proxy-list/network/members
[stars-shield]: https://img.shields.io/github/stars/jetkai/proxy-list?style=flat&logo=github
[stars-url]: https://github.com/jetkai/proxy-list/stargazers
[issues-shield]: https://img.shields.io/github/issues/jetkai/proxy-list?style=flat&logo=github
[issues-url]: https://github.com/jetkai/proxy-list/issues
[license-shield]: https://img.shields.io/github/license/jetkai/proxy-list?style=flat&logo=github
[license-url]: https://github.com/jetkai/proxy-list/blob/main/LICENSE
[commit-shield]: https://img.shields.io/github/last-commit/jetkai/proxy-list?style=flat&logo=github
[commit-url]: https://github.com/jetkai/proxy-list/commits/main
[commit-activity]: https://img.shields.io/github/commit-activity/w/jetkai/proxy-list?style=flat&logo=github
[commit-activity-url]: https://github.com/jetkai/proxy-list/commits/main

# 🎁 SOCKS4/5 & HTTP/S PROXIES // ONLINE & READY

[![Commits][commit-shield]][commit-url]
[![Commits][commit-activity]][commit-activity-url]
[![Stargazers][stars-shield]][stars-url]
[![Forks][forks-shield]][forks-url]
[![Issues][issues-shield]][issues-url]

## 📰About This Project & The Proxies:
This repository contains a free list of tested SOCKS4/5 & HTTP/S proxies in -> **JSON**, **TXT**, **CSV**, **XML** & **YAML** format. No authentication is required when connecting to these proxies.

## 👩‍💻Proxy Testing:

These proxies are tested ~12x/day (every 2 hours) against EU/US hosting providers - **see below**, they have been verified to write & read data <**AT THE TIME OF TESTING**>.

**Hosting Provider**|**Country**|**Continent**
:-----:|:-----:|:-----:
OVH|France|EU
Amazon Web Services|United States|NA
Oracle Cloud|United Kingdom|EU
Microsoft Azure|Hong Kong|AS

[Source Code](https://github.com/jetkai/ProxyBuilder/blob/main/src/main/kotlin/spb/net/proxy/ProxyTester.kt)
```kotlin
    //SOCKS example (HTTP/S) is also supported
    private fun useSocksProxy(serverAddress: String?, serverPort: Int): ClientSocket? {
        val proxy = Proxy(Proxy.Type.SOCKS, InetSocketAddress(proxyAddress, proxyPort))
        val socket = Socket(proxy)
        if(socks4)
            forceSocks4(socket)
        try {
            socket.soTimeout = Constants.CONNECTION_TIMEOUT //3000ms
            socket.tcpNoDelay = true
            socket.connect(InetSocketAddress(serverAddress, serverPort), Constants.CONNECTION_TIMEOUT)
        } catch (e : IOException) {
            socket.close()
        }
        if(socket.isClosed)
            return null
        return ClientSocket().init(socket) //Read/Write Data Function
    }
```

## 📝Proxy Formatting:

These proxies are scraped from various sources & I compile this data using my [ProxyBuilder](https://github.com/jetkai/ProxyBuilder) application. Proxies are sorted from lowest to highest 0-255 & duplicated proxies are removed — the only exception is if an IP has a different port open, which is also a working proxy tunnel <**Less than 1% of the total proxies at the time of testing**>.

```IP:Port -> 1.0.132.249:4153```

## ✔Compatability:

Proxies work for any application that can establish a socket connection, such as... An application that has proxy support (FireFox, Chrome), or as an example, these Java Apps -> [JaySyiPker](https://github.com/JayArrowz/JaySyiPker), [Bruteforce-RSPS](https://github.com/jetkai/Bruteforce-RSPS) & [718 Cheat Client (Final)](https://github.com/jetkai/718-Cheat-Client-Final).

## 🔗ProxyList Links (Direct URL):

- _Online Proxies:_
    - **JSON** -> [proxies.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/json/proxies.json)
    - **TXT** -> [proxies.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies.txt)
    - **CSV** -> [proxies.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/csv/proxies.csv)
    - **XML** -> [proxies.xml](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/xml/proxies.xml)
    - **YAML** -> [proxies.yaml](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/yaml/proxies.yaml)
- _Online/Offline Proxies (Archive):_
  - **JSON** -> [working-proxies-history.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/working-proxies-history.json)
  - **TXT** -> [working-proxies-history.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
  - **CSV** -> [working-proxies-history.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history.csv)
  - **XML** -> [working-proxies-history.xml](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xml/working-proxies-history.xml)
  - **YAML** -> [working-proxies-history.yaml](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/yaml/working-proxies-history.yaml)

## 🌍Geolocation & Graphs (Weekly):
Analytics are updated on a weekly basis and contains raw data, tables & graphs. 

You can view/download this data below.

**Query**|**Result**
:-----:|:-----:
Most Proxies By Country|Brazil (6749)
Most Detected Proxies By Country|Brazil (4680)
Most Proxies By Provider|Bharat Sanchar Nigam Ltd (2455)
Most Proxies By Port|5678 (33668)
Most Proxies By Protocol|SOCKS4 (44037)
Most Proxies By Continent|Asia (27864)

**Data Type**|**Link**
:-----:|:-----:
Graphs, Tables & Data (Excel) | [(analysis.xlsx)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xlsx/analysis.xlsx)
Raw Data (JSON) | [(archive-geo.json)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/working-proxies-history-geo-beautify.json)
Raw Data (CSV) | [(archive-geo.csv)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history-geo.csv)
Raw Data (XML) | [(archive-geo.xml)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xml/working-proxies-history-geo.xml)
Raw Data (YAML) | [(archive-geo.yaml)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/yaml/working-proxies-history-geo.yaml)

![image](https://user-images.githubusercontent.com/26250917/135766207-17d4c531-2738-4209-808e-82c04b871331.png)


## Next Updates:

Further updates will be made to this project throughout the year, the next update I am working on will keep a record of proxy up-time, location, isp & speed.

---

# [SAMPLE PROXIES] - [January 20 2022 | 09:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 0
   - **SOCKS5** -> 638
   - **HTTP** -> 1539
   - **HTTPS** -> 1410

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 3587
   - **Unique Online Proxies** -> 3061
   - **Unique Online/Offline Proxies (Archive)** -> 45705

## [SOCKS4 (0/3061)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml

```

## [SOCKS5 (638/3061)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.12.224.175:9091
1.12.224.175:9090
1.12.224.175:8888
3.127.21.209:1080
5.11.17.230:1080
5.56.134.237:45698
5.58.178.99:7777
5.130.89.32:1080
5.196.224.66:5005
8.210.49.92:16600
8.218.173.230:47678
18.223.3.192:11086
23.88.100.242:10039
23.88.100.242:10026
23.94.73.246:1080
23.94.149.131:53335
23.224.46.21:5555
24.249.199.4:4145
24.249.199.12:4145
27.116.51.119:6667
27.116.51.178:6667
27.116.51.181:6667
27.116.51.186:6667
31.13.202.83:1080
31.22.7.188:35633
31.128.248.1:1080
31.128.248.2:1080
36.27.223.80:51620
36.27.223.80:56708
36.27.223.80:43891
```

## [HTTP (1539/3061)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.1.189.58:8080
1.10.183.38:8080
1.12.224.175:9091
1.12.224.175:8888
1.15.182.239:7890
1.20.217.52:8080
1.32.59.217:47045
1.117.231.98:8080
1.179.144.41:8080
1.179.148.9:55636
1.179.183.73:50178
1.180.156.226:65001
2.137.213.1:8080
2.188.166.22:3128
3.20.236.208:49205
3.215.177.148:49205
5.16.0.49:8080
5.16.0.97:1256
5.16.0.174:8080
5.16.0.180:8080
5.20.91.12:60792
5.56.133.236:3128
5.134.221.222:8080
5.141.244.97:61288
5.160.91.130:3128
5.160.122.84:41253
5.160.122.94:41253
5.189.179.67:3128
8.208.91.118:3128
8.208.91.118:8000
```

## [HTTPS (1410/3061)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.205.87:8080
1.2.252.65:8080
1.12.224.175:8888
1.13.165.87:8080
1.15.182.239:7890
1.179.148.9:55636
1.180.156.226:65001
2.179.193.146:80
2.188.166.25:3128
3.20.236.208:49205
3.109.185.168:3128
5.16.0.180:8080
5.26.96.212:8080
5.34.153.142:8080
5.131.243.11:8080
5.149.219.201:8080
5.153.234.91:3128
5.160.122.84:41253
8.208.91.118:8000
12.90.37.182:8181
12.218.209.130:53281
14.102.44.1:44047
14.139.184.130:3128
14.143.168.230:8080
14.161.31.192:53281
14.177.236.212:55443
14.207.144.47:9080
14.241.39.191:8080
14.245.240.175:55443
15.235.49.112:3128
```

## [ARCHIVE (3061/45705)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.42:4145
1.0.136.161:4145
1.0.136.168:4145
1.0.136.201:4145
1.0.136.222:4145
1.0.141.90:4145
1.0.145.246:4145
1.0.147.198:4145
1.0.148.132:4145
1.0.152.157:4145
1.0.154.141:4145
1.0.161.151:4153
1.0.162.24:4145
1.0.162.181:4145
1.0.163.17:4145
1.0.163.85:4145
1.0.163.172:8081
1.0.170.50:8080
1.0.170.50:80
1.0.173.104:4145
1.0.174.87:4145
1.0.205.87:8080
1.0.209.187:8080
1.0.213.133:8080
1.0.220.169:4153
1.0.226.138:4145
1.0.228.243:5678
```



Thx Co Pure Gs - Sort Meister! 💟