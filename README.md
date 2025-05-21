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

## ⚙️ 설치 및 실행 방법

### 1. Docker 환경 준비

```bash
docker run -it --name chat-app -p 3000:3000 -p 22:22 ubuntu:20.04 /bin/bash
```

### 2. 컨테이너 내 패키지 설치

```bash
apt-get update && apt-get upgrade -y
apt-get install -y python3 python3-pip python3-venv nodejs npm git openssh-server curl
```

### 3. 사용자 계정 및 SSH 설정

```bash
useradd -m -s /bin/bash chatuser
passwd chatuser
usermod -aG sudo chatuser
service ssh start
```

### 4. VS Code Remote-SSH 연결

- Remote-SSH 확장 설치 후 `chatuser@127.0.0.1`로 접속

### 5. Git 클론 및 설정

```bash
git clone https://github.com/your-username/fastapi-websocket-chat.git
cd fastapi-websocket-chat
```

### 6. 백엔드 설정

```bash
cd backend
python3 -m venv venv
source venv/bin/activate
pip install fastapi uvicorn websockets pyngrok jinja2 python-multipart
```

### 7. 프론트엔드 설정

```bash
cd ../frontend
npm install
npm run build
```

### 8. 빌드 파일 복사

```bash
rm -rf ../backend/www/*
cp -r build/* ../backend/www/
```

### 9. 서버 실행

```bash
cd ../backend
source venv/bin/activate
python -m uvicorn app.app:app --host 0.0.0.0 --port 3000
```

### 10. ngrok으로 외부 연결

```bash
cd backend
source venv/bin/activate
python ngrok_setup.py
```

## 🌐 접속 주소

ngrok 실행 시 표시된 URL을 통해 외부에서도 채팅 서비스 접속 가능

예: `https://xxxx-3000.ngrok-free.app`

## 🚀 GitHub 배포

```bash
git add .
git commit -m "초기 구현: FastAPI 웹소켓 채팅 애플리케이션"
git push origin main
```

## 🛠 문제 해결

- 웹소켓 연결 문제 발생 시 포트(3000) 또는 ngrok 인증 여부 확인
- 빌드 후 파일 복사 누락 시 프론트 페이지가 로딩되지 않음
- SSH 접속 불가 시 SSH 서버 재시작 필요 (`service ssh restart`)

## 📄 라이선스

MIT License

## 🙌 기여

Pull Request는 언제든 환영입니다! 버그 제보 및 기능 제안도 자유롭게 남겨주세요.