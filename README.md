<img width="1536" height="1024" alt="cover" src="https://github.com/user-attachments/assets/a69b5080-6f94-4c3c-84a8-57a6d242318c" />

# 🧠 AI 기반 강의 영상 생성 Agent 시스템

PPT 교안을 업로드하면 슬라이드 내용을 자동 분석하고,

- 발표 스크립트 생성
- TTS 음성 생성
- 영상(mp4) 생성
- 
까지 수행하는 AI 기반 강의 영상 생성 Agent 시스템 프로젝트입니다.

LangGraph 기반 Workflow 구조를 활용하여 PPT 분석부터 영상 생성까지의 전체 흐름을 State 기반 AI Agent 형태로 설계했습니다.

---

# 📌 Project Overview

기업 및 교육 환경에서는 발표 자료(PPT)를 교육 영상 형태로 변환하는 과정에 많은 시간과 비용이 필요합니다.

특히:

- 발표 영상 직접 녹화 필요
- 영상 편집 및 자막 작업 필요
- 발표자별 전달 품질 차이 발생
- 교육 자료 영상화까지 장시간 소요

등의 비효율 문제가 존재했습니다.

본 프로젝트에서는 이러한 문제를 해결하기 위해:

- PPT 분석
- 발표 스크립트 생성
- 음성 생성(TTS)
- 영상 생성

과정을 자동화하는 AI Agent 시스템을 구축했습니다.

---

# 🎯 Project Goals

- PPT 기반 발표 내용 자동 분석
- 슬라이드별 발표 스크립트 생성
- TTS 기반 음성 생성
- 슬라이드 + 음성 기반 영상 자동 생성
- LangGraph 기반 Workflow 구조 설계
- State 기반 데이터 흐름 관리

---

# ⚙️ Tech Stack

## AI / LLM
- OpenAI GPT-4o-mini
- GPT-4o-mini-tts

## Framework
- LangChain
- LangGraph
- Gradio

## Backend
- Python

## PPT / Data Processing
- python-pptx
- Base64 Encoding

## Media Processing
- FFmpeg

---

# 🧩 System Workflow

```text
PPT Upload
    ↓
Slide Parsing
(Text / Table / Image)
    ↓
Page Content Generation
    ↓
Presentation Script Generation
    ↓
TTS Voice Generation
    ↓
Video Generation
    ↓
Final Video Merge
```

LangGraph 기반 상태(State) 관리 구조를 통해 각 단계의 데이터를 연결하고 추적할 수 있도록 설계했습니다.

---

# 🔍 Main Features

## 1. PPT Parsing
- 슬라이드 텍스트 추출
- 표(Table) 데이터 추출
- 이미지 추출 및 처리
- 슬라이드 구조 분석

## 2. Multimodal Processing
- Text + Image 기반 입력 구성
- Base64 기반 이미지 처리
- 슬라이드별 멀티모달 프롬프트 구성

## 3. Script Generation
- GPT 기반 발표 스크립트 생성
- 슬라이드 흐름 기반 설명 생성
- 발표 형식 자동 구성

## 4. TTS Generation
- OpenAI TTS 모델 기반 음성 생성
- 발표용 내레이션 자동 생성

## 5. Video Generation
- 슬라이드 + 음성 기반 영상 생성
- FFmpeg 기반 영상 병합
- 최종 mp4 출력

---

# 🧠 Architecture Design

프로젝트에서는:

- PPT 추출 데이터
- 생성된 발표 스크립트
- 음성 파일
- 영상 결과물

등 다양한 산출물이 단계별로 생성되었습니다.

단순 함수 호출 방식으로는 Workflow 관리와 데이터 흐름 추적이 어려워,
LangGraph 기반 State 구조를 활용하여:

- 단계별 데이터 관리
- Node 기반 Workflow 분리
- Workflow 확장성 확보
- 디버깅 편의성 향상

을 고려해 설계했습니다.

---

# ⚙️ Agent Workflow

```text
parse_ppt
    ↓
generate_page
    ↓
generate_script
    ↓
tts_mp3
    ↓
make_video
```

각 단계를 독립적인 Node로 구성하여 유지보수성과 확장성을 높였습니다.

---

# 📈 What I Learned

- LangGraph 기반 Agent 시스템 설계 경험
- State 기반 Workflow 관리 경험
- 멀티모달 입력 처리 경험
- PPT Parsing 경험
- TTS 및 영상 생성 파이프라인 구현 경험
- AI 기능을 실제 서비스 흐름으로 연결하는 경험
- Workflow 기반 시스템 설계 경험

---

# 🚀 Future Improvements

- Multi-Agent 구조 확장
- 발표 스타일별 음성 생성 기능 추가
- 자막 자동 생성 기능 추가
- 실시간 스트리밍 영상 생성
- 사용자 피드백 기반 Script 개선 기능

---

# 📁 Repository Structure

```bash
ai-lecture-agent
│
├── notebooks/
│   └── lecture_video_agent.ipynb
│
├── images/
│   └── cover.png
│
├── outputs/
│   └── generated_video.mp4
│
└── README.md
```

---

# 👩‍💻 Author

장현지  
AI Application Developer
