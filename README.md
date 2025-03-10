캡스톤 디자인

📌 6-8주 개발 일정 계획표
주제: 소규모 모임을 위한 방(또는 캐릭터) 꾸미기 + 일정 공유 앱
개발 기간: 6~8주 (1인 개발 기준)

🛠 프로젝트 진행 방식
Week 1-2: 기획 및 기본 기능 구현
Week 3-5: 주요 기능 개발 (방 꾸미기, 일정 공유)
Week 6-8: 기능 추가 & 최적화, 테스트 & 배포
📅 상세 일정 계획
주차	주요 작업	세부 내용
Week 1	📌 프로젝트 기획 & 환경 세팅	- 프로젝트 목표 & 핵심 기능 정리
- UI 와이어프레임(Figma) 제작
- 기본 개발 환경 세팅 (React Native/Flutter + Firebase)
Week 2	✅ 사용자 인증 및 데이터 구조 설계	- Firebase Authentication (이메일 로그인)
- Firestore DB 구조 설계 (사용자, 방, 일정)
- 기본적인 UI 레이아웃 구축
Week 3	✅ 방(또는 캐릭터) 꾸미기 기능	- 방/캐릭터 커스터마이징 UI 구현
- 색상, 아이콘, 테마 선택 기능 추가
- 사용자별 커스터마이징 데이터 Firestore에 저장
Week 4	✅ 공유 달력 & 일정 관리 기능	- react-native-calendars 또는 FullCalendar 라이브러리 적용
- 일정 추가, 수정, 삭제 기능 구현
- RSVP(참석 여부) 선택 기능 추가
Week 5	✅ 참여자 프로필 & 역할 설정	- 사용자 프로필 편집 (닉네임, 역할 선택)
- 초대된 사용자 목록 표시
- 역할(관리자/참여자) 설정 기능 추가
Week 6	🚀 푸시 알림 & 실시간 동기화	- Firebase Cloud Messaging(FCM) 연동
- 일정 변경 시 실시간 동기화 구현
Week 7	🛠 최적화 & UI 개선	- 앱 성능 최적화 (불필요한 API 호출 줄이기)
- UI/UX 개선 (애니메이션 추가, 디자인 다듬기)
Week 8	🏁 최종 테스트 & 배포	- 주요 기능 테스트 (버그 수정)
- Android/iOS 빌드 후 배포
- 사용성 테스트 및 피드백 반영


✅ 1. 개발 환경 구축 (무료 도구 사용)
할 일	사용 도구	설명
코드 편집기 설치	VS Code	무료 & 플러그인 지원
모바일 앱 프레임워크 선택	React Native + Expo	크로스 플랫폼 지원 (Android & iOS)
UI 라이브러리 사용	React Native Paper / TailwindCSS (NativeWind)	무료 UI 컴포넌트 활용
버전 관리 & 협업	GitHub (프라이빗 저장소 무료)	코드 백업 & 협업 가능
✅ 2. 앱 개발 (기능별 해야 할 일)
🎨 UI/UX 디자인
할 일	사용 도구	설명
와이어프레임 디자인	Figma (무료 플랜)	UI 레이아웃 설계
아이콘 & 그래픽	Phosphor Icons / Material Icons	무료 아이콘 라이브러리
🛠 기능 개발
기능	해야 할 일	사용 도구
✅ 방(캐릭터) 꾸미기	- 사용자별 프로필 생성 (색상, 테마 설정)
- 방(또는 캐릭터) 선택 기능 개발	Firestore (무료)
✅ 일정 공유 (캘린더)	- 일정 추가, 수정, 삭제 구현
- RSVP 기능 개발 (참석 여부 선택)	react-native-calendars (무료)
✅ 사용자 로그인	- Firebase Authentication 사용
- 이메일 로그인 지원	Firebase Auth (무료)
✅ 실시간 데이터 저장	- Firestore 데이터베이스 구축
- 보안 규칙 설정 (인증된 사용자만 접근)	Firebase Firestore (무료 한도 내 사용)
✅ 푸시 알림	- Firebase Cloud Messaging 연동	FCM (무료)
✅ 3. APK 빌드 & 배포 (무료 방식)
할 일	사용 도구	설명
APK 파일 빌드	Expo EAS Build (무료 플랜)	expo build:android -t apk 사용
배포	직접 배포 (Google Drive, 웹사이트 등)	앱스토어 없이 APK 배포
Firebase 설정	SHA 키 등록 (Firebase Auth 사용 시)	Firebase 콘솔에서 SHA 키 등록
📅 개발 일정 (6~8주 기준)
주차	해야 할 일
Week 1~2	프로젝트 기획 + UI 디자인 (Figma) + 환경 세팅 (Expo, Firebase)
Week 3~4	방 꾸미기 기능 개발 + 사용자 프로필 관리 (Firestore 연동)
Week 5~6	일정 공유 기능 + 캘린더 구현 + RSVP 기능 추가
Week 7	푸시 알림 기능 추가 + 성능 최적화
Week 8	APK 빌드 + 최종 테스트 + 배포
🔥 최종 정리 (무료 도구만 사용)
✅ 앱 개발

React Native + Expo (무료) → 크로스 플랫폼 개발
Firebase (무료 한도 내 사용) → 데이터 저장, 로그인, 푸시 알림
✅ 디자인 & 관리

Figma (무료 플랜) → UI 디자인
GitHub (무료 프라이빗 저장소) → 코드 관리
✅ APK 배포 (무료)

Expo EAS Build (무료 플랜 사용 가능)
APK 파일 직접 배포 (Google Drive, GitHub 등)
👉 최종 결론: APK 배포 + 무료 개발 환경 OK!
✅ 모든 개발 도구 무료 사용 가능
✅ Firebase 무료 한도 내에서 유지 가능 (추후 확장 가능)
✅ Google Play 없이 APK 직접 배포 가능
