# pcap_flow

![Alt text](http://fmad.io/analytics/logo_flow_analyzer.png "fmadio flow analyzer logo")

displays flow information from pcap and can extract individual or all tcp streams

###Options

Command line options

```
-o <filename>               | write filtered flows to the specified file name
                            | for bulk tcp extraction this is the prefix filename
--packet-max  <number>      | only process the first <number> packets
--extract <number>          | extract FlowID <number> into the output PCAP file
--extract-tcp <number>      | extract FlowID <number> as a TCP stream to the output file name
--extract-tcp-port <number> | extract all TCP flows with the specified port in src or dest 
--stdin                     | read pcap from stdin. e.g. zcat capture.pcap | pcap_flow --stdin
--disable-display           | do not display flow information to stdout
```

###Examples


**1) generate flow information from a compressed pcap file**

```
zcat capture.pcap.gz | pcap_flows --stdin
```

2) output a specific flow to a seperate pcap file 

```
pcap_flows --extract 1234 raw_capture.pcap -o capture_flow_1234.pcap
```

3) extract a tcp stream from a pcap

```
pcap_flows --extract-tcp 1234 raw_capture.pcap -o capture_flow_as_tcp1234.pcap
```


### Output

Display flow info from hitcon defcon CTF capture


```

pcap_flows  /hitcon.pcap  --flow-packet-min 1000

1048549 FlowID:   592897 | TCP  00:10:18:72:00:3c -> 00:16:3e:ef:36:38 |  10.  5. 17.  2 ->  10.  5.  9.  2 |  43942 ->   8888  |             4,102 Pkts           288,909 Bytes
1048550 FlowID:   761379 | TCP  00:10:18:72:00:3c -> 00:16:3e:ef:36:38 |  10.  5.  3.  2 ->  10.  5.  9.  2 |  48716 ->   8888  |             4,113 Pkts           289,197 Bytes
1048551 FlowID:   981924 | TCP  00:10:18:72:00:3c -> 00:16:3e:ef:36:38 |  10.  5.  7.  2 ->  10.  5.  9.  2 |  42653 ->   8888  |             4,183 Pkts           294,250 Bytes
1048552 FlowID:   642639 | TCP  e0:3f:49:6a:af:a1 -> 00:10:18:72:00:3c |  10.  5.  9.102 ->  17.253.  2.226 |  63281 ->     80  |             4,301 Pkts           295,014 Bytes
1048553 FlowID:   902015 | TCP  00:10:18:72:00:3c -> 00:16:3e:ef:36:38 |  10.  5. 12.  2 ->  10.  5.  9.  2 |  36486 ->   8888  |             4,352 Pkts           305,988 Bytes
1048554 FlowID:    53839 | TCP  00:10:18:72:00:3c -> 00:16:3e:ef:36:38 |  10.  5. 16.  2 ->  10.  5.  9.  2 |  43103 ->   8888  |             4,715 Pkts           331,990 Bytes
1048555 FlowID:   658515 | TCP  00:10:18:72:00:3c -> 00:16:3e:ef:36:38 |  10.  5. 15.  2 ->  10.  5.  9.  2 |  45683 ->   8888  |             4,786 Pkts           337,001 Bytes
1048556 FlowID:    33656 | TCP  00:10:18:72:00:3c -> e0:3f:49:6a:af:a1 | 130.204. 67.136 ->  10.  5.  9.102 |   9025 ->  56574  |             4,930 Pkts           537,324 Bytes
1048557 FlowID:   643944 | TCP  00:10:18:72:00:3c -> 00:16:3e:ef:36:38 |  10.  5. 10.  2 ->  10.  5.  9.  2 |  44934 ->   8888  |             4,995 Pkts           351,892 Bytes
1048558 FlowID:     8462 | TCP  00:10:18:72:00:3c -> 00:16:3e:ef:36:38 |  10.  5.  2.  2 ->  10.  5.  9.  2 |  41809 ->   8888  |             5,126 Pkts           360,763 Bytes
1048559 FlowID:   627433 | TCP  00:10:18:72:00:3c -> 00:16:3e:ef:36:38 |  10.  5.  8.  2 ->  10.  5.  9.  2 |  44283 ->   8888  |             5,394 Pkts           379,946 Bytes
1048560 FlowID:    88064 | TCP  00:10:18:72:00:3c -> e0:3f:49:6a:af:a1 | 140.115. 50. 51 ->  10.  5.  9.102 |     22 ->  42271  |             6,102 Pkts           417,083 Bytes
1048561 FlowID:    24006 | TCP  00:10:18:72:00:3c -> e0:3f:49:6a:af:a1 |  74.125.129.189 ->  10.  5.  9.102 |    443 ->  61860  |             6,502 Pkts           658,192 Bytes
1048562 FlowID:   785299 | TCP  00:10:18:72:00:3c -> e0:3f:49:6a:af:a1 |  10.  5.  6.108 ->  10.  5.  9.102 |     80 ->  53303  |             6,559 Pkts         9,849,540 Bytes
1048563 FlowID:    23999 | TCP  e0:3f:49:6a:af:a1 -> 00:10:18:72:00:3c |  10.  5.  9.102 ->  74.125.129.189 |  61860 ->    443  |             6,588 Pkts         2,583,463 Bytes
1048564 FlowID:    33651 | TCP  e0:3f:49:6a:af:a1 -> 00:10:18:72:00:3c |  10.  5.  9.102 -> 130.204. 67.136 |  56574 ->   9025  |             6,609 Pkts           622,258 Bytes
1048565 FlowID:  1005605 | TCP  e0:3f:49:6a:af:a1 -> 00:10:18:72:00:3c |  10.  5.  9.102 ->  10.  5.  6.108 |  63779 ->     80  |             7,149 Pkts           453,291 Bytes
1048566 FlowID:   786260 | TCP  00:10:18:72:00:3c -> e0:3f:49:6a:af:a1 |  10.  5.  6.108 ->  10.  5.  9.102 |     80 ->  53413  |             8,367 Pkts        12,625,278 Bytes
1048567 FlowID:   642795 | TCP  e0:3f:49:6a:af:a1 -> 00:10:18:72:00:3c |  10.  5.  9.102 ->  54.183.128. 64 |  52940 ->  22222  |            10,502 Pkts         2,409,657 Bytes
1048568 FlowID:    88059 | TCP  e0:3f:49:6a:af:a1 -> 00:10:18:72:00:3c |  10.  5.  9.102 -> 140.115. 50. 51 |  42271 ->     22  |            10,955 Pkts        16,496,355 Bytes
1048569 FlowID:        1 | TCP  e0:3f:49:6a:af:a1 -> 00:10:18:72:00:3c |  10.  5.  9.102 ->  54.183.128. 64 |  51697 ->  22222  |            11,666 Pkts         3,839,832 Bytes
1048570 FlowID:  1005606 | TCP  00:10:18:72:00:3c -> e0:3f:49:6a:af:a1 |  10.  5.  6.108 ->  10.  5.  9.102 |     80 ->  63779  |            14,670 Pkts        21,774,873 Bytes
1048571 FlowID:        2 | TCP  00:10:18:72:00:3c -> e0:3f:49:6a:af:a1 |  54.183.128. 64 ->  10.  5.  9.102 |  22222 ->  51697  |            16,714 Pkts         1,830,744 Bytes
1048572 FlowID:   642798 | TCP  00:10:18:72:00:3c -> e0:3f:49:6a:af:a1 |  54.183.128. 64 ->  10.  5.  9.102 |  22222 ->  52940  |            16,997 Pkts         1,921,123 Bytes
1048573 FlowID:   642638 | TCP  e0:3f:49:6a:af:a1 -> 00:10:18:72:00:3c |  10.  5.  9.102 ->  17.253.  2.226 |  63280 ->     80  |            98,135 Pkts         6,584,162 Bytes
1048574 FlowID:   642642 | TCP  00:10:18:72:00:3c -> e0:3f:49:6a:af:a1 |  17.253.  2.226 ->  10.  5.  9.102 |     80 ->  63280  |           115,911 Pkts       245,630,927 Bytes
```

Extract only port 80 traffic from hitcon.pcap to a seperate file. This is the individual TCP port 80 -> 63280 flow.

1048574 **FlowID:   642642** | TCP  00:10:18:72:00:3c -> e0:3f:49:6a:af:a1 |  17.253.  2.226 ->  10.  5.  9.102 |     80 ->  63280  |           115,911 Pkts       245,630,927 Bytes

```
$ pcap_flows  hitcon.pcap  --extract 642642 -o /mnt/capture/hitcon_http.pcap --disable-display 

writing PCAP to [/mnt/capture/hitcon_http.pcap]
[/mnt/capture/hitcon_small.pcap] FileSize: 2GB
[02:00:30.000.332.313 0.000%] Flows:2 0.00M Pkts 0.000Gbps : 0.00GB Out:0.00GB
[05:10:22.000.316.568 0.307%] Flows:899478 2.66M Pkts 7.419Gbps : 0.79GB Out:0.25GB
[02:27:22.000.060.690 0.816%] Flows:1048576 9.71M Pkts 12.695Gbps : 2.16GB Out:0.25GB
```
