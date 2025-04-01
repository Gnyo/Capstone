# Capstone Design 04

## 🌦️ WeatherAPI
### WeatherAPI 가입 및 키 발급
[WeatherAPI](https://www.weatherapi.com) 접속 후 API Key 발급

### 원하는 API 종류
기능 | API 종류 | 예시
---|---|---
현재 날씨	| /current.json | https://api.weatherapi.com/v1/current.json?key=YOUR_KEY&q=위치
시간별 예보 (최대 24시간) | /forecast.json |	https://api.weatherapi.com/v1/forecast.json?key=YOUR_KEY&q=위치&days=1&hour=1
주간 날씨 | /forecast.json | ...&days=7 형태로 사용

### WeatherAPI 연동
![image](https://github.com/user-attachments/assets/71a2ad95-4673-4953-8290-3724ced1b798)

---
## 🧑‍💻 프론트&백 동시 실행
개발 시에 프론트는 Vite React, 백은 node.js 서버를 열어야함 → 귀찮다
> 동시 실행 가능하도록 스크립트 생성

### `nodemon` 설치
```
npm install -D nodemon
```

### `concurrently` 패키지 설치
```
npm install -D concurrently
```

### `pakage.json` 수정
```json

  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "lint": "eslint .",
    "preview": "vite preview",
    "start-server": "node server.js",
    "dev-server": "nodemon server.js",
    "dev:all": "concurrently \"npm run dev\" \"npm run dev-server\""
  }
```

### 실행
```
npm run dev:all
```
![image](https://github.com/user-attachments/assets/9770003e-2010-463a-b559-fcd22afef040) |
---|

---
## ✍️ 로고 디자인
### 디자인 툴
> Inkscape

### Logo 제작
![Logo](https://github.com/user-attachments/assets/62fa522f-b5a7-4229-93ec-a355b7662408)| ![Logo1](https://github.com/user-attachments/assets/be4fcd6a-64f2-4190-ae41-980d2025be04) | ![Logo2](https://github.com/user-attachments/assets/6a64eea7-7c7d-49f6-8341-0e8e159a84e2)
---|---|---

---
## 🎨 프로토타입 제작
### 디자인 툴
> Figma

### 아이콘 
#### 날씨 아이콘 라이브러리
Weather Icons: MIT 라이선스 하에 제공 [https://github.com/erikflowers/weather-icons](https://github.com/erikflowers/weather-icons)
> 개발 시에는 CDN 방식으로 사용

#### 표정 아이콘
아이콘 제공: Icons8
![image](https://github.com/user-attachments/assets/676defa1-147a-40b4-a864-43bda668e075) |
---|
![image](https://github.com/user-attachments/assets/e247dba1-b2a7-4779-8e84-31a540fe4154) |
![image](https://github.com/user-attachments/assets/8cef286e-cb17-4d16-8552-1af8eeecc96a) |
![image](https://github.com/user-attachments/assets/8910f7b0-1889-43ff-a1a7-b5fb3cec5a6c) |
![image](https://github.com/user-attachments/assets/a89c1160-270a-42eb-a779-b21c5a9f835b) |



