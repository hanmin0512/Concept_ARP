# Concept_ARP
- Address Resolution Protocol - > ARP 개념 및 원리에 대해 알아볼 것이다.

## 개념
- IP 주소에 맞는 MAC 주소를 알려주는 프로토콜이다.
- IP Address : 논리적인 주소
- MAC Address : 물리적인 주소 (하드웨어주소 NIC)

## 동작 원리
- 시나리오 : 같은 Wifi를 사용중인 A 와 B가 처음으로 통신을 하려고 한다. 통신을 하려면 상대방의 MAC주소를 알아야 통신을 할 수있다.
- 정보
![ARP_concept1](https://github.com/hanmin0512/Concept_ARP/assets/37041208/94ae808f-6720-441e-903a-cd43e57a36ca)

- A는 B의 논리적 주소 192.168.0.24를 이용해 B의 MAC 주소를 알아낸다.
- 1. A는 192.168.0.24의 MAC주소를 요청하는 패킷을 Broadcast 주소로 패킷을 전송한다.
  2. Broadcast에서는 A의 요청 패킷을 받아 같은 네트워크의 모든 노드(클라이언트)에게 IP주소가 192.168.0.24가 맞냐고 묻는 패킷을 Broadcasting 한다.
  3. IP주소가 192.168.0.24가 아닌 노드는 응답을 하지 않는다.
  4. IP주소가 192.168.0.24인 B노드는 A노드에게 유니케스트(1:1) 통신으로 자신의 MAC주소가 담긴 ARP 패킷을 전송한다.
  5. A는 B(192.168.0.24)의 MAC주소(A5:6F:F5:5A:84:AC)를 알아내고 자신의 ARP cache 테이블에 기록한다.
  6. A는 B와 통신을 할 수 있게 되었다.
