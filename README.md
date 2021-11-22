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

# [SAMPLE PROXIES] - [November 22 2021 | 01:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 4649
   - **SOCKS5** -> 317
   - **HTTP** -> 1004
   - **HTTPS** -> 954

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 6924
   - **Unique Online Proxies** -> 6548
   - **Unique Online/Offline Proxies (Archive)** -> 32895

## [SOCKS4 (4649/6548)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.0.133.100:51327
1.2.187.111:4145
1.2.187.221:4145
1.9.71.4:4153
1.9.165.67:4153
1.9.167.36:60489
1.9.213.114:4153
1.10.133.17:4145
1.10.140.43:4145
1.10.141.220:37718
1.20.96.30:4153
1.20.96.164:4153
1.20.137.82:32241
1.20.198.8:4153
1.20.198.9:4153
1.20.198.10:4153
1.20.227.66:4145
1.53.137.84:4145
1.53.137.164:4145
1.179.145.101:33109
1.179.147.5:52210
1.179.151.165:31948
1.179.183.73:61468
1.179.186.69:1080
1.179.202.33:5678
1.186.40.177:39651
1.186.46.36:5678
1.186.82.4:5678
1.186.93.237:9050
```

## [SOCKS5 (317/6548)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.13.165.87:1088
1.186.93.237:9050
3.234.216.105:1080
4.79.207.214:9050
5.42.158.110:1080
5.42.158.113:1080
5.42.158.114:1080
5.42.158.117:1080
5.42.158.118:1080
5.139.76.210:1080
5.167.53.191:9999
5.189.165.226:8088
8.210.179.3:25170
8.210.251.244:35662
14.105.19.195:1080
14.213.137.182:9050
18.181.146.180:1088
23.94.149.131:53335
23.95.137.162:9050
24.249.199.4:4145
24.249.199.12:4145
31.7.232.178:1080
31.13.202.83:1080
31.128.248.1:1080
36.94.126.50:1080
37.139.243.34:1080
37.187.72.30:57257
43.135.95.75:1080
43.224.8.12:6667
43.224.10.8:6667
```

## [HTTP (1004/6548)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.205.87:8080
1.1.220.100:8080
1.2.252.65:8080
1.14.104.146:808
1.20.166.142:8080
1.117.100.196:7788
1.119.196.202:1080
1.179.144.41:8080
1.179.148.9:55636
2.188.166.25:3128
3.90.235.224:49205
3.135.231.173:49205
3.235.197.149:49205
5.16.0.49:8080
5.16.0.77:1256
5.34.153.142:8080
5.42.158.11:11111
5.59.136.230:8080
5.130.90.3:8080
5.149.219.201:8080
5.160.91.130:3128
5.167.5.159:8080
5.202.115.102:8080
12.90.37.182:8181
14.20.235.129:34100
14.102.13.161:8080
14.115.107.197:9797
14.241.111.38:8080
14.241.225.134:443
15.235.132.138:8080
```

## [HTTPS (954/6548)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.20.217.149:8080
1.32.59.217:47045
2.188.166.22:3128
3.89.71.229:49205
5.56.134.237:55963
5.141.82.95:81
5.160.101.170:3128
8.208.91.118:8080
8.208.91.118:81
8.208.91.118:80
12.218.209.130:53281
14.161.252.185:55443
14.241.111.38:8080
15.235.132.138:8080
18.234.51.98:49205
24.106.221.230:53281
24.113.42.177:48678
24.245.85.51:1516
27.72.28.32:8008
27.72.31.78:4007
27.72.95.176:8080
27.109.116.119:23500
27.116.51.119:8080
27.116.51.178:6666
27.123.4.106:8181
27.147.193.82:8080
31.47.37.92:8080
31.202.162.42:8080
31.220.183.217:53281
34.201.149.253:49205
```

## [ARCHIVE (6548/32895)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.141.90:4145
1.0.145.246:4145
1.0.147.198:4145
1.0.148.132:4145
1.0.152.157:4145
1.0.154.141:4145
1.0.162.24:4145
1.0.163.17:4145
1.0.163.85:4145
1.0.163.172:8081
1.0.170.50:8080
1.0.205.87:8080
1.0.213.133:8080
1.0.239.61:5678
1.0.243.247:4145
1.0.245.18:4145
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
```



Thx Co Pure Gs - Sort Meister! 💟