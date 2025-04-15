# Capstone Design 05

## 🎛️ 환경 세팅
### 라우터
`react-router-dom`

### 상태 관리
`zustand`: React에서 전역 상태를 쉽게 관리하는 간단한 도구
- React에서 여러 컴포넌트가 공통으로 데이터를 공유해야 할 때 사용
  + 다크/라이트 테마 상태
  + 사용자의 위치 정보

## ✍️ 디자인
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

#### 아이콘 코드
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
| 물방울 | ![image](https://github.com/user-attachments/assets/32ff44f1-97f2-4a3e-aaa7-12fb727aedf7) | `import { IoWaterSharp } from "react-icons/io5";` `<IoWaterSharp />` |
