## Protocol
통신 프로토콜 또는 통신 규약은 컴퓨터나 원거리 통신 장비 사이에서 메시지를 주고 받는 양식과 규칙의 체계를 뜻한다.
  
## Internet and internet
  
## ISP (Internet Server Provider)
  
## TCP/IP and OSI 7 layer
  
## Routing table
  
 
## IPv4
IPv4는 internet protocol version 4를 뜻하며, 전 세계적으로 사용된 첫 번째 internet protocol이다. IPv4는 패킷 교환 네트워크(packet switching network)상에서 데이터를 교환하기 위해 사용하는 프로토콜이다.  
  
데이터가 정확하게 전달되는 것을 보장하지 않고, 잘못 전달될 가능성이 존재하지만, 이에 대한 부분은 상위 layer의 protocol인 TCP or UDP에서 보장한다.

IPv4의 주소체계는 총 12자리이며, 네 개의 부분으로 나누어진다. 각 부분은 8bits = 1byte 크기로 표현되기 때문에 0 ~ 255 범위의 값을 갖고, 네 개의 부분이 합쳐져 총 32bits = 4byte로 구성된다.
  
하나의 장치(computer or smartphone)에도 여러 개의 interfaces가 존재하는 경우 각 interface에 IP address가 하나씩 할당되어야 한다. ex) mobile communication(4G, 3G, 2G), Wi-Fi, Bluetooth 등 interfaces마다 다양한 통신 양식을 갖고 있다.

최근에는 인터넷 사용자의 증가로 인한 주소의 고갈 문제로 인해 IPv6가 등장해 주류로 사용되고 있다.

- Subnet Mask
서브넷마스크(subnet mask)는 32bits 숫자로 0은 호스트 부분을 1은 네트워크 부분을 나타내기 위해 사용합니다. 이러한 방식으로 서브넷마스크를 이용해 IP address를 네트워크 주소와 호스트 주소로 분리할 수 있다.
  
서브넷마스크의 특징  
Internet은 Subnets으로 나눠지고, Subnets은 더 작은 subnets으로 나뉘어진다.  
SubnetMask는 Client(PC)가 연결되어있는 Subnet의 크기에 기반한다.  
IPv4 Subnet Mask는 32bits로 규격화된다. (1s, 0s의 sequence left(MSB) -> right(LSB))

서브넷마스크는 패킷이 이 서브넷에 속하는지 아닌지를 쉽게 판단하기 위해서 IP address를 mask(filter)하기 위해 사용한다.

- Default gateway
Default gateway는 이 PC에 대한 모든 internet IP packets를 주고받을 전용 internet router이다. 집이나 사무실같은 환경에서 default gateway는 local network를 Internet으로 연결하는 DSL router나 cable router같은 device를 의미한다.
router <-> gateway, 

## DNS(Domain Name Server)
DNS는 hostnames을 IP address로 변환해주는 서버를 의미합니다.  
ex) www.facebook.com -> 173.252.110.27

## DHCP(Dynamic Host Configuration Protocol)



## References
Introduction to TCP/IP - yonsei university
