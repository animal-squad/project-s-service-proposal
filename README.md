# project-s-service-proposal
서비스 기획서 업데이트를 확인할 수 있는 레포지토리입니다.

# 링킷(Link Bucket) 서비스 기획서

## **프로젝트 소개**

### 개발자 업무 도우미 링킷(Link Bucket)

브라우저 탭을 한 번에 묶어 저장하고 주제별로 정리해주는 AI 정리 어시스턴트 서비스입니다.

## **프로젝트 목표**

1. 프로젝트 기획
2. 계획한 기능 구현 완료
3. 실서비스 운영

### AI 관리 기능

- 정리 가능한 기록물 종류
    - 크롬 브라우저 탭(링크)
    - 링크 바구니의 제목&메모
1. 링크 입력
2. 링크에 대한 카테고리 태그 자동 생성 기능
3. 오래된 링크(바구니) 삭제 기능
    
    세부 기능
    
    - **입력:**
        1. **(익스텐션) 브라우저 상단 버튼 혹은 특정 단축키 클릭 → 현재 열린 탭 저장 가능한 팝업 생성**
            - **사용자는 링크 바구니의 제목&메모 입력 가능**
            - **현재 탭만 저장 / 전체 탭 저장 중 선택 가능**
        2. 서비스 내에 접속 → 링크 붙여넣기
    - **AI 분류: AI가 링크(바구니)의 제목, 메모와 링크 속 문서 내용을 읽고(크롤링) 카테고리 분류 후 태그 생성**
    - 삭제: 기록물 확인율이 낮거나, 추가한지 너무 오래된 링크(바구니)는 자동 삭제
        - 사용자 별 삭제 기준 설정 기능: 주기 등

### 리마인드 및 추천 기능

1. 삭제 전 확인 알림
2. 링크 추천

  세부 기능
  
  - 미리 알림: AI 관리 기능의 ‘삭제’ 전 사용자가 확인하도록 알림 제공
  - **링크 추천:**
      - **사용자가 링크를 조회했는지 확인**
      - **사용자가 읽은 링크, 읽지 않은 링크를 UI로 나누어서 제공**
      - 사용자가 저장한 링크 기반으로 관심사를 분석, 사용자가 관심 있지만 오랫동안 확인하지 않은 링크를 확인하도록 추천 알림 제공

### SNS 기능

1. **내 링크 바구니 공유 기능**
    - **다른 사람에게 내 링크 바구니 보내기**
    - **다른 사용자의 링크 바구니를 자신의 스토리지에 가져온 후, 수정 가능(원작자와 동기화되지 않음)**

****볼드체 처리된 부분이 1차 프로젝트 기간(~11/13)까지 완료할 최소 기능**

[1차 프로젝트 기간 MVP](https://github.com/animal-squad/project-s-service-proposal/blob/main/1st_mvp_241008.md)

## **사용 스택**

`FullStack`

- OpenGraph (페이지 썸네일)
- 브라우저 별 Extension 또는 앱
- Nest.js
- MongoDB
- React
    - Zustand

`Cloud`

- AWS(RDS,  ALB, EBS)
- Kubernetes(Kubeadm)
- Jenkins
- Kaniko
- Prometheus
- Grafana
- Ansible
- Terraform

`AI`

- Python
- OpenAI API
- FastAPI

### 역할

```
sean.park (팀장)
- 서버 운영 관리 및 스케일링
- 트래픽 관리
- 데이터 스토리지 생성/관리
- CI/CD 파이프라인 설정
- 로그 및 모니터링 시스템 구성
- 네트워크 보안 관리

alyssa.jeong(정예은)/인공지능
- OpenAI API 활용한 문서 정리 구축
- 사용자 개인화 추천 시스템 구축
 
bruce.kim(김도현)/풀스택
- React를 활용한 Frontend 화면 구현
- Recoil, Zustand 등의 상태관리 라이브러리 도입
- 백엔드 및 AI 서버와의 통신 구현
- 백엔드 개발에 참여

gene.an
- OpenAI API 활용한 문서 정리 구축
- AI 모델 서빙

nina.lee(이미나)/풀스택
- API 설계 작성
- 데이터베이스 설계
- 백엔드 코드 구현
- 테스트 코드 작성

ronald.lee
- CI/CD 파이프라인
- 로그 및 모니터링 시스템
- 서버 운영
- DB 서버 생성 및 구축
- 백업 자동화

```

### 유사 서비스

- 차별점
    - AI 기반 카테고리 분석, 알림, 추천시스템
    - 브라우저 익스텐션을 활용하여 PC 환경에서 사용 가능

  [SOPT](https://www.sopt.org/project/153)
  
  [YAPP](https://www.yapp.co.kr/project/24th/pokit)

