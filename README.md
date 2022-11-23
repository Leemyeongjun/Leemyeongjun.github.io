
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

   [vagrant/@host1 ~]$ pwd  
   
   /home/vagrant

```

---

<div align="center">

<a href="https://github.com/Leemyeongjun/Leemyeongjun.github.io"><img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fleemyeongjun.github.io&count_bg=%23000000&title_bg=%23000000&icon=&icon_color=%23E7E7E7&title=Visit&edge_flat=false"/></a>

<a href="https://www.twitter.com" target="_blank"><img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-thebadge&logo=트위터아이콘&logoColor=black"/></a>

<a href="https://ko-kr.facebook.com/" target="_blank"><img src="https://img.shields.io/badge/Facebook-1877F2?style=for-thebadge&logo=페이스북아이콘&logoColor=black"/></a>

<a href="https://www.youtube.com/" target="_blank"><img src="https://img.shields.io/badge/Youtube-FF0000?style=for-thebadge&logo=유튜브아이콘&logoColor=wihte"/></a>

<a href="https://www.naver.com/" target="_blank"><img src="https://img.shields.io/badge/Naver-03C75A?style=for-thebadge&logo=네이버아이콘&logoColor=wihte"/></a>

</div>
