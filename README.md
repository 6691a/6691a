<div align="center">
    <h1>김준 (Jun Kim)</h1>
    <h3>Python BackEnd Developer</h3>
    <p>레거시를 안정화하고, 비용과 성능을 개선하는 백엔드 개발자</p>
    <a href="https://6691a.notion.site/ec2bf2a881c4498187677132205225ba?pvs=4">
        <img src="https://img.shields.io/badge/Notion-ffffff?style=flat-square&logo=notion&logoColor=black"/>
    </a>
    <a href="mailto:6691a@naver.com">
        <img src="https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white"/>
    </a>
    <a href="https://github.com/6691a">
        <img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white"/>
    </a>
</div>

---

<div align="center">

![py-badge](https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![dj-badge](https://img.shields.io/badge/django-092E20?style=for-the-badge&logo=django&logoColor=white)
![aws-badge](https://img.shields.io/badge/amazonaws-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![gcp-badge](https://img.shields.io/badge/googlecloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white)

</div>

---

## 소개

1인 백엔드 전담으로 일정·이슈 관리부터 인프라, 기능 개발까지 백엔드 전반을 책임져 온 Python 개발자입니다. 관리되지 않던 레거시 서비스와 빈약한 문서를 인수해 운영을 안정화하고, 그 위에서 신규 기능을 설계·구축하는 일을 해왔습니다.
결제·정산 자동화, Celery 기반 비동기 처리, 인프라 비용 최적화, AWS Lambda·MediaConvert 기반 서버리스 미디어 처리(WebP/HLS) 파이프라인 등을 직접 다뤘습니다. 단순히 기능을 구현하는 데 그치지 않고, "월 비용에 어떻게 찍힐지", "응답이 몇 초가 걸릴지"를 함께 고민하며 인프라 비용을 약 40% 절감하고 정산 배치 시간을 30분에서 10분으로 단축하는 등 실질적인 개선을 만들었습니다.
코드를 작성하기 전에 "왜 이 기능이 필요한가"를 먼저 묻는 것을 중요하게 생각합니다. 표면적인 요구를 그대로 받기보다 본질적인 목적을 함께 정의해 더 단순하고 적합한 해법을 찾고, 그 의사결정 과정을 문서로 남기는 것을 습관처럼 해왔습니다. 비용·성능·운영 효율을 함께 고려해 작은 팀에서 빠르게 임팩트를 만드는 데 강점이 있습니다.

---

## Working Style

- **작게 만들고 빠르게 검증** — 작은 단위로 배포하고, 운영 지표와 피드백을 기준으로 다음 개선을 결정합니다.
- **레거시를 두려워하지 않음** — 오래되고 관리되지 않은 코드라도 버그나 개선이 필요한 상황이라면 주저하지 않습니다.
- **비용과 시간에 민감** — 기능을 추가할 때마다 "월 비용에 어떻게 찍힐지", "몇 초가 걸릴지"를 먼저 생각합니다.

---

## 경력

### Xpace

`Backend Developer (1인 백엔드 전담) · 정규직` · `2024.05 ~ 2026.05`

모임 중계 플랫폼 — SNS 기반 동영상·사진으로 모임을 홍보하고, 결제·참여 인원 관리·호스트 Q&A 등 모임 운영 전반을 중계하는 서비스. 1인 백엔드 전담으로 관리되지 않던 코드와 빈약한 문서를 이어받아 운영·고도화·신규 기능 개발을 모두 책임졌습니다.

#### 메인 피드 추천 로직 구현

- 모든 사용자에게 동일하게 노출되던 메인 피드를 사용자별로 차별화된 콘텐츠가 노출되도록 개선
- 사용자 액션(최근 조회·좋아요 등)을 카테고리 단위로 집계하고, Celery 주기 태스크로 개인별 선호도 점수를 갱신
- 선호도 점수 기반 정렬로 개인화 메인 피드 구성 — 데이터·인력이 부족한 초기 단계에서 추천 모델 대신 가벼운 대안으로 목적 달성

#### 레거시 코드 및 인프라 정리

- 모니터링 지표 기반으로 필요 이상의 인프라, 사용 의도를 알 수 없는 인프라 식별 후 제거 및 통합 → **인프라 비용 약 40% 절감**
- 오버 스펙으로 프로비저닝되어 있던 EC2 사양 조정, RDS 스펙 다운그레이드
- Linux 데몬 기반 수동 배포를 Docker · Docker Compose 기반으로 전환해 운영 안정성 확보

#### 모임 결제 기능 구축

- 결제가 필요한 모임에 대한 결제 및 티켓 발행 플로우 구현
- NicePay 연동(결제 요청 / 결제 확인 / 전체 결제 처리), 환불 처리, 노쇼 패널티, 정원 관리 및 관련 어드민·정산 기능 개발

#### Celery 기반 비동기 전환

- 동기적으로 처리되던 알림 메시지·이메일 발송을 Celery 태스크로 분리, API 응답 속도 향상 및 실패 재시도 체계 확보

#### SNS 피벗 대응 — 모임 서비스 → 일상 공유 SNS

- 모임 중심 도메인 모델을 피드·팔로우·타임라인 중심 SNS 구조로 재설계
- 이미지 WebP 변환·리사이즈, 동영상 HLS 트랜스코딩으로 모바일 재생 품질·대역폭 비용 개선

---

### 에임 (AIM)

`Backend Developer · 프리랜서` · `2024.04 ~ 2024.05 (2개월)`

자산관리 서비스 플랫폼.

#### 자산관리 신청 버그 해결

- 자산관리 신청(입금 완료) 상태에서 주식 자문을 받지 못하는 이슈가 발생하여, Spring 기반 펌뱅킹 시스템과 Django 기반 백엔드 시스템을 오가며 두 서비스 간 높은 결합도와 각 서비스의 역할을 파악
- 펌뱅킹 서비스에 영향이 가지 않도록 백엔드 시스템 측에서 버그 개선 — 프레임워크·언어에 구애받지 않고 이종 시스템 경계를 넘나들며 문제 해결

#### 신규 기능 개발

- 에임 라이트(30만 원 미만 소액 자산으로 자산관리 서비스를 체험할 수 있는 상품) 자산관리 서비스 신청 플로우 및 관련 어드민 기능 개발

#### 어드민 개발

- 정기적으로 금감원에 제출해야 하는 정산 관련 내역을 어드민에서 자동 다운로드 받을 수 있도록 구현 — 반복 업무 자동화

---

### (주) 얼리페이 (EarlyPay)

`Backend Developer · 정규직` · `2022.12 ~ 2024.01 (1년 2개월)` · 핀테크 (선정산 서비스)

#### 정산 고도화

- **배달의민족·요기요 광고비 기능 추가** — 정산 당시 표기되지 않던 광고비를 추적·반영해 사장님이 정산 내역에서 광고비 흐름을 확인할 수 있도록 개선
- **부가 금액 정산 고도화** — 사장님 할인, 배달 대행사 수수료 등 부가 금액의 정산 표기·추적 로직 추가
- **선정산 계산 속도 개선** — 병목 구간이던 선정산 계산을 병렬 처리로 전환해 작업 시간 단축
- 매출 API **7분 → 3분** (인덱스·쿼리 재설계), Celery 배치 **30분 → 10분** (동시성·쿼리 최적화)
- 수동 검증 정산 로직을 자동화하여 **3분 내 정산 완료**

#### 개발 문화 개선

- 전무했던 개발팀 문서 체계 도입 — 배치 시스템 명세 등 핵심 영역 문서화
- PR(Pull Request) 리뷰 프로세스 도입 및 자동 배포 시스템 도입 — 코드 품질·배포 안정성 동시 개선

#### 인프라 보안 및 모니터링

- 변화된 운영 상황에 맞춰 인프라 구성도 최신화
- 비어 있던 보안 그룹 정책·접근 권한 신규 설계
- 보안 이슈로 인해 BE 파일 저장 방식 개편, 기존 파일을 AWS S3로 마이그레이션

#### 기타

- 정산 관련 크롤러 고도화 및 신규 크롤링 파이프라인 개발
- 운영팀용 지표·통계 대시보드 구축

---

### 주식회사 스프링클라우드 (SpringCloud Inc.)

`Backend Developer · 정규직` · `2021.09 ~ 2022.12 (1년 4개월)` · 자율주행 모빌리티 · 데이터 분석

Tasio — 여수 엑스포에서 운영 중인 자율주행 셔틀 예약 시스템.

#### 협력사 CS 페이지 API 제작

- 협력사가 직접 쿠폰을 발권·관리하는 기능 개발
- 협력사가 발권한 쿠폰으로 예약된 건의 취소 및 환불 기능 구현
- 예약 취소 플로우의 N+1 쿼리 문제를 `select_related` · `prefetch_related`로 해소

#### 타시오 사용자 환경 개선 — 인증 체계 통합

- Firebase Auth, Django JWT, Base64로 혼재되어 있던 사용자 인증 구조를 Django Token으로 일원화, 서버 단 인증 관리 통일화
- Authorization(인가) 세분화 — 사용자 / 관리자 / 대시보드 / 협력사 등 계정 타입별 인가 체계 설계

---

## 학력

- **프라임칼리지** · AI 전공 · 2026.02 ~ 재학 중 (방송통신대학교에서 운영하는 AI 관련 학과)
- **전남공업고등학교** · 화학공업과(생명정보화공과) · 2013.03 ~ 2016.02 졸업

---

## 기술 스택

| 분류 | 스택 |
|---|---|
| Backend | Python, Django, DRF, FastAPI, SpringBoot |
| Async | Celery, Redis |
| Database | PostgreSQL, MySQL, ORM 최적화 (N+1, select_related, prefetch_related) |
| Infra & DevOps | AWS (EC2, S3, RDS, CloudFront), Docker, GitHub Actions |
| Media | WebP, HLS |
| Payment | NicePay, 정산 자동화 |
