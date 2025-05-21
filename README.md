# 🧠 FastAPI WebSocket Chat App

FastAPI와 React를 기반으로 한 실시간 웹소켓 채팅 서비스입니다. Docker 환경에서 백엔드와 프론트엔드를 구성하고, ngrok을 통해 외부 접속이 가능하도록 구현되었습니다.

## 📌 주요 기능

- FastAPI 기반의 백엔드 웹소켓 서버
- React 기반의 프론트엔드 UI
- 실시간 채팅 및 채팅방 선택 기능
- ngrok을 통한 외부 접속 지원
- Docker 컨테이너에서의 개발 환경 설정

## 🗂 프로젝트 구조

```
fastapi-websocket-chat/
├── backend/
│   ├── app/
│   │   └── app.py
│   ├── www/
│   └── ngrok_setup.py
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   └── styles/
│   └── package.json
├── .gitignore
└── README.md
```

## 🌐 접속 주소

ngrok 실행 시 표시된 URL을 통해 외부에서도 채팅 서비스 접속 가능

예: `https://xxxx-3000.ngrok-free.app`


## 🛠 문제 해결

- 웹소켓 연결 문제 발생 시 포트(3000) 또는 ngrok 인증 여부 확인
- 빌드 후 파일 복사 누락 시 프론트 페이지가 로딩되지 않음
- SSH 접속 불가 시 SSH 서버 재시작 필요 (`service ssh restart`)

## 📄 라이선스

MIT License

## 🙌 기여

Pull Request는 언제든 환영입니다! 버그 제보 및 기능 제안도 자유롭게 남겨주세요.
