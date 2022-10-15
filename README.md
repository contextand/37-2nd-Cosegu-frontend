# 코세구, 프로젝트 개요

- 개발자들을 위한 채용 사이트
- Work-Flow : 소셜로그인 -> 채용정보 확인 -> QnA -> 찜하기 -> 지원하기 || 크루 지원하기
- 개발은 초기 세팅부터 전부 직접 구현했으며, 아래 데모 영상에서 보이는 부분은 모두 백앤드와 연결하여 실제 사용할 수 있는 서비스 수준으로 개발한 것입니다.

### 개발 인원 및 기간

- 개발기간 : 2022/10/04 ~ 2022/10/14
- 개발 인원 : 프론트엔드 3명, 백엔드 2명
- [백엔드 github 링크](https://github.com/wecode-bootcamp-korea/37-2nd-Cosegu-backend)

### **적용 기술**

- Front-End : React.js, Styled-Components, Naver-API
- Back-End : My SQL, Bcrypt, Node.js
- Common :  RESTful API, Git, Github, Trello, Slack

### 프로젝트 시연 영상

[코세구 시연영상](https://youtu.be/6lNsXWvzYf4) 

<br>

# 구현 페이지 및 기능 소개

## 구현 목표 (내가 작업한 페이지)

- [x] Nav, Footer
- [x] 회원가입/로그인 (소셜로그인으로 통합)
- [x] 메인
- [ ] 지원하기 (공고 리스트, 지원서 작성하기)
- [ ] 짬한 목록
- [ ] 크루지원하기
- [ ] 자주 묻는 질문, 1:1 문의
- [x] 마이페이지


## 구현 사항 설명

### 소셜로그인

- 네이버 로그인 API 를 사용해 소셜 로그인을 적용했습니다.
- 프론트에서 토큰까지 받으면 보안상 문제가 되므로, 인가코드만 받아서 백엔드에 전송한 후 백엔드에서 새로운 토큰을 발급 받았습니다.
- Client ID, Redirect URI 등 보안상 노출되면 안되는 정보는 .env 파일에 환경변수로 저장하고 .gitignore 파일에 추가해 깃허브에 노출되지 않게 했습니다.
- 백엔드와 통신하며 각종 에러를 체험했습니다. (Redirect URI 를 백엔드 ip 로 세팅하거나, 중복된 코드를 보내거나..)

### 메인, Nav, Footer

- react-slick 라이브러리를 사용해 캐러셀을 구현했습니다.
- 스크롤 이벤트 값을 가져와 특정 위치에서 플로팅 버튼을 구현했습니다.
- 그리드를 사용해 사진 레이아웃을 표현했습니다.
- 로그인 후 토큰 여부에 따라 상단 Nav의 아이콘 및 경로를 수정했습니다. (로그아웃 생성 및 마이파에지 경로 업데이트)
- Footer 에서 외부사이트을 누르면 드롭다운 메뉴가 위로 보이게 구현했습니다.

### 마이페이지

- 로그인 후 유저정보를 받아와 props 사용해 각 컴포넌트에 전달해 화면을 구성했습니다.
- 각 항목들을 최대한 컴포넌트로 분리해 관리 했습니다.
- 지원서 보기 모달은 바깥 영역이 스크롤되지 않도록 고정하는 useLockBodyScroll 커스텀 훅을 가져와 사용했습니다.

<br>

# 관련 블로그 포스팅

## 프로젝트를 진행하며 정리한 내용을 블로그에 포스팅했습니다.

- [카카오톡 소셜로그인 인가 코드 받기](https://velog.io/@rayong/%EC%B9%B4%EC%B9%B4%EC%98%A4%ED%86%A1-%EC%86%8C%EC%85%9C%EB%A1%9C%EA%B7%B8%EC%9D%B8-%EC%9D%B8%EA%B0%80-%EC%BD%94%EB%93%9C-%EB%B0%9B%EA%B8%B0)
- [깃 캐쉬 삭제, Git Cache](https://velog.io/@rayong/%EA%B9%83-%EC%BA%90%EC%89%AC-%EC%82%AD%EC%A0%9C-Git-Cache)
- [리액트 슬릭 캐러셀, 슬라이더, react-slick](https://velog.io/@rayong/%EB%A6%AC%EC%95%A1%ED%8A%B8-%EC%8A%AC%EB%A6%AD-%EC%BA%90%EB%9F%AC%EC%85%80-%EC%8A%AC%EB%9D%BC%EC%9D%B4%EB%8D%94-react-slick)
- [네이버 소셜로그인, 프론트엔드, 리액트](https://velog.io/@rayong/%EB%84%A4%EC%9D%B4%EB%B2%84-%EC%86%8C%EC%85%9C%EB%A1%9C%EA%B7%B8%EC%9D%B8-%ED%94%84%EB%A1%A0%ED%8A%B8%EC%97%94%EB%93%9C-%EB%A6%AC%EC%95%A1%ED%8A%B8)
- [리액트 config.js 파일로 API 관리하기](https://velog.io/@rayong/%EB%A6%AC%EC%95%A1%ED%8A%B8-config.js-%ED%8C%8C%EC%9D%BC%EB%A1%9C-API-%EA%B4%80%EB%A6%AC%ED%95%98%EA%B8%B0)
- [스타일드 컴포넌트, S 객체로 묶어서 관리하기](https://velog.io/@rayong/%EC%8A%A4%ED%83%80%EC%9D%BC%EB%93%9C-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8-S-%EA%B0%9D%EC%B2%B4%EB%A1%9C-%EB%AC%B6%EC%96%B4%EC%84%9C-%EA%B4%80%EB%A6%AC%ED%95%98%EA%B8%B0)
- [리액트, 스크롤 값에 따라 플로팅 버튼 띄우기](https://velog.io/@rayong/%EB%A6%AC%EC%95%A1%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A1%A4-%EA%B0%92%EC%97%90-%EB%94%B0%EB%9D%BC-%ED%94%8C%EB%A1%9C%ED%8C%85-%EB%B2%84%ED%8A%BC-%EB%9D%84%EC%9A%B0%EA%B8%B0)

## **Reference**

- 이 프로젝트는 [우아한청년들 인재영입](https://career.woowayouths.com/) 사이트를 참조하여 학습목적으로 만들었습니다.
- 실무수준의 프로젝트이지만 학습용으로 만들었기 때문에 이 코드를 활용하여 이득을 취하거나 무단 배포할 경우 법적으로 문제될 수 있습니다.
- 이 프로젝트에서 사용하고 있는 사진 대부분은 위코드에서 구매한 것이므로 해당 프로젝트 외부인이 사용할 수 없습니다.
