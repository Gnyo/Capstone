# Capstone Design 02

## ⚙️ 환경 세팅
### React 프로젝트 생성(Vite 사용)

![image](https://github.com/user-attachments/assets/5a3c3e1b-fbdb-478b-8c4d-3e186e5782df) |
---|

---
## 🌦️ 날씨 API 연동 테스트 
### [OpenWeatherMap](https://openweathermap.org/) API 키 발급받기

### 테스트
![image](https://github.com/user-attachments/assets/83f4ca1d-7a29-42ce-8880-bb992fc40872) |
---|

---
## 📍 Geolocation 기반 날씨 조회

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

### Kakao API 연동
1. 403 오류 발생 ☞ headers 문제? ☞ 카카오맵 API 활성화를 누르지 않아 생긴 오류였음... 수정✅
2. 클라이언트에서 API 키 노출 가능성 ☞ 보안 위험

> 백엔드 우회 프록시 사용 (Node.js 서버로 요청 보내기)
배포할 때 프록시 서버도 같이 옮기기

### Kakao 로컬 API 역지오코딩
![image](https://github.com/user-attachments/assets/ddd8617a-dfdd-40ac-97ac-d4cb11cb15a0)

### 테스트
![image](https://github.com/user-attachments/assets/06b72a5c-6e12-4715-b32e-3cbbf4e01a5c)
