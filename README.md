![Auto Assign](https://github.com/Side-Project-26-01/demo-repository/actions/workflows/auto-assign.yml/badge.svg)

![Proof HTML](https://github.com/Side-Project-26-01/demo-repository/actions/workflows/proof-html.yml/badge.svg)

# Welcome to your organization's demo respository
This code repository (or "repo") is designed to demonstrate the best GitHub has to offer with the least amount of noise.

The repo includes an `index.html` file (so it can render a web page), two GitHub Actions workflows, and a CSS stylesheet dependency.

## Git 및 버전 관리 규칙 (필수 준수)

협업 시 충돌을 방지하고 코드 리뷰를 원활하게 진행하기 위해 모든 팀원은 다음 규칙을 반드시 준수해 주세요

### 🚨 개인 브랜치 사용 및 Pull Request (PR) 워크플로우

**메인 개발은 절대 `main` 브랜치에서 직접 작업하지 않습니다.** 모든 변경 사항은 **개인 브랜치**에서 진행 후, **Pull Request(PR)를 통해서만** `main` 브랜치에 통합합니다.

| 유형 | 의미 | 예시 |
| :--- | :--- | :--- |
| **`feat`** | 새로운 기능 추가 | `feat: 사용자 로그인 기능 추가` |
| **`fix`** | 버그 수정 | `fix: 메인 페이지 이미지 깨짐 현상 수정` |
| **`style`** | 코드 포맷 변경 (스타일만) | `style: CSS 띄어쓰기 및 주석 정리` |
| **`docs`** | 문서 변경 (README 등) | `docs: README.md 내용 업데이트` |
| **`chore`** | 기타 설정, 빌드 작업 | `chore: .gitignore 파일 업데이트` |


## [Project] B2B Jewel-Mall : B2B 귀금속 수출업체 소개 랜딩 페이지 & 고객, order 관리 시스템

## 1. 프로젝트 개요

-   **목적**: 귀금속 수출 산업의 디지털 전환(DX)을 위한 주문 및 인보이스 관리 시스템 구축.
    
-   **배경**:  **AS-IS**:현업의 수동 고객 오더 메신저로 받기 및 엑셀 인보이스 작업  **TO-BE**: 고객 정보 기반 주문 자동화, API 기반의 체계적인 장바구니 , 고객정보 데이터 관리 프로세스 수립.
    
-   **기대효과**: 실제 상용 서비스 수준의 ERD/API/PRD 설계 및 Enterprise 급 배포 경험 확보.
    

----------

## 2. 개발 요구사항 명세 (MVP)

### 🛠 핵심 기능 (Core Features)

1.  **인증 및 인가 (Auth)**
    
    -   Spring Security 기반 보안 설정.
        
    -   바이어 접근성 향상을 위한 Google/소셜 로그인 연동.
        
2.  **회원 및 업체 관리 (CRM)**
    
    -   B2B 기업 회원 등급(Tier) 및 바이어 정보 관리.
        
3.  **주문 관리 시스템 (Core OMS)**
    
    -   수동 엑셀 인보이스를 대체하는 디지털 주문서 자동 생성.
        
    -   주문 생명주기 관리: `접수` → `결제 확인` → `배송` → `완료`.
        
4.  **장바구니 및 견적함**
    
    -   상품 담기 기능.
        

### 💻 기술 스택 (Tech Stack)

-   **Backend**: Java + SpringBoot (현업 표준 준수)
    
-   **Frontend**: TypeScript + React (컴포넌트 기반 UI)
    
-   **Database**: PostgreSQL
    
-   **Infrastructure**: AWS (Free-tier) & Oracle, Docker Container, EKS , Railway
    
-   **Collaborator Tools**: Figma, GitHub Enterprise, Slack Pro, Trello
    

----------

## 3. 팀 구성 및 R&R (Role & Responsibilities)

**이름**

**역할**

**주요 담당 업무**

**17상호님**

**기획 /Infra /QA**

비즈니스 로직 정의, 팀원모집 및 회의주도, 인프라 배포 & csp 비용 관리 & Readme.md 작성, QA 

**17진욱님**

**Frontend**

요구사항 명세서 정의, Figma 와이어프레임 구현, React 클라이언트 개발, Next.js , API 연동 , FE QA

**17상우님**

**Backend / Infra**

ERD 설계 및 DB 구축, API연동 , Swagger, CI/CD 파이프라인, BE QA

** 준영님(예정) **
chatbot , 데이터 시각화, Claude.md 작성

**현직 멘토**
**Advisor  (기술 스택 의사결정 지원 및 인프라 구축 가이드)**

**BE 현직AUTOEVER 김호진님**
**FE 전직 TOSS 6년차**
**Infra 현직 AWS korea 2년차**



----------

## 4. 단기 로드맵 (Roadmap) & (Milestones)

*주차*

**단계**

*1-3주*

**기획 및 설계**

요구사항 명세 확정, 타 사이트 벤치마킹 malabargoldanddiamonds, ERD 설계, API 명세서 확정, Figma 시안

*4-7주*

**집중 개발**

**FE**

**Store**
**Brand**

**BE**
Auth(로그인) 기능, 장바구니/주문 생성 로직 개발, FE-BE API 연동

*7-8주차*

**인프라 및 배포**

AWS 환경 구축, Docker 컨테이너화, 도메인 연결 및 통합 테스트

9주차
**마무리**

QA 및 버그 수정, 프로젝트 문서화(README/API documentation/Claude.md)

----------

## 5. 협업 및 관리 가이드

-   **Documentation**: 핵심 비즈니스 로직(언어 전환, 동시성 제어, 세션 만료 등) 및 API 엔드포인트는 `Claude.md`에 상시 업데이트.
    
-   **Communication**: 모든 의사결정, 회의사항 및 정보공유 Discord 에 기록하고, 작업 진행도는 Trello 칸반 보드로 시각화.
    
-   **Code Quality**: 현직자 멘토, copilot code review 거쳐 Main Branch Merge.
