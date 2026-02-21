# **PRD (Practice) — Deco indco**

> Product Requirements DocumentVersion: v1.0 (Kickoff Draft)
Owner: Satoshi (PO) Timeline:  8weeks (2 months)
> 

---

### 📝 [수정본] Jewel-Trade PRD (v1.0)

> 수정 사항: 바이어 역할 추가, 장바구니(견적함), T/T 입금 확인 프로세스 명시.
> 

**PRD (Practice) — Jewel-TradeProduct Requirements Document**

- **Version:** v1.0 (Final Draft)
- **Timeline:** 8 weeks (2 months)

### 1. 배경 (Background)

**1.1 산업 / 사업 상황**

- **산업군:** 귀금속(주얼리) 수출 B2B
- **특성:** 해외 바이어와의 주문 커뮤니케이션 + 수동 인보이스(Excel) 의존도 높음

**1.2 현재 문제 (As-is)**

- 회사 소개 웹사이트 부재
- 주문 접수 후 담당자가 엑셀로 인보이스를 수작업 작성 (휴먼 에러 위험).
- 주문 상태(제작 중, 배송 중)를 바이어가 실시간으로 확인 불가.

**1.3 우리가 해결하려는 핵심 (Target)**

- "엑셀 수작업" → "웹 기반 주문 관리(OMS)"**로 전환.
- 바이어가 직접 주문(견적)을 넣고, 관리자가 승인하면 PDF 인보이스가 자동 발급되는 구조.

### 2. 목적 (Objectives)

**2.1 프로젝트 목적**

- **포트폴리오:** 기획-ERD-API-개발-배포까지 전체 사이클 완주.
- **실무 개선:** 실제 T/T(무통장 입금) 기반의 B2B 거래 흐름을 웹으로 구현.
- **레거시:** 데모 이후에도 deco에서 실제 카탈로그/주문용으로 사용 가능하도록 구축.

**2.2 성공 기준 (Success Metrics)**

- 바이어는 가입 후 어드민이 구매 권한을 부여해야 주문 가능하다
- 바이어가 로그인 후 상품을 담아 주문 요청까지 5**분 이내** 완료.
- 주문 확정 시 **PDF 인보이스가 즉시 자동 생성**되어 다운로드 가능.
- AWS 환경에 배포되어 외부(해외)에서 접속 가능.(North korea 등 제외) (해킹방지)

### 3. 범위 (Scope) MVP 기준

**3.1 포함 (In Scope)**

- ✅ **공통:** 회사 소개(Brand), 상품 목록(Catalog) 조회
- ✅ **인증:** email로 관리자 로그인(Admin),바이어 로그인,구글 소셜 로그인(시간남으면) (Buyer), spring security & **Redis 이용** why: JWT 블랙리스트(로그아웃 토큰 무효화) 및 세션 관리
- ✅ **주문(핵심):**
    - **장바구니(견적함):** 상품을 담아 '견적 요청(Order Request)' 전송
    - **상태 관리:** 주문 접수 → 인보이스 발행 → **T/T 입금 확인(영수증 업로드)** → 배송 중 확인→ 완료
- ✅ **관리:** 회원 user /상품 product 관리(CRUD), 주문 승인 및 PDF 인보이스 발행
- ✅ **인프라:** AWS 배포 및 도메인 연결

**3.2 제외 (Out of Scope)**

- ❌ **PG사 결제 연동** (T/T 무통장 입금 프로세스로 대체)
- ❌ 실시간 재고 연동 (ERP 미연동, 수동 관리)
- ❌ 다국어 처리 (영어 단일 지원)
