
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
  -  코드 변경 사항을 자동으로 빌드 및 배포하여 개발에만 집중 할 수 있다.
  -  서로의 작업이 자동으로 통합되며, 팀원들과 더 쉽게 협업할 수 있다. 
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
<br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/vuejs-%2335495e.svg?style=flat&logo=vuedotjs&logoColor=%234FC08D"/></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/SpringBoot-181717?style=flat&logo=SpringBoot&logoColor=6DB33F&color=white"></a>
<br><br>

---
## 🔎 CI/CD 의 기대효과 
---
전통적인 배포 파이프라인은 코드 변경 사항을 커밋-> 코드 통합 -> 빌드 -> 배포 준비 및 배포 -> 모니터링 방식이었다. <br>
이렇듯 전통적인 배포 파이프라인은 수동 작업이 많고, 통합의 어려움, 개발자의 오류 리스크를 증가 시켰다.

현대의 CI/CD는 위와 같은 문제점들을 보완함과 동시에 더 빠르고 안정적인 소프트웨어 배포가 가능하다.

- #### CI를 통해 애플리케이션 변경 사항이 자동으로 에러 테스트를 거치고, 깃허브 레포지토리에 업로드 됨으로써

#### &nbsp;&nbsp;&nbsp;　신뢰성 높은 환경을 구성 할 수 있고, 항시 배포 가능한 환경이 된다.

- #### CD는 개발자가 깃허브 레포지토리에 있는 애플리케이션을 수 분내에 지속적으로 배포함으로써,

#### &nbsp;&nbsp;&nbsp;　수동으로 배포할 때 보다 시간을 절약 할 수 있다.

<br>

---
## 🌌 운영 환경
---
#### - 클러스터 노드 구성
💻 Master 1대<br>
💻 Worker 4대의 클러스터 구성
<br>

#### - 쿠버네티스 적용
-  운영 환경에서 유연성, 동일한 환경을 제공하여 버그를 최소화할 수 있다.
-  프라이빗 클라우드 인프라에서 안정적으로 실행될 수 있는 기능을 제공하여 서비스가 안정적으로 운영되고 개발 및 배포 과정을 더욱 효율적으로 만들어 주었다.


### 쿠버네티스 선택 이유  ⚙ 
#### 1. Automated Deployment
    
    애플리케이션의 자동 배포, 업데이트, 롤백을 지원하므로, 점진적 업데이트를 통해 무중단 배포 수행 가능하다
    
#### 2. Scaling and Autoscaling
    
    쿠버네티스는 클러스터 내의 리소스를 효율적으로 관리하고, 자동으로 Pod의 수를 조절할 수 있는 오토스케일링 기능으르 제공하므로, 트래픽 변화에 동적으로 대응 가능하다.
    
#### 3. Service  and Load Balancing
    
     애플리케이션의 컴포넌트 간의 통신을 쉽게 설정하고 관리할 수 있다.

<br>


### 젠킨스 선택 이유 ⚙ 
#### 1. CI/CD
    
     코드 변경 사항을 자동으로 빌드하고 테스트하는 CI/CD 파이프라인을 쉽게 구성할 수 있는 기능을 제공하여, 배포를 자동화하여 개발 주기를 단축시킨다
    
#### 2. Flexibility
    
    다양한 빌드 도구와 배포 시스템을 지원하며, 파이프라인을 코드로 정의할 수 있어, 복잡한 배포 프로세스를 자동화하고 버전 관리를 할 수 있다

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
우리팀은 다운 타임이 없는 무중단 배포 방식 중 Blue/Green 배포 방식을 적용하였다.
### Blue/Green 배포 방식 📘📗
- 블루그린 배포 방식은 지속적 배포 방식 중 하나로 신 버전을 배포가 완료되면 구 버전을 바라보던 서비스가 신 버전으로 일제히 전환하도록 하는 방식이다.
- 신속한 업데이트와 동시에 서버 안정성이 좋기 때문에 이 방식을 선택했다.
<br><br><br>



---
## 🎞 CI/CD 시나리오
---

#### 1. github에 be-dev, fe-dev에 최신 버전 프로젝트를 머지
 a. 최신 버전 코드를 머지하면 이벤트 발생

#### 2. github는 젠킨스에게 webhook을 통해서 젠킨스에게 이벤트 전달

#### 3. 젠킨스는 파이프라인에 저장된 절차 실행
- a. 젠킨스는 github에서 최신 코드를 clone한다.
- b. 클론된 코드를 기반으로 빌드 작업 수행
- c. 빌드를 통해 도커 이미지 생성 및 도커 허브에 push
    
#### 4. 쿠버네티스 마스터에 SSH 접속 후 쉘스크립트 실행
  1) 현재 실행 중인 디플로이먼트가 blue라면 green으로 디플로이먼트 생성
  -    젠킨스에서 도커 허브에 푸쉬한 이미지로 컨테이너 실행
  2) rollout명령어를 활용하여 생성한 디플로이먼트내의 프로그램이 정상 작동인지 확인
  3) 정상 작동중이라면 서비스를 신버전 디플로이먼트의 파드들과 연결하도록 수정
  4) 구버전 디플로이먼트 삭제   

 CI/CD 프로세스와 Blue-Green 배포 방식을 통해 빠르고 안전한 애플리케이션 배포를 가능하게 하며, 쿠버네티스의 기능을 활용하여 확장성 및 복구 능력이 극대화 가능하다.


<br>
<br>

---
## 💻 CI/CD 테스트 및 결과
---
<br>
<br>

