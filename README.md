# 2026-Summer-AI-Server

## 프로젝트 소개

WSL, Docker를 활용해 OpenWebUI 기반 로컬 AI 서버를 구축하고,
Ollama, ComfyUI를 연동하여 LLM 및 이미지 생성 환경을 구성한다.

## 개발 환경

- CPU: Intel i5-13500
- GPU: RTX 5070
- RAM: DDR4 32GB
- OS: Windows 11

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

#### OpenWebUI 서버 구축
- Docker 환경으로 OpenWebUI 컨테이너 생성
- 외부에서 사용을 위한 포트포워딩
- 서버 접속 테스트
- Ollama 연동
- LLM 모델 실행 테스트

#### ComfyUI 연동 및 문제 해결
- ComfyUI 연동
  - 포트 충돌 발생 → 포트 변경으로 해결
- 이미지 모델 테스트
  - 생성 오류 발생 → 노드 재배선으로 해결

#### 기능 및 사용자 설정
- 웹 검색 기능을 위해 Tavily 추가
- 모든 사용자 기본 모델을 gemma4:12b로 설정
- 모델별 매개변수 및 기능 설정 조정
- 사용자 권한 및 사용자 관리

#### Tool Call 테스트 및 개선
- 외부 테스터를 통한 서버 기능 테스트
- 이미지 생성 요청 과정에서 LLM의 ComfyUI 호출 문제 발견
- 호출 매개변수 및 시스템 프롬프트 수정으로 안정화

#### UI 구성
- 모델 이름 변경
- 태그 및 설명 추가
- 로고 이미지 생성 계획


### 2026-08-17

- 장시간 사용 시 답변 끊김 문제 발견. → 컨텍스트(num_ctx) 크기 수정 (16,384 → 32,768)
- 이미지 생성 시 도구 호출 안정성 소규모 테스트 → 모두 다른 채팅방에서 다른 유형의 프롬프트로 10회 테스트 → 10/10 모두 호출 성공
- Context Compaction 기능 세팅 → 장시간 대화 시 컨텍스트 사용량을 효율적으로 관리
