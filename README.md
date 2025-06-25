# Vibe Coding Week 2-1 Project

LangGraph Agent를 활용한 상품 검색 서비스

## 📌 프로젝트 개요

이 프로젝트는 LangGraph와 Google Gemini를 활용하여 개발된 지능형 상품 검색 Agent 서비스입니다. 사용자가 상품명을 입력하면 DuckDuckGo 검색을 통해 실시간 상품 정보를 검색하고, AI Agent가 유용한 정보를 제공합니다.

## 🏗️ 프로젝트 구조

```
vibe_coding_w2-1/
├── backend/                # FastAPI 백엔드 서버
│   ├── app/
│   │   ├── agent.py       # LangGraph Agent 구현
│   │   ├── main.py        # FastAPI 애플리케이션
│   │   ├── config.py      # 설정 관리
│   │   ├── models/        # 데이터 모델
│   │   └── routers/       # API 라우터
│   ├── tests/             # 테스트 코드
│   └── requirements.txt   # Python 의존성
├── frontend/              # Streamlit 프론트엔드
│   ├── app.py            # Streamlit 앱
│   └── requirements.txt  # 프론트엔드 의존성
├── docs/                 # 문서 및 와이어프레임
└── .github/              # GitHub 워크플로우
```

## 🚀 주요 기능

### ✨ 백엔드 (FastAPI + LangGraph)

- **LangGraph React Agent**: 단일 턴 상품 검색 Agent
- **Google Gemini 2.0-flash**: 최신 LLM 모델 연동
- **DuckDuckGo Search Tool**: 실시간 웹 검색
- **RESTful API**: `/chat/` 엔드포인트 제공
- **완전한 테스트 커버리지**: pytest 기반 TDD

### 🎯 프론트엔드 (Streamlit)

- **사용자 친화적 채팅 인터페이스**
- **실시간 상품 검색 결과 표시**
- **반응형 웹 디자인**

## 🛠️ 기술 스택

### Backend

- **Framework**: FastAPI
- **AI Framework**: LangGraph
- **LLM**: Google Gemini 2.0-flash
- **Search Tool**: DuckDuckGo Search
- **Testing**: pytest
- **Code Quality**: Black, isort, flake8

### Frontend

- **Framework**: Streamlit
- **UI Components**: Streamlit native components

### DevOps

- **CI/CD**: GitHub Actions
- **Testing**: Automated test workflows
- **Code Review**: PR template & code review workflows

## 📋 설치 및 실행

### 1. 저장소 클론

```bash
git clone https://github.com/Tonyson8245/vibe_coding_w2-2.git
cd vibe_coding_w2-2
```

### 2. 환경 변수 설정

`.env` 파일을 생성하고 다음 변수들을 설정하세요:

```bash
# AI 모델 API 키 (필수)
GOOGLE_API_KEY=your_google_api_key_here

# LangSmith 모니터링 (선택사항)
LANGSMITH_API_KEY=your_langsmith_api_key_here
LANGCHAIN_TRACING_V2=true
LANGCHAIN_PROJECT=vibe-coding-w2-1
```

### 3. 백엔드 실행

```bash
cd backend
pip install -r requirements.txt
python run.py
```

서버가 http://localhost:8000 에서 실행됩니다.

### 4. 프론트엔드 실행

```bash
cd frontend
pip install -r requirements.txt
streamlit run app.py
```

웹 앱이 http://localhost:8501 에서 실행됩니다.

## 🔧 API 사용법

### 상품 검색 API

```bash
curl -X POST "http://localhost:8000/chat/" \
  -H "Content-Type: application/json" \
  -d '{"message": "아이폰 15 프로"}'
```

### 응답 예시

```json
{
  "response": "아이폰 15 프로에 대한 최신 정보를 찾았습니다. 현재 시장 가격과 주요 특징, 그리고 구매 가능한 곳들에 대한 정보를 제공합니다..."
}
```

## 🧪 테스트 실행

```bash
cd backend

# 모든 테스트 실행
python -m pytest tests/ -v

# 특정 테스트 실행
python -m pytest tests/test_agent.py -v
python -m pytest tests/test_chat.py -v
```

## 🏛️ 아키텍처

이 프로젝트는 Clean Architecture와 SOLID 원칙을 따라 설계되었습니다:

- **단일 책임 원칙**: 각 모듈은 명확한 역할을 가짐
- **의존성 역전**: 추상화에 의존하는 구조
- **테스트 우선 개발**: TDD 방식으로 개발
- **간단한 구조**: 과도한 모듈화를 피한 심플한 아키텍처

## 📚 개발 원칙

### TDD (Test-Driven Development)

1. **테스트 코드 작성**
2. **기능 구현**
3. **테스트 실행 및 수정**
4. **리팩토링**

### 코드 품질

- **SOLID 원칙** 준수
- **Clean Architecture** 적용
- **최소한의 모듈화**로 단순성 유지

## 🤝 기여 방법

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다.

## 👥 작성자

- **Tonyson8245** - [GitHub Profile](https://github.com/Tonyson8245)

## 🔗 관련 링크

- [프로젝트 저장소](https://github.com/Tonyson8245/vibe_coding_w2-2)
- [이슈 트래커](https://github.com/Tonyson8245/vibe_coding_w2-2/issues)
- [Pull Requests](https://github.com/Tonyson8245/vibe_coding_w2-2/pulls)
