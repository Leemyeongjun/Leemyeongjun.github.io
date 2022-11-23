
---

### Introduce

---

![myeongjun](https://user-images.githubusercontent.com/77829885/202432139-d9dfd194-b81e-4058-8de2-19aec00e2e7e.png)

---

|이름| 이명준|  
|이메일| 2myeongjun@naver.com|  
|나이| 27|  

---

안녕하세요.  
잘부탁드립니다. ^^123

---

### Markdown

마크다운은 일반 텍스트 기반의 경량 마크업 언어다.  
일반 텍스트로 서식이 있는 문서를 작성하는데 사용되며,  
일반 마크업 언어에 비해 문법이 쉽고 간단한 것이 특징이다.  
HTML과 RTF 등 서식 문서로 쉽게 변환되기 때문에 응용 소프트웨어와  
함께 배포되는 README 파일이나 온라인 게시물 등에 많이 사용 된다.  

1. 장점
    - 간결하다.
    - 별도의 도구없이 작성가능
    - 다양한 형태로 변환가능
    - 텍스트로 저장되기 때문에 용량이 적다.

2. 단점
    - 표준이 없다.
    - 도구에 따라 변환방식이나 생성물이 다르다.
    - 모든 HTML 마크업을 대신하지 못한다.

---

### Hypervisor

하이퍼바이저는 가상 머신(Virtual Machne, VM)을 생성하고 구동하는 소프트웨어다. 
가상 머신 모니터(VMM)라고도 불리는 하이퍼바이저는 하이퍼바이저  
운영 체제와 가상 머신의 리소스를 분리해 VM의 생성과 관리를 지원한다.  

* Natvie or Bare-metal Hypervisor
    * 가상 시스템 또는 게스트운영 체제 중 하나의 문제가 하드웨어에서  
    실행 중인 다른 게스트 운영체제에 영향을 미치지 않는다.  
    2번째 수준으로 실행된다.  
    대표적으로 Xen, KVM, Oracle VM server for SPARC, Microsoft Hyper-V가 있다.  

    ![HPV1](https://user-images.githubusercontent.com/77829885/202845957-b21258d4-25be-4932-a91b-83bd47f87381.png)

* Hosted Hypervisor
    * 일반 프로그램과 같이 호스트 운영체제에서 실행되며  
    VM 내부에서 동작되는 게스트 운영체제는 하드웨어에서 3번째 수준으로 실행된다.  
    대표적으로 VMwar Server, VMware, Workstation, Virtual box가 있다.

    ![HPV2](https://user-images.githubusercontent.com/77829885/202845961-9e47e467-ac68-4213-806b-86fefb0d5179.png)  

전가상화(Full Virtualiztion)
>>하드웨어를 모두 가상화 한 것을 말한다.  
하이버바이저를 베어메탈에 구동하면, DOMO라고 하는 관리용 가상머신이 구동된다.  
전가상화는 나머지 모든 가상머신들의 하드웨어 접근이 이 DOMO를 통해서 이뤄진다.  
모든 명령에 대해 DOMO가 개입하는 형태이다.  
하드웨어를 전부 가상화 하기 때문에 게스트운영체제의 별다른 수정없이 사용할 수 있다.  
하지만 하이퍼바이저가 모든 명령을 중재하기 때문에 성능이 비교적 느리다.  
특정 인스트럭션의 경우 반드시 처리해줘야하며, 트랩 처리도 해줘야 하는 문제가 있다.  

반가상화
>>하드웨어를 완전히 가상화하지 않는다.  
전가상화의 가장 큰 단점인 서능 저하를 해소하고자 모든 명령을 DOMO를 통해  
하이퍼바이저에게 요청을 하는 것이 아니라 하이퍼콜(Hyper Call)이라는  
인터페이스로 직접 하이퍼바이저에게 요청을 하는 것 이다.  
따라서 전가상화에 비해 성능이 빠르다.  
하지만 하이퍼콜을 이용하여 하이퍼바이저에게 요청을 보내는 동작을 기존 OS들은 할 수 없다.  
즉, 게스트 운영체제가 하드웨어의 가상화 여부를 알고 있어야 하며,  
필요한 경우 하이퍼바이저에게 하이퍼콜을 요청할 수 있도록 운영 체제의 커널을 수정해야 한다.  
오픈소스 운영체제가 아니라면 반가상화를 이용하기 쉽지 않다.  

---

### 리눅스 명령어

```
1. pwd : 현재 작업중인 디렉토리 표시

   [vagrant@host1 ~]$ pwd

   /home/vagrant

```

```

2. cd : 디렉토리를 이동하는 명령어

   [vagrant@host1 ~]$ cd git

   [vagrant@host1 git]$

```

```

3. ls : 특정 디렉토리와 특정 파일 내용 제공

   [vagrnat@host1 ~]$ ls

   git

```

```

4. file : 지저오딘 파일의 종류(타입)을 확인하는 명령어

   [vagrant@@host1 ~]$ file git

   git: directory

```

```

5. less : 내용을 페이지로 나누어 보여주는 명령어

   [vagrant@host1 bitcamp-ncp]$ less x.txt

   새로운 창에서
   1111
   2222
   x.txt (END)

```

```
6. cp : 파일, 디렉토리를 복사하는 명령어

   [vagrnat@host1 bitcamp-ncp]$ cp x.txt l.txt

   [vagrant@host1 bitcamp-ncp]$ ls

   l.txt  x.txt

   [vagrant@host1 bitcamp-ncp]$ cat l.txt

   1111
   2222

   cp [원본파일이름] [옮길파일이름]
   cp [원본파일위치/원본파일이름] [옮길파일위치][옮길파일이름]
   cp[원본파일이름][옮길파일위치]

```

```
7. mv : move의 줄임말로 파일, 디렉토리를 이동 시킬때 사용하는 명령어

   [vagrant@host1 bitcamp-ncp]$ mv l.txt c.txt

   복사한 l.txt를 1111만 있는 c.txt에 이동

   [vagrant@host1 bitcamp-ncp]$ cat c.txt

   1111
   2222

```

```

8. mkdir : make directory의 약자로 디렉토리(폴더)를 생성할 때 사용하는 명령어

   mkdir [옵션][생성 할 디렉토리]

   [vagrant@host1 ~]$ mkdir test 
   [vagrant@host1 ~]$ ls

   git test

```

```

9. rm : remvoce의 약자로 파일이나 디렉토리를 삭제 시킬때 사용하는 명령어

   다시한번 x.txt를 l.txt로 카피해서 지운다
   [vagrant@host bitcamp-ncp]$ cp x.txt l.txt

   [vagrant@host1 bitcamp-ncp]$ ls
   l.txt  x.txt

   [vagrant@host1 bitcamp-ncp]$ rm l.txt
   [vagrant@host1 bitcamp-ncp]$ ls
   x.txt

   디렉토리를 삭제할땐 rm -r 디렉토리명

```

```

10. ln : Link의 약자로 리눅스 파일시스템에서 링크파일을 만드는 명령어

   심볼릭링크(Symbolic Link)
   - 단순히 원본파일을 가리키도록 링크만 시켜둔 것으로 윈도우의 바로가기같은 기능
   원본파일의 크기와는 무관하다. 원본파일이 삭제되어 존재하지 않으면 링크파일은
   깜박거리면서 없다는 것을 알려준다.

   하드링크(Hard Link)
   - 원본파일과 다른 이름으로 존재하는 동일한 파일이며 동일한 내용의 다른 파일이라고 할 수 있다.
   서로 다른 파일이기 때문에 원본 파일이 삭제되더라도 그대로 남아 있다.
   원본파일의 내요잉 변경될 경우에 링크파일의 내용도 자동으로 변경된다.

   git이라는 디렉토리에 link_test라는 심볼릭링크 생성
   [vagrnat@host1 ~]$ ln -s git link_test
   [vagrant@host1 ~]$ ls -al

   lrwxrwxrwx. 1 vagrant vagrant  3 Nov 21 21:22 link_test -> git

   심볼릭 링크 삭제
   [vagrant@host1 ~]$ rm link_test

```

```

11. type : 명령 유형에 대한 정보를 표시하는 명령어

   [vagrant@host1 ~]$ type pwd
   pwd is a shell builtin

   [vagrant@host1 ~]$ type ls
   ls is aliased to 'ls --color=auto'

   [vagrant@host1 ~]$ type git 
   git is hashed (/usr/bin/git)

```

```

12. which : 특정명령어의 위치를 찾아주는 명령어

   [vagrant@host1 ~]$ which pwd
   /usr/bin/pwd

   [vagrant@host1 ~]$ which ls
   alias ls='ls -color=auto'
               /usr/bin/ls

```

```

13. man : 각종 명령어, 프로그램의 사용법을 확인하는 명령어

   [vagrant/host1 ~]$ man pwd

   새로운 창에서
   PWD(1)

   NAME
          pwd - print name of current/working directroy
   SYNOPSIS
          pwd [OPTION]...
   .
   .
   .

```

```

14 apropos : 검색어와 관련있는 명령어를 설명과 함께 출력하는 명령어

   [vagrant@host1 ~]$ apropos pwd

   lckpwdf (3)          - get shaodw ~
   pwd (1)              - print name of ~
   pwd (1p)             - return working ~
   .
   .
   .

```

```

15. info : 리눅스 명령어의 사용 방법, 옵션 등을 나타내는 명령어

   [vagrnat@host1 ~]$ info pwd

```

```

16. whatis : 명령어에 대한 간단한 설명을 출력하는 명령어
   [vagrant@host1 ~]$ whatis ls
   ls (1)               - list directory contents
   ls (1p)              - list directory contents

```

```

17. alias : 명령어를 별칭으로 지정하는 명령어

   [vagrant@host1 ~]$ alias where='pwd'
   [vagrant@host1 ~]$ where
   /home/vagrant

   $ alias 단축명령어='명령어'
   $ unalias : 별칭해제 명령어

```

---

### 웹기술의 등장 과정

인터넷은 1960년대에 미국 국방부 산하의 고등 연구국에서 군사적 목적으로 처음 개발되었다.

하지만 우리가 아는 "인터넷"의 시작은 1990년대 팀 버너스 리가 개발한 월드 와이드 웹(World Wide Web)이다.

WWW은 물리학자들 사이에서 효율적이고 신속한 자료를 공유받기 위한 목적 이었다.
그렇게 1990년 말에 HyperText라는 프로젝트가 생겨났고 HyperText를 이용한 기술 중 중요한 두가지가 탄생했다.

팀 버너스 리는 웹서버와 웹브라우저를 개발하고, 이 둘이 통신할때 사용하는 프로토콜인 HTTP라는 통신 규약을 정의하고, 웹 브라우저에 정보를 표현할 수 있게 하는 프로그래밍 언어, HTML을 발명했다.
그리고, 이러한 기술들을 Public Domain으로  공개하면서 인터넷은 폭발적으로 발전하게 된다.

* 1세대 웹 서비스 - Web System Architecture(정적 웹)
   * 웹 서버가 HTML 페이지 전체를 클라이언트에게 전송

* 2세대 웹 서비스 - User Interaction의 증가(동적 웹)
   * 웹 기반의 언어인 자바스크립트가 출현
   * Web server에서 전체 HTML 페이지 뿐만 아니라 JavaScript를 통해 서버와 필요한 데이터만 주고 받음

* 3세대 웹 서비스 - SPA (Frontend / Backend)
   * 자바스크립트가 주가 되고 그 안에 일부 HTML, CSS가 포함
   * 단일의 html 페이지에서 전체 웹 사이트/서비스를 구현
   * 파일은 처음 한번만 송수신. 그 뒤로는 실시간 데이터만 주고 받음
   * 처음 전송된 단일 HTML 페이지에 포함되어 있는 JavaScript 에서 필요한
     데이터를 API 서버로부터 호출해 필요한 화면을 새롭게 구성해주는 방식
   * HTML 태그 자체를 자바스크립트가 동적으로 생성
   * 프론트엔드와 백엔드가 나뉘게 되는 기점
        (프론트 - UI/UX, 백엔드 - Data)
   * 구조적으로 분리가 되면서, Frontend 서버와 Backend API 서버도 분리가 된다.

---

<div align="center">

<a href="https://github.com/Leemyeongjun/Leemyeongjun.github.io"><img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fleemyeongjun.github.io&count_bg=%23000000&title_bg=%23000000&icon=&icon_color=%23E7E7E7&title=Visit&edge_flat=false"/></a>

<a href="https://www.twitter.com" target="_blank"><img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-thebadge&logo=트위터아이콘&logoColor=black"/></a>

<a href="https://ko-kr.facebook.com/" target="_blank"><img src="https://img.shields.io/badge/Facebook-1877F2?style=for-thebadge&logo=페이스북아이콘&logoColor=black"/></a>

<a href="https://www.youtube.com/" target="_blank"><img src="https://img.shields.io/badge/Youtube-FF0000?style=for-thebadge&logo=유튜브아이콘&logoColor=wihte"/></a>

<a href="https://www.naver.com/" target="_blank"><img src="https://img.shields.io/badge/Naver-03C75A?style=for-thebadge&logo=네이버아이콘&logoColor=wihte"/></a>

</div>
