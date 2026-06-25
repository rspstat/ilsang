# SubZero — 정기결제 관리 AI 플랫폼

> **"넷플릭스 3개월째 안 보셨어요. 이번 달에 해지하면 연 14만 원 절약돼요."**
> 그냥 알려주는 게 아니라, 실제로 행동을 제안하는 AI 구독 큐레이터

</br>

## 📌 프로젝트 소개

뱅크샐러드도, 토스도 정기결제를 **"보여주기만"** 합니다.

SubZero는 다릅니다.
AI가 소비 패턴을 분석해서 **"지금 이 구독을 해지하세요"**, **"이 두 개는 중복이에요"**, **"가족 플랜으로 바꾸면 더 싸요"** 처럼 구체적인 행동을 제안합니다.

매달 조용히 빠져나가는 구독료, 이제 AI가 대신 챙겨드립니다.

</br>

## 😤 이런 문제 있지 않으셨나요?

- 넷플릭스, 왓챠, 웨이브 중 어느 게 내 돈인지 헷갈려요
- 유튜브 프리미엄 있는데 멜론도 구독 중인 걸 몰랐어요
- 갱신일이 언제인지 기억이 안 나서 어느새 또 결제됐어요
- 구독료가 얼마인지 다 더해본 적이 없어요

**한국 성인의 평균 구독 서비스 개수: 5.3개**
**하지만 실제로 매달 쓰는 건: 2.1개**

</br>

## ✨ 주요 기능


</br>

### 1. 구독 자동 감지
오픈뱅킹 API 연동으로 정기결제 내역을 자동으로 불러오고 분류합니다.
직접 추가도 가능합니다.


</br>

### 2. AI 낭비 탐지
```
"넷플릭스를 마지막으로 사용한 게 89일 전이에요.
이번 달 해지하면 연 17만 원을 아낄 수 있어요."
```
사용 패턴을 분석해서 실제로 안 쓰는 구독을 콕 집어냅니다.


</br>

### 3. 중복 서비스 감지 ️
```
"유튜브 프리미엄(월 14,900원)에 이미 유튜브 뮤직이 포함돼요.
멜론(월 10,900원)은 중복입니다. 해지하면 연 130,800원 절약."
```
카테고리가 겹치는 서비스를 자동으로 찾아냅니다.


</br>

### 4. 절약 시뮬레이션
해지하거나 플랜을 바꿨을 때 월/연 단위로 얼마나 아낄 수 있는지 즉시 계산합니다.


</br>

### 5. 갱신일 3일 전 알림
"3일 후 스포티파이 결제일이에요. 계속 쓰실 건가요?"
결제되기 전에 한 번 더 생각할 기회를 줍니다.


</br>

### 6. 플랜 업그레이드 추천 ‍‍
```
"Netflix 개인 플랜 3개 구독 중인 가족 계정이 감지됐어요.
패밀리 플랜으로 합치면 월 12,000원 → 17,000원으로
3명 기준 월 24,700원을 절약할 수 있어요."
```


</br>

### 7. 월간 소비 리포트
매달 1일, 지난 달 구독 소비를 AI가 자동으로 정리해서 알려드립니다.

</br>

## 🛠 기술 스택

| 분류 | 기술 |
|------|------|
| 프론트엔드 | React Native (iOS / Android) |
| 백엔드 | FastAPI (Python) |
| 데이터베이스 | PostgreSQL |
| 금융 연동 | 오픈뱅킹 API (금융결제원) |
| AI 분석 | Claude API (Anthropic) |
| 푸시 알림 | Firebase Cloud Messaging (FCM) |
| 인증 | OAuth 2.0 + JWT |

</br>

## 🗂 시스템 구조

```
사용자
  │
  ▼
React Native 앱
  │
  ├── 오픈뱅킹 API ──── 정기결제 내역 수집
  │
  ├── FastAPI 서버
  │     ├── 구독 파싱 & 분류 엔진
  │     ├── Claude API 연동 (패턴 분석 / 추천 생성)
  │     └── 알림 스케줄러 (FCM)
  │
  └── PostgreSQL
        ├── users
        ├── subscriptions
        ├── transactions
        └── recommendations
```

</br>

## 📱 주요 화면

| 화면 | 설명 |
|------|------|
| 홈 대시보드 | 이번 달 총 구독료 + AI 추천 카드 |
| 구독 목록 | 전체 구독 서비스 리스트 + 사용 빈도 |
| AI 리포트 | 낭비 탐지 결과 + 절약 시뮬레이션 |
| 알림 설정 | 갱신일 알림 / 리포트 주기 설정 |

</br>

## 🎯 차별점

| 기능 | 뱅크샐러드 | 토스 | **SubZero** |
|------|:---------:|:----:|:-----------:|
| 정기결제 모아보기 |  |  |  |
| 사용 패턴 분석 |  |  |  |
| AI 낭비 탐지 |  |  |  |
| 중복 서비스 감지 |  |  |  |
| 절약 시뮬레이션 |  |  |  |
| 플랜 전환 추천 |  |  |  |
| 갱신일 사전 알림 |  | 일부 |  |

</br>

## 🚀 실행 방법


</br>

### 사전 요구사항
- Node.js 18+
- Python 3.11+
- PostgreSQL 15+
- Firebase 프로젝트


</br>

### 백엔드 설치

```bash
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

`.env` 파일 생성:

```env
DATABASE_URL=postgresql://user:password@localhost:5432/subzero
OPENBANKING_API_KEY=your_key_here
ANTHROPIC_API_KEY=your_key_here
FIREBASE_CREDENTIALS=path/to/firebase.json
SECRET_KEY=your_jwt_secret
```

```bash
uvicorn main:app --reload
```


</br>

### 프론트엔드 설치

```bash
cd frontend
npm install
npx expo start
```

</br>

## 📁 프로젝트 구조

```
subzero/
├── backend/
│   ├── main.py
│   ├── routers/
│   │   ├── auth.py
│   │   ├── subscriptions.py
│   │   └── recommendations.py
│   ├── services/
│   │   ├── openbanking.py     # 정기결제 수집
│   │   ├── ai_analyzer.py     # Claude API 연동
│   │   └── notifier.py        # FCM 알림
│   └── models/
│       └── schemas.py
│
└── frontend/
    ├── app/
    │   ├── (tabs)/
    │   │   ├── index.tsx       # 홈 대시보드
    │   │   ├── subscriptions.tsx
    │   │   └── report.tsx
    │   └── _layout.tsx
    └── components/
        ├── SubscriptionCard.tsx
        └── AIRecommendCard.tsx
```

</br>

## 🔒 개인정보 및 보안

- 금융 데이터는 서버에 저장하지 않고 분석 후 즉시 파기
- 오픈뱅킹 표준 보안 프로토콜 준수 (금융결제원 가이드라인)
- 모든 통신 TLS 1.3 암호화
- JWT + Refresh Token 방식 인증
