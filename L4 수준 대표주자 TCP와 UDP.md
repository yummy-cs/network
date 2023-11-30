## 🤝 L4 수준 대표주자 TCP와 UDP 

####  TCP와 UDP의 차이점 (2개)

    연결 개념의 여부
    혼잡 제어의 여부

#### TCP 클라이언트와 서버 연결 과정

    서버는 소켓을 오픈해 연결 대기
    클라이언트는 PID를 가진 프로세스가 연결을 위한 소켓을 오픈하고, 서버에 연결하고자 할 때 kernel에게 TCP Port 번호를 부여 받음
    이후 클라이언트의 소켓이 연결하고자 하는 서버의 대기 중인 소켓을 찾아가서 연결

#### TCP 연결 과정(3-way handshaking) 에서 주고받는 정보?

    시퀀스 번호
    정책(mss: maximum segment size)

#### 3-way handshaking와 4-way handshaking는 각각 무슨 목표를 가진 과정일까요?

    3-way handshaking : 연결 요청
    4-way handshaking : 종료 요청

#### HeartBeat란?

    연결 재확인

#### L4 수준에서의 식별자

    Port 번호

#### TCP와 UDP의 데이터 전달 단위

    TCP: Segment 
    UDP: Datagram

#### TCP 통신에서 segment는 payload가 있을까요?

    없습니다. IP, TCP만 있습니다.

#### TCP 통신할 때 클라이언트의 mss가 1460, server의 mss가 1400이라면 뭐에 맞춰질까요?

    클라이언트와 서버 간 MSS 협상 시 사양이 더 낮은 것에 맞춰지기 때문에 1400에 맞춰집니다.
    협상 시 TCP는 하향 평준화, UDP는 상향 평준화라 생각하면 쉽습니다~

#### 혼잡 제어란 무엇일까요

    데이터가 제대로 전송이 되지 않는 상황(Loss, Retransmission과 duplicated ACK, Zero Window, Out of order)을 제어하는 것.
    TCP 헤더에서 해주고, UDP는 혼잡 제어를 해주지 않습니다.

#### window size란?

    데이터 전송 시 여유 공간입니다. 

#### 네트워크 통신 시 active close와 passive close의 주체

    active close: client 
    passive close: server

#### sequence number는 몇 씩 증가할까요?

    최초 시퀀스 번호는 랜덤으로 부여, 그 후 번호는 세그먼트의 바이트 수 만큼 증가합니다.

#### TCP 대신 UDP을 사용하는 경우 예시를 말하시오.

    멀티미디어 전송 및 IPTV, 게임서버

#### 4-way handshaking에서 Time wait을 하는 곳의 의미는?

    time wait가 발생한 쪽이 연결을 끊자고 요청한 주체!
    보통 연결을 끊자고 client에서 요청하기 때문에 time wait가 server에서 발생하면 문제가 발생한 것이라고 간주해도 무방합니다.
    
#### TCP 연결은 보안성이 있는가?

    TCP가 데이터를 신뢰성 있게 보내는 것에 초점을 맞춘 반면에 데이터에 대한 기밀성, 무결성 등은 보장되지 않습니다.
