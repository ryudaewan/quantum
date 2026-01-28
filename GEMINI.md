# Project Context: Quantum

이 파일은 Gemini CLI 에이전트가 이 프로젝트(`quantum`)를 이해하고 작업하는 데 필요한 핵심 컨텍스트를 담고 있습니다.

## 프로젝트 개요
- **이름:** quantum (또는 quant)
- **목적:** Udemy 강좌 "챗GPT와 파이썬으로 주식 자동매매 앱 및 웹 투자 리포트 만들기"를 바탕으로 한 키움증권 REST API 기반 자동매매 시스템 실습 및 개발.
- **주요 특징:**
    - 기존 OCX 방식 대신 **Kiwoom REST API**를 사용하여 OS 제약 없이(macOS, Linux 가능) 동작합니다.
    - Anaconda 대신 **uv**를 패키지 매니저로 사용합니다.

## 기술 스택 및 환경
- **언어:** Python (>= 3.13)
- **패키지 매니저:** `uv` (pip, venv 대신 `uv sync`, `uv run` 등 사용)
- **주요 라이브러리:**
    - `requests`, `websocket-client`: API 통신 및 실시간 데이터 수신
    - `python-dotenv`: 환경 변수 관리
    - `timedelta`: 시간 계산
- **운영체제:** 제한 없음 (현재 사용 환경: darwin)

## 프로젝트 구조 및 주요 파일
- `main.py`: 애플리케이션 진입점
- `core/`: 핵심 로직 (API 핸들러 등)
- `config.toml`: 애플리케이션 설정 (실거래/모의투자 구분, API 키 경로 등)
- `keys/`: API 키 및 토큰 정보 저장 폴더 (주의: `.gitignore`를 통해 보안 유지)
- `kiwoom_sample/`: 키움 API 활용 예제 코드들
- `pyproject.toml` & `uv.lock`: 프로젝트 의존성 관리

## 개발 가이드라인
- **언어:** 모든 소통과 주석, 문서화는 한국어를 우선으로 합니다.
- **의존성 관리:** 새로운 패키지가 필요할 경우 `uv add <package>`를 사용합니다.
- **설정:** `config.toml`과 `keys/` 폴더 내의 `.toml` 파일들을 참조하여 API 인증을 처리합니다.
- **보안:** API Key, App Secret, Access Token 등이 포함된 파일은 절대 Git에 커밋하거나 노출하지 않습니다.

## 에이전트 행동 지침
- 한국어로 응답하십시오.
- 프로젝트의 `uv` 기반 환경을 존중하고, 관련 명령어를 우선적으로 사용하십시오.
- 코드 수정 시 `core/` 내의 기존 모듈 구조를 따르고, `kiwoom_sample/`의 예제를 참고하십시오.