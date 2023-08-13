# CLI-Starter
> 운영체제 상관없이 사용가능한 CLI(Command Line Interface) 명령어 사용 정리

## 유틸리티  
### smartmontools
> **설명**   
> ssd 스펙 및 상태 정보 리포트 해주는 명령어 입니다.
> 
> **설치**  
> Ubuntu: `sudo apt install -y smartmontools`    
> macOS: `brew install smartmontools`
> 
> **사용 예시 - Ubuntu**  
> 디스크 목록 보기: `sudo lsblk`  
> 디스크 정보 보기: `sudo smartctl -a /dev/sda`   
> 
> **사용 예시 - macOS**  
> 디스크 목록 보기: `diskutil list`  
> 디스크 정보 보기: `smartctl -a /dev/disk0`    

### cpufetch
> **설명**  
> cpufetch 명령은 서버의 CPU 정보를 리포트 해주는 명령어 입니다.  
> 
> **설치**  
> Ubuntu: 
> ```shell 
> sudo apt update
> sudo apt install -y snapd
> sudo snap install cpufetch
> ```
> macOS: `brew install cpufetch`  

### watch  
> **설명**  
> watch 명령은 원하는 명령어의 결과를 원하는 시간(초) 주기로 리프레시 하여 결과를 보여주는 명령어 입니다.  
> 
> **설치**  
> Ubuntu: 선탑재   
> macOS: `brew install watch`  
> 
> **Arguments**  
> -n <seconds>: 새로고침 시간(default 2초)  
> -d: 이전 출력결과와 비교해서 변경된 부분 하이라이트 표시  
> 
> **사용 예시**  
> 현재 시간 값을 화면에 1초마다 업데이트로 출력: `watch -d -n 1 'date'`  

### bat
> **설명**  
> cat 대신 사용. syntax highlighting 해줌.
> 
> **설치**    
> Ubuntu: `sudo apt install -y bat`  
> macOS: `brew install bat`  

### ranger
> **설명**  
> file explorer for linux   
> 
> **설치**  
> Ubuntu: `apt install -y ranger`  
> masOS: `brew install ranger`  
> 
> **사용법**  
> `r`: open with command  
> `y`: copy  
> `p`: paste  
> `d`: cut/delete  
> `u`: undo  
> `q`: quit  

### mycli
> **설명**  
> 자동완성 기능이 있는 MySQL 및 MariaDB 클라이언트   
> 
> **설치**  
> Ubuntu: `apt install -y mycli`  
> macOS: `brew install mycli`

### htop
> **설명**  
> top 대용. CPU 및 Memory 사용량 체크가 top 보다 훨씬 직관적임.  
> 
> **설치**  
> Ubuntu: `apt install -y htop`  
> macOS: `brew install htop`

### glances
> **설명**  
> htop 보다 조금 더 많고 자세한 정보들을 보여줌.  
> 
> **설치**  
> Ubuntu: `apt install -y glances`  
> macOS: `brew install glances`  

### base64
> **설명**  
> 리눅스용 base64 인코딩/디코딩 도구  
> 
> **설치**  
> Ubuntu: 내장   
> macOS: 내장  
> 
> **사용법**  
> base64 인코딩(\n 미포함): `echo -n '<인코딩할 문자열>' | base64`  
> base64 인코딩(\n 포함): `echo '<인코딩할 문자열>' | base64`  
> base64 디코딩: `echo '<Base64 인코딩된 문자열>' | base64 --decode`  
> 
> **파일 인코딩**  
> ```shell
> echo hello > 1.txt
> base64 -i 1.txt
> ```
> 
> **파일 디코딩**  
> ```shell
> echo aGVsbG8K > 2.txt
> base64 -d -i 2.txt
> ```

### jq
> **설명**  
> JSON 포맷의 문자열을 읽어서 원하는 항목만 추출할 수 있다.  
> 
> **설치**  
> Ubuntu: `sudo apt install -y jq`  
> macOS: `brew install jq`  
>
> **사용법**  
> `<json 문자열> | jq '<추출할 항목명>'`  
> 
> **예시**  
> 1.name 항목 추출: `echo "{ \"name\": \"이름입니다\", \"age\": 33, \"arr\": [ 1, 2, 3 ] }" | jq '.name'`    
> 2.age 항목 추출: `echo "{ \"name\": \"이름입니다\", \"age\": 33, \"arr\": [ 1, 2, 3 ] }" | jq '.age'`    
> 3.배열 전체 추출: `echo "{ \"name\": \"이름입니다\", \"age\": 33, \"arr\": [ 1, 2, 3 ] }" | jq '.arr'`  
> 4.배열 일부 추출: `echo "{ \"name\": \"이름입니다\", \"age\": 33, \"arr\": [ 1, 2, 3 ] }" | jq '.arr[0]'`  
> 5.json 문자열을 이쁘게 출력: `echo "{ \"name\": \"이름입니다\", \"age\": 33, \"arr\": [ 1, 2, 3 ] }" | jq '.'`  

### sed
> **설명**  
> sed는 stream editor 이름을 줄인 명령어로, 말그대로 스트림 편집기를 의미한다. 주로 문자열을 치환하거나 삭제할때 유용하게 사용할 수 있는 명령어다. 
> 이 외에도 특정 라인까지 출력, 특정 패턴에 맞는 행들만 출력하는 기능을 지원한다.
>
> **설치**  
> Ubuntu: 내장  
> macOS: 내장
>
> **사용법**  
> 문자열 치환    
> 처음 찾은 문자열 1개만 치환: `sed 's/원본문자열/바꿀문자열' 파일명`    
> 일치하는 문자열 전부 치환: `sed 's/원본문자열/바꿀문자열/g' 파일명`  
> 대소문자 구분없이 찾으면 치환: `sed 's/원본문자열/바꿀문자열/i' 파일명`  
> 
> 삭제  
> 특정 문자열이 포함된 줄 삭제하여 출력: `sed '/특정문자열/d' 파일명`  
>
> **예시**  
> 특정 문자열 지우기: `sed 's/특정문자열//g' 파일명`    
> 처음 1줄, 2줄을 지워서 출력: `sed '/1,2d' 파일명`    
> 공백 라인을 삭제해서 출력한다: `sed '/^$/d' 파일명`  
> hello 문자열이 들어있는 line 만 출력: `sed -n '/hello/p' 파일명`   
> 
> **참조사이트**  
> [[linux] sed 명령어를 통한 파일 문자열 치환 예제](https://devpouch.tistory.com/187)

### grep
> **설명**  
> 리눅스에서 grep 명령어는 특정 파일에서 지정한 문자열이나 정규표현식을 포함한 행을 출력해주는 명령어입니다. 
> 특히 tail이나 ls 등 다양한 명령어와 조합하여 응용되는 경우가 많아서 이 grep명령어는 리눅스에서 능숙하게 사용할 줄 알아야 하는 기본 명령어입니다.  
>
> **설치**  
> Ubuntu: 내장  
> macOS: 내장
>
> **사용법**
> `grep <옵션> <패턴> <파일명>`   
> 
> **자주 사용하는 옵션**  
> -c : 일치하는 행의 수를 출력한다.  
> -i : 대소문자를 구별하지 않는다.  
> -v : 일치하지 않는 행만 출력한다.  
> -n : 포함된 행의 번호를 함께 출력한다.  
> -l : 패턴이 포함된 파일의 이름을 출력한다.  
> -w : 단어와 일치하는 행만 출력한다.  
> -x : 라인과 일치하는 행만 출력한다.  
> -r : 하위 디렉토리를 포함한 모든 파일에서 검색한다.  
> -m 숫자 : 최대로 표시될 수 있는 결과를 제한한다.  
> -E : 찾을 패턴을 정규 표현식으로 찾는다.  
> -F : 찾을 패턴을 문자열로 찾는다.  
>
> **예시**  
> 특정 파일에서 error 문자열 찾기: `grep 'error' 파일명`
> 
> **참조사이트**  
> [[Linux] 리눅스 grep 명령어 사용법 (파일 내 특정 문자열 찾기)](https://coding-factory.tistory.com/802)

---

## 네트워크 관련 명령어
### wrk 
> **설명**    
> 부하테스트 도구  
> 
> **설치**  
> Ubuntu : `sudo apt install -y wrk`   
> macOS : `brew install wrk`
> 
> **Arguments**  
> -c <n>: Connection 갯수   
> -d <t>: Duration(부하 지속시간)  
> -t <n>: Thread 갯수(동시 접속 갯수)
> 
> **예시**  
> `wrk -c10 -d10000 -t10 https://api.test.com/v1/users`  
> 
> 참고사이트: [wrk - 모던 웹 성능 측정 도구(Modern HTTP bench marking tool)](https://www.lesstif.com/software-architect/wrk-modern-http-bench-marking-tool-106856711.html)

### OpenSSH Server
> **설명**  
> SSH: Secure Shell 의 줄임말  
> 리눅스 원격 접속을 가능하게하는 서버    
> 
> **설치**     
> Ubuntu : `sudo apt install -y openssh-server`  
> Windows : `scoop install openssh-server`  
> macOS : 선탑재   
> 
> **설정**  
> 위치: /etc/ssh  
> ssh_host_res_key: 해당 리눅스 접속을 위한 프라이빗 키  
> sshd_config : ssh 접근을 위한 config 파일, 변경 이후 `service ssh restart`로 재시작한다.  
> 참고사이트 : [링크](http://programmingskills.net/archives/315)  

### netcat
> **설명**  
> 외부 서버의 특정 포트로 접속이 가능한지 확인해주는 프로그램  
> 
> **설치**   
> Ubuntu : 선탑재  
> macOS : `brew install netcat`  
> Windows : `scoop install netcat`
> 
> **사용법**      
> 1.외부 서버에 특정 포트로 접속이 가능한지 확인 : `nc -z [외부 서버 주소] [포트]`    
> 예시 1) 123.456.789.101 서버 mysql(3306포트) 접속 가능한지 테스트: $ `nc -z -v 123.456.789.101 3306`  
> 예시 2) 123.456.789.101 서버 포트 20부터 80까지 접속 가능한지 테스트: $ `nc -z -v 123.456.789.101 20-80`  
>
> 2.Listening 서버를 로컬에 띄우기 : `nc -l [포트]`    
> 예시 : `nc -l 4321`    
> 참고 사이트 : [리눅스에서 현재 열려 있는 포트를 확인하는 방법](https://khie74.tistory.com/1169521441)  

### ngrok
> **설명**   
> 외부망에서 tcp 접속할 수 있도록 지정 포트를 ngrok 에서 제공해주는 도메인 및 포트에 바인딩해준다.  
> 
> **설치**  
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
> **설명**   
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
> **설치**  
> Ubuntu : `sudo apt-get install -y net-tools`  
> macOS : 선탑재  
> Windows : 선탑재  
> 
> **Arguments**   
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
> **설치**     
> Ubuntu : `sudo apt install -y iftop`  
> macOS : `brew install iftop`  
> Windows : 못 찾음
> 
> **사용법**   
> 실행 : `iftop`   
> macOS의 경우 관리자 권한 필요 : `sudo iftop -i en0`    
> gh 
> **정보**   
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
> **설치**  
> Ubuntu : `sudo apt install -y traceroute`  
> macOS : 선탑재  
> Windows : 윈도우는 tracert 사용  
> 사용법 : `traceroute -p [포트] [서버 IP 혹은 도메인]`   

### tracert
> 설명 : 윈도우 용 traceroute
> 
> **설치**  
> Windows : 선탑재  
> 사용법 : `tracert -p [포트] [서버 IP 혹은 도메인] -T`  

### Httpie
> 설명: 터미널에서 웹 페이지 요청 및 응답에 대한 Header 및 Body 정보를 모두 표시
> 
> 공식 페이지: [HTTPie](https://httpie.org/)
> 
> **설치**  
> macOS : `brew install httpie`  
> 사용법: `http GET localhost:8080`  

---

## 서비스
### Executable-Jar 서비스 등록
> **서비스 파일 생성**  
> 생성 위치: `/etc/systemd/system`  
> 생성 파일: `<서비스 파일 명>.service`
> service 에서 Jar 를 실행시키는 bash script 를 실행하는 경우
> ```shell
> cd /etc/systemd/system
> sudo vi cli-starter.service
> 
> [Unit]
> Description=Service description
> After=syslog.target network.target
> 
> [Service]
> Type=forking
> User=ec2-user
> Group=ec2-user
> WorkingDirectory=/home/ec2-user/cli-starter
> ExecStart=/bin/bash start.sh
> ExecStop=/bin/kill -15 $MAINPID
> Restart=on-failure
> RestartSec=10
> 
> [Install]
> WantedBy=multi-user.target
> 
> :wq 
> ```
> 
> service 에서 직접 Jar 를 실행하는 경우
> ```shell
> cd /etc/systemd/system
> sudo vi cli-starter.service
> 
> [Unit]
> Description=Service description
> After=syslog.target network.target
> 
> [Service]
> Type=simple
> User=ec2-user
> Group=ec2-user
> WorkingDirectory=/home/ec2-user/cli-starter
> ExecStart=/bin/bash -c "exec java -Dspring.profiles.active=dev -jar cli-starter-0.0.1-SNAPSHOT.jar"
> ExecStop=/bin/kill -15 $MAINPID
> Restart=on-failure
> RestartSec=10
> 
> [Install]
> WantedBy=multi-user.target
> 
> :wq
> ```
> Description: 서비스에 대한 설명  
> After: 서비스가 언제 실행될 것인지 설정하는 부분. 위의 예시에서는 네트워크가 잡힌 후 시작.
> 
> Type: `simple`: Jar 파일을 직접 실행할 때 simple, `forking`: bash script 를 통해서 Jar 파일을 실행할 때는 forking 사용.   
> User, Group: 서비스 실행을 위한 권한  
> WorkingDirectory: 서비스가 바라보는 작업 디렉터리 경로. WorkingDirectory 를 Executable-Jar 파일이 위치한 경로로 설정하면 
> ExecStart 에서 Jar 파일의 풀 경로를 적을 필요없이 Jar 파일의 이름만 명시하면 된다.    
> 
> ExecStart: jar 파일을 절대 경로로 작성. WorkingDirectory 를 위에서 설정한 경우에는 경로를 적어줄 필요없음.    
> Restart: 'on-failure'는 서비스를 실행시키는데 실패하면 다시 시작시키겠다는 의미의 설정이다.  
> RestartSec: 서비스를 다시 시작하기 전에 몇 초동안 잠시 기다릴지에 대한 설정이다.  
> WantedBy: 서비스 run level을 설정하는 부분이다. 'multi-user.target'로 설정하면 다중 사용자로 설정된다.  
> 
> **서비스 등록**  
> ```shell
> # 서비스 파일 등록
> sudo systemctl daemon-reload
> 
> # 서비스 등록
> sudo systemctl enable cli-starter.service
> 
> # 서비스 재시작
> sudo systemctl restart cli-starter.service
> ```
> 
> **서비스 확인**  
> ```shell
> # 구동되는 서비스 목록 조회
> sudo systemctl -t service list-unit-flies | grep cli-starter.service
> 
> # 서비스 실행 상태 확인
> sudo systemctl status cli-starter.service
> ```

### 참조사이트
> [[AWS] Ubuntu Spring Boot jar 서비스 등록](https://garve32.tistory.com/65)  
> [Linux에서 SpringBoot jar 파일 서비스 등록해 자동실행 되게 하기(+ 서비스 관련 기본 명령어들)](https://pamyferret.tistory.com/16)  
> [Run a Java Application as a Service on Linux](https://www.baeldung.com/linux/run-java-application-as-service)
