# 🗺️ ToUs - AI 여행 계획 자동제작 플랫폼 

**카카오 지도 API**와 **OpenAI API**를 활용해  
여행 일정을 자동으로 생성하고,  
출발지~목적지 경로를 지도에 시각화하는 웹 서비스입니다.

회원가입, 로그인, 마이페이지, SNS 로그인, 사이드바 등  
실제 서비스에 가까운 다양한 부가 기능도 포함되어 있습니다.

---

## 📦 폴더 구조 및 역할

```
/
├── main/           # 메인페이지(탭, 지도, 일정, UI 등 핵심 로직)
├── sign_up/        # 회원가입(폼, 스타일, 이미지)
├── login/          # 로그인/로그아웃, SNS(카카오 등) 로그인, 이미지
├── findAccount/    # 아이디/비밀번호 찾기
├── sidebar/        # 사이드바 UI, 아이콘 이미지
├── mypage/         # 마이페이지(개인정보, 모달, 이미지)
├── header/         # 상단 헤더(네비게이션)
├── map/            # 지도/경로 로직, 카카오맵 연동
├── images/         # 지역별/공통 이미지 리소스
├── *.json          # 장소, 지역, 리스트 등 데이터
├── index.html      # 프로젝트 진입점(홈)
├── scripts.js      # 일정 생성(Gemini/OpenAI API 연동)
├── styles.css      # 공통 스타일
└── README.md       # 프로젝트 설명서
```

---

## 🧩 주요 기능

### 1. 여행 일정 자동 생성 (AI 활용)
- 선택한 장소, 날짜를 바탕으로 OpenAI API로 여행 일정을 자동 생성
- 생성된 일정은 JSON 및 텍스트로 확인 가능

### 2. 지도 기반 경로 안내
- 카카오 지도 API로 출발지/목적지 검색 및 마커 표시
- 두 지점 간 경로(선) 시각화
- 좌표, 거리 자동 계산/표시

### 3. 회원 관리
- 회원가입, 로그인/로그아웃, 마이페이지(개인정보 확인/수정)
- 아이디/비밀번호 찾기
- SNS(카카오, 네이버, 구글, 애플) 로그인 지원

### 4. UI/UX
- 탭 기반 메인 UI(날짜, 지역, 장소, 일정, 편집 등)
- 사이드바, 헤더, 모달 등 다양한 UI 컴포넌트
- 반응형 CSS, 이미지 리소스 활용

---

## 🚀 실행 방법

1. **카카오 지도 API 키 발급**
   - [카카오 개발자](https://developers.kakao.com/)에서 JavaScript용 지도 API 키를 발급
   - `map/kakaomap.html` 등에서 API 키를 입력

2. **OpenAI API 키 발급**
   - `scripts.js`의 `OPENAI_API_KEY`에 본인 키 입력 (보안 주의)

3. **프로젝트 파일 다운로드**
   - 이 저장소를 로컬에 클론하거나 압축 해제

4. **main.html 실행**
   - `main.html`을 VSCode의 Live Server 등으로 실행
   - (주의) 로컬환경에서 실행 시, api 접근 거부될 수 있음

5. **회원가입/로그인 후 다양한 기능 체험**
   - SNS 로그인, 마이페이지, 일정 생성, 지도 경로 등 직접 사용해보기

---

## 🗂️ 폴더별 주요 파일 설명

- **main/**  
  메인페이지 UI/로직, 탭 전환, 지도/일정/장소/캘린더 등 핵심 기능 구현  
  (예: `MainPage.js`, `MainPage.html`, `MainPage.css`)

- **sign_up/**  
  회원가입 폼, 스타일, 로고 이미지 등  
  (예: `sign_up.html`, `sign_up.js`, `sign_up_style.css`)

- **login/**  
  로그인/로그아웃, SNS 로그인(카카오, 네이버, 구글, 애플), 관련 이미지  
  (예: `login.html`, `login.js`, `sns_login/kakaoTalkLogin.js`)

- **findAccount/**  
  아이디/비밀번호 찾기 폼 및 로직  
  (예: `findId.html`, `findPassword.html`, `findId.js`)

- **sidebar/**  
  사이드바 UI, 메뉴/마이페이지/로그아웃 등 아이콘 이미지  
  (예: `sidebar.html`, `sidebar.css`, `sidebar_img/`)

- **mypage/**  
  마이페이지(개인정보, 모달, 증명사진 등)  
  (예: `mypage.html`, `mypage.js`, `mypage_img/`)

- **header/**  
  상단 헤더(네비게이션)  
  (예: `header.html`, `header.js`)

- **map/**  
  지도/경로 로직, 카카오맵 연동  
  (예: `kakaomap.html`, `logics.js`)

- **images/**  
  지역별/공통 이미지 리소스  
  (예: `seoul.jpg`, `busan.jpg`, `all.png` 등)

- **.json 파일들**  
  장소, 지역, 리스트 등 데이터 관리  
  (예: `listEx.json`, `areaCode.json`, `place.json`)

---

## 🛠️ 개발 환경 및 요구 사항

- **필수**
  - 인터넷 연결(카카오 지도, OpenAI API 사용)
  - 최신 웹 브라우저(Chrome, Edge, Safari 등)

- **추천**
  - VSCode + Live Server 확장
  - 카카오 API 키, OpenAI API 키 발급 및 도메인 등록(`localhost` 허용)

---

## ⚠️ 주의 사항

- **API 키 보안**  
  API 키는 외부에 노출되지 않도록 주의하세요.  
  (테스트 시에는 `localhost` 도메인 등록 필요)

- **데이터 파일**  
  `*.json` 파일은 장소/지역/리스트 등 데이터 관리용입니다.  
  직접 수정 시 JSON 포맷을 꼭 지켜주세요.

- **이미지 리소스**  
  각 폴더별로 필요한 이미지가 분리되어 있습니다.  
  (예: 지역별 지도 이미지, SNS/로고 이미지 등)

---

## 💡 개발 팁

- 각 폴더별로 HTML, CSS, JS가 분리되어 있어 유지보수가 쉽습니다.
- 기능별로 파일이 나뉘어 있으니, 원하는 기능을 빠르게 찾을 수 있습니다.
- 초보자라면, `index.html` → `main/` → `map/` 순서로 코드를 읽어보는 걸 추천합니다.
- SNS 로그인, 일정 생성 등은 실제 API 키가 필요하니, 테스트 시 주의하세요.

---

## 🙋‍♂️ 문의/기여

- 궁금한 점이나 버그 제보는 이슈로 남겨주세요!
- 코드 개선/기여도 언제든 환영합니다.
