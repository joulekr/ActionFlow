<p align="center">
  <img src="/docs/img/actionflow.png" alt="ActionFlow icon" />
</p>

<h1 align="center">ActionFlow</h1>

> **<p align="center">Windows용 키보드 중심 런처 & 생산성 도구</p>**
> <p align="center">A keyboard-driven launcher and productivity tool for Windows, built with Tauri v2 + Rust + React.</p>

<p align="center">
  <img alt="Platform" src="https://img.shields.io/badge/platform-Windows-blue?logo=windows" />
  <a href="https://github.com/joulekr/ActionFlow/releases/latest">
    <img alt="Latest release" src="https://img.shields.io/github/v/release/joulekr/ActionFlow?style=flat-square" />
  </a>
  <a href="https://tauri.app">
    <img alt="Built with Tauri" src="https://img.shields.io/badge/Built%20with-Tauri%20v2-24C8DB?style=flat-square&logo=tauri" />
  </a>
  <img alt="Language" src = "https://img.shields.io/badge/language-Rust%20%2B%20React-orange" />
</p>

---

## 소개 / Overview

ActionFlow는 `Ctrl+Shift+Space` 단축키 하나로 호출하는 **Windows 전용 런처**입니다.  
앱 실행, 파일 검색, 클립보드 히스토리, 계산기, 단위·환율 변환, 타이머, 스니펫, 플러그인까지 — 마우스 없이 키보드만으로 대부분의 작업을 처리할 수 있습니다.

ActionFlow is a **Windows-only launcher** invoked with a single shortcut (`Ctrl+Shift+Space`).  
Launch apps, search files, manage clipboard history, calculate, convert units, run timers, expand snippets, and more — all without leaving your keyboard.

<p align="center">
<img src = "/docs/img/actionflow01.png" width="340"/> <img src = "/docs/img/actionflow02.png" width="340"/>
<img src = "/docs/img/actionflow03.png" width="340"/> <img src = "/docs/img/actionflow04.png" width="340"/>
</p>
---

## 주요 기능 / Features

### ⚡ 앱 검색 & 창 전환
- 설치된 앱을 이름으로 즉시 검색·실행
- Jaro-Winkler 기반 **퍼지 매칭** — 오타가 있어도 찾아줌 (`chorme → Chrome`)
- 현재 열린 창 목록 표시, 선택 시 바로 전면으로 활성화
- 검색어 없이 열면 **최근 자주 실행한 앱** 자동 표시 (frecency 기반)

### 📋 클립보드 히스토리
- 텍스트 복사 시 자동 저장, 최대 200개 · SQLite 영구 저장
- 검색, 고정(Pin), 수정, 삭제 지원
- **출처 앱 표시** — `chrome · 2분 전` 형식으로 어느 앱에서 복사했는지 표시
- **서식 없이 붙여넣기** — 우클릭 → CF_UNICODETEXT만 설정, RTF/HTML 서식 제거 후 이전 창에 붙여넣기
- 보관 기간·최대 개수 설정 가능, 모니터링 일시정지 지원

### 🧮 계산기
- 기본 사칙연산 및 `sqrt`, `sin`, `log`, `abs` 등 수학 함수
- **날짜 산술** — `today + 7` → `2026-06-21 (7일 후)`, `2026-12-31 - today` → `200일`
- **작업시간 계산** — `8h * 22` → `176h = 22일`, `40h * 5` → `200h = 25일 = 5주`
- 진법 변환 — `0xFF`, `0b1010`, `0o377` 입력 시 다른 세 진법으로 즉시 변환
- 색상 코드 — `#ff6b6b`, `rgb(255,0,0)` 입력 시 컬러 스와치 및 변환값 표시

### 📏 단위 & 환율 변환
- `100 km to miles`, `37 c to f`, `70 kg to lbs` 등 다양한 단위 지원
- `100 usd to krw`, `50 eur in jpy` — 실시간 환율 변환 (open.er-api.com, 1시간 캐시)

### ⏱️ 타이머 & 리마인더
- `timer 25m`, `타이머 1시간 30분` — 동시에 여러 타이머 실행 가능
- `remind 14:30 회의 준비` — 특정 시각에 Windows 시스템 알림 + 런처 자동 팝업
- 타이머 목록 조회 및 개별/전체 취소

### 📌 스니펫
- 트리거 단어(`:이름`, `:주소`)로 자주 쓰는 텍스트 즉시 붙여넣기
- `{{today}}`, `{{time}}`, `{{uuid}}` 동적 변수 지원
- 내보내기/가져오기, 핀 고정, 순서 변경

### ⭐ 즐겨찾기 & 워크스페이스
- 앱·폴더·URL을 즐겨찾기로 등록, Enter로 즉시 실행
- **워크스페이스** — 여러 앱·폴더·링크를 묶어 한 번에 동시 실행

### 📁 파일 검색
- 바탕화면·문서·다운로드 기본 검색 (깊이 4단계)
- 전체 드라이브 인덱싱 모드 (SQLite 기반, 시스템 폴더 제외)
- `Space` 키로 **인라인 미리보기** — 텍스트 파일 앞 10줄, 이미지 썸네일
- 우클릭 → 폴더 열기 / 경로 복사 / 속성 / 즐겨찾기 추가

### 😊 이모지 검색
- 영문 키워드로 이모지 검색, Enter로 즉시 클립보드 복사

### 📊 시스템 모니터
- `cpu`, `ram`, `disk` 입력 시 CPU·RAM·디스크 사용률을 프로그레스바로 실시간 표시

### 🖥️ 시스템 명령
- `lock`, `sleep`, `shutdown`, `restart`, `logout` — 2단계 확인 후 실행
- `kill chrome` — 실행 중인 프로세스 이름으로 강제 종료
- `empty trash` — 휴지통 비우기

### 🔌 플러그인
- TOML 파일로 커스텀 커맨드 정의 (shell, open, copy, http 액션 지원)
- 실시간 파일 변경 감지로 플러그인 자동 재로드

### 🌐 웹 검색
- `?검색어` 입력 시 설정한 브라우저로 구글 검색

### 🕒 최근 통합 검색
- 클립보드·즐겨찾기·파일을 한 화면에서 통합 조회 및 검색

---

## 설치 / Installation

[Releases 페이지](https://github.com/joulekr/ActionFlow/releases/latest)에서 최신 인스톨러를 다운로드하세요.

```
ActionFlow_x.x.x_x64-setup.exe
```

설치 후 시스템 트레이 아이콘이 생성되며, `Ctrl+Shift+Space`로 런처를 열 수 있습니다.  
단축키는 설정에서 변경할 수 있습니다.

---

## 빠른 시작 / Quick Start

| 동작 | 방법 |
|------|------|
| 런처 열기/닫기 | `Ctrl+Shift+Space` |
| 실행 / 복사 | `Enter` |
| 항목 이동 | `↑` / `↓` |
| 모드 전환 | `Tab` / `Shift+Tab` |
| 닫기 | `Esc` |

### 모드 전환 키워드

| 입력 | 모드 |
|------|------|
| `/clip` 또는 `/클립` | 📋 클립보드 히스토리 |
| `/snip` 또는 `/스니펫` | 📌 스니펫 |
| `/link` 또는 `/즐겨찾기` | ⭐ 즐겨찾기 |
| `/file` 또는 `/파일` | 📁 파일 검색 |
| `/emoji` 또는 `/이모지` | 😊 이모지 |
| `/recent` 또는 `/최근` | 🕒 최근 통합 검색 |
| `/setting` 또는 `/설정` | ⚙️ 설정 |

---

## 계산기 예제 / Calculator Examples

```
2 + 3 * 4          → 14
sqrt(16)           → 4
sin(pi/2)          → 1
100 km to miles    → 62.137 miles
100 usd to krw     → 실시간 환율 변환
today + 30         → 2026-07-14 (30일 후)
2026-12-31 - today → 200일
8h * 22            → 176h = 22일
0xFF               → 255 (DEC) · 0b11111111 (BIN) · 0o377 (OCT)
```

---

## 가이드 문서 / Documentation

- 🇰🇷 [한국어 가이드](https://github.com/joulekr/ActionFlow/blob/main/docs/GUIDE_KO.md)
- 🇺🇸 [English Guide](https://github.com/joulekr/ActionFlow/blob/main/docs/GUIDE_EN.md)

---

## 기술 스택 / Tech Stack

| 영역 | 기술 |
|------|------|
| 플랫폼 | 윈도우 10/11 전용 |
| 프레임워크 | [Tauri v2](https://tauri.app/) |
| 백엔드 | Rust |
| 프론트엔드 | React 18 + TypeScript |
| 데이터베이스 | SQLite (rusqlite, bundled) |
| 업데이트 | tauri-plugin-updater + minisign 서명 검증 |
| 단축키 | tauri-plugin-global-shortcut |

---

## 자동 업데이트 / Auto Update

앱 시작 시 GitHub Releases에서 최신 버전을 자동으로 확인합니다.  
새 버전이 있으면 런처 하단에 업데이트 배너가 표시됩니다.

---

## 기능 목록 / Feature List

### 완료 / Completed

- [x] 파일 미리보기 기능 (v0.1.9)
- [x] 리마인더 기능 (v0.1.9)

### 계획 / Planned

- [ ] 클립보드 매니저에 이미지 지원

---

## 라이선스 / License

Copyright (c) 2026 Joule Jang

All rights reserved.

개인적·비상업적 사용은 무료로 허용됩니다.
재배포, 수정, 상업적 이용은 저작권자의 명시적 허가가 필요합니다.

---

<p align="center">
  Made with ❤️ for Windows power users
</p>
