
<br>

<h1 align="center"> 데브옵스 아키텍처 구현 </h1>

### 🤼‍♂️팀원 소개

<br><br>
&nbsp;　&nbsp;　&nbsp;　&nbsp;　&nbsp;　&nbsp;　&nbsp;　&nbsp;　  **🐥[김다윤](https://github.com/dyun23)**&nbsp;　  **🦊[김우혁](https://github.com/sue06004)** &nbsp;　  **😼[도지민](https://github.com/jimnyy)** &nbsp;　  **🐰[이가은](https://github.com/dlrkdms125)** &nbsp;　  **🐻[이재룡](https://github.com/ashd89)**
<br><br><br><br><br>

## ✨ 프로젝트 기본 소개

<br>

## 📌 기술 스택

&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=GitHub&logoColor=white&color=black"></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Git-F05032?style=flat&logo=Git&logoColor=white&color=ffa500"></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Jenkins-D24939?style=flat&logo=jenkins&logoColor=white"/></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Docker-2496ED?style=flat&logo=Docker&logoColor=black&color=blue"/></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=Kubernetes&logoColor=blue&color=skyblue"/></a></a>
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://img.shields.io/badge/Slack-4A154B?style=flat&logo=Slack&logoColor=yellow&color=purple"/></a></a>
<br>
<br>

---

## 🤳 프로젝트 목표


<br>

##  CI / CD 구성의 필요성

### 🧐 기존 프로젝트 현황

- #### 팀원끼리 기능을 만든 후 통합하는 과정에서 충돌을 해결하고, 테스트하는 과정이 지속적으로 반복되다 보니,

#### &nbsp;&nbsp;&nbsp;　절차가 까다로워, 직접 웹페이지로 접속하여 기능을 테스트하거나, 포스트맨을 이용해 테스트를 하였다.

#### &nbsp;&nbsp;&nbsp;&nbsp;　 ➡ 따라서, 많은 시간과 비용이 발생하며, 다양한 케이스를 테스트할 수 없게 된다. ( CI의 필요성 대두 )

- #### 개발용 컴퓨터에서 직접 빌드를 하고 배포용 컴퓨터에 배포파일을 옮겨 배포

  #### ➡ 새로운 기능을 추가하거나, 에러를 수정할 때마다 배포과정을 반복한다. ( CD 필요성 대두 )

<br>

## CI/CD 의 기대효과 💥

- #### CI를 통해 애플리케이션 변경 사항이 자동으로 에러 테스트를 거치고, 깃허브 레포지토리에 업로드 됨으로써

#### &nbsp;&nbsp;&nbsp;　신뢰성 높은 환경을 구성 할 수 있고, 항시 배포 가능한 환경이 된다.

- #### CD는 개발자가 깃허브 레포지토리에 있는 애플리케이션을 수 분내에 지속적으로 배포함으로써,

#### &nbsp;&nbsp;&nbsp;　수동으로 배포할 때 보다 시간을 절약 할 수 있다.

  <br>

---

## 🖥️ 운영 환경 : 쿠버네티스 & 컨테이너 운영 환경 구성

### 🧐 쿠버네티스 선택 이유

<br>


### 🧐 젠킨스 선택 이유


<br>


### 🧐우리팀의 배포 방식

<br>

---

### 📁 &nbsp;&nbsp;k8s 클러스터 구성도

<br>


## 💡&nbsp;&nbsp;시스템 아키텍처

<br>


<br>

### 💽&nbsp;&nbsp;CI/CD 시스템 아키텍처

<br>

---

<br>

<br>
<img src="./img/cicdArhitecture.jpg">

<br>

### 🚀 CI/CD 시나리오 : blue/green 방식을 이용한 무중단 배포

#### 1. develop branch에서 통합이 이루어지면, github action이 Junit을 통해 작성된 테스트 코드를 실행한다.

#### 2. 깃허브(원격 저장소) main branch 에 최신 버전의 프로젝트가 "push" 된다.

#### 3. 깃허브는 젠킨스에게 Webhook을 보낸다.

#### 4. 젠킨스는 파이프라인에 저장된 절차를 실행한다.

#### &nbsp;　 a. 젠킨스 서버에 깃허브의 있는 프로젝트를 가져온다. (git clone)



<br>

---

<br>

## 💻 CI/CD 테스트 및 결과

