# CLI-Starter
> 운영체제 상관없이 사용가능한 CLI(Command Line Interface) 명령어 사용 정리

## 유틸리티  
### smartmontools
> 설명   
> ssd 스펙 및 상태 정보 리포트 해주는 명령어 입니다.
> 
> 설치  
> Ubuntu: `sudo apt install -y smartmontools`    
> macOS: `brew install smartmontools`
> 
> 사용 예시 - Ubuntu  
> 디스크 목록 보기: `sudo lsblk`  
> 디스크 정보 보기: `sudo smartctrl -a /dev/sda`   
> 
> 사용 예시 - macOS  
> 디스크 목록 보기: `diskutil list`  
> 디스크 정보 보기: `smartctl -a /dev/disk0`    

### cpufetch
> 설명  
> cpufetch 명령은 서버의 CPU 정보를 리포트 해주는 명령어 입니다.  
> 
> 설치  
> Ubuntu: 
> ```shell 
> sudo apt update
> sudo apt install -y snapd
> sudo snap install cpufetch
> ```
> macOS: `brew install cpufetch`  

### watch  
> 설명  
> watch 명령은 원하는 명령어의 결과를 원하는 시간(초) 주기로 리프레시 하여 결과를 보여주는 명령어 입니다.  
> 
> 설치  
> Ubuntu: 선탑재   
> macOS: `brew install watch`  
> 
> Arguments
> -n <seconds>: 새로고침 시간(default 2초)  
> -d: 이전 출력결과와 비교해서 변경된 부분 하이라이트 표시  
> 
> 사용 예시  
> 현재 시간 값을 화면에 1초마다 업데이트로 출력: `watch -n 1 'date'`  

### bat
> 설명  
> cat 대신 사용. syntax highlighting 해줌.
> 
> 설치  
> Ubuntu: `sudo apt install -y bat`  
> macOS: `brew install bat`  

### ranger
> 설명  
> file explorer for linux   
> 
> 설치  
> Ubuntu: `apt install -y ranger`  
> masOS: `brew install ranger`  
> 
> 사용법  
> `r`: open with command  
> `y`: copy  
> `p`: paste  
> `d`: cut/delete  
> `u`: undo  
> `q`: quit  

### mycli
> 설명  
> 자동완성 기능이 있는 MySQL 및 MariaDB 클라이언트   
> 
> 설치  
> Ubuntu: `apt install -y mycli`  
> macOS: `brew install mycli`

### htop
> 설명  
> top 대용. CPU 및 Memory 사용량 체크가 top 보다 훨씬 직관적임.  
> 
> 설치  
> Ubuntu: `apt install -y htop`  
> macOS: `brew install htop`

### glances
> 설명  
> htop 보다 조금 더 많고 자세한 정보들을 보여줌.  
> 
> 설치  
> Ubuntu: `apt install -y glances`  
> macOS: `brew install glances`  

---

## 네트워크 관련 명령어
### wrk 
> 설명  
> 부하테스트 도구  
> 
> 설치
> Ubuntu : `sudo apt install -y wrk`   
> macOS : `brew install wrk`
> 
> Arguments
> -c <n>: Connection 갯수   
> -d <t>: Duration(부하 지속시간)  
> -t <n>: Thread 갯수(동시 접속 갯수)
> 
> 참고사이트: [wrk - 모던 웹 성능 측정 도구(Modern HTTP bench marking tool)](https://www.lesstif.com/software-architect/wrk-modern-http-bench-marking-tool-106856711.html)

### OpenSSH Server
> 설명  
> SSH: Secure Shell 의 줄임말  
> 리눅스 원격 접속을 가능하게하는 서버    
> 
> 설치     
> Ubuntu : `sudo apt install -y openssh-server`  
> Windows : `scoop install openssh-server`  
> macOS : 선탑재   
> 
> 설정  
> 위치: /etc/ssh  
> ssh_host_res_key: 해당 리눅스 접속을 위한 프라이빗 키  
> sshd_config : ssh 접근을 위한 config 파일, 변경 이후 `service ssh restart`로 재시작한다.  
> 참고사이트 : [링크](http://programmingskills.net/archives/315)  

### netcat
> 설명
> 외부 서버의 특정 포트로 접속이 가능한지 확인해주는 프로그램  
> 
> 설치   
> Ubuntu : 선탑재  
> macOS : `brew install netcat`  
> Windows : `scoop install netcat`
> 
> 사용법    
> 1.외부 서버에 특정 포트로 접속이 가능한지 확인 : `nc -z [외부 서버 주소] [포트]`  
> 예시 1) 123.456.789.101 서버 mysql(3306포트) 접속 가능한지 테스트: $ `nc -z -v 123.456.789.101 3306`  
> 예시 2) 123.456.789.101 서버 포트 20부터 80까지 접속 가능한지 테스트: $ `nc -z -v 123.456.789.101 20-80`  
>
> 2.Listening 서버를 로컬에 띄우기 : `nc -l [포트]`  
> 예시 : `nc -l 4321`    
> 참고 사이트 : [리눅스에서 현재 열려 있는 포트를 확인하는 방법](https://khie74.tistory.com/1169521441)  

### ngrok
> 설명   
> 외부망에서 tcp 접속할 수 있도록 지정 포트를 ngrok 에서 제공해주는 도메인 및 포트에 바인딩해준다.  
> 
> 설치  
> Ubuntu : `snap install ngrok`  
> macOS : `brew install ngrok`  
> Windows : `scoop install ngrok`  
> 
> 공식 사이트 : [링크](https://ngrok.com)   
> 주의 : 회원가입 필요(무료)  
> 
> 사용법 : `ngrok tcp [지정 포트]`  
> 예시 : `ngrok tcp 4321`  

### nslookup
> 설명 
> 특정 도메인에 맵핑된 IP 확인
>
> Ubuntu : 선탑재   
> macOS : 선탑재    
> Windows : 선탑재  
>  
> 사용법: `nslookup [도메인]`  
> 예시: `nslookup 0.tcp.ngrok.io`  

### netstat
> 설명 : 리눅스 서버에 현재 열려 있는 포트 확인
> 
> 설치  
> Ubuntu : `sudo apt-get install -y net-tools`  
> macOS : 선탑재  
> Windows : 선탑재  
> 
> Arguments   
> -n: host명으로 표시 안함  
> -a: 모든소켓 표시  
> -p: 프로세스ID와 프로그램명 표시  
> 
> 사용법: `netstat -anp`  
> 예시: LISTEN 중인 프로세스만 표시) `netstat -anp | grep LISTEN`  
> 
> macOS 에서는 netcat 대신에 `sudo lsof -iTCP -sTCP:LISTEN -P` 를 사용한다.  
> 
> 참고 사이트 : [리눅스에서 현재 열려 있는 포트를 확인하는 방법](https://khie74.tistory.com/1169521441)  

### iftop
> 설명 : 서버 내부의 실시간 트래픽 확인  
> 
> 설치   
> Ubuntu : `sudo apt install -y iftop`  
> macOS : `brew install iftop`  
> Windows : 못 찾음
> 
> 사용법   
> 실행 : `iftop`   
> macOS의 경우 관리자 권한 필요 : `sudo iftop`  
> 
> 정보   
> TX : 전송  
> RX : 수신  
> TOTAL : 전체(TX + RX)  
> cumm : iftop 실행 후 현재까지의 총 데이터량  
> peak : 피크 시의 데이터  
> rates : 각각 2초, 4초, 10초의 평균흐름    
> 참고 사이트 : [링크](http://blog.weirdx.io/post/51971)  

### traceroute
> 설명 : 서버 접속 가능 및 경로 파악  
> 
> 설치  
> Ubuntu : `sudo apt install -y traceroute`  
> macOS : 선탑재  
> Windows : 윈도우는 tracert 사용  
> 사용법 : `traceroute -p [포트] [서버 IP 혹은 도메인]`   

### tracert
> 설명 : 윈도우 용 traceroute
> 
> 설치 
> Windows : 선탑재  
> 사용법 : `tracert -p [포트] [서버 IP 혹은 도메인] -T`  

### Httpie
> 설명: 터미널에서 웹 페이지 요청 및 응답에 대한 Header 및 Body 정보를 모두 표시
> 
> 공식 페이지: [HTTPie](https://httpie.org/)
> 
> 설치  
> macOS : `brew install httpie`  
> 사용법: `http GET localhost:8080`  

