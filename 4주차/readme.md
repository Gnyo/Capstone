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
| Light Mode | Dark Mode |
|------------|-----------|
![Logo_Sun](https://github.com/user-attachments/assets/356ecc71-1d7d-4ff3-b259-3aa35d4e270d) | ![Logo_Moon](https://github.com/user-attachments/assets/6738bd23-884f-4aa6-ba92-34d42425a70b)


---
## 🎨 프로토타입 제작
### 디자인 툴
> Figma

### 아이콘 
#### UI 컴포넌트 라이브러리
- `Ant Design Icons`: [Ant Design Icons](https://ant.design/components/icon/)
- 라이선스: **MIT 라이선스**

>[!note]
> 개발 시: React 컴포넌트에서 사용
```bash
npm install @ant-design/icons@5.x --save
```
```react
import { SmileOutlined, CloudOutlined, RainOutlined } from '@ant-design/icons';
```

#### 날씨 아이콘 라이브러리
- `Weather Icons`: [https://github.com/erikflowers/weather-icons](https://github.com/erikflowers/weather-icons)
- 라이선스: **MIT 라이선스**

>[!note]
>  개발 시: CSS 파일 임포트 후 React에서 사용
```bash
npm install weather-icons --save
```
```css
import 'weather-icons/css/weather-icons.css'; // weather-icons CSS 임포트
```
