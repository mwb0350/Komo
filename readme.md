# Komo 综合资产收集和漏洞扫描工具

```python
Komo is a comprehensive asset collection and vulnerability scanning tool

██╗  ██╗ ██████╗ ███╗   ███╗ ██████╗ {v1.0 #dev}
██║ ██╔╝██╔═══██╗████╗ ████║██╔═══██╗
█████╔╝ ██║   ██║██╔████╔██║██║   ██║
██╔═██╗ ██║   ██║██║╚██╔╝██║██║   ██║
██║  ██╗╚██████╔╝██║ ╚═╝ ██║╚██████╔╝
╚═╝  ╚═╝ ╚═════╝ ╚═╝     ╚═╝ ╚═════╝  By Komomon

```

![image-20220927001227577](images/image-20220927001227577.png)

注：如果需要获得最新beta版本请前往[beta分支](https://github.com/komomon/Komo/tree/beta)，该分支更新将比较慢。

## Intro&&Feature

🚀**Komo**是一个综合资产收集和漏洞扫描工具，并且支持进度记录，通过多种方式对子域进行获取，收集域名，邮箱，子域名存活探测，域名指纹识别，域名反查ip，ip端口扫描，web服务链接爬取并发送给xray扫描，对web服务进行POC扫描，web弱口令扫描，对主机进行主机POC扫描，常见端口弱口令扫描。

🚋**Komo**集成了**oneforall**，**subfinder**，**ksubdomain**，**amass**，**ctfr**，**emailall**，**httpx**，**naabu**，**TxPortMap**，**ehole**，**goon3**，**crawlergo**，**rad**，**hakrawler**，**gau**，**gospider**，**URLfinder**，**vscan**，**nuclei**，**afrog**，**vulmap**，**SweetBabyScan**，**xray**等**20**多款工具，全自动化、智能化工具。本工具依托各工具特色，进行模块化构建。

Komo的目的为了一键化，便捷性，可移植性，便于打点和红队外围渗透工作，所以将基于模块化开发，所有工具都汇总到统一接口，以便于下一个模块调用和后续某模块新增工具。**==如果你有好的工具和改进建议，可以添加下面的公众号群聊来沟通==**。

~~Komo的每个模块可以单独拿出来直接使用，每个模块下面都有一个main，注意工具下载到对应目录下即可。~~

Komo可以自动下载所需的所有工具，不用使用者自己下载每个工具，使用`python3 Komo.py install` 即可，同时也便于移动，**这保证了Komo的体积足够精简**。

Komo目前已经适配window、linux。





## Project structure

![流程图](images/流程图.jpg)



## Usage

### 初始化

安装`python3`（`python2`暂时不支持）

安装相应的库文件`pip3 install -r requirements.txt`

第一次使用下载所需工具，以及部分工具初始化（goon，vulmap，afrog）

**注：国内访问github可能存在超时问题，推荐使用代理下载工具进行初始化。**

```python
python3 Komo.py install
python3 Komo.py  --proxy http://127.0.0.1:10809 install
python3 Komo.py  --proxy socks5://127.0.0.1:10809 install
```

如下图所示，如果下载失败，则需要手动去下载对应工具到对应目录。

**推荐公众号文章：[综合资产收集和漏洞扫描工具](https://mp.weixin.qq.com/s?__biz=MzI5NTUzNzY3Ng==&mid=2247485631&idx=1&sn=d255af0bf051055b1f84056415a86772&chksm=ec5355dcdb24dcca0656c88558c0fac629b96d3ebf7853c0968c25155dc8dfc2b597f70a3919&scene=132&ascene=0&devicetype=Windows+11+x64&version=63090217&nettype=WIFI&abtest_cookie=AAACAA%3D%3D&lang=zh_CN&countrycode=CN&fontScale=100&exportkey=n_ChQIAhIQDbjBFqKJCWspv93aFzMrCRLfAQIE97dBBAEAAAAAAILxJ4D9f4wAAAAOpnltbLcz9gKNyK89dVj02LCVjULwqTdba0IAPjFFYOtZD3ibye9x0cp1fclqGrnv55FsadiGS6wvzzgZyuhiUG7MSoF98mT4YvnnSC94yEcdre5XuXyRXRBUlzJfB4L8DS6CyGGODdMERamqWX1KD%2BeFhJzab8rSOzIXKi3LD%2B078jqIKuvNmRy9fZ1oNhUaHcwXb85nR%2FpUedvCg21kjP6yi7yN%2FLhWo90NKn%2F8K7zg9DApy0oqWQXJu6eepV5KFvCOy603zVs%3D&pass_ticket=eSBPHSjdSvXWCTggPny%2BRb0kk88VYlZB58F2yrq%2Bqe8nQjtdJZ%2Fwex97%2FxJkSm3P1HrJAqZk9D5GmIJvY4qYSg%3D%3D&wx_header=1&key=db5741f71e06fac51e38034f8de9511f8827f63d6ddb4e2c87f9850aab238ca214ab08442d8844c3f4558c27e509f8e2c0177600e9f9fde820a35dfc3f13be76dc9606126cba73992f88a43fefcec88c7a253236dbbb0688962e7833580763794e75ba8a31510e063910e478f306b3eaa70557e83d1aae02e179ccbff237ce9f&uin=OTE4MDYzMjYx&acctmode=0)**


**附带工具下载链接**

```
https://commondatastorage.googleapis.com/chromium-browser-snapshots/Win_x64/1051001/chrome-win.zip
https://github.com/4dogs-cn/TXPortMap/releases/download/v1.1.2/TxPortMap_windows_x64.exe
https://github.com/boy-hack/ksubdomain/releases/download/v1.9.5/KSubdomain-windows.tar
https://github.com/chaitin/rad/releases/download/0.4/rad_windows_amd64.exe.zip
https://github.com/i11us0ry/goon/releases/download/v3.5/goon3_win_amd64.zip
https://github.com/inbug-team/SweetBabyScan/releases/download/v0.1.0/SbScanAmd64.exe
https://github.com/jaeles-project/gospider/releases/download/v1.1.6/gospider_v1.1.6_windows_x86_64.zip
https://github.com/lc/gau/releases/download/v2.1.2/gau_2.1.2_windows_amd64.zip
https://github.com/maurosoria/dirsearch/archive/refs/heads/master.zip
https://github.com/OWASP/Amass/releases/download/v3.21.2/amass_windows_amd64.zip
https://github.com/pingc0y/URLFinder/blob/master/URLFinder-windows64.exe?raw=true
https://github.com/projectdiscovery/httpx/releases/download/v1.2.4/httpx_1.2.4_windows_amd64.zip
https://github.com/projectdiscovery/naabu/releases/download/v2.1.1/naabu_2.1.1_windows_amd64.zip
https://github.com/projectdiscovery/nuclei/releases/download/v2.8.3/nuclei_2.8.3_windows_amd64.zip
https://github.com/projectdiscovery/subfinder/releases/download/v2.5.3/subfinder_2.5.3_windows_amd64.zip
https://github.com/Qianlitp/crawlergo/releases/download/v0.4.4/crawlergo_win_amd64.exe
https://github.com/rverton/webanalyze/releases/download/v0.3.8/webanalyze_0.3.8_Windows_x86_64.tar.gz
https://github.com/shmilylty/OneForAll/blob/master/data/ip2location.zip?raw=true
https://github.com/shmilylty/OneForAll/blob/master/data/ip2region.db?raw=true
https://github.com/shmilylty/OneForAll/blob/master/data/subnames_big.7z?raw=true
https://github.com/veo/vscan/releases/download/v2.1.0/vscan_2.1.0_windows_amd64.zip
https://github.com/zan8in/afrog/releases/download/v2.1.1/afrog_2.1.1_windows_amd64.zip
https://github.com/zhzyker/vulmap/archive/refs/tags/v0.9.zip
```

注意：使用v2ray的开全局不一定能行，可以使用clash开TUN。



### 配置

配置文件config/config.yaml

**部分配置讲解**

修改有runtime字段的工具的runtime字段，设置工具的运行时间，如果超时则kill掉，推荐设置600-1200s

```
crawlergo:
      toolname: crawlergo
      runtime: 900
rad:
      toolname: rad
      runtime: 900
```

修改xray的监听端口

```
other:
    xray:
      toolname: xray
      listenport: 7777 #修改监听端口
```

其他配置为以后扩充开发预留配置，暂时不用修改。

oneforall等工具的配置，要在初始化之后进入到对应工具目录进行修改，比如oneforall：`core/tools/domain/Oneforall`



### **Komo 支持多种模式**

> install：下载所有工具
>
> all: 资产收集+攻击，多种方式收集域名，收集域名邮箱，域名存活探测，域名反查ip，域名指纹识别，ip端口扫描，web服务链接爬取，将爬取的链接发送给xray进行扫描，POC漏洞扫描，反查的ip进行其他端口漏洞扫描，弱口令扫描
>
> all2: 资产收集+攻击，提供子域名，域名存活探测，域名反查ip，域名指纹识别，ip端口扫描，web服务链接爬取，将爬取的链接发送给xray进行扫描，POC漏洞扫描，反查的ip进行其他端口漏洞扫描，弱口令扫描
> 
> collect:只资产收集，多种方式收集域名，收集域名邮箱，域名存活探测，域名反查ip，域名指纹识别，ip端口扫描，web服务链接爬取
>
> subdomain: 通过多种方式进行域名收集，dns爬取，爆破，证书获取，DNS运营商处获取。
>
> finger: 对收集到的域名或域名文件进行存活探测和指纹识别（Ehole+wapplyzer）
>
> portscan：对反查的ip列表或ip文件进行端口扫描
>
> sensitive：对收集到的存活域名或域名文件进行url爬取
>
> webattack：对收集到的存活域名或域名文件进行url爬取，然后发送给xray进行扫描，同时也调用nuclei，afrog，vulmap，vscan进行漏洞扫描
>
> hostattack：对反查的ip列表或ip文件进行常见服务弱口令扫描和漏洞扫描
>
> 



#### install 下载所有工具

功能：根据系统下载所有工具以及部分工具初始化

```
python3 Komo.py install
python3 Komo.py  --proxy http://127.0.0.1:10809 install
python3 Komo.py  --proxy socks5://127.0.0.1:10809 install
```



#### all 全扫描 

输入：域名/域名文件

功能：多种方式收集域名，收集域名，邮箱，域名存活探测，域名反查ip，域名指纹识别，ip端口扫描，web服务链接爬取，将爬取的链接发送给xray进行扫描，POC漏洞扫描，反查的ip进行其他端口漏洞扫描，弱口令扫描

```python
python3 Komo.py --domain example.com all
python3 Komo.py --domains ./domains.txt all
```

**注意：记得使用该模式之前先启动xray，否则webattack不能完全扫描**

```
xray.exe webscan --listen 127.0.0.1:7777 --html-output 1.html
```



#### all2

输入：子域名/子域名文件

功能：提供子域名，不扫描子域，域名存活探测，域名反查ip，域名指纹识别，ip端口扫描，web服务链接爬取，将爬取的链接发送给xray进行扫描，POC漏洞扫描，反查的ip进行其他端口漏洞扫描，弱口令扫描

```python
python3 Komo.py --subdomain aaa.example.com all2
python3 Komo.py --subdomains ./subdomains.txt all2
```

**注意：记得使用该模式之前先启动xray，否则webattack不能完全扫描**

```
xray.exe webscan --listen 127.0.0.1:7777 --html-output 1.html
```



#### collect

输入：域名/域名文件

功能：全方位资产收集，多种方式收集域名，收集域名，邮箱，域名存活探测，域名反查ip，域名指纹识别，ip端口扫描，web服务链接爬取

```python
python3 Komo.py --domain example.com collect
python3 Komo.py --domains ./domains.txt collect
```

#### collect1

输入：域名/域名文件

功能：只资产收集，多种方式收集域名，收集域名，域名存活探测，域名反查ip，域名指纹识别

功能比collect 少了端口扫描，web链接爬取

```python
python3 Komo.py --domain example.com collect1
python3 Komo.py --domains ./domains.txt collect1
```

#### collect2

输入：域名/域名文件

功能：只资产收集，多种方式收集域名，收集域名，邮箱，域名存活探测，域名反查ip，域名指纹识别，ip端口扫描

功能比collect 少了web链接爬取

```python
python3 Komo.py --domain example.com collect2
python3 Komo.py --domains ./domains.txt collect2
```







#### subdomain

输入：域名/域名文件

功能：通过多种方式进行域名收集，dns爬取，爆破，证书获取，DNS运营商处获取。

```python
python3 Komo.py --domain example.com subdomain
python3 Komo.py --domains ./domains.txt subdomain
```

#### finger

输入：url/url文件

功能：对收集到的域名或域名文件进行存活探测和指纹识别（Ehole+wapplyzer）

```python
python3 Komo.py --url http://example.com finger
python3 Komo.py --urls ./urls.txt finger
```

#### **portscan**

输入：ip/ip文件

功能：对反查的ip列表或ip文件进行端口扫描和端口指纹识别

默认端口扫描列表

```
21,22,23,25,53,53,69,80,81,88,110,111,111,123,123,135,137,139,161,177,389,427,443,445,465,500,515,520,523,548,623,626,636,873,902,1080,1099,1433,1434,1521,1604,1645,1701,1883,1900,2049,2181,2375,2379,2425,3128,3306,3389,4730,5060,5222,5351,5353,5432,5555,5601,5672,5683,5900,5938,5984,6000,6379,7001,7077,8080,8081,8443,8545,8686,9000,9001,9042,9092,9100,9200,9418,9999,11211,11211,27017,33848,37777,50000,50070,61616
```

```python
python3 Komo.py --ip 1.1.1.1 portscan
python3 Komo.py --ips ./ips.txt portscan
```



#### sensitive

输入：url/url文件

功能：对收集到的存活域名或域名文件进行url爬取（crawlergo，rad，gau，URLFinder，gospider，hakrawler）

```python
python3 Komo.py --url http://example.com sensitive
python3 Komo.py --urls ./urls.txt sensitive
```

#### webattack

输入：url/url文件

功能：对url进行爬取，然后发送给xray进行扫描，同时也调用nuclei，afrog，vulmap，vscan进行漏洞扫描

```python
python3 Komo.py --url http://example.com webattack
python3 Komo.py --urls ./urls.txt webattack
```

**注意：记得使用该模式之前先启动xray，否则webattack不能完全扫描**

```
xray.exe webscan --listen 127.0.0.1:7777 --html-output 1.html
```

#### webattack2

输入：url/url文件

功能：只进行poc扫描（nuclei，afrog，vulmap，vscan）

```python
python3 Komo.py --url http://example.com webattack2
python3 Komo.py --urls ./urls.txt webattack2
```



#### hostattack

输入：ip/ip文件

功能：对反查的ip列表或ip文件进行常见服务弱口令扫描和漏洞扫描

```python
python3 Komo.py --ip 1.1.1.1 hostattack
python3 Komo.py --ips ./ips.txt hostattack
```







## **完整Usage**

```python
    Komo help summary page

    Komo is an automated scanning tool set

    mode:
    install     Download the required tools
    	--proxy Set proxy
    all         all scan and attack:subdomain, survival detection, finger, portscan, email collect, sensitive(crawl urls), pocscan, Weak password scanning, to_xray
        --domain    one domain
        --domains   a domain file
    all2        run scan and attack except domain collection: survival detection, finger, portscan, email collect, sensitive(crawl urls), pocscan, Weak password scanning, to_xray
        --subdomain    one subdomain
        --subdomains   a subdomain file
    collect     run all collection modules :subdomain, survival detection, finger, port, email collect, sensitive(crawl urls), pocscan, to_xray
        --domain    one domain
        --domains   a domain file
    collect1    run collection modules :subdomain, survival detection, finger
        --domain    one domain
        --domains   a domain file
    collect2    run collection modules :subdomain, survival detection, finger, portscan
        --domain    one domain
        --domains   a domain file
    subdomain   only collect subdomain
        --domain    one domain
        --domains   a domains file
    finger      only collect the survival URL and  fingerprint
        --url       one url
        --urls      an urls file
    portscan    only collect port from ip or ips
        --ip        one ip
        --ips       an ips file
    sensitive   only collect directory with crawl,email
        --url       one url
        --urls      an urls file
    webattack   only attack web from url or urls: pocscan, Weak password scanning, crawl urls to xray
        --url       one url
        --urls      an urls file
    webattack2  only poc scan from url or urls: pocscan, Weak password scanning
        --url       one url
        --urls      an urls file
    hostattack  only attack ip from ip or ips
        --ip        one ip
        --ips       an ips file
    attack      run webattack and hostattack: crawl url to xray, pocscan, Weak password scanning


    Example:
        python3 Komo.py install
        python3 Komo.py --domain example.com all
        python3 Komo.py --domains ./domains.txt all
        python3 Komo.py --domain example.com collect
        python3 Komo.py --domains ./domains.txt collect
        python3 Komo.py --domain example.com collect1
        python3 Komo.py --domains ./domains.txt collect1
        python3 Komo.py --domain example.com collect2
        python3 Komo.py --domains ./domains.txt collect2
        python3 Komo.py --domain example.com subdomain
        python3 Komo.py --domains ./domains.txt subdomain

        python3 Komo.py --subdomain aaa.example.com all2
        python3 Komo.py --subdomains ./subdomains.txt all2

        python3 Komo.py --url http://example.com finger
        python3 Komo.py --urls ./urls.txt finger
        python3 Komo.py --url http://example.com sensitive
        python3 Komo.py --urls ./urls.txt sensitive
        python3 Komo.py --url http://example.com webattack
        python3 Komo.py --urls ./urls.txt webattack
        python3 Komo.py --url http://example.com webattack2
        python3 Komo.py --urls ./urls.txt webattack2

        python3 Komo.py --ip example.com portscan
        python3 Komo.py --ips ./domains.txt portscan
        python3 Komo.py --ip example.com hostattack
        python3 Komo.py --ips ./domains.txt hostattack
```



## Result

Komo会将输出结果记录到result/{date} 目录下

该目录下会有多个文件夹，分别对应各个模块的输出:

> domain_log
>
> fingerlog
>
> portscan_log
>
> sensitive_log
>
> vulscan_log

result/{date} 根目录下会有输出结果文件：

target 为domain或date

> {target}.final.subdomains.txt 最终找到的所有子域名
>
> {target}.links.csv 多个工具爬取到的所有link
>
> {target}.many.tools.subdomains.txt 除oneforall之外的其他子域名收集工具收集到的域名
>
> {target}.subdomains.ips.txt 域名反查的ip
>
> {target}.subdomains.with.http.txt 存活的子域名并且带http(s)









欢迎Star :star: :star:



## 更新日志



### 20230106

1、修复linux下子线程执行进入交互shell的bug

2、配置文件修改hakrawler采用下载方式，进一步缩进Komo体积

3、log文件增加扫描参数记录，便于回忆使用的参数。

4、install 模块添加代理参数`--proxy`，解决国内无法访问github下载工具的问题



### 20221227

1、增加进度机制，可以记录扫描进度，当未运行完终止时，下次再次运行的时候，使用原参数并增加--date参数，
来指定上次运行的结果文件夹，这样Komo会从上次终止的位置继续运行
比如第二次再运行使用`python Komo.py --domain xx.com --date 11-11-11-11-11-11 all`

2、linux版本适配完成

3、download模块添加goon，vulmap，afrog初始化

4、添加common模块

5、修改config.yaml,sensitiveinfo模块的工具运行时间，xray监听端口通过config.yaml配置

6、修改vulsan 模块，子线程不能执行的bug



### 20221011

    download_tools 逻辑修改，bug修改，tools.yaml 添加tool_main_filename 键
    sensitive模块添加killprocess
    sensitive模块修改to_xray添加fromurl参数 只发送给xray，爬取的url的相关链接，减少请求量，提高效率
    rad，gospider添加运行时间timeout，运行时间太长会卡住
    domain模块修改 merge_result，将非目标子域名提取出来，放到result/{date}/{domain}.other.subdomains.txt中



### 20220907

```
今天完善了main，domain finger sensitive vulscan 在main中实现调用

domain finger sensitive vulscan 四个模块实现了顺序模块扫描，也实现了单独使用的时候指定单url 单urlsfile
vulscan的main分成了两个webmanager和hostmanager分别对web和ip进行漏洞扫描

hostmanager加上一个goon,去识别指纹和对端口服务进行弱口令扫描

第一版完成
```











































​    
