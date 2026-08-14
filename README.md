# 2026-Summer-AI-Server

## 프로젝트 소개

WIL, Docker를 활용해 OpenWebUI 기반 로컬 AI 서버를 구축하고,
Ollama, ComfyUI를 연동하여 LLM 및 이미지 생성 환경을 구성한다.

## 개발 환경

- CPU: Intel i5-13500
- GPU: RTX 5070
- RAM: DDR4 32GB
- OS: Windows

## 사용 기술

- OpenWebUI
- Ollama
- Docker
- ComfyUI

## 개발 기록

### 2026-08-12

- Ollama 설치 및 모델 실행 테스트
  - gemma4:12b
  - gemma4:e4b
  - qwen2.5-coder:14b-instruct
  - qwen3-coder:30b
- Stability Matrix 설치 , ComfyUI 워크플로우 구성 및 모델 실행 테스트


### 2026-08-15

- Docker 환경으로 OpenWebUI 컨테이너 생성
- 외부에서 사용을 위한 포트포워딩
- 서버 접속 테스트
- Ollama 연동
- LLM 모델 실행 테스트
- ComfyUI 연동 -> 포트 충돌발생 -> 포트 변경으로 해결
- 이미지 모델 테스트 -> 생성오류 -> 노드 재배선으로 해결
- 웹 검색 기능을 위해 검색엔진 추가 (Tavily)
- 모든 사용자 기본모델(gemma4 12b) 세팅
- 서버 하드웨어 자원 관리 및 안정적인 운영을 위해 모델별 매개변수와 기능 설정 조정
- 사용자 권한 수정 등 사용자 관리
- 외부 테스터를 통한 서버 기능 테스트 -> 이미지 생성 요청 과정에서 LLM의 Comfy 호출에서 문제 발견 -> 호출 매개변수 및 시스템 프롬프트 수정으로 안정화
- 모델 이름변경, 태그, 설명추가 등으로 디자인 (로고 이미지 생성 계획)
