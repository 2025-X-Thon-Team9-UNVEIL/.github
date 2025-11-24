# 보이지 않는 위험의 베일을 벗긴다 : 언베일(UNVEIL)

![index](https://github.com/user-attachments/assets/41c1404f-3824-4bda-abe8-0cbc2807f81e)

---

## 📋 프로젝트 개요

UNVEIL은 청년들의 자취방에서 마주하는 '보이지 않는 리스크'를 과학적 분석을 통해 시각화하는 안전 플랫폼입니다.

자취방을 구할 때 햇살(채광), 물줄기(수압)는 확인하면서, 왜 가장 고통스러운 '소음'은 살아보기 전엔 모를까요? UNVEIL은 이 문제를 해결합니다.

---

## 🎯 주요 기능

### 1. 소음 분석 (Echo Zone)


https://github.com/user-attachments/assets/ce2468d7-97f8-4969-ba9b-9105000e7688


원룸에서 옆방의 말소리가 벽을 타고 넘어오는 **'벽간 소음'** 진단

- 핑 소리 재생 후 반향음 분석
- **Bass Ratio 알고리즘**: 저주파와 고주파 잔향 시간 비율로 가벽 공명 탐지
- 등급: A (흡음) / B (콘크리트) / C (가벽 의심)

### 2. 안전도 분석 (Light Zone)


https://github.com/user-attachments/assets/e9f91eb0-7317-43b2-9e55-6da376b19dd0


- 분석 반경: 기준 위치 100m 반경 내 CCTV 수·가로등 수 분석
- 시각화: CCTV는 반경 30m 파란 원, 가로등은 반경 15m 노란 원으로 지도 표시
- 등급 산출: CCTV와 가로등 밀도를 종합하여 A~F 등급 제공

**데이터 소스**:

- 가로등: 공공데이터 포탈\_서울특별시 가로등 위치 정보
- CCTV: 서울 열린 데이터 광장

### 3. 통합 안전 점수

방음 구조 진단과 귀갓길 위험 구간 점수를 종합하여 안전 판단 기준 제공

---

## 🏗️ 프로젝트 구조

```
UNVEIL/
├── UNVEIL_AI/      # Python/FastAPI - 소음 분석 서비스
├── UNVEIL_BE/      # Java/Spring Boot - 메인 백엔드 서비스
└── UNVEIL_FE/      # React/TypeScript - 프론트엔드
```

### 기술 스택

| 구성 요소      | 기술 스택                            |
| -------------- | ------------------------------------ |
| **AI 서비스**  | Python, FastAPI, NumPy, SciPy        |
| **백엔드**     | Java 17, Spring Boot, MySQL, JWT     |
| **프론트엔드** | React, TypeScript, TailwindCSS, Vite |

---

## 👥 팀원 소개

| 역할                | GitHub                                         |
| ------------------- | ---------------------------------------------- |
| BE     | [wlgusqkr](https://github.com/wlgusqkr)       |
| BE     | [sunnyanna0](https://github.com/sunnyanna0)   |
| BE     | [DOHOON0127](https://github.com/DOHOON0127)   |
| FE | [hansol65](https://github.com/hansol65)       |
| FE | [fbehdgus906](https://github.com/fbehdgus906) |
| FE | [kiyeonkimm](https://github.com/kiyeonkimm)   |

---

### 커스텀 음향 분석 엔진

기존 라이브러리는 표준 옥타브 밴드별 RT60만 제공하지만, 우리는 **특정 저주파 대역(125~500Hz)과 고주파 대역을 정밀하게 타겟팅**해야 했습니다.

- NumPy/SciPy로 음향 분석 엔진 구현
- 슈뢰더 역방향 적분법, T20 선형 회귀 분석 구현
- 분석 구간과 필터링 대역에 대한 통제

---

**보이지 않는 위험의 베일을 벗긴다** 🎯
