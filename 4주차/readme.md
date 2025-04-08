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
## 🖼️ 로고 디자인
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
#### 아이콘 라이브러리
- `React Icons`: [React Icons](https://react-icons.github.io/react-icons/)
- 라이선스: **MIT 라이선스**

```bash
npm install react-icons --save
```
>[!note]
> 개발 시: React 컴포넌트에서 사용
```js
import { FaSmile, FaFrown, FaMeh } from 'react-icons/fa';  // Font Awesome Icons
```
```js
import { IconName } from "react-icons/wi";  // Weather Icons
```

### 아이콘 코드
| 사용처 | 이미지 | 코드 |
|--------|--------|------|
| 검색 버튼 | ![image](https://github.com/user-attachments/assets/77fd0181-ca2a-4ddf-9d8c-9b5c0b795e9c) | `import { IoIosSearch } from "react-icons/io";` `<IoIosSearch />` |
| 위치 버튼 | ![image](https://github.com/user-attachments/assets/77700eac-7f4d-444d-95dd-f3c1829a9028) | `import { IoMdPin } from "react-icons/io";` `<IoMdPin />` |
| 설정 버튼 | ![image](https://github.com/user-attachments/assets/f6a894b5-62d0-4226-98ff-86422556aa11) | `import { IoIosSettings } from "react-icons/io";` `<IoIosSettings />` |
| 뒤로가기 버튼 | ![image](https://github.com/user-attachments/assets/d6cd83da-d9da-4052-ac67-af9050d403a8) | `import { IoIosArrowBack } from "react-icons/io";` `<IoIosArrowBack />` |
| home버튼 | ![image](https://github.com/user-attachments/assets/846d7b17-d1ee-4cc8-b5c4-9d0613c54dfd) | `import { PiHouse } from "react-icons/pi";` `<PiHouse />` |
| home버튼: hover | ![image](https://github.com/user-attachments/assets/365c2885-f005-4163-9c29-88fa39c1671f) | `import { PiHouseFill } from "react-icons/pi";` `<PiHouseFill />`|
| room버튼 | ![image](https://github.com/user-attachments/assets/d620e1e2-9d11-439d-9a21-be72a46e7868) | import { PiCoatHanger } from "react-icons/pi";` `<PiCoatHanger />` |
| room버튼: hover | ![image](https://github.com/user-attachments/assets/9a885d70-18f3-4460-96e8-a689c8bef43f) | `import { PiCoatHangerBold } from "react-icons/pi";` `<PiCoatHangerBold />`|
| 표정: 완전좋음 |![image](https://github.com/user-attachments/assets/facdbd59-9edb-41d6-b633-d16f8cb25222) | `import { FaRegFaceLaughSquint } from "react-icons/fa6";` `<FaRegFaceLaughSquint />` |
| 표정: 좋음 |![image](https://github.com/user-attachments/assets/5a03bf16-8950-4ae5-ab77-44adfcf6ba82) |`import { FaRegFaceSmile } from "react-icons/fa6";` `<FaRegFaceSmile />` |
| 표정: 무난 |![image](https://github.com/user-attachments/assets/6a606eb8-d8f5-4820-b35e-9f64462ef963) |`import { FaRegFaceMeh } from "react-icons/fa6";` `<FaRegFaceMeh />`|
| 표정: 나쁨 |![image](https://github.com/user-attachments/assets/ea419167-5ce7-4cde-a023-4c05cbb6ad61) |`import { FaRegFaceFrown } from "react-icons/fa6";` `<FaRegFaceFrown />`|
| 표정: 완전나쁨 |![image](https://github.com/user-attachments/assets/aab87911-a776-4f6c-b19d-499d38649f8e)|`import { FaRegFaceTired } from "react-icons/fa6";` `<FaRegFaceTired />`|
