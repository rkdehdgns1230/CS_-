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

## Chapter 2. Application layer

network application program은 다음의 두 가지 구조 중 하나를 따른다. network application protocol 또한 마찬가지이다.
1. client-server
2. peer-to-peer (P2P)

주의 - 커뮤니케이션의 주체는 호스트 자체가 아니라 호스트에서 실행되고 있는 프로그램이다.

### client - server architecture

커뮤니케이션의 두 주체 중 하나는 서버, 나머지 하나를 클라이언트라고 부른다.

서버와 클라이언트의 특징

server
- 항상 켜져있는 host
- 영구적인 IP 주소
- 다수의 client에 응답 가능한 data center의 형태

client
- 서버와 통신
- 클라이언트 끼리는 통신하지 않는다.
- 통신할 때만 켜져있는 상태
- 동적 IP 주소를 할당 받는다.

client-server architecture에서는 `서버 호스트 상의 프로세스`와 `클라이언트 호스트 상의 프로세스`가 서로 통신을 하게 된다.

### P2P architecture

P2P 구조는 서버-클라이언트 구조와는 다르게 정해진 always-on 서버가 없고 서로 통신을 하는 구조이다.

이 때 통신의 주체를 peer라고 부르며, peers 간에 request와 response를 주고 받게된다.

따라서 새로운 peers가 생기면 service 요구량이 증가함과 동시에 service 수용량이 증가하게 되기 때문에 self scalability를 갖는다고 말할 수 있다.

하지만, 모든 peers가 항상 켜져있지 않고, ip 주소가 계속해서 변하기 때문에, 관리가 매우 복잡하다.

### Process communicating

앞서 network application program의 두 가지 구조를 살펴보았는데, 결국 통신의 주체는 host가 아니라 process가 된다.

process: host 상에서 실행되고 있는 program을 의미

같은 host내의 두 개의 processes가 통신하는 경우 inter-process communication

서로 다른 호스트끼리 통신하는 경우 messages를 교환하면서 통신한다.

process 통신에서 두 가지 종류의 process가 있다.
- client process: client host에서 실행중인 process. 통신을 시작하는 process
- server process: server host에서 실행중인 process. 접촉을 기다리는 process

### Sockets

application layer는 개발자에 의해 control 되는 영역이고, 그 아래 계층은 OS에 의해 control 되는 processes의 영역이다.

따라서 transport layer를 포함한 그 아래의 layer에서 동작하는 process에 우리는 접근할 수 없기 때문에, application layer에서 만들어진 message의 전송을 transport layer에게 부탁한다.

여기에 transport layer와 application layer 사이의 door의 역할을 하는 것을 `socket`이라고 부른다.

summary: socket은 application layer에서 전송하고 수신하는 message들이 드나드는 `통로`이다.

### Process간 통신에서 주소를 식별하는 방법

단순 32bit ip address 만으로는 process간 통신시 통신 위치를 구분할 수 없다.

여기에 더해 port number 정보가 추가로 필요하다.

따라서 `identifier = IP address + port #`인 것이다.

well-known port #
1. HTTP server: 80
2. Mail server: 25

특정 process에 대해서 전용으로 사용하는 port number를 well-known port number라고 부른다.

예를 들어 HTTP protocol에 따라 통신을 한다면 message에는
```
ip address: 128.119.245.11 (32bits, 8bits x 4)
port number: 80
```
위의 정보가 request를 요청할 process로의 identifier로서 작성되어야 한다.

### 어떤 transport service가 있을까?

data integrity
- 일부 apps은 reliable data가 요구되기도 하고
- 또 일부 apps은 약간의 loss를 허용하기도

timing
- 일부 apps은 low delay service를 요구할수도
- 그렇지 않을 수도

throughput
- 일부 apps은 minimum throughput을 최소치 이상 요구한다.
- 또한 나머지 일부 apps은 throughput과 상관없이 사용만 가능하면 된다. (elastic apps)

이에 따라서 서비스 요구사항에 맞는 transport service를 선택해야 한다.

### TCP vs UDP

실제로 internet transport service protocol에는 TCP, UDP 두 가지 종류가 존재한다.

각각의 특징은 따로 정리하겠지만, 일단 다음과 같이 정리할 수 있다.

TCP
- reliable transport
- flow control
- connection-oriented
- congestion control
- does not provide (timing, min throughput, guarantee, security)

UDP
- unreliable data transfer
- does not provide (reliability, flow control, congestion control, throughput guarantee, security, connection setup)

### Application layer protocol 정의

- 교환하는 메시지의 종류를 결정한다.
    - request, response message
- 메시지의 문법을 정의한다.
    - 메시지 내부의 필드와 필드 간의 구별법을 정의?
- 메시지가 어떻게 해석이 되어야 하는지
    - 필드내에 있는 정보의 의미
- 규칙
    - 언제, 어떻게 프로세스가 메시지를 전송하고 메시지에 응답하는지를 결정한다.

Application-layer protocol의 종류로는 크게 두 가지가 있다.
- 개방 프로토콜
    - RFC(Request For Comment, 인터넷 표준)에 정의되어 있다.
    - ex) HTTP, SMTP..
- 비개방 프로토콜
    - 어떤식으로 동작하는지 짐작을 할뿐 방식을 알 수 없다.
    - ex) Skype..

### WEB과 HTTP(Hypertext Transfer Protocol)

HTTP는 다양한 application을 위해 만들어진 protocol이지만, 그 중 가장 대표적인 application은 WEB이다.

web page는 여러 개의 objects로 구성되며, 여러가지 객체들에 대한 reference를 포함하는 HTML file 기반으로 구성되어 있다.

이러한 reference는 url의 형태로 object를 가리키고 있다.

```
ex) URL
www.someschool.edu/someDept/pic.png
host name + path name 으로 구성된다.
```

**Objects의 종류**
- HTML file
- JPEG images
- Java applet
- audio file
- ...

**HTTP는 client/server model로 동작**

`Client`: browser에 요청한 url에 맞는 web page를 위해 serverr로 request를 보내고 response를 받아서 web page를 사용자에게 보여준다.

`Server`: request에 맞는 objects를 전송한다.

firefox browser, safari browser 서로 다른 process이지만, HTTP protocol에 따라 server와 같은 종류의 통신이 가능하다.

### HTTP overview
1. WEB application을 위해 디자인된 protocol
2. client / server 구조를 따른다.
3. TCP를 사용한다.
4. stateless 하다. 

### Non-persistent, persistent HTTP

- 비지속 연결(non-persistent) HTTP
    - user에 요청에 따라 여러 개의 객체(object)를 요구하는 경우 객체를 가져올 때 마다 TCP connection을 맺어야 한다.

- 지속 연결(persistent) HTTP
    - 한 번의 connection으로 여러 개의 객체를 가져온다.

최초의 HTTP는 non-persistent였으나 non-persistent의 단점을 개선하기 위해 persistent HTTP로 변경되었다.

예를 들어 TCP connection 이후 url에 따른 request의 응답으로 base HTML을 response로 전송 받는다.

이후 base HTML이 참고하고 있는 여러 개의 objects를 client가 parsing하여 확인한 후 이 여러 개의 objects를 가져오는데

한 번의 connection으로 모든 objects를 가져온다면, persistent, 그렇지 않은 경우 non-persistent 방식에 해당

### non-persistent, persistent HTTP에서의 응답 시간

우선 아래의 그림과 같이 HTTP protocol에 따라 client와 server가 통신을 한다고 하자.

![image](https://user-images.githubusercontent.com/87526189/184528977-358c470e-0d04-420e-9592-1d22195d02d9.png)

RTT(Rount Trip Time): packet이 client -> server, server -> client로 이동하는데 걸리는 시간을 의미

이럴 때 non-persistent HTTP 방식으로 통신하면 우선 위 과정에서만 base HTML 파일을 가져오는데 2RTT의 시간이 소모된다. `TCP connection을 위한 1RTT + base HTML을 가져오기 위한 1RTT`

만약 base HTML 파일을 parsing 했을 때 추가적인 참고 objects가 필요하다면, `2RTT * # of objs` 만큼의 시간이 추가적으로 필요하게 된다.

반면에, persistent HTTP 방식으로 통신하는 경우 TCP 통신을 한 번만 하면 이후에 object를 가져오기 위해 TCP connection을 형성할 필요가 없기 때문에 `2RTT + # of objs * 1RTT` 만큼의 시간이 소모된다.

`위 과정은 일단 file transmission은 고려하지 않는 상황을 가정한 설명이다`

### HTTP request message

앞서 정리한 바와 같이 HTTP protocol에 따라 통신을 하는 경우 request, response 두 가지의 message가 존재한다.

![image](https://user-images.githubusercontent.com/87526189/184542496-22bad173-e86b-41bf-bec3-53044c45ec7d.png)

request message 구성
1. 요청 라인(request line)
    - 방식: 서버에게 요청할 작업의 종류를 명시
    - URL: 요청하는 파일의 URL
    - 버전: 클라이언트가 사용하는 HTTP의 버전을 명시
2. 헤더 라인(header line)
    - header field의 이름과 값의 쌍
    - hostname: name_of_the_host..
3. 공백 라인
4. entity body

method type
1. HTTP/1.0
    1. GET: 단순히 url에 해당하는 page를 요청할 때 사용
    2. POST: form input을 제공했을 때 이것을 반영해서 웹 페이지를 요청할 때
    3. HEAD: 주로 개발 과정에서 테스트시 사용되며, object 없는 response message만 받아오고 싶을 때 사용한다.
2. HTTP/1.1 이후
    1. GET, POST, HEAD
    2. PUT: server에 파일을 upload하고 싶을 때 사용
    3. DELETE: server에서 파일을 삭제하고 싶을 때 사용


![image](https://user-images.githubusercontent.com/87526189/184549011-cb2d7271-8135-46e8-99fd-61cb33eee192.png)

response message 구성
1. 상태 라인(status line)
    - 버전: 서버에서 사용하는 HTTP의 버전 정보
    - 상태 코드: response의 상태를 전달
    - 상태 구문: 상태 코드와 같은 기능이나 사람이 이해하기 쉽게
2. 헤더 라인(header line)
    - 헤더 필드 이름과 값을 쌍으로 표기된다.
    - date, server, last_modified, connection 등의 필드 이름과 그에 따른 값을 표기하는 구역이다.
3. 공백 라인
4. entity body
    - request에 따른 response message에 실어 보낼 객체들을 body에 담아서 전송한다. ex) html file, images, video..

HTTP status code
- 200: response message의 body에 요청된 객체가 실려있음을 의미
- 301: 요청된 객체의 위치가 다른 곳으로 옮겨져 저장되어 있는 경우
- 400: request message가 잘못되어 해석이 불가능한 경우
- 404: 요청된 url에 대한 웹 페이지가 서버에 없는 경우
- 505: client의 HTTP 버전을 서버가 지원하지 못하는 경우

--------------------------

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
  

## References
Introduction to TCP/IP - yonsei university  
https://namu.wiki/w/%EC%84%9C%EB%B8%8C%EB%84%B7%20%EB%A7%88%EC%8A%A4%ED%81%AC  
광운대학교 컴퓨터네트워킹-이혁준 교수님 강의  
