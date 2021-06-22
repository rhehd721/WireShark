# WireShark

## 용어
- SRC port : 발신 주소
- DES port : 수신 주소
- TCP Segment Len
- Sequence Number : 몇번째 보내는 패킷인지
- Sequence Number (raw)
- Next Sequence Number
- Acknowledgment Number : 이제 몇번째 받을 차례인지
- Acknowledgment Number (raw)
- Header Length : 내가 보낸 패킷의 크기가 얼마인지
- Flags : 내가 하고싶은 말의 상태? (급한지 여유로운지 ?)
- Window Size : 내가 받을 수 있는 패킷의 크기
- Checksum : 데이터가 전송 중에 손실되지 않았는지 검사
- Urgent Point : 긴급 데이터가 전송 되는 경우 데이터의 마지막 Byte의 일련번호를 표시

## 필터링

- TCP, UDP
	- : tcp.port == 1004  or  : udp.port == 1004

    - 포트 목적지 포트 번호로 검색
	    - : tcp.dstport == 1004  or  : udp.dstport == 1004  

    - 포트 출발지 포트 번호로 검색  
	    - : tcp.srcport == 1004  or  : udp.srcport == 1004

- 무선랜 사용 시
	- : wlan.addr == 00:0C:29:78:96:2C   

    - 무선랜 사용 시 출발지 MAC 주소로 검색
	    - : wlan.sa ==  00:0C:29:78:96:2C  

    - 무선랜 사용 시 목적지 MAC 주소로 검색
	    - : wlan.da ==  00:0C:29:78:96:2C 

- 출발지나 목적지 MAC 주소로 검색
	- : eth.addr == 00:0C:29:1D:1F:0F   

    - 출발지 MAC주소 검색
	    - : eth.src == 00:0C:29:1D:1F:0F  

    - 목적지 MAC주소 검색
	    - : eth.dst == 00:0C:29:1D:1F:0F  


- 출발지나 목적지 IP주소로 검색
	- : ip.addr == 192.168.0.10  

    - 출발지 IP주소로 검색
	    - : ip.src == 192.168.0.20  


- icmp를 제외한 모든 패킷 검색
	- : not icmp

    - icmp 패킷 검색
	    - : icmp (icmp는 ping 프로그램에서 사용되기 때문에 ping 패킷만 확인할때)

- DHCP 패킷 검색
	- : bootp (와이어샤크에서는 아직까지도 bootp를 dhcp로 인식한다.)








