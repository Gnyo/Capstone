# Capstone Design 02

## ⚙️ 환경 세팅
### React 프로젝트 생성(Vite 사용)

![image](https://github.com/user-attachments/assets/5a3c3e1b-fbdb-478b-8c4d-3e186e5782df) |
---|

---
## 🌦️ 날씨 API 연동 테스트 
### [OpenWeatherMap](https://openweathermap.org/) API 키 발급받기
### src/api/weatherApi.js 생성
```js
const API_KEY = "**내 API 키**";

export const getWeatherByCity = async (city = "Seoul") => {
  const response = await fetch(
    `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${API_KEY}&units=metric`
  ); // units=metric: 섭씨, (imperial: 화씨)
  const data = await response.json();
  return data;
};
```
### App.jsx 수정
```js
import { useEffect, useState } from "react";
import { getWeatherByCity } from "./api/weather"; // ← 방금 만든 API 함수 가져오기
import "./App.css";

function App() {
  const [weather, setWeather] = useState(null);

  useEffect(() => {
    getWeatherByCity("Seoul").then((data) => {
      console.log("🌤️ 날씨 데이터:", data);
      setWeather(data);
    });
  }, []);

  return (
    <div className="App">
      <h1>Wearther 날씨 테스트</h1>

      {weather ? (
        <div>
          <p>🌍 도시: {weather.name}</p>
          <p>🌡️ 기온: {weather.main.temp}°C</p>
          <p>⛅ 날씨: {weather.weather[0].main}</p>
        </div>
      ) : (
        <p>날씨 정보를 불러오는 중...</p>
      )}
    </div>
  );
}

export default App;
```

### 테스트
![image](https://github.com/user-attachments/assets/83f4ca1d-7a29-42ce-8880-bb992fc40872) |
---|

---
## 📍 Geolocation 기반 날씨 조회

### src/hooks/useGeolocation.js 파일 생성
위치 가져오기용 훅
```js
import { useEffect, useState } from "react";

export const useGeolocation = () => {
  const [coords, setCoords] = useState(null);
  const [error, setError] = useState(null);

  useEffect(() => {
    if (!navigator.geolocation) {
      setError("이 브라우저는 위치 정보를 지원하지 않습니다.");
      return;
    }

    navigator.geolocation.getCurrentPosition(
      (position) => {
        setCoords({
          lat: position.coords.latitude,
          lon: position.coords.longitude,
        });
      },
      () => {
        setError("위치 정보를 가져오는 데 실패했습니다.");
      }
    );
  }, []);

  return { coords, error };
};
```

### weather.js 수정
```js
const API_KEY = "**내 API KEY**";

export const getWeatherByCoords = async (lat, lon) => {
  const response = await fetch(
    `https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}&appid=${API_KEY}&units=metric`
  );
  const data = await response.json();
  return data;
};
```

### App.jsx 수정
```js
import { useEffect, useState } from "react";
import { useGeolocation } from "./hooks/useGeolocation";
import { getWeatherByCoords } from "./api/weather";
import "./App.css";

function App() {
  const { coords, error: locationError } = useGeolocation();
  const [weather, setWeather] = useState(null);

  useEffect(() => {
    if (coords) {
      getWeatherByCoords(coords.lat, coords.lon).then((data) => {
        console.log("📍 위치 기반 날씨 데이터:", data);
        setWeather(data);
      });
    }
  }, [coords]);

  return (
    <div className="App">
      <h1>📍 내 위치 날씨</h1>

      {locationError && <p>{locationError}</p>}

      {weather ? (
        <div>
          <p>🌍 위치: {weather.name}</p>
          <p>🌡️ 기온: {weather.main.temp}°C</p>
          <p>⛅ 날씨: {weather.weather[0].main}</p>
        </div>
      ) : (
        <p>위치 및 날씨 정보를 불러오는 중...</p>
      )}
    </div>
  );
}

export default App;
```

### 테스트
![image](https://github.com/user-attachments/assets/cab76c0f-5ce8-4feb-a8f9-f3454e41d0e7) | ![image](https://github.com/user-attachments/assets/c410f5d2-dd87-495a-9ce8-b16778a8a15c)
---|---

---
## 오류 잡기
### 피드백
1. 현재 위치가 송정이 아닌데 송정이라고 뜨는 오류 발생(현재 위치는 울산)
☞ 비슷한 위·경도에 있기 때문에 오류 발생 가능
2. 영어 도시 이름이 별로임
☞ 한글화 필요

> 정확한 위치 정보, 한글 주소 지원 가능한 Kakao Location API 사용

### [Kakao](https://developers.kakao.com/) API 키 발급 받기

### src/api/location.js 파일 작성 
```js
const KAKAO_API_KEY = "내 KAKAO REST API 키";


```
