# Chapter 1. Roadmap

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

# Chapter 2. Application layer

network application program은 다음의 두 가지 구조 중 하나를 따른다. network application protocol 또한 마찬가지이다.
1. client-server
2. peer-to-peer (P2P)

주의 - 커뮤니케이션의 주체는 호스트 자체가 아니라 호스트에서 실행되고 있는 프로그램이다.

## client - server architecture

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

## P2P architecture

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

## TCP vs UDP

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

## Application layer protocol 정의

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

## WEB과 HTTP(Hypertext Transfer Protocol)

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

## HTTP overview
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

## User와 Server간에 상태 정보를 기록하기 위해 사용하는 cookies

HTTP가 stateless protocol이므로, 이전 통신에 대한 history를 유지하기 위해서 cookie라는 것을 사용한다.

**cookie 기술의 4가지 요소**
```
1. HTTP response message에 cookie headerline을 추가해야 한다.
2. 다음 HTTP request message에 cookie headerline과 그에 따른 정보가 전송된다.
3. 사용자의 브라우저에 의해 관리되는 cookie 파일을 client에서 유지하고
4. back-end database를 website(server)에서 유지한다.
```

Server에서는 해당 web site를 처음 방문하는 사용자에 대해 unique id를 생성하고, 이를 back-end db에 저장한다.

Client는 website로부터 부여 받은 id를 cookie file을 이용해서 저장한다.

이렇게 생성된 unique id를 이용해서 client, server 간의 transaction history를 db에 기록할 수 있게 된다.

![image](https://user-images.githubusercontent.com/87526189/184567345-ba866635-360c-4e7d-aa41-6c104fd628f1.png)

처음 사용자가 웹사이트에 방문하는 경우 서버는 해당 이용자에게 set-cookie headline을 추가하여 cookie를 부여하는 response message를 client로 전송하고, 이에 client는 새로운 cookie에 대한 unique id를 부여받게 됩니다.

이렇게 한 번 cookie를 부여받게 되면, 이후에는 cookie headerline을 이용해서 통신을 주고받게 되어 server side에서 db에 유지하고 있는 transaction entry에 통신 정보가 저장됩니다.

### Cookie의 기능

1. 인증(authorization)
    - 한 번 로그인을 하게 되면, 이후에는 인증 없이 로그인이 가능하다.
2. 쇼핑몰 페이지의 장바구니 기능
3. 추천 기능 사용 가능
4. 사용자 세션(session) 유지
    - 세션(session): 통신을 하기 위해 서로 연결된 순간부터 연결을 마무리할 때까지의 기간을 의미한다. 즉, 웹사이트에서의 세션은 HTTP 통신 시작 시점부터 끝날 때까지를 의미하는 것 같다.
    - 즉, 이러한 세션의 유지를 한 번의 로그인 이후에는 쿠키로 가능하게 한다. (authorization을 간소화할 수 있다는 개념같다.)


## Web caches (proxy server)

웹 캐시의 목적은 굳이 매 번 통신할 때마다 멀리 있는 서버까지 접근하는 수고로움을 덜기 위해서 로컬에 있는 캐시에 저장해 두었다가 중복된 요청을 하는 경우 더 빠르게 원하는 정보를 전달하기 위해서 사용한다.

`Web cache가 있는 경우의 HTTP 통신 방식`
1. user가 browser를 이용해 server와 통신하려 할 때, 모든 HTTP 통신은 web cache를 거쳐서 간다.
2. 우선 browser가 user의 requests를 cache로 전송한다.
3. cache에 있는 object를 요청하는 경우 해당 objects를 돌려준다. (이 때, server 방문 안하게됨)

More about Web caching

- web cache는 server이자 client로서의 역할을 수행한다.
- 통상적으로 cache는 ISP에 의해 설치된다.
- 왜 Weh caching을 사용할까?
    - client의 request에 대한 응답 시간을 줄이기 위해
    - 기관의 access link에 대한 traffic을 줄이기 위해
    - 자금이 부족한 CP(content provider)가 효율적으로 content를 제공할 수 있도록 돕는다.

### Web cache의 조건부(conditional) GET

구버전의 objects를 반환하지 않기 위해 최신(up-to-date) 정보가 caching 되어있는지 확인해야한다.

그렇게 하기 위해 Conditional GET 이라는 method를 사용한다!

1. web cache에서 server로 날짜 정보를 명시한 HTTP request를 보낸다. (HTTP request message의 L.M(Last Modified)칸에 작성)
```
If-modified-since:
    <date>
```
2. server는 cached copy가 up-to-date인 경우 object가 없는 response를 반환한다.
```
HTTP/1.0 304 NOT Modified
```
3. cached copy의 최신 버전이 존재한다면, 새로운 버전의 object를 실은 response를 반환한다.
```
HTTP/2.0 200 OK
    <data>
```

이렇게 Conditional GET method를 사용하면, out-of-date object를 web cache에서 반환할 일이 없다는 장점이 있지만, 반대로 매 번 server와 통신해야 한다는 단점이 생기게 된다.

그래서 체크하는 간격을 두고 update를 진행하는 구조로 동작하는 것 같다. check 주기에 따라 average delay가 달라질 것이다.

## E-mail (electronic mail)

Electronic mail의 세 가지 주요 구성 요소
- user agents
- mail servers
- mail protocols
    - SMTP(simple mail transfer protocol)
    - POP3, IMAP

### User Agent
- mail reader라고 불린다.
- mail messsages를 작성, 수정, 조회하는 기능을 제공
- e.g. Outlook, Thunderbird, iPhone mail client, Gmail 등..

### Mail Servers
- 전송, 수신하는 모든 messages를 mail server가 받아서 저장한다.
- mailbox: user에게 전송되는 messages를 저장
- message queue: user가 발송하는 mail messages를 저장

![image](https://user-images.githubusercontent.com/68600592/193401193-c414eb96-f9e2-447d-a6c1-3b4984ec9d5e.png)

message queue는 user 구분이 없이 사용되고, meilbox는 user 별로 존재한다. 왜냐하면 mail server 안에 user 별로 전송된 mail messages를 관리해야 되기 때문이다.

**Mail Protocols**

![image](https://user-images.githubusercontent.com/68600592/193401309-66df2224-bc4a-42d2-9023-485416c7c557.png)

user agent(sender's, receiver's), mail server(sender's, receiver's)이 존재한다.

1. sender 측 user agent에서 email을 작성
2. SMTP protocol의 정의에 따라 email을 sender's mail server로 전송
3. sender's mail server에서 SMTP protocol의 정의에 따라 receiver's mail server로 email 전송
4. receiver's mail server 측의 email을 receiver user agent 측에서 읽어가는데 이 때는 email access protocol(POP, IMAP, HTTP. .)을 사용한다.


**SMTP protocol**

user agent에서 email 발송을 위해 mail server로 email을 보내는 경우
- client: user agent
- server: mail server

이는 먼저 통신을 시작하는 쪽을 client, 그렇지 않은 쪽을 server로 정의하기 때문이다.

mail serve간에 email messages를 전송하는 경우
- client: sending mail server
- server: receiving mail server

SMTP protocol의 특징
- 신뢰할 수 있는 email messages의 전송을 위해 TCP를 사용한다. (port번호 25번에서 대기, well-known port number)
- 3가지 전송의 phases
    1. handshaking (greeting)
    2. transfer of messages
    3. closure
- command(client)/response(server) interaction
    - command: ASCII text
    - response: status code(phrase)
- messages는 ASCII code만을 포함한다. (text version) 물론 지금은 audio, video 가능

### SMTP vs HTTP

- HTTP는 pull protocol, SMTP는 push protocol이다.
- 둘 다 ASCII command/response 상호작용, status code 이용
- HTTP는 각각의 objects가 자신의 response message에 담긴다.
- SMTP는 여러 개의 objects가 multipart message에 담겨 전송된다.

## 메일 접속 프로토콜(Mail access protocols)

mail system은 user agent와 mail server로 구성된다. 

전송자의 user agent가 SMTP protocol을 이용해 mail server를 거쳐 수신자의 mail server까지 email messages가 도달하게 되고

수신자측 user agent에서는 여러 가지의 mail access protocols를 이용하여 수신자측 mail server의 본인 mail box에 저장되어 있는 email messages를 읽어온다.

이 때, 수신자측 user agent는 mail messages를 pull해야 하는데, 이로 인해서 SMTP protocol을 사용할 수 없어, 별도의 protocol이 사용되어야 하고 이를 mail access protocol이라고 한다.

Mail access protocols의 종류
- POP: Post Office Protocol, 가장 단순한 protocol
- IMAP: Internet Mail Access Protocol, pop의 단점을 보완한 복잡한 protocol
- HTTP: 수신측 메일 서버가 웹 메일인 경우 HTTP protocol을 이용해 웹 메일을 가져오기도 한다.

### POP3 protocol

POP3 protocol은 2개의 phase로 구성된다.

1. authorization phase
    - client commands
        - user: username을 선언
        - pass: password
    - server responses
        - +OK (성공시)
        - -ERR (오류 발생)
2. transaction phase, client
    - list: message numbers를 나열
    - retr: 번호로 message를 회수
    - dele: delete
    - quit

![image](https://user-images.githubusercontent.com/87526189/185606257-9ebf3841-a2e4-4519-9b41-5e047e0b378c.png)

1. 바로 POP3 server process에서 OK response를 받는다.
2. 다음 command는 user command를 이용해 username을 지정
3. server측에서 username이 가능하면 OK response를 전송
4. 다음 user command는 pass로 password를 지정한다.
5. server측에서 password 가능하면 OK response를 전송
6. 이후에는 transaction phase 시작된다.

7. list command를 client에서 보내면, msg numbers를 돌려준다.
8. 현재 mailbox에 들어있는 msg 정보를 수신 가능, 마지막은 .으로 표기한다.
9. retr 1 => 첫 번째 msg를 가져오는 command
10. server는 이에 대한 response로 msg content를 client로 전송 (msg의 끝을 .으로 표시한다.)
11. dele 1 => 첫 번째 msg를 삭제하는 command
12. delete는 response 없고, quit command 이용시 server와의 연결을 끊는다.

**summary**

POP3 protocol은 list로 msg lists를 받아온 후에 retrieve 후 delete하는 과정을 반복하다 마지막까지 읽고난 후에 quit command를 실행하여 연결을 끊는 방식으로 동작



**POP3의 두 가지 mode**

1. 위에서 봤던 것과 같이 download and delete mode
2. download-and-keep mode, retrieve 하지만, delete는 하지 않는 방식으로 동작

지금은 거의 없지만, 과거에는 download-and-delete mode가 흔한 방식이었다고 한다. (한 번 조회시 다시 메일 확인이 불가능한 불편한 점이 존재한다.)

반대로, download-and-keep mode는 다른 브라우저를 통해 읽어도 새로운 환경에서 접속시 읽었던 메시지를 새로운 메시지로 취급하는 불편함이 있다.

## IMAP

POP3의 두 가지 mode의 불편성을 해소하기 위해 만들어진 protocol이 IMAP protocol이다.

POP3는 user agent 즉, local 환경에서 명령어를 통해 조작하여 mail을 받아오기 때문에, mailbox에 있는 메일에는 아무런 변화가 었다.

IMAP protocol은 server에 모든 messages를 보관하며, mailbox에 user가 하는 일을 모두 반영한다. 즉, 서버의 mailbox를 직접 user가 조작하는 개념이다.

**summary**
- 모든 msgs가 mail server에 유지된다.
- server의 mailbox에 folder를 생성하여 구성이 가능하다.
- 한 세션에서 작업한 애용이 다른 세션에서도 그대로 반영된다.

## DNS(Domain Name System)

`www.google.com` 이런 것을 host name 또는 domain name이라고 부른다. domain name이라고 부르는 이유는 .com domain의 google domain이라는 뜻을 가지고 있기 때문에, domain을 명시한다고 하여 domain name이라고 부르기도 한다고 함.

실제 client에서 server에 접속하기 위해 필요한 주소는 host name(domain name)이 아닌 32bit IP address이기 때문에, 모든 network application은 hostname을 ip address로 mapping 하는 작업이 필요한데, 이 service를 DNS(Domain Name System)가 담당한다.

이러한 기능은 모든 network에 걸쳐 요구되기 때문에, network 자체에 구현되는 것이 맞지만, network는 가능한 가장 간단한 형태를 유지한다라는 internet의 philosophy로 인해 application으로 따로 구현되어 있다.

### DNS services

- hostname -> ip address translation
- hostname aliasing (외부 세상에 알려진 별칭(alias)을 실제 이름(canonical)으로 변환)
- 특정 domain의 mail server를 알려준다.
- 해당 web server에 대한 request가 몰릴 때, web server의 replica 존재 그러나, 외부에는 replica 드러나지 않고, 하나의 별칭(alias)으로 접속하는데, 여러 개의 replica로 request를 분배하는 역할을 수행한다. (load distribution)

### 왜 centralize DNS가 아닌 분산 DNS인가?

- network application에 있어서 매우 critical한 service이므로 실패시 대체 가능해야
- traffic이 과다하게 집중된다.
- 지역적으로 먼 경우 network resource의 낭비 발생
- 유지/보수가 어렵다.

### DNS, 분산 계층 DB

DNS 서버는 서버 사이에 분산된 세가지 유형의 DNS 서버가 존재한다.

![image](https://velog.velcdn.com/images%2Fckstn0777%2Fpost%2Fd8c3ac1e-36ee-4ecb-93dc-1d37669c4928%2Fimage.png)

총 세 단계의 hierarchy를 가지며, 최상단에는 root DNS server가 위치한다.
Root DBS server아래의 server들은 TLD(Top-Level-Domain) servers라고 부른다.

DNS의 client가 hostname의 ip address를 translation하기 위해서는 다음과 같은 과정을 거친다.
1. 최상위 레벨의 root DNS 서버 중 하나로 접속
2. Root DNS 서버가 hostname에 해당하는 TLD 서버의 IP address중 하나를 보낸다.
3. client가 TLD서버 중 하나로 접속
4. TLD서버가 hostname(domain name)에 맞는 서버의 IP address를 보낸다.

### Local DNS server

위 세 개의 계층 외에 Local DNS server가 존재하며, "default name server" or "proxy name server" 라고도 불린다.

각각의 ISP(지역 ISP, 회사, 대학 등..)마다 하나씩 가지고 있다. `web cache가 web page를 cachign 하여 web server 역할을 수행하듯`이 Local DNS server를 ISP가 설치하여, `마치 DNS 서버 같은 역할`을 수행한다.


### TLD, authoritative servers

TLD server
- com, org, net, edu, aero, jobs, museums.. 등의 모든 top-level 국가 domain을 담당한다.
- .com TLD server는 Network Solutions라는 기관에서 관리를 담당
- .kr: 한국인터넷정보센터 기관에서 관리를 담당
- `어떤 domain에 대해 담당하고 있는 authoritative server가 누군지`를 알고 있다.

authoritative DNS server
- `조직내의 모든 host들에 대해 authoritative hostname을 IP address로 mapping할 수 있는 정보를 보유한 DNS server.`
- organization 또는 service provider에 의해 유지된다.

### Root name server

- 계층 구조의 가장 상위 레벨을 담당하는 name server이다.
- domain 별 TLD 서버를 알고 있다.
- 각 site에는 local name server가 있는데, local name server가 모르는 domain에 대한 요청이 root name server로 온다.

## DNS name resolution 예제 (query가 resolve되는 방식)

1. 반복 질의 (iterated query)

![image](https://user-images.githubusercontent.com/87526189/185649023-65df9f80-25f9-431e-b237-0cdc24102efb.png)

질문을 받은 서버가 mapping 정보를 제공하지 않고, 누구를 contact 해야 하는지를 알려준다.

2. 재귀 질의 (recursive query)

![image](https://user-images.githubusercontent.com/87526189/185649607-fb578846-d630-4c79-9b6f-4a6905274be8.png)

질문을 받은 서버가 자기가 어떻게든 정보를 알아내서 request를 보낸 client에게 제공한다.

재귀 질의 방식의 경우 root, TLD DNS server에 대한 load가 커지는데, 상위 레벨의 서버일수록 load가 증가한다.

## DNS: caching, updating records

local DNS server가 caching을 하고 있으면, caching 하고 있는 정보는 빠르게 반환해줄 수 있을 것이다. 

일반적으로 local name server는 TLD server를 caching 하고 있으며, 이를 통해서 root name server로 향하는 trip을 save할 수 있다. (top level DNS server로의 부담을 줄이기 위해서)

이 때, cached entries가 out-of-date 정보일 수 있는데, 이를 위해 TTL(Time-to-live) 정보를 항상 갖는다. 따라서 그 시간 동안만 caching을 하고 이후에는 정보를 버린다.

IETF에서는 추후에 local site에서 ip mapping 정보가 변하는 경우 세상에 update/modify하는 mechanism이 제안되었다.

## DNS protocol, messages

query와 reply 두 가지 종류의 messages를 사용하고, 두 가지는 같은 양식을 갖는다.

msg header

![image](https://user-images.githubusercontent.com/68600592/193620641-ee181e28-b1c9-4dd0-b6ac-996eadf19897.png)

- identification: query를 위한 16bit numbers로 reply시 같은 숫자를 사용한다.
- flags
    - query or reply
    - recursion desired (client: recursion을 원한다.)
    - recursion available (server: recursion이 가능하다.)
    - reply is authoritative (reply 정보가 authoritative server인지)

----------------------------------------------------------------------

`이 아래는 강의 정리가 아닌 따로 조사한 개념들 정리 부분입니다.`


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
