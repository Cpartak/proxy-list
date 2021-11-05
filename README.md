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

# [SAMPLE PROXIES] - [November 05 2021 | 09:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 4818
   - **SOCKS5** -> 287
   - **HTTP** -> 1631
   - **HTTPS** -> 1640

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 8376
   - **Unique Online Proxies** -> 7611
   - **Unique Online/Offline Proxies (Archive)** -> 28251

## [SOCKS4 (4818/7611)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.141.90:4145
1.0.152.157:4145
1.0.243.247:4145
1.2.214.154:4145
1.4.195.114:4145
1.9.71.4:4153
1.9.164.242:35471
1.9.167.35:60489
1.10.186.167:55167
1.10.189.133:50855
1.20.95.95:5678
1.20.99.41:5678
1.20.168.236:4145
1.20.184.75:4153
1.20.198.10:4153
1.20.220.79:4145
1.32.59.217:31981
1.53.137.84:4145
1.71.133.58:5678
1.179.147.5:52210
1.179.148.9:36476
1.179.173.114:4153
1.179.181.213:30500
1.179.183.73:61468
1.179.202.33:5678
1.186.40.2:39651
1.186.40.9:39651
1.186.40.177:39651
1.186.82.4:5678
1.186.139.9:39651
```

## [SOCKS5 (287/7611)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
3.110.44.32:1080
5.105.0.135:16379
8.142.27.108:7890
8.210.179.3:25170
8.210.251.244:24691
8.210.251.244:6655
8.210.251.244:35662
13.250.172.147:48540
20.198.168.89:1080
23.94.149.131:53335
24.249.199.4:4145
24.249.199.12:4145
27.116.51.181:6667
31.7.232.178:1080
31.128.248.1:1080
31.128.248.2:1080
36.27.223.80:37640
36.57.77.225:4216
36.82.224.191:1080
37.52.48.238:8888
37.187.72.228:32740
39.98.142.195:1080
39.105.147.76:8888
39.106.71.115:7891
43.132.205.99:1080
43.135.95.75:1080
43.224.8.14:6667
43.224.10.11:6667
43.224.10.19:6667
43.224.10.26:6667
```

## [HTTP (1631/7611)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.1.189.58:8080
1.1.220.100:8080
1.2.252.65:8080
1.10.234.91:8080
1.20.99.122:8080
1.20.166.142:8080
2.188.166.22:3128
2.188.166.25:3128
3.215.177.148:49205
5.16.0.97:1256
5.16.0.180:8080
5.20.91.12:60792
5.56.134.237:55963
5.58.33.187:55507
5.131.243.11:8080
5.133.27.61:3129
5.133.30.222:8080
5.139.13.224:80
5.160.101.165:3128
5.160.223.254:8080
5.164.211.117:8080
8.129.129.23:9999
8.208.91.118:8008
12.127.133.62:48678
12.139.210.105:8080
12.220.14.50:8181
13.211.234.15:49205
13.213.74.144:9090
14.102.152.158:8080
14.161.10.191:8080
```

## [HTTPS (1640/7611)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.205.87:8080
1.10.234.91:8080
1.15.182.239:7890
1.20.217.52:8080
1.20.217.149:8080
1.116.151.207:7788
1.179.148.9:55636
2.188.166.22:3128
3.88.202.89:49205
3.215.177.148:49205
5.16.0.174:8080
5.16.0.180:8080
5.44.54.16:8080
5.44.54.103:8080
5.131.243.11:8080
5.133.27.61:3129
5.133.30.222:8080
5.139.13.224:80
5.141.82.95:81
5.190.29.161:8080
8.208.91.118:8800
8.208.91.118:80
8.208.91.118:8008
8.208.91.118:3128
8.243.120.54:999
12.139.210.105:8080
14.102.7.142:1337
14.102.44.25:44047
14.161.10.191:8080
14.192.2.161:83
```

## [ARCHIVE (7611/28251)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.141.90:4145
1.0.145.246:4145
1.0.147.198:4145
1.0.148.132:4145
1.0.152.157:4145
1.0.163.172:8081
1.0.205.87:8080
1.0.213.133:8080
1.0.239.61:5678
1.0.243.247:4145
1.1.128.155:5678
1.1.129.166:4145
1.1.167.139:4145
1.1.187.209:5678
1.1.187.210:4145
1.1.189.58:8080
1.1.214.117:8081
1.1.220.100:8080
1.1.227.53:4145
1.1.227.187:4145
1.1.227.254:4145
1.1.229.44:4145
1.1.240.121:5678
1.2.187.41:4145
1.2.187.111:4145
1.2.187.168:4145
1.2.187.196:4145
```



Thx Co Pure Gs - Sort Meister! 💟