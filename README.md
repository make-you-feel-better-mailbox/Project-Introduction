# 너를 위로 Project Introduction
- 위로가 필요한 익명의 누군가에게 따듯한 말 한마디 건네보시는건 어떤가요?
- 일상에 지친 시간을 누군가에게 위로받아보시는 건 어떤가요?
- 분란이나 경쟁에서 벗어나 서로를 위로하는 SNS 힐링 우편함 서비스 너를 위로입니다.

## Project Planning

#### 기획 의도

- 익명으로서 얻는 용기로 서로를 위로하기 위한 SNS 서비스

## ERD

![Make you feel better ERD (3)](https://github.com/make-you-feel-better-mailbox/Project-Introduction/assets/105261146/e4a1d23f-5f51-4992-8be1-8bc9cd71d339)


## Service Architecture

![make-you-feel-better-system-with-lang (4)](https://github.com/make-you-feel-better-mailbox/Project-Introduction/assets/105261146/5015eccc-e035-4dcf-a981-4349a1ed3f5a)


## Service View

![IMG_0005](https://github.com/user-attachments/assets/e5d3043f-6780-46d0-a77d-9dcb8215afbf)

#### 주요 기능

- WebSocket을 통한 사용자간 채팅
- OAuth를 통한 로그인 ( 구글 로그인 )
- 랜덤 우편 발송
- gRPC를 통한 경량화된 서버간 통신
- 우편 딜레이 발송
- 유저간 Follow
- 추천 게시글 조회

#### 사용 기술

Java, Kotlin, JDK 21, Spring Boot, Spring Cloud, Spring Batch, Spring Security, gRPC, Kafka, JPA, JWT, Query DSL, Redisson, OAuth 2.0, Web Socket, MySQL, Redis, Kubernetes, Jenkins, ArgoCD, Docker, Git, Github, Spring Rest Docs, Asciidoc

#### 느낀 점

- gRPC
  > MSA 환경에서 각 서비스가 독립적으로 가지고 있는 도메인의 데이터를 가져오기 위해 기존 사용했던 CQRS, Zero-payload가 아닌 다른 방법을 사용해보고 싶었고 네트워크 오버헤드를 줄이고 데이터를 보다 작고 빠르게 주고받기 위해 서버간 통신에 사용했습니다.
CQRS, Zero-payload 방식은 서버간 Event Streaming이 필요해 외부 의존성이 하나 더 생기게 되고 순서에 대한 보장이 필요할때 구현이 까다로워 질 수 있는 점이 있었습니다. gRPC는 그러한 문제가 없다는 점에서 좋았습니다. 그러나 유저의 Request 과정에서 서버간 gRPC 통신을 한번 더 거쳐야하기 때문에 레이턴시가 조금 더 생긴다는 단점이 있었던 것 같습니다. 
전자와 후자를 비교했을때 서버 아키텍처를 어떻게 구성하는 지에 따라 장단점이 있기때문에 만들고자 하는 서비스가 어떤 것을 목표로 하는지 잘 생각하고 결정해야겠다는 생각을 가지게 됐습니다.

- Jenkins, ArgoCD
  > CI/CD를 구축함으로써 가질 수 있는 장점은 아주 많다고 생각합니다. 그중에서도 제가 느꼈던 점은
개발자가 불필요하게 반복되는 배포와 통합의 과정을 거치지 않아도 되기때문에 개발에 집중 할 수 있는 환경이 가장 큰 것 같습니다.
위와 같은 장점은 사실 회사에서 CI/CD가 이미 구축돼 있었기 때문에 사용하면서 느꼈던 점이였습니다. 
이번 프로젝트를 통해서 위 환경을 구성하기 위해 노력하며 DevOps 분야에 흥미를 느낄 수 있었습니다.

- Kubernetes
  > 컨테이너 오케스트레이션 플랫폼 역시 기존 회사에서 구성돼 있던 환경을 이용했었습니다. 그렇기 때문에 컨테이너 오케스트레이션 플랫폼을 사용하면서 느낄 수 있는 장점들( 무중단 배포, 선언전 API 특성을 이용한 자동 관리 및 자동 복구, 파드 스케일 인, 아웃의 용이함  )은 이미 너무나 많이 체감한 상태였습니다.
그러나 관리형 쿠버네티스이기도 했고, 직접 환경을 구성해본적은 없었기 때문에 이번에 직접 구성해 보고 싶었습니다.
직접 구성해보며 역시 편리한만큼이나 공부해야할 것이 많다는 것을 느낄 수 있었습니다.

#### 별첨

ERD Cloud : https://www.erdcloud.com/d/Gz8Yq6ibQE77ub7sE

## Developer

https://github.com/12OneTwo12
