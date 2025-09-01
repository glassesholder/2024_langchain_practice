# PDF 기반 AI 챗봇 시스템

**Python 3.10.0** (3.8~3.12 버전 호환)

## 📋 프로젝트 개요

이 프로젝트는 PDF 교재를 기반으로 한 AI 챗봇 시스템입니다. LangChain과 OpenAI API를 활용하여 교재를 벡터화하고, 질문에 맞춤형 답변을 제공합니다.

### 🎯 주요 기능
- **PDF 문서 벡터화**: 교재를 AI가 이해할 수 있는 형태로 변환
- **텍스트 기반 질의응답**: 교재 내용을 참고한 정확한 답변 제공
- **이미지 기반 문제 해결**: 이미지를 분석하여 단계별 풀이 제공
- **개인화된 학습**: 중학교 1학년 수준에 맞춘 친근한 설명

### 📁 파일 구조
```
2024_langchain_practice/
├── file_trans.ipynb     # PDF → 벡터 스토어 변환 도구
├── main.ipynb          # AI 챗봇 실행 파일
├── requirements.txt    # 필요한 패키지 목록
├── pdf/               # 교재 PDF 파일 저장소
├── faiss_data/        # 생성된 벡터 스토어 (실행 후 생성)
├── image.jpg          # 수학 문제 이미지 예시
└── .env              # OpenAI API 키 설정 파일
```

## 🚀 설치 및 실행 가이드

### 1단계: 가상환경 설정
```bash
# 터미널 열기: Ctrl + `
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### 2단계: OpenAI API 키 설정
`.env` 파일을 생성하고 API 키를 입력하세요:
```env
OPENAI_API_KEY="sk-proj-your-api-key-here"
```

### 3단계: PDF 교재 준비
- `pdf/` 폴더에 교재 PDF 파일을 넣으세요
- OCR이 필요한 경우 알PDF 등으로 텍스트 추출 가능한 형태로 변환하세요

### 4단계: 벡터 스토어 생성
1. `file_trans.ipynb` 실행
2. Jupyter에서 가상환경 커널 선택
3. 모든 셀을 순차적으로 실행 (Shift + Enter)
4. `faiss_data/` 폴더 생성 확인

### 5단계: AI 튜터 사용
1. `main.ipynb` 실행  
2. 가상환경 커널 선택
3. 셀을 실행하여 질의응답 테스트
4. 프롬프트 수정으로 다양한 답변 스타일 실험

## 🔧 기술 스택

- **LangChain**: 문서 처리 및 체인 구성
- **OpenAI GPT-4**: 자연어 처리 및 이미지 분석
- **FAISS**: 고성능 벡터 검색
- **PyPDF**: PDF 문서 로딩
- **PIL**: 이미지 처리

## 💡 사용 예시

### 텍스트 질문
```
"소인수분해가 뭐야?"
→ "소인수분해란 자연수를 소수의 곱으로 표현하는 것을 말해요..."
```

### 이미지 문제 해결
수학 문제 이미지를 업로드하면 단계별 풀이를 제공합니다:
- 전략 1단계 → 풀이 1단계
- 전략 2단계 → 풀이 2단계  
- 최종 답안

## ⚠️ 주의사항

- OpenAI API 사용량에 따른 비용이 발생할 수 있습니다
- PDF 파일은 텍스트 추출이 가능한 형태여야 합니다
- 인터넷 연결이 필요합니다 (OpenAI API 호출)