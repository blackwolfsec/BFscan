# BFscan
BFscan is a tiny Bypass waF  Scanner

基于python3默认模块，无需安装任何第三方模块即可使用
## 防火墙规避策略
- 基于telnetlib实现telnet扫描，可以达到一定bypass防火墙的效果
- 支持ip段扫描（CIDR地址块），采取ip地址随机化，避免同一时间段对相邻ip进行扫描，尽量规避触发防火墙规则
- 极限情况下，--slow参数设置单进程扫描，并在每次端口探测之前添加5-20秒的随机延迟
## Usage
```
    ___   ___
  / __\ / __\__  ___ __ _ _ __
 /__\/// _\/ __|/ __/ _` | '_ \
/ \/  \ /  \__ \ (__ (_| | | | |
\_____\/   |___/\___\__,_|_| |_|

A Bypass waF  Scanner

starting......

Usage: BFscan.py [options]

Options:
  -h, --help            show this help message and exit
  -m MULTIPROCESS, --multiprocess=MULTIPROCESS
                        Num of multiprocess running concurrently, 30 by
                        default
  -t THREADS, --threads=THREADS
                        Num of scan threads for each scan process, 10 by
                        default
  --ip=IP               IP addresses. Ex: 192.168.0.1 or 192.168.1.0/24
  -p PORT, --port=PORT  Scan specified ports, default: 21-22,445,80-88,1433,27
                        017,3306,3389,6379,8080-8088,9200
  --timeout=TIMEOUT     Max timeout for each telnet connection, 10 by default
  --slow                Slow model to bypass waf,which will set threads=1 and
                        add random delay of 5-20 seconds for each port scan.
                        It will be very slow, please use it carefully.
```