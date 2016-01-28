# Apache-mod_status-Cacti
Cacti template for module mod_status of Apache web server. ([Screenshots] (https://github.com/Busindre/Apache-mod_status-Cacti/issues/1 "Cacti template for Apache server-status screenshots"))

**Apache stadistics with mod_status page.**
```
Total Accesses: 824549677
Total kBytes: 39869016655
CPULoad: .25456
Uptime: 7511517
ReqPerSec: 109.771
BytesPerSec: 5435100
BytesPerReq: 49512.9
BusyWorkers: 160
IdleWorkers: 590
ConnsTotal: 4615
ConnsAsyncWriting: 536
ConnsAsyncKeepAlive: 1083
ConnsAsyncClosing: 2776
Scoreboard: LG...
```

## Apache statistics (mod_status) Host Template (Associated Graph Templates)

- WebServer - Apache Statistics - Bits / s
- WebServer - Apache Statistics - Connections
- WebServer - Apache Statistics - CPU Load
- WebServer - Apache Statistics - Req / s
- WebServer - Apache Statistics - Request
- WebServer - Apache Statistics - Request bytes
- WebServer - Apache Statistics - Thread Details
- WebServer - Apache Statistics - Thread Scoreboard 

## Installation

- Copy the script "ss_apache_stats.php" to <cacti_dir>/scripts/ directory.
- Import the file xml in Cacti.
- The URL to "server-status?auto" should be written in the field "hostname" of "Device" (http://XXX/server-status?auto).

## Dependencies

- PHP CLI (Cacti).

## Use / Output example

**Sintax**
```
php ss_apache_stats.php http://XXX/server-status?auto [option]
```

**Options**:
```
kbytes
workers
workers
cpuload
reqpersec
bytespersec
bytesperreq
connstotal
connsasyncwriting
connsasynckeepalive
connsasyncclosing
```

**Examples**
```
# Only workers data
php ss_apache_stats.php http://XXX/server-status?auto workers
apache_busy_workers:600 apache_idle_workers:600

# Default
php ss_apache_stats.php http://XXX/server-status?auto
apache_total_hits:824640706 apache_total_kbytes:39873178449 apache_cpuload:.269279 reqpersec:109.774 bytespersec:5435190 bytesperreq:49512.6 apache_busy_workers:195 apache_idle_workers:555 connstotal:4691 connsasyncwriting:520 connsasynckeepalive:1151 connsasyncclosing:2761 thread_W:555 threadS:0 threadR:176 threadW:19 threadK:0 threadD:0 threadC:0 threadL:1575 threadG:1275 threadI:0 thread_O:150
```
