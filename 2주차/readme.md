# Capstone Design 02

## 환경 세팅
### 1. expo 설치
### 2. React Native 프로젝트 생성 → wearther
### 3. 스마트폰에 Expo go 앱 설치(구글 플레이스토어)
### 4. QR코드로 스캔하여 정상적인 실행 확인

---
## 날씨 API 연동 테스트 
### 1. [OpenWeatherMap](https://openweathermap.org/) API 키 발급받기
### 2. Expo 프로젝트에서 API 요청하기
expo-location 설치 (현재 위치 가져오기)
### 3. constants/`weatherApi.ts` 작성
```ts
export const getWeather = async (lat: number, lon: number) => {
  try {
    const response = await fetch(
      `https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}&units=metric&appid=YOUR_API_KEY`
    );
    const json = await response.json();

    return {
      temperature: json.main.temp,
      weather: json.weather[0].main,
      location: json.name,
    };
  } catch (error) {
    console.error("날씨 데이터를 가져오지 못했습니다:", error);
    return null;
  }
};

```

### 4. hooks/`useLocation.ts` 작성
```ts
import * as Location from "expo-location";
import { useState, useEffect } from "react";

// 위치 정보 타입 정의
interface LocationType {
  latitude: number;
  longitude: number;
}

// 커스텀 훅: 위치 정보 가져오기
export const useLocation = () => {
  const [location, setLocation] = useState<LocationType | null>(null);
  const [errorMsg, setErrorMsg] = useState<string | null>(null);

  useEffect(() => {
    (async () => {
      let { status } = await Location.requestForegroundPermissionsAsync();
      if (status !== "granted") {
        setErrorMsg("위치 권한이 필요합니다.");
        return;
      }

      let currentLocation = await Location.getCurrentPositionAsync({});
      setLocation({
        latitude: currentLocation.coords.latitude,
        longitude: currentLocation.coords.longitude,
      });
    })();
  }, []);

  return { location, errorMsg };
};
```

### 5. App.tsx 생성
```tsx
import React, { useEffect, useState } from "react";
import { View, Text, ActivityIndicator } from "react-native";
import { useLocation } from "./hooks/useLocation"; // 현재 위치 가져오기
import { getWeather } from "./constants/weatherApi"; // 날씨 API 불러오기

export default function App() {
  const { location, errorMsg } = useLocation();
  const [weather, setWeather] = useState(null);

  useEffect(() => {
    if (location) {
      getWeather(location.latitude, location.longitude).then(setWeather);
    }
  }, [location]);

  if (errorMsg) return <Text>{errorMsg}</Text>;
  if (!weather) return <ActivityIndicator size="large" color="#0000ff" />;

  return (
    <View style={{ flex: 1, justifyContent: "center", alignItems: "center" }}>
      <Text>위치: {weather.location}</Text>
      <Text>기온: {weather.temperature}°C</Text>
      <Text>날씨: {weather.weather}</Text>
    </View>
  );
}

```

### 6. QR코드로 스캔하여 정상적인 실행 확인

---
## 위치 권한 설정
