## Protocol
통신 프로토콜 또는 통신 규약은 컴퓨터나 원거리 통신 장비 사이에서 메시지를 주고 받는 양식과 규칙의 체계를 뜻한다.
  
## Internet and internet
대문자로 시작하는 Internet은 전세계의 host와 상호 통신이 가능한 대규모 네트워크 전체를 의미하고, 소문자로 시작하는 internet은 Internet보다 작은 복수의 네트워크를 의미한다. (2개 이상의 host가 연결된 경우 internet이라고 한다.)
  
## ISP (Internet Server Provider)
IPS는 개인 또는 기업체에게 인터넷 접속 서비스를 제공하는 회사를 의미한다. 한국에는 대표적으로 KT, LG U+, SK브로드밴드 등이 있다고 한다. 인터넷은 이러한 ISP들의 interconnection으로 구성되어 있다. 
 
ISP의 규모에 따라 global ISP, regional ISP, instituitional ISP 등으로 구분된다.
  
## Routing table
  
 
## IPv4
IPv4는 internet protocol version 4를 뜻하며, 전 세계적으로 사용된 첫 번째 internet protocol이다. IPv4는 패킷 교환 네트워크(packet switching network)상에서 데이터를 교환하기 위해 사용하는 프로토콜이다.  
  
데이터가 정확하게 전달되는 것을 보장하지 않고, 잘못 전달될 가능성이 존재하지만, 이에 대한 부분은 상위 layer의 protocol인 TCP or UDP에서 보장한다.

IPv4의 주소체계는 총 12자리이며, 네 개의 부분으로 나누어진다. 각 부분은 8bits = 1byte 크기로 표현되기 때문에 0 ~ 255 범위의 값을 갖고, 네 개의 부분이 합쳐져 총 32bits = 4byte로 구성된다.
  
하나의 장치(computer or smartphone)에도 여러 개의 interfaces가 존재하는 경우 각 interface에 IP address가 하나씩 할당되어야 한다. ex) mobile communication(4G, 3G, 2G), Wi-Fi, Bluetooth 등 interfaces마다 다양한 통신 양식을 갖고 있다.

최근에는 인터넷 사용자의 증가로 인한 주소의 고갈 문제로 인해 IPv6가 등장해 주류로 사용되고 있다.

- Subnet Mask
IP address는 네트워크 부분과 호스트 부분으로 나누어진다. 여기서 하나의 로컬 네트워크는 하나의 라우터(Router)를 거쳐가는 여러 개의 호스트들이 연결된 broadcast 영역을 의미한다. (여기서 말하는 호스트란 pc, 스마트폰, 노트북, 테블릿pc 등을 의미한다.)
  
IP 주소를 실제 주소 형식인 "서울시 구로구 ~동 ~건물 ~호"라고 한다면, 같은 건물의 다른 호수에 해당하는 주소로 찾아가는 경우 건물 밖을 나갈 필요가 없이 이동이 가능한 것 처럼 네트워크 통신에서도 효율적인 네트워크 통신과 broad casting을 위해 장치들을 일정한 규칙에 따라 하나의 그룹으로 묶고자 하였고, 이를 서브넷(subnet)이라는 개념이라고 한다. (이렇게 서브넷 내의 호스트는 서브넷 내의 다른 호스트랑만 통신이 가능하다고 한다.)  
  
만약 다른 서브넷의 호스트와 통신하고자 하는 경우, 다시 비유 예시로 돌아가면 다른 건물의 다른 집으로 찾아가는 경우에 해당하고, 이를 위해서는 건물의 출입구를 거쳐야 하듯이, 네트워크 통신에서는 게이트웨이(gateway)를 거쳐야 다른 서브넷의 호스트와 통신이 가능하다.  
  
다시 본론으로 돌아오면, 서브넷 마스크는 서브넷을 구분하는 방법 중 하나로 예시에 비교해서 다시 설명하면 서브넷 마스크를 같은 건물 한채로 비유할 수 있다. 즉, 서브넷 마스크를 이용해서 로컬 네트워크(서브넷)에 속하는지 판단할 수 있다.
  
서브넷마스크(subnet mask)는 32bits 숫자로 0은 호스트 부분을 1은 네트워크 부분을 나타내기 위해 사용한다. 이러한 방식으로 서브넷마스크를 이용해 IP address를 네트워크 주소와 호스트 주소로 분리할 수 있다.
  
**서브넷마스크의 특징**  
  
Internet은 Subnets으로 나눠지고, Subnets은 더 작은 subnets으로 나뉘어진다.  
SubnetMask는 Client(PC)가 연결되어있는 Subnet의 크기에 기반한다.  
IPv4 Subnet Mask는 32bits로 규격화된다. (1s, 0s의 sequence left(MSB) -> right(LSB))

서브넷마스크는 패킷이 이 서브넷에 속하는지 아닌지를 쉽게 판단하기 위해서 IP address를 mask(filter)하기 위해 사용한다.

- Default gateway
Default gateway는 이 PC에 대한 모든 internet IP packets를 주고받을 전용 internet router이다. 집이나 사무실같은 환경에서 default gateway는 local network를 Internet으로 연결하는 DSL router나 cable router같은 device를 의미한다. (Access network에서의 Router를 의미한다고 이해했다.)
  
router <-> gateway, 

## DNS(Domain Name System)
  
DNS는 IP 네트워크에서 사용하는 시스템으로 domain name을 IP address로 변환해주는 역할을 수행한다. 이러한 DNS를 운영하는 서버를 네임서버(Name Server)라고 하며, 규모가 있는 사이트의 경우 네임 서버를 자체적으로 운영하기도 한다고 한다.  
  
간단하게 설명하면, 우리가 인터넷 브라우저를 통해 웹 서핑 및 이메일등을 사용하는 경우 도메인 이름을 브라우저 창에 입력해서 다양한 주소의 웹 페이지를 이용하는데, DNS는 이러한 도메인 이름을 222.222.222.222 같은 IP 주소 형식으로 변환하는 작업을 담당하는 시스템이라고 정리할 수 있을 것 같다.  
  
e.g. www.facebook.com -> 173.252.110.27

## DHCP(Dynamic Host Configuration Protocol)
  
네트워크 상에서 동적으로 IP주소 및 기타 구성 세부 정보(subnet mask, default gateway, dns server ip address, lease time  등..)를 부여 및 관리하는 protocol이다.  

**장점:**  
현재 pc를 사용 중인 사용자에게만 IP address가 할당되기 때문에, 고정 IP에 비해 IP address 절약 효과가 있다. 또한 사용자가 직접 네트워크 정보를 설정할 필요 없이 자동으로 설정을 관리해주기 때문에, 네트워크 관리가 용이해진다.  
 
**단점:**  
IP address를 할당해주는 DHCP 서버에 전적으로 의존하기 때문에, 서버가 다운되는 경우 IP 주소를 할당받을 수 없는 문제가 발생한다. Lease time 이전에 PC를 off하는 경우 Lease time이 끝날 때까지 해당 IP address가 다른 단말에 부여될 수 없다.
  
**DHCP의 특징:**  
우선 DHCP protocol에 따라 PC같은 단말이 서버와 통신하는 단계는 다음과 같다.  
  
1. **DHCP discover (client side)**: 단말(client)에서 DHCP 서버를 찾는 단계이다. 동일 서브넷에 있는 모든 단말은 해당 메시지를 수신한다.
2. **DHCP offer    (server side)**: DHCP 서버에서 client의 discover 메시지에 따른 응답이다. IP address를 제공받고 싶은지 여부를 확인하기 위해 client로 전송한다.
3. **DHCP request  (client side)**: 단말(client)에서 IP address를 DHCP 서버에 요청하고 싶은 경우 해당 메시지를 전송한다.
4. **DHCP ack      (server side)**: 요청한 IP address 및 필요한 다양한 네트워크 정보를 Ack 메시지와 함께 단말로 전송한다.
  

## TCP/IP and OSI 7 layer
TCP(Transmission Controlo Protocol)
  



## References
Introduction to TCP/IP - yonsei university  
https://namu.wiki/w/%EC%84%9C%EB%B8%8C%EB%84%B7%20%EB%A7%88%EC%8A%A4%ED%81%AC  
