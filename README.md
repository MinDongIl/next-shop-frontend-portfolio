# Next Shop Frontend (Portfolio)

**레포지토리명**: next-shop-frontend-portfolio  
**작업자**: MinDongil  

---

## 프로젝트 개요
이 프로젝트는 쇼핑몰 웹서비스의 프론트엔드 부분으로, Next.js 기반으로 개발되었습니다.  
주요 목표는 백엔드 API(cart, order, payment, user)와 안정적으로 연동하며, 로그인/결제 흐름에서 JWT 기반 인증을 유지하는 것입니다.  
프론트엔드 작업의 핵심은 API 연동과 데이터 구조 통일이며, UI/디자인보다는 실제 서비스 연동과 구조적 안정성에 집중했습니다.

---

## 내 역할 (MinDongil)

1. **API 연동 및 데이터 구조 통일**
   - 기존 프론트 구조를 전체적으로 점검하고 API 호출 중심으로 폴더 구조 및 데이터 흐름 재정비
   - 백엔드 API(cart, order, payment, user)에 맞춰 프론트 엔티티 구조 표준화
   - 실제 배포 도메인을 이용해 API 호출 테스트 수행

2. **JWT 인증 처리**
   - 로그인 시 발급되는 JWT 토큰을 로컬 스토리지에 저장
   - API 요청 시 헤더에 토큰을 자동 포함하여 로그인 상태 유지
   - 주문/결제 페이지에서도 인증 흐름 유지

3. **AWS CodePipeline 배포 경험**
   - 프론트 변경 사항을 자동 배포하도록 파이프라인 구성
   - 동적 요소와 정적 빌드 충돌 문제를 해결하며 배포 안정화
   - 배포 과정에서 CI/CD 흐름 이해 및 문제 해결 경험 확보

4. **API 테스트 페이지 구성**
   - 백엔드 API 연결 테스트를 위한 UI 구성
   - 실 운영 API로 데이터 흐름 확인 가능

---

## 기술 스택
- **프레임워크**: Next.js  
- **언어**: JavaScript  
- **HTTP 클라이언트**: Axios (또는 Fetch)  
- **상태 관리**: React Context / SWR / React Query  
- **스타일링**: 프로젝트 내 기존 스타일 유지  
- **환경 변수 관리**: `.env`  
- **배포**: AWS CodePipeline

---

## 폴더 구조 예시

frontend/\n
├─ pages/
│ ├─ index.tsx
│ ├─ login.tsx
│ ├─ cart.tsx
│ ├─ checkout.tsx
│ └─ orders.tsx
├─ components/
│ ├─ Header.tsx
│ ├─ ProductCard.tsx
│ └─ CartItem.tsx
├─ hooks/
│ └─ useAuth.ts
├─ utils/
│ └─ api.ts
├─ public/
│ └─ assets/
└─ styles/

```yaml

---

## 주요 문제점 및 극복 경험
1. **동적 vs 정적 빌드 문제**
   - Next.js의 일부 동적 요소가 CodePipeline 배포 환경에서 제대로 처리되지 않음
   - 정적 자원 기준으로 라우팅 및 환경 변수 경로를 직접 수정하며 해결

2. **API 인증 유지**
   - JWT 토큰을 로컬 스토리지에 저장하고 헤더에 적용하며 로그인 유지 및 결제 플로우 안정화

3. **배포 실패 경험**
   - 여러 번 배포 실패 후 로그 확인 및 빌드 환경 이해
   - CI/CD 파이프라인과 정적 페이지 최적화 이해

---

## 배운 점
- 실제 운영 API와의 연결 구조를 설계하며 프론트 전체 데이터 흐름 이해
- JWT 기반 인증 관리 및 상태 유지 로직 설계
- AWS CodePipeline 기반 CI/CD 경험
- Next.js 동적/정적 빌드 문제 해결 능력

---

## 실행 방법 (로컬 개발)

1. 레포 클론
```bash
git clone https://github.com/MinDongIl/next-shop-frontend-portfolio.git
cd next-shop-frontend-portfolio/frontend

2. 의존성 설치
```bash
npm install

3. 개발 서버 실행
```bash
npm run dev

4. 브라우저에서 http://localhost:3000 접속

5. aws 서버에 업로드 후 www.next-shop.com 도메인으로 접속

6. api (backend)도 업로드 후 받은 도메인으로 엔드포인트 연결 후 확인.

---