
<br>

<h1 align="center"> DevOps 아키텍처 구현 </h1>
<br>
<br>

## 🎁팀원 소개
---

&nbsp;　&nbsp;　&nbsp;　&nbsp;　&nbsp;　&nbsp;　&nbsp;　&nbsp;　  **🐥[김다윤](https://github.com/dyun23)**&nbsp;　  **🦊[김우혁](https://github.com/sue06004)** &nbsp;　  **😼[도지민](https://github.com/jimnyy)** &nbsp;　  **🐰[이가은](https://github.com/dlrkdms125)** &nbsp;　  **🐻[이재룡](https://github.com/ashd89)**
<br><br>


### 목차
- [프로젝트 목표](#-프로젝트-목표)
- [기술 스택](#-기술-스택)
- [CI/CD 의 기대효과](#-cicd-의-기대효과)
- [DevOps 운영 환경](#-운영-환경)
- [배포 방식](#-우리팀의-배포-방식)
- [CI/CD 시나리오](#-cicd-시나리오)
<br><br>
---
## 🤳 프로젝트 목표
---
#### 1. 운영 중인 환경에 CI/CD 적용
  -  코드 변경 사항을 자동으로 빌드, 테스트, 배포하여 문제 발생 시 신속한 조치가 가능하도록 함.
  -  팀원들이 더 쉽게 협업할 수 있고, 서로의 작업이 자동으로 통합되며, 충돌이 최소화되도록 함.
#### 2. 유연한 배포
  - 무중단 배포 방식인 <Blue-Green 배포 방식> 을 사용하여 서비스 중단 없이 새로운 기능을 배포할 수 있고, 사용자에게 지속적으로 안정적인 서비스를 제공 가능하게 함.
  - 새로운 버전(Green) 배포 후 문제가 발생할 경우, 기존 버전(Blue)으로 빠르게 롤백이 가능하므로 안정적인 롤백이 가능함.

<br>

---
## 🛠 기술 스택
---
<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=GitHub&logoColor=white&color=black"></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Git-F05032?style=flat&logo=Git&logoColor=white&color=ffa500"></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Docker-2496ED?style=flat&logo=Docker&logoColor=black&color=blue"/></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=Kubernetes&logoColor=blue&color=skyblue"/></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Jenkins-D24939?style=flat&logo=jenkins&logoColor=white"/></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Slack-4A154B?style=flat&logo=Slack&logoColor=yellow&color=purple"/></a></a>
<br><br>

---
## 🔎 CI/CD 의 기대효과 
---
전통적인 배포 파이프라인은 코드 변경 사항을 커밋-> 코드 통합 -> 빌드 및 테스트 -> 배포 준비 및 배포 -> 모니터링<br>
이렇듯 전통적인 배포 파이프라인은 수동 작업이 많고, 통합의 어려움, 개발자의 오류 리스크를 증가 시켰다.

현대의 CI/CD는 위와 같은 문제점들을 해결함과 동시에 더 빠르고 안정적인 소프트웨어 배포가 가능하다.

- #### CI를 통해 애플리케이션 변경 사항이 자동으로 에러 테스트를 거치고, 깃허브 레포지토리에 업로드 됨으로써

#### &nbsp;&nbsp;&nbsp;　신뢰성 높은 환경을 구성 할 수 있고, 항시 배포 가능한 환경이 된다.

- #### CD는 개발자가 깃허브 레포지토리에 있는 애플리케이션을 수 분내에 지속적으로 배포함으로써,

#### &nbsp;&nbsp;&nbsp;　수동으로 배포할 때 보다 시간을 절약 할 수 있다.

<br>

---
## 🌌 운영 환경
---
#### - 클러스터 노드 구성
💻 Master 1대, 💻 Worker 4대의 클러스터 구성

<br>

#### - 쿠버네티스 적용
-  운영 환경에서 유연성, 동일한 환경을 제공하여 버그를 최소화할 수 있다.
-  프라이빗 클라우드 인프라에서 안정적으로 실행될 수 있는 기능을 제공하여 서비스가 안정적으로 운영되고 개발 및 배포 과정을 더욱 효율적으로 만들어 주었다.


### ⚙ 쿠버네티스 선택 이유

<br>


### ⚙ 젠킨스 선택 이유

<br><br>

### 📁&nbsp;&nbsp;k8s 아키텍처

<br>
<br>


### 💡&nbsp;&nbsp;시스템 아키텍처

<br>
<br>

---

## 📣 우리팀의 배포 방식
---
우리팀은 무중단 배포 방식을 선택했는데, 그 중에 Blue/Green 배포 방식을 적용하였다.
<br><br><br>



---
## 🎞 CI/CD 시나리오
---

#### 1. develop branch에서 통합이 이루어지면, github action이 Junit을 통해 작성된 테스트 코드를 실행한다.

#### 2. 깃허브(원격 저장소) main branch 에 최신 버전의 프로젝트가 "push" 된다.

#### 3. 깃허브는 젠킨스에게 Webhook을 보낸다.

#### 4. 젠킨스는 파이프라인에 저장된 절차를 실행한다.

#### &nbsp;　 a. 젠킨스 서버에 깃허브의 있는 프로젝트를 가져온다. (git clone)



<br>
<br>

---
## 💻 CI/CD 테스트 및 결과
---
<br>
<br>

