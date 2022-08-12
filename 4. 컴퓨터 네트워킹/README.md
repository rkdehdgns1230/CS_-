# 컴퓨터 네트워킹
  
## Internet and internet
Internet: 전세계의 host와 상호 통신이 가능한 대규모 네트워크 전체를 의미 (network of networks)  
internet: Internet보다 작은 복수의 네트워크를 의미 (2개 이상의 host가 연결된 경우 internet이라고 한다.)
  
Internet ("nuts and bolts" view)

## 네트워크의 구성 요소
1. network edge
    - hosts = end systems(network의 가장자리에 있다.)  
application program을 실행(hosting)해줘서 host라고 부른다.

2. network core
    - router or switch: 사용자의 message가 목적지로 찾아갈 수 있도록 돕는 컴퓨터

3. access networks, physical media
    - wired, wireless communication links
    - network core, network edge를 연결하는 역할을 수행

router와 router 또는 router와 host를 연결해주는 것을 link라고 부른다.

### Protocol

통신 프로토콜 또는 통신 규약은 컴퓨터나 원거리 통신 장비 사이에서 메시지를 주고 받는 양식과 규칙의 체계를 뜻한다.

프로토콜은 msg의 양식, 네트워크 개체 간에 msg를 주고 받는 순서 그리고 msg 송수신시 수행할 행동 들을 정의한다.

### Internet standards

RFC: Request for comments  
IETF: Internet Engineering Task Force

protocol의 표준화는 매우 중요하다. Internet protocol의 표준화 기관을 IETF라 하고 이 곳에서 발표한 표준안이 RFC이다.

## 네트워크 가장자리(Network Edge)

network edge 구성 요소
- end systems(hosts)
- access networks
- links(physical media)

### Access networks
network edge를 network core로 연결해주는 역할을 수행하는 network 유형이다.

**access network의 특성**

bandwidth(transmission rate, Mbps Gbps): 단위 시간당 실어나를 수 있는 bit 수를 의미한다.

`shared / dedicated`로 network access 제공 방식을 구분

#### Digital subscriber line (DSL):  
![image](https://user-images.githubusercontent.com/68600592/183641778-e1d5109f-4736-4564-ba24-e57c6f44c1c8.png)

전화 회사에서 제공해주는 access network  
각각의 집마다 dedicated line(with different frequencies)을 통해 central office와 연결된다. 

DSL modem을 각각의 집마다 가지고 있어 DSL modem에 컴퓨터를 연결해서 인터넷과 연결될 수 있다. 

splitter를 이용해 전화선과 인터넷선을 분할한다.

DSLAM (DSL access multiplexer): 일종의 multiplexer, 모든 집의 회선을 받아 multiplexing 전화선이면 telephone network로 인터넷 선이면 인터넷쪽(ISP)로 연결

#### Cable network: 
![image](https://user-images.githubusercontent.com/68600592/183641936-80fcc065-5591-4de2-a0bb-d36e2d480c94.png)

cable network 회사를 통해 access network를 제공받는 방식, 여러 가구가 shared link(bandwidth가 굉장히 큼)를 사용해 연결된다.

cable modem을 각각의 집마다 가지고 있어 cable modem에 컴퓨터를 연결해 인터넷에 접속이 가능하다.

splitter에서는 cable modem과 TV로 가는 회선을 분리하는 역할을 수행, cable headend (전화 회사의 central office 개념)와 연결된다.

CMTS (cable modem termination system): cable modem에 연결된 hosts가 인터넷에 연결되도록 돕는 시스템

HFC (hybrid fiber coax): CMTS 또한 여러 개가 존재하여 네트워크를 형성하는데, CMTS 끼리는 굉장히 큰 대역폭을 갖는 fiber 회선으로 연결되고, cable model와 CMTS가 coax로 연결되어 HFC라는 이름으로도 cable network가 불린다고 한다.

#### home network:
![image](https://user-images.githubusercontent.com/68600592/183641978-c005790b-e213-4f5b-a33c-b3519377714f.png)

집을 internet에 연결하는건 cable network or DSL, 집 내부에는 home network가 존재한다. 여러 개의 pc, smartphone 등이 home network에 연결되고, home network가 전화 회사 network or cable 회사 network로 연결된 후 인터넷으로 연결되는 구조를 갖는다.

home network의 core에는 router가 존재, router에는 여러 개의 pc와 wifi access point가 연결될 수 있다. 

즉, home network에서 router는 여러 개의 end systems(hosts)를 묶어 DSL modem or cable modem에 연결하는 역할을 수행한다.

주로 서비스를 제공할 때 router와 wifi access point를 하나의 박스로 묶어서 제공한다. 

#### Enterprise access networks (Ethernet):
![image](https://user-images.githubusercontent.com/68600592/183642021-fe48ba21-1477-45c8-ab98-f334a28de5e5.png)

학교 혹은 회사에는 home network보다 많은 hosts(end systems)이 존재한다. 이러한 네트워크에는 여러 개의 ethernet switch를 router와 함께 이용해서 access network와 연결될 수 있도록 돕는다.

이더넷(ethernet)은 네트워크 상에서의 통신 방식 중 하나를 의미하고, 빛의 전달 물질인 에테르(ether)에서 이름이 유래했다고 한다. 유선 인터넷이 된다면, 이더넷 통신 방식을 사용하면 된다고 보면 된다고 함.

ex) 한 건물(or 한 개의 방)에 ethernet swtich를 배치해 건물 내부의 모든 hosts를 연결, 각 건물마다 배치된 ethernet switch가 router와 연결되어 `ISP의 router`와 연결된다.

`기관의 network는 규모가 크다 보니 전화 회사나 케이블 회사를 거쳐 Internet과 연결되지 않고, 학교나 기관을 대표하는 router가 직접 ISP(Internet service provider)의 router와 연결된다.`

`router는 dedicated link를 통해 연결되는데, 이 전용 회선은 ISP에서 직접 제공한다.`

#### Wireless access networks

smartphone을 이용해 wife(802.11b/g, 11/54 Mbps)나 3G, LTE, 4G, 5G(cellular network) 등을 통해 인터넷에 연결되는 경우를 의미한다.

wifi: 건물 내에서, wireless LANs
cellular network: wide-areaw wireless access

#### Host
network application program을 hosting하고 있으며, data에 대한 packets(message)를 전송하는 주체

Data를 packet이라 불리는 chunk로 잘라서 전송한다. packet의 길이를 L, packet을 access network로 전송하는 transmission rate를 R로 부르자.

`packet transmission delay` = `time needed to transmit L-bit packet into link` = $L(bits)/R(bits/sec)$

위의 수식처럼 transmission delay를 표현할 수 있다.

#### Physical media

packet의 이동 통로(link)

2가지 종류로 나뉜다.
- guided media: signals propagate in solid media, e.g. copper(Ethernet), fiber(HFC), coax(HFC)..
- unguided media: signals propagate freely, e.g. radio(WiFi, cellular network)..

**coax, fiber(유선 방식)**

coaxial cable, fiber optic cable 등이 존재.

**radio link**

radio link 특징
1. 전자기파를 통해 전달.
2. 물리적인 회선 없음
3. 반사, 장애물에 의한 가로막힘, 간섭 등이 발생
4. 양방향

radio link types
- terrestrial microwave
- LAN (e.g. WiFi): 와이파이는 300m 내외만 커버 가능 -> 건물 내에서만 사용 가능
- wide-area(e.g. cellular): 수십km coverage area
- satelite

## 네트워크 중심(Network Core)

network core는 source host에서 destination host으로 사용자의 message(packet)을 전달하는 것을 목표로 한다.

**Packet 전송 방식 2가지**
- packet switching
- circuit switching

### Circuit Switching

주로 전화 network에서 사용하는 전송 방식이다.

반드시 user의 call이 있어야 시작되며, 이러한 방식을 `call-setup` 방식이라고 한다.

`call-setup` 단계에서 source-destination 사이의 경로 결정 및 경로 형성을 위한 resources를 reserve하는 작업을 수행한다.

미리 자원을 분할하고, 요청이 들어오는 경우 남은 분할된 자원을 할당해주는 방식으로 resource를 제공한다.

#### Resource 분할 방식

1. FDM (Frequency Domain Multiplexing)
2. TDM (Time Domain Multiplexing)

**FDM**

frequency domain으로 resource를 나눈다.

**TDM**

time domain으로 resource를 나눈다.

### Packet Switching

전화 network 상에서의 통신에는 `circuit switching` 방식이 적합할 수 있으나, 새롭게 등장한 인터넷 통신에는 continuous한 통신이 주가 아니기 때문에, `circuit switching` 방식이 적합하지 않게 되어 (자원의 낭비가 심함) `packet switching` 방식이 등장했다.

Packet swtiching은 `no call-setup`, `no resource reserved` 이다.

전달할 데이터가 있는 경우 link 대역폭 전체를 사용해서 전송 `each packet transmitted at full link capacity` host가 data를 packets 단위로 쪼갠 뒤에 packet 단위로 전송한다.

다른 host에 의해 전송 불가하면, 전송 끝날 때까지 대기한다.

각 packet은 목적지 주소를 가지고 있으며, router에서 packet의 목적지 주소를 기반으로 다음 경로(router or switch)를 선택한다.

이 때, 목적지를 확인하기 위해서는 전체 packet을 수신한 뒤에 가능하기 때문에, 저장한 후에 전송을 한다고 해서 `store and forward` 방식이라고 부른다.

#### queueing delay, loss

packet 전송 대기열인 queue에서 packet이 대기하는 시간을 queueing delay라고 한다. 이 queue의 길이는 무한할 수 없기 때문에, 길어진 queueing delay로 인해서 packet loss가 발생하게 된다.

#### Congestion 발생 가능

Circuit Switching과는 다르게 resource를 예약해서 사용하지 않기 때문에, congestion이 발생할 수 있다. circuit switching에 비해 resource sharing 측면에서 탁월하고, call setup 과정이 없어 빠르지만, 문제는 congestion.

특히 audio, video data 같은 경우 delay에 민감하기 때문에, 어느 정도의 bandwidth를 보장해야 한다. 이건 여전히 문제라고 한다.

### Internet structure

인터넷의 network의 network 형태의 구조를 갖는다. 따라서 매우 복잡

수 백만개의 access network가 인터넷 상에 존재하고, 이를 fully connected 하게 연결하면 굉장히 비효율적이기 때문에, 이를 위해서 `ISP`라는 것이 존재한다.

#### ISP (Internet Server Provider)

IPS는 개인 또는 기업체에게 인터넷 접속 서비스를 제공하는 회사를 의미한다. 한국에는 대표적으로 KT, LG U+, SK브로드밴드 등이 있다고 한다. 인터넷은 이러한 ISP들의 interconnection으로 구성되어 있다. 

ISP의 규모에 따라 `global ISP, regional ISP, instituitional ISP` 등으로 구분된다.

#### IXP (Internet Exchange Provider)

ISP끼리 연결해주는 사업자. ISP는 peering link를 통해 연결된다.

#### Content Provider networks

Google, Microsoft 같은 회사들이 자체적으로 services, contents를 제공하는 네트워크를 운영하는데, 이를 content provider network라고 부른다. 전세계에 위치한 data center에 연결되어 content를 연결하지만, 한계가 있기 때문에 1 tier ISP에 연결되어있음. (하지만 1 tier ISP에 의존적이지는 않다.)

----------------------

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
  
• **Default gateway**  
Default gateway는 이 PC에 대한 모든 internet IP packets를 주고받을 전용 internet router이다. 집이나 사무실같은 환경에서 default gateway는 local network를 Internet으로 연결하는 DSL router나 cable router같은 device를 의미한다. (Access network에서의 Router를 의미한다고 이해했다.)
  
router <-> gateway, 
  
• **CIDR (Classless Inter-Domain Routing)**  
  
CIDR은 1993년 IETF에 의해 도입된 방식으로 IP address를 효율적으로 할당할 수 있게한다. 기존의 IP address 할당 방식이던 network class를 대체했고, 클래스 없는 도메인간 라우팅 기법이라고 불린다.  
  
e.g. x.x.x.x/24, x.x.x.x/16  

위와 같이 기존의 IP address에 /24, /16 같은 수를 붙이는 표기법을 사용하며, IP 주소에서 이 숫자만큼의 비트를 묶어 하나의 CIDR 그룹에 포함된다고 판단한다.  
  
• **VLSM (Variable-Length Subnet Mask)**  
  
CIDR는 VLSM(Variable-Length Subnet Mask)을 사용하며, 이는 기존의 FLSM(Fixed Length Subnet Mask)와 같이 고정된 개수로 서브넷을 할당하는 비효율 적인 방식을 해결할 수 있다.

123.234.100.56/24
IPv4 address (32bits): 123.234.100.56  
Subnet mask with 24 ones  
11111111.11111111.11111111.00000000 => 255.255.255.0  

=> Subnet size = 2^(32 - 24) = 2^8 = 256 => 256개의 IPv4 address가 서브넷에 존재한다.  
이처럼 CIDR을 사용하는 경우 동적으로 서브넷사이즈(IP address의 수)를 조절할 수 있게 된다.
  
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
광운대학교 컴퓨터네트워킹-이혁준 교수님 강의  
