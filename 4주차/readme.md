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

### Kakao API + WeatherAPI 연동
