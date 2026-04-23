# 🫧 Bubble-Pop-Up

### 빅데이터 기반 팝업스토어 경영 시뮬레이션 게임

*서울시 실제 유동인구·교통·뉴스 데이터로 구동되는 실시간 경영 전략 게임*

<img width="2856" height="1504" alt="눈오는배경 (4)" src="https://github.com/user-attachments/assets/aa6baa5f-c806-4ec7-b15a-412262bde492" />





---

## 📋 목차

- [프로젝트 소개](#-프로젝트-소개)
- [주요 기능](#-주요-기능)
- [기술 스택](#-기술-스택)
- [시스템 아키텍처](#-시스템-아키텍처)
- [API 문서](#-api-문서)
- [프로젝트 구조](#-프로젝트-구조)
- [개발 가이드](#-개발-가이드)
- [배포](#-배포)
- [프로젝트 통계](#-프로젝트-통계)
- [참고 자료](#-참고-자료)

---

## 🎯 프로젝트 소개

### 왜 Bubble-Pop-Up?

> "팝업스토어 창업, 데이터로 시뮬레이션하고 전략으로 승부하라."

팝업스토어 시장이 급성장하고 있지만, 실제 창업은 높은 리스크를 수반합니다. BubbleBubble은 **서울시 실제 빅데이터**를 기반으로 팝업스토어 경영을 시뮬레이션하여, 데이터 기반 의사결정 역량을 키울 수 있는 교육형 게임입니다.

### 핵심 가치

- 📊 **빅데이터 기반 시뮬레이션**: 서울시 유동인구, 교통, 뉴스 데이터를 Spark ETL로 가공하여 게임 내 경제에 실시간 반영
- 🏪 **팝업스토어 경영 체험**: 지역 선택 → 메뉴 결정 → 가격 책정 → 마케팅 → 매출 관리의 전체 경영 사이클 체험
- 🎮 **실시간 멀티플레이**: 같은 시즌에 여러 유저가 동시에 경쟁하며 ROI 기반 랭킹 경쟁
- 🌐 **3D 서울 지도**: Three.js 기반 실제 서울 행정구역 3D 맵에서 입지 선택
- 🎲 **동적 이벤트 시스템**: 뉴스·날씨·재난 등 실제 데이터 기반 랜덤 이벤트가 경영에 영향

### 타겟 유저

- 팝업스토어 창업에 관심 있는 예비 창업자
- 데이터 기반 의사결정을 학습하고 싶은 학생
- 경영 시뮬레이션 게임을 즐기는 일반 유저

---

## ✨ 주요 기능

### 1. 🗺️ 3D 서울 지도 기반 지역 선택

<img width="2856" height="1510" alt="지역 선택, 팝업명 설명" src="https://github.com/user-attachments/assets/b0afe974-5505-4298-93a3-e370b3221b96" />


- **GeoJSON 기반 3D 서울 행정구역 맵**: Three.js + React Three Fiber로 구현
- **8개 상권 지역**: 홍대, 강남, 성수, 명동, 이태원, 건대, 여의도, 잠실
- **지역별 실제 데이터**: 유동인구 점수, 임대료, 경쟁 매장 수 등 실제 데이터 기반 정보 제공
- **브랜드명 설정**: 나만의 팝업스토어 브랜드명 입력

### 2. 📰 버블 뉴스 시스템

<img width="2858" height="1520" alt="영업중_뉴스" src="https://github.com/user-attachments/assets/c3bbde19-af5c-43a0-9b0d-2434d6561780" />


- **AI 기반 뉴스 생성**: 실제 트렌드 데이터를 활용한 게임 내 뉴스 기사
- **뉴스가 경영에 미치는 영향**: 원가 변동, 유동인구 증감, 정부 정책 등
- **유동인구 순위**: 지역별 실시간 유동인구 랭킹
- **지역 매출 순위**: 상권별 매출 경쟁 현황

### 3. 🏪 영업 준비 & 발주 시스템

<img width="2858" height="1520" alt="영업준비_정규발주" src="https://github.com/user-attachments/assets/43587280-204a-41f5-8f2b-7cc0d9d12bdb" />



- **정규 발주**: 2, 4, 6일차에 메뉴·수량·가격 결정
- **재고 관리**: 남은 재고는 2일 뒤 폐기, 과잉 주문 주의
- **내일 날씨 예보**: 날씨에 따른 수요 변동 대비

### 4. 🎮 실시간 영업 (2분 = 인게임 12시간)

<img width="2856" height="1504" alt="영업중_실시간순위" src="https://github.com/user-attachments/assets/6cb1d8dc-f4e3-4afb-be2c-6f7b3401f929" />



- **Unity WebGL 3D 배경**: 실시간 날씨 효과, 방문객 스폰, 혼잡도 시각화
- **10초 폴링 실시간 갱신**: 손님 수, 재고, 잔액, 유동인구 실시간 반영
- **6가지 경영 액션**:

| 액션 | 설명 | 효과 |
|------|------|------|
| 할인 | 판매가 할인 적용 | 손님 유입 증가 |
| 긴급발주 | 영업 중 추가 재고 확보 | 교통 상황에 따라 도착 시간 변동 |
| 홍보 | 인플루언서, SNS, 전단지, 지인 | 유동인구 캡처율 상승 |
| 나눔 | 재고 기부 | 평판 상승 |
| 팝업이전 | 다음 영업일 지역 변경 | 새로운 상권 도전 |

- **실시간 랭킹**: 시즌 참가자 간 ROI 기반 실시간 순위
- **이벤트 알림 사이드바**: 뉴스 이벤트 발생 시 실시간 알림

### 5. 📊 일일 리포트


<img width="2856" height="1510" alt="지역 선택, 팝업명 설명" src="https://github.com/user-attachments/assets/fd7af90d-2ac6-4a9d-9c84-24a05d8157cd" />




- **매출·비용·순이익 분석**: 일별 경영 성과 상세 리포트
- **수익 그래프**: 일별 수익 추이 차트
- **평판 시스템**: 0~5점 스케일, 경영 활동에 따라 변동
- **파산 경고**: 3일 연속 적자 시 파산 처리
- **내일 날씨 예보**: 다음 영업일 날씨 미리보기

### 6. 🏆 시즌 랭킹 & 보상


 <img width="800" height="407" alt="_online-video-cutter com-ezgif com-video-to-gif-converter" src="https://github.com/user-attachments/assets/87a8ce08-6219-4165-9cd8-67cc1e20bb8f" />


- **7일간의 시즌 경쟁**: 총 매출, ROI 기반 최종 순위
- **포디움 (1~3위)**: 상위 3명 특별 표시
- **파산 매장 별도 표시**: 파산 이력도 기록에 남김
- **보상 포인트**: 순위별 포인트 지급 → 다음 시즌 아이템 구매에 활용

### 7. 🎒 아이템 & 포인트 시스템

<img width="2858" height="1520" alt="대시보드_포인트, 아이템" src="https://github.com/user-attachments/assets/6e09ca2f-454f-450b-bdf4-e58a09d63758" />


- **원재료 할인권**: 20% / 5% 할인
- **임대료 할인권**: 20% / 5% 할인
- **포인트 구매**: 시즌 보상 포인트로 아이템 구매
- **시즌 참여 시 자동 적용**: 선택한 아이템이 다음 시즌에 반영

### 8. 👤 마이페이지 & 시즌 기록


<img width="800" height="407" alt="_online-video-cutter com1-ezgif com-video-to-gif-converter" src="https://github.com/user-attachments/assets/c578d650-005e-4f14-b787-75599d171819" />



- **통산 시즌 기록**: 참여한 모든 시즌의 매장별 성과
- **파산/정상 구분**: 파산 매장은 별도 표시
- **닉네임 변경**: 프로필 수정
- **최고 순위 표시**: 역대 최고 성적

---

## 🛠 기술 스택

### Backend

| 기술 | 버전 | 용도 |
|------|------|------|
| Spring Boot | 4.0.2 | 메인 백엔드 프레임워크 |
| Java | 17 | 백엔드 언어 |
| MySQL | 8.4 | 주 데이터베이스 |
| Redis | 7 | 캐싱, 실시간 랭킹, 게임 상태 |
| Flyway | - | 데이터베이스 마이그레이션 |
| SpringDoc OpenAPI | 3.0.1 | API 문서 자동화 |

### Frontend

| 기술 | 버전 | 용도 |
|------|------|------|
| React | 19 | UI 프레임워크 |
| TypeScript | 5.9 | 타입 안정성 |
| Three.js + R3F | 0.183 | 3D 서울 지도, 지역 선택 |
| Tailwind CSS | 3.4 | 스타일링 |
| Zustand | 5.0 | 상태 관리 |
| Axios | 1.13 | HTTP 클라이언트 |
| Vite | 8.0 | 빌드 도구 |
| Unity WebGL | - | 영업 중 3D 배경 (iframe) |

### Data & ETL

| 기술 | 용도 |
|------|------|
| Apache Spark | 빅데이터 ETL (유동인구, 교통, 뉴스 점수 산출) |
| Apache Hadoop HDFS | 분산 파일 저장소 |
| Python | Spark 잡 스크립트 |
| Parquet | 중간 데이터 포맷 |

### Infrastructure

| 기술 | 용도 |
|------|------|
| Docker Compose | 컨테이너 오케스트레이션 |
| Nginx | 리버스 프록시, 정적 파일 서빙 |
| AWS EC2 | 클라우드 서버 (웹/데이터/모니터링 3대) |
| Prometheus + Grafana | 모니터링 & 대시보드 |
| Let's Encrypt | SSL 인증서 |
| GitLab CI/CD | 자동 빌드 & 배포 |

### External Services

| 서비스 | 용도 |
|------|------|
| Google OAuth2 | 소셜 로그인 |
| SSAFY OAuth | SSAFY 계정 로그인 |
| 서울시 공공 데이터 | 유동인구, 교통 원천 데이터 |

### Development Tools

```
- Build: Gradle (BE), Vite (FE)
- IDE: IntelliJ IDEA, VS Code
- API Testing: Swagger UI
- Version Control: Git, GitLab
- Issue Tracking: GitLab Issues
- Communication: Notion, Mattermost
```

---

## 🏗 시스템 아키텍처

### 전체 구조도

```
┌──────────────────────────────────────────────────────────────────────┐
│                            Client Layer                             │
│   ┌─────────────────┐    ┌─────────────────┐    ┌───────────────┐   │
│   │  React + Three.js│    │  Unity WebGL    │    │  Chrome/Safari│   │
│   │  (3D 서울 지도)   │    │  (영업 중 배경)  │    │    Browser    │   │
│   └────────┬─────────┘    └────────┬────────┘    └───────┬───────┘   │
└────────────┼───────────────────────┼─────────────────────┼───────────┘
             │ HTTPS                 │ postMessage          │
             │                       │                      │
┌────────────┼───────────────────────┼──────────────────────┼──────────┐
│            ▼                       ▼                      ▼          │
│   ┌──────────────────────────────────────────────────────────────┐   │
│   │                    Nginx (Reverse Proxy)                     │   │
│   │              :80 → 301 HTTPS  |  :443 SSL                   │   │
│   └──────────────────────────┬───────────────────────────────────┘   │
│                              │                                      │
│            ┌─────────────────┼─────────────────┐                    │
│            ▼                 ▼                  ▼                    │
│   ┌────────────────┐ ┌──────────────┐ ┌────────────────┐            │
│   │  Frontend      │ │ Spring Boot  │ │  Unity Static  │            │
│   │  (Vite Build)  │ │   Backend    │ │   Files        │            │
│   │   :5173 (dev)  │ │    :8080     │ │                │            │
│   └────────────────┘ └──────┬───────┘ └────────────────┘            │
│                             │                                       │
│              ┌──────────────┼──────────────┐                        │
│              ▼              ▼              ▼                        │
│   ┌──────────────┐ ┌──────────────┐ ┌──────────────┐               │
│   │   MySQL 8.4  │ │   Redis 7   │ │  Scheduler   │               │
│   │              │ │              │ │              │               │
│   │ - Users      │ │ - Game State │ │ - Tick (10s) │               │
│   │ - Stores     │ │ - Rankings   │ │ - Phase 전환  │               │
│   │ - Orders     │ │ - Session    │ │ - 뉴스 생성   │               │
│   │ - Reports    │ │              │ │ - 랭킹 집계   │               │
│   │ - Rankings   │ │              │ │              │               │
│   └──────────────┘ └──────────────┘ └──────────────┘               │
│                        Web Server (EC2)                             │
└─────────────────────────────────────────────────────────────────────┘
             │
┌────────────┼────────────────────────────────────────────────────────┐
│            ▼             Data Server (EC2)                          │
│   ┌──────────────────────────────────────────────────────────┐      │
│   │                 Spark + Hadoop Cluster                    │      │
│   │                                                          │      │
│   │  ┌────────────┐  ┌────────────┐  ┌────────────────────┐ │      │
│   │  │ HDFS       │  │ Spark      │  │ ETL Jobs (Python)  │ │      │
│   │  │ Namenode   │  │ Master     │  │                    │ │      │
│   │  │ + Datanode │  │ + Worker   │  │ - 유동인구 점수     │ │      │
│   │  │            │  │            │  │ - 교통 점수        │ │      │
│   │  │ 서울시     │  │ 2GB/2core  │  │ - 뉴스 점수        │ │      │
│   │  │ 원천 데이터 │  │            │  │                    │ │      │
│   │  └────────────┘  └────────────┘  └────────────────────┘ │      │
│   └──────────────────────────────────────────────────────────┘      │
└─────────────────────────────────────────────────────────────────────┘
             │
┌────────────┼────────────────────────────────────────────────────────┐
│            ▼          Monitoring Server (EC2)                       │
│   ┌──────────────┐  ┌──────────────┐  ┌──────────────┐             │
│   │  Prometheus  │  │   Grafana    │  │ AlertManager │             │
│   │  (수집)      │  │  (시각화)    │  │  (알림)      │             │
│   └──────────────┘  └──────────────┘  └──────────────┘             │
└─────────────────────────────────────────────────────────────────────┘
```

### 게임 타임라인

```
┌─────────────┐   ┌──────────────────────────────────────────────┐   ┌─────────┐
│ 지역 선택    │   │              7일 반복 (1일 = 3분)              │   │ 시즌 종료│
│   (2분)     │   │                                              │   │         │
│             │   │  ┌──────┐  ┌──────────┐  ┌────────┐          │   │ 랭킹    │
│ · 지역 선택  │──▶│  │ 준비  │─▶│  영업 중   │─▶│ 리포트  │ ── × 7  │──▶│ 보상    │
│ · 브랜드 설정│   │  │ 40초  │  │   2분    │  │  20초  │          │   │         │
│ · 메뉴 결정  │   │  │      │  │          │  │        │          │   │         │
│             │   │  │ 발주  │  │ 6가지    │  │ 매출   │          │   │         │
│             │   │  │ 뉴스  │  │ 액션     │  │ 평판   │          │   │         │
│             │   │  │ 날씨  │  │ 이벤트   │  │ 파산?  │          │   │         │
└─────────────┘   │  └──────┘  └──────────┘  └────────┘          │   └─────────┘
                  └──────────────────────────────────────────────┘
```

### 데이터 플로우

#### 1. Spark ETL 파이프라인

```
서울시 공공 데이터 (CSV)
    │
    ▼
HDFS (원천 데이터 저장)
    │
    ▼
Spark ETL Jobs
├── etl_population_score.py  →  지역별 유동인구 점수
├── etl_traffic_score.py     →  지역별 교통 점수
└── etl_news_score.py        →  뉴스 영향 점수
    │
    ▼
MySQL (게임 시즌 데이터에 반영)
    │
    ▼
Spring Boot (게임 엔진이 점수 기반으로 손님 수, 이벤트 계산)
```

#### 2. 게임 틱 시스템

```
Scheduler (10초 주기)
    │
    ├── 유동인구 기반 손님 수 계산
    ├── 매장별 매출 정산
    ├── 이벤트 발동 체크
    ├── 교통 혼잡도 갱신
    └── 실시간 랭킹 갱신
    │
    ▼
Redis (게임 상태 캐시)
    │
    ▼
FE 10초 폴링 → PlayPage 헤더 갱신
```

#### 3. Unity-FE 통신

```
React (PlayPage)
    │ postMessage({type: "unity", method, payload})
    ▼
Unity WebGL (iframe)
    │ SendMessage("WebGLBridge", method, payload)
    ▼
Unity C# (날씨, 카메라, 방문객 스폰, 혼잡도)
    │ window.notifyPopupArrival(index)
    ▼
React (손님 수 +1, delta 표시)
```

---


### 주요 테이블 관계

**유저 & 매장**
```
users (1) ─── (N) store        : 시즌별 매장 생성
store (1) ─── (N) orders       : 발주 내역
store (1) ─── (N) daily_report : 일별 리포트
store (N) ─── (1) location     : 입지 지역
store (N) ─── (1) menu         : 판매 메뉴
store (N) ─── (1) season       : 소속 시즌
```

**게임 엔진**
```
season (1) ─── (N) daily_event       : 일별 랜덤 이벤트
season (1) ─── (N) news_report       : 뉴스 리포트
season (1) ─── (N) season_ranking_record : 시즌 최종 랭킹
random_event (1) ─── (N) daily_event : 이벤트 풀
```

**액션 & 아이템**
```
store (1) ─── (N) action_log  : 액션 사용 기록
action (1) ─── (N) action_log : 액션 종류
users (1) ─── (N) user_item   : 아이템 보유
item (1) ─── (N) user_item    : 아이템 종류
```

---


## 📚 API 문서

### 주요 API 엔드포인트

#### 인증 (Auth)

| Method | Endpoint | 설명 |
|--------|----------|------|
| GET | `/auth/login` | OAuth2 로그인 |
| POST | `/auth/refresh` | 토큰 갱신 |
| POST | `/auth/logout` | 로그아웃 |

#### 게임 (Game)

| Method | Endpoint | 설명 |
|--------|----------|------|
| GET | `/game/waiting` | 게임 대기 상태 조회 |
| GET | `/game/seasons/time` | 현재 시즌 시간 정보 |
| GET | `/game/seasons/current/participation` | 시즌 참여 상태 |
| POST | `/game/seasons/current/join` | 시즌 참여 |
| GET | `/game/day/start` | 영업일 시작 |
| GET | `/game/day/state` | 실시간 게임 상태 |
| GET | `/game/day/reports/{day}` | 일일 리포트 조회 |
| GET | `/game/seasons/current/rankings/top` | 실시간 랭킹 |
| GET | `/game/seasons/current/rankings/final` | 최종 랭킹 |

#### 매장 (Store)

| Method | Endpoint | 설명 |
|--------|----------|------|
| GET | `/stores` | 내 매장 정보 |
| GET | `/stores/menus` | 메뉴 목록 |
| GET | `/stores/locations` | 지역 목록 |
| PUT | `/stores/location` | 지역 변경 (팝업이전) |

#### 발주 (Order)

| Method | Endpoint | 설명 |
|--------|----------|------|
| GET | `/orders` | 현재 발주 조회 |
| POST | `/orders/regular` | 정규 발주 |

#### 액션 (Action)

| Method | Endpoint | 설명 |
|--------|----------|------|
| POST | `/actions/discount` | 할인 적용 |
| POST | `/actions/emergency-order` | 긴급 발주 |
| POST | `/actions/promotion` | 홍보 실행 |
| POST | `/actions/donation` | 나눔 실행 |
| GET | `/actions/promotion/price` | 홍보 가격 조회 |

#### 뉴스 (News)

| Method | Endpoint | 설명 |
|--------|----------|------|
| GET | `/news/today/{day}` | 오늘의 뉴스 |
| GET | `/news/ranking/{day}` | 뉴스 랭킹 |

#### 유저 (User)

| Method | Endpoint | 설명 |
|--------|----------|------|
| GET | `/users` | 내 정보 조회 |
| PATCH | `/users/nickname` | 닉네임 변경 |
| GET | `/users/points` | 포인트 조회 |
| GET | `/users/records` | 시즌 기록 조회 |

#### 아이템 (Shop)

| Method | Endpoint | 설명 |
|--------|----------|------|
| GET | `/shop/items` | 아이템 목록 |
| POST | `/shop/items/purchase` | 아이템 구매 |

---

## 📁 프로젝트 구조

```
S14P21A205/
├── .gitlab-ci.yml                    # GitLab CI/CD 파이프라인
│
├── S14P21A205_BE/                    # Backend
│   ├── build.gradle                  # Gradle 빌드 설정
│   ├── Dockerfile                    # 백엔드 Docker 이미지
│   ├── docker-compose.yml            # 프로덕션 (BE + Redis + Nginx)
│   ├── docker-compose.local.yml      # 로컬 개발 (MySQL + Redis + Hadoop + Spark)
│   ├── docker-compose.data.yml       # 데이터 서버 (Hadoop + Spark)
│   ├── docker-compose.monitoring.yml # 모니터링 (Prometheus + Grafana)
│   │
│   ├── src/main/java/com/ssafy/S14P21A205/
│   │   ├── action/                   # 액션 도메인 (할인, 발주, 홍보, 나눔)
│   │   ├── auth/                     # OAuth2 인증 (Google, SSAFY)
│   │   ├── config/                   # Spring 설정
│   │   ├── exception/                # 글로벌 예외 처리
│   │   ├── game/                     # 게임 엔진 (핵심)
│   │   │   ├── day/                  # 일별 게임 상태, 틱, 리포트
│   │   │   ├── environment/          # 날씨, 환경 요소
│   │   │   ├── event/                # 랜덤 이벤트 시스템
│   │   │   ├── news/                 # 뉴스 생성 & 영향
│   │   │   ├── scheduler/            # 게임 스케줄러
│   │   │   ├── season/               # 시즌 관리 & 랭킹
│   │   │   └── time/                 # 게임 시간 정책
│   │   ├── order/                    # 발주 관리
│   │   ├── security/                 # Security 설정
│   │   ├── shop/                     # 아이템 상점
│   │   ├── store/                    # 매장 관리
│   │   └── user/                     # 유저 관리
│   │
│   ├── src/main/resources/
│   │   ├── application.yml           # 기본 설정
│   │   ├── application-local.yml     # 로컬 설정
│   │   ├── application-prod.yml      # 프로덕션 설정
│   │   ├── data.sql                  # 초기 시드 데이터
│   │   └── db/migration/             # Flyway 마이그레이션 (V1~V8)
│   │
│   ├── data/seed/                    # CSV 시드 데이터
│   │   ├── action.csv, item.csv, location.csv, menu.csv
│   │   ├── weather.csv, festival.csv, random_event.csv
│   │   └── init-hdfs.sh              # HDFS 초기화 스크립트
│   │
│   ├── spark/jobs/                   # Spark ETL 잡 (Python)
│   │   ├── etl_population_score.py   # 유동인구 점수 산출
│   │   ├── etl_traffic_score.py      # 교통 점수 산출
│   │   ├── etl_news_score.py         # 뉴스 영향 점수
│   │   └── ...                       # 검증 & 유틸 스크립트
│   │
│   ├── monitoring/                   # 모니터링 설정
│   │   ├── prometheus/               # Prometheus 스크래핑 설정
│   │   ├── grafana/                  # Grafana 대시보드
│   │   └── alertmanager/             # 알림 설정
│   │
│   └── ops/                          # 운영 스크립트
│       ├── nginx/docker/             # Nginx 설정 템플릿
│       └── scripts/                  # EC2 부트스트랩 스크립트
│
└── S14P21A205_FE/                    # Frontend
    ├── package.json                  # npm 의존성
    ├── vite.config.ts                # Vite 빌드 설정
    ├── tailwind.config.ts            # Tailwind CSS 설정
    │
    ├── public/
    │   └── unity/                    # Unity WebGL 빌드 파일
    │       ├── index.html            # Unity-FE 브릿지
    │       └── Build/                # .data, .wasm, .framework.js
    │
    └── src/
        ├── pages/                    # 페이지 컴포넌트 (22개)
        │   ├── HomePage.tsx          # 랜딩 / 대시보드
        │   ├── LoginPage.tsx         # OAuth 로그인
        │   ├── LocationSelectPage.tsx # 3D 지역 선택
        │   ├── PrepPage.tsx          # 영업 준비 + 뉴스
        │   ├── PlayPage.tsx          # 영업 중 (핵심)
        │   ├── ReportPage.tsx        # 일일 리포트
        │   ├── RankingPage.tsx       # 시즌 랭킹
        │   ├── MyPage.tsx            # 마이페이지
        │   ├── WaitingPage.tsx       # 대기 화면
        │   └── ...                   # 에러, 튜토리얼, 관리자 페이지
        │
        ├── components/               # 재사용 컴포넌트
        │   ├── common/               # 헤더, 모달, 버튼, 카운트다운
        │   ├── game/                 # 3D 서울맵, 뉴스, 지역 패널
        │   ├── play/                 # 영업 중 헤더, 액션바, 사이드바
        │   │   ├── modals/           # 할인, 긴급발주, 홍보, 나눔, 이전
        │   │   ├── effects/          # 이벤트 3D 이펙트
        │   │   └── UnityCanvas.tsx   # Unity WebGL 래퍼
        │   ├── ranking/              # 포디움, 랭킹 리스트
        │   └── report/               # 수익 차트, 날씨 카드
        │
        ├── stores/                   # Zustand 상태 관리
        │   ├── useUserStore.ts       # 유저 인증 & 정보
        │   ├── useGameStore.ts       # 게임 상태 (시즌, 파산 등)
        │   ├── useBrandStore.ts      # 브랜드명
        │   └── useAppNoticeStore.ts  # 알림 (서버 오류, 인증 등)
        │
        ├── api/                      # API 클라이언트
        │   ├── client.ts             # Axios 인스턴스 + 인터셉터
        │   ├── game.ts               # 게임 API
        │   ├── store.ts              # 매장 API
        │   ├── order.ts              # 발주 API
        │   ├── action.ts             # 액션 API
        │   └── ...                   # auth, user, news, shop
        │
        ├── router/                   # 라우터
        │   ├── index.tsx             # 라우트 정의
        │   ├── GameGuard.tsx         # 게임 페이즈 가드
        │   ├── PrivateRoute.tsx      # 인증 가드
        │   └── AppShell.tsx          # 루트 레이아웃 + 알림
        │
        ├── hooks/                    # 커스텀 훅
        ├── constants/                # 상수 (게임 시간 정책 등)
        ├── utils/                    # 유틸리티
        └── types/                    # TypeScript 타입 정의
```


## 💻 개발 가이드

### 코드 컨벤션

#### Java/Spring Boot

```java
// 클래스: PascalCase
public class SeasonLifecycleService {}

// 메서드/변수: camelCase
public void startGameDay() {}
private int currentDay;

// 상수: UPPER_SNAKE_CASE
public static final int BUSINESS_SECONDS = 120;
```

#### TypeScript/React

```typescript
// 컴포넌트: PascalCase
function PlayHeader() {}

// 변수/함수: camelCase
const remainingSeconds = 120;
function applyGameState() {}

// 상수: UPPER_SNAKE_CASE
const PREP_SECONDS = 40;

// 타입/인터페이스: PascalCase
interface GameStateResponse {}
type SeasonPhase = "DAY_BUSINESS" | "DAY_REPORT";
```

### Git 컨벤션

#### 브랜치 전략

```
master                          # 프로덕션 배포
└── develop                     # 통합 브랜치
    ├── feat/S14P21A205-{이슈번호}/{기능명}
    └── fix/S14P21A205-{이슈번호}/{버그명}
```

#### 커밋 메시지

```
S14P21A205-{이슈번호} <type> : <subject>
```

| Type | 설명 |
|------|------|
| Feat | 새로운 기능 |
| Fix | 버그 수정 |
| Refactor | 리팩토링 |
| Docs | 문서 수정 |
| Chore | 빌드, 설정 변경 |

### Redis 키 컨벤션

```
{domain}:{resource}:{identifier}:{subresource}:{qualifier}
```

- 소문자 + 하이픈 사용, camelCase 금지
- 단일값: String, 객체: JSON (opsForValue)

---

## 🚢 배포

### 서버 구성 (AWS EC2 × 3)

| 서버 | 역할 | 구성 |
|------|------|------|
| Web Server | 앱 서비스 | Spring Boot + React + Redis + Nginx |
| Data Server | 데이터 처리 | Hadoop + Spark |
| Monitoring | 모니터링 | Prometheus + Grafana + AlertManager |

### GitLab CI/CD 파이프라인

```yaml
# Build Stage
build-backend:   Gradle bootJar (Java 17)
build-frontend:  npm build (Node 22-alpine)

# Deploy Stage (manual, master only)
deploy-web:          BE + FE + Nginx 배포
deploy-data:         Hadoop/Spark 배포
deploy-monitoring:   Prometheus/Grafana 배포
setup-web-https:     Let's Encrypt 인증서 설정
```


### Nginx 라우팅

| 경로 | 프록시 대상 | 설명 |
|------|------------|------|
| `/` | Frontend (Vite Build) | React SPA |
| `/api/*` | Backend (:8080) | Spring Boot API |
| `/unity/*` | Static Files | Unity WebGL |

---

## 📊 프로젝트 통계

| 항목 | 수치 |
|------|------|
| 개발 기간 | 35일 (5주) |
| 팀원 수 | 6명 |
| 시즌 1회 플레이 시간 | 약 23분 |
| FE 페이지 수 | 22개 |
| BE 도메인 수 | 10개 |
| Spark ETL 잡 | 10개 |
| Docker Compose 파일 | 5개 |
| 게임 내 상권 지역 | 8개 |
| 영업 액션 | 6종 |
| Flyway 마이그레이션 | 8개 |

### 개발 일정

```
Week 1: 기획 및 설계
  - 게임 메커니즘 설계
  - ERD, API 명세서
  - 기술 스택 선정

Week 2: 기반 시스템 개발
  - OAuth2 인증
  - 게임 엔진 (틱 시스템, 페이즈 전환)
  - Spark ETL 파이프라인
  - 3D 서울 지도 (Three.js)

Week 3: 핵심 게임플레이
  - 영업 중 실시간 시스템
  - 액션 시스템 (6종)
  - 뉴스 & 이벤트 시스템
  - Unity WebGL 연동

Week 4: 부가 기능 & 안정화
  - 랭킹 시스템
  - 아이템 & 포인트
  - 마이페이지
  - 버그 수정 & 최적화

Week 5: 테스트 & 배포
  - 통합 테스트
  - AWS 3서버 배포
  - 모니터링 구축
  - 문서화
```

---

### 역할 상세

**박지원 (팀장 / BE / Infra)**
- 프로젝트 총괄 및 일정 관리
- 게임 엔진 핵심 로직 (틱 시스템, 시즌 라이프사이클)
- AWS 3서버 인프라 구축 & CI/CD
- Unity NPC 군중 시뮬레이션(NavMesh) 및 오브젝트 풀링 제어 로직
- Unity ↔ React 간 양방향 통신(WebGL Bridge) 모듈 개발

**박솔희 (풀스택)**
- 인게임 실시간 뉴스 피드 및 동적 알림창(Toast) 컴포넌트 개발
- React 기반 팝업스토어 개설 및 관리 UI 구현

**양다희 (풀스택)**
- Spring Boot 기반 메뉴 재고/잔액 관리 API 개발
- Redis Lua 스크립트를 활용한 동시 결제/접근 동시성 제어
- 유저 상호작용(할인, 긴급발주, 홍보 등) 이벤트 비즈니스 로직 구현

**정은지 (풀스택 / AI / Data)**
- Spark ETL 파이프라인 설계 & 구현
- 유동인구, 교통, 뉴스 데이터 가공
- Hadoop HDFS 클러스터 구성

**사윤진 (풀스택)**
- 10초 틱(Tick) 단위 시뮬레이션 결과 클라이언트 동기화 API 및 비동기 처리 로직 개발
- React 전역 상태 관리(Zustand 등) 설계 및 컴포넌트 렌더링 최적화
- Spring Boot 기반 실시간 이벤트 알림(SSE/WebSocket) 및 전역 에러 핸들링 시스템 구축

**채지원 (풀스택)**
- GameGuard 페이즈 자동 전환 시스템
- PlayPage 실시간 영업 UI & API 연동
- 시즌 랭킹 & 파산 처리 로직
- 대시보드, 리포트, 대기화면 UX 개선

---

## 📚 참고 자료

### 공식 문서

- [Spring Boot Documentation](https://spring.io/projects/spring-boot)
- [React Documentation](https://react.dev/)
- [Three.js Documentation](https://threejs.org/docs/)
- [Zustand Documentation](https://docs.pmnd.rs/zustand/)
- [Apache Spark Documentation](https://spark.apache.org/docs/latest/)
- [Apache Hadoop Documentation](https://hadoop.apache.org/docs/)
- [Redis Documentation](https://redis.io/documentation)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [Unity WebGL Documentation](https://docs.unity3d.com/Manual/webgl.html)

### 데이터 출처

- [서울 열린데이터 광장](https://data.seoul.go.kr/) — 유동인구, 교통 데이터
- [Google OAuth2](https://developers.google.com/identity) — 소셜 로그인

---

**Made with 🫧 by BubbleBubble Team**

[⬆ 맨 위로 이동](#-bubblebubble)
