# ESP8266 AT Command



# TCP Connect & HTTP Request

```
AT+CIPSTART="TCP","172.20.10.12",80
AT+CIPSTART="TCP","192.168.1.69",80

AT+CIPSTART="TCP","simplewebflask.herokuapp.com",80

AT+CIPSEND=<length>

AT+CIPSEND=9
GET /

AT+CIPSEND=15
GET /submit

AT+CIPSEND=13
GET /haha

AT+CIPCLOSE
//====================================
14+2
20+2
38+2

AT+CIPSEND=40

GET / HTTP/1.1
Host:172.20.10.12:80
//================

AT+CIPSEND=44

GET /haha HTTP/1.1
Host:172.20.10.12:80
//==========

AT+CIPSTART="TCP","simplewebflask.herokuapp.com",80

https://simplewebflask.herokuapp.com
```





# 掃描 WIFI 基地台

```

AT+CWLAP 

: 列出附近偵測得到的基地台
注意, 此指令只能在 STA (=1) 與 BOTH (=3) 模式下才會回應, 在 AP 模式下會出現 ERROR.
AT+CWLAP                                                                       
+CWLAP:(2,"edimax.setup",-71,"74:da:38:15:16:00",1)                            
+CWLAP:(3,"bryan",-90,"78:54:2e:26:66:28",1)                                   
+CWLAP:(3,"TP-LINK_33C1",-86,"c4:e9:84:66:33:c1",4)                            
+CWLAP:(4,"ching",-84,"54:b8:0a:84:f4:70",5)                                   
+CWLAP:(4,"HOME",-70,"04:8d:38:52:ea:f7",6)                                    
+CWLAP:(4,"alex",-85,"fc:75:16:01:26:0c",6)                                    
+CWLAP:(4,"andy",-85,"fc:75:16:02:61:60",6)                                    
+CWLAP:(1,"JANE-WIRELESS",-94,"00:24:01:ad:a0:65",6)                           
+CWLAP:(4,"RFTQAD",-93,"c8:d3:a3:5f:d8:fd",9)                                  
+CWLAP:(3,"TP-LINK_601A04",-73,"e8:de:27:60:1a:04",10)                         
+CWLAP:(4,"EDIMAX-tony",-44,"90:1f:02:2d:5a:9f",11)  我的基地台                    
+CWLAP:(3,"CHT5668",-89,"d8:fe:e3:5c:c0:fb",11)                                
+CWLAP:(3,"MOTOROLA-5N6F",-89,"f8:35:dd:74:d2:b6",11)                          
+CWLAP:(3,"45-9",-91,"d8:fe:e3:e6:90:87",11)                                   
+CWLAP:(3,"family",-89,"6c:19:8f:b7:9a:79",1) 
```



# 連結指定WIFI網路

```
AT+CWJAP="SSID","PWD" : 連線指定之基地台 (Join AP)
AT+CWJAP="EDIMAX-tony","123456789111"

OK 
```



# 查詢自己目前的IP位址

```
連線成功後再下 AT+CIFSR 查詢新指派的 IP, 還沒下 CWJAP 連線前為 0.0.0.0  :                                                                           
AT+CIFSR

192.168.2.105
```

