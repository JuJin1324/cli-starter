# CLI-Starter
운영체제 상관없이 사용가능한 CLI(Command Line Interface) 명령어 사용 정리

## 네트워크 관련 명령어
### ssh server
* 설치 
  - Ubuntu : `sudo apt-get install -y openssh-server`
  - Windows : `scoop install openssh-server`
  - macOS : 선탑재
* 설정
  - 위치 : /etc/ssh
  - ssh_host_res_key : 해당 리눅스 접속을 위한 프라이빗 키
  - sshd_config : ssh 접근을 위한 config 파일, 변경 이후 `service ssh restart`로 재시작한다.
* 참고사이트 : [링크](http://programmingskills.net/archives/315)

### netcat
* 설치 
  - Ubuntu : 선탑재
  - macOS : `brew install netcat`
  - Windows : `scoop install netcat`
* 사용법 
    - 1. 외부 서버에 특정 포트로 접속이 가능한지 확인 : `nc -z [외부 서버 주소] [포트]`
    - 예시(123.456.789.101 서버 mysql(3306포트) 접속 가능한지 테스트) : $ `nc -z 123.456.789.101 3306`
    - 2. Listening 서버를 로컬에 띄우기 : `nc -l [포트]`
    - 예시 : `nc -l 4321`
* 참고 사이트 : [리눅스에서 현재 열려 있는 포트를 확인하는 방법](https://khie74.tistory.com/1169521441)

### ngrok
* 설명 : 외부망에서 tcp 접속할 수 있도록 지정 포트를 ngrok에서 제공해주는 도메인 및 포트에 바인딩해준다.
* 설치
  - Ubuntu : `snap install ngrok`
  - macOS : `brew install ngrok`
  - Windows : `scoop install ngrok`
* 공식 사이트 : [링크](https://ngrok.com)
* 주의 : 회원가입 필요(무료)
* 사용법 : `ngrok tcp [지정 포트]`
* 예시 : `ngrok tcp 4321`

### nslookup
* 설명 : 특정 도메인에 맵핑된 IP 확인
* 설치 : 선탑재
* 사용법 : `nslookup [도메인]`
* 예시 : `nslookup 0.tcp.ngrok.io`

### netstat
* 설명 : 리눅스 서버에 현재 열려 있는 포트 확인
* 설치
  - Ubuntu : `sudo apt-get install -y net-tools`
  - macOS : 선탑재
  - Windows : 선탑재
* n:host명으로 표시 안함
* a:모든소켓 표시
* p:프로세스ID와 프로그램명 표시
* 사용법 : `netstat -anp`
* 예시(LISTEN중인 프로세스만 표시) : `netstat -anp | grep LISTEN`
* 참고 사이트 : [리눅스에서 현재 열려 있는 포트를 확인하는 방법](https://khie74.tistory.com/1169521441)

### iftop
* 설명 : 서버의 실시간 트래픽 확인
* 설치 : 
  - Ubuntu : `sudo apt-get install -y iftop`
  - macOS : `brew install iftop`
  - Windows : 못 찾음
* 사용법 : 
  - 실행 : `iftop` 
  - macOS의 경우 관리자 권한 필요 : `sudo iftop`
* 정보 : 
  - TX : 전송
  - RX : 수신
  - TOTAL : 전체(TX + RX)
  - cumm : iftop 실행 후 현재까지의 총 데이터량
  - peak : 피크 시의 데이터
  - rates : 각각 2초, 4초, 10초의 평균흐름  
* 참고 사이트 : [링크](http://blog.weirdx.io/post/51971)

### traceroute
* 설명 : 서버 접속 가능 및 경로 파악
* 설치
  - Ubuntu : `sudo apt-get install -y traceroute`
  - macOS : 선탑재
  - Windows : 윈도우는 tracert 사용
* 사용법 : `traceroute -p [포트] [서버 IP 혹은 도메인] -T`

### tracert
* 설명 : 윈도우 용 traceroute
* 설치
  - Windows : 선탑재
* 사용법 : `tracert -p [포트] [서버 IP 혹은 도메인] -T`

### Httpie
* 설명: 터미널에서 웹 페이지 요청 및 응답에 대한 Header 및 Body 정보를 모두 표시
* 공식 페이지: [HTTPie](https://httpie.org/)
* 설치
  - macOS : `brew install httpie`
* 사용법: `http GET localhost:8080`

