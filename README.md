# React-Router

### SPA

1. 라우팅 : 어떤 "주소"에 어떤 "UI"를 보여줄지
   - 옛날에는 보통 서버에서 관리(SSR)하는 로직 이제는 클라이언트가 관리(CSR)한다.
2. non-SPA
   - Client <->(html) 서버 <-> DB
   - 새로운 데이터를 요청 할 때마다 화면 정보를 다시 받아와야 한다.
   - 불필요한 트레픽 발생.
3. SPA
   - re-render <->(json) server
4. 장점
   - 서버쪽에서 자원을 아낄 수 있다.
   - 클라이언트에서는 사용자가 좋은 사용자 경험을 얻을 수 있다.
5. 앱의 규모가 커지면 코드스플릿팅을 사용한다.
6. 서버사이드 렌더링 사용하여 검색엔진 크롤링.

### 리액트 라우팅

1. 컴포넌드 단위의 라우팅을 한다.

### 넥스트

1. 파일 경로, 이름을 기반으로 라우팅을 함.

### BrowserRouter

1. HTML5 History API 사용
   - 주소만 바꾸고 페이지는 다시 불러오진 않음

### HashRouter

1. example.com/#/path
   - #를 사용함. 못생김, 옛날 브라우저 전용

### MemoryRouter

1. 브라우저의 주소와 무관함, 일체 건들이지 않음
   - 임베디드 웹앱, 리액트 네이티브 등에서 사용

### StaticRouter

1. 서버사이드 렌더링에서 사용하는 용도.

### Route

- <Route path="/login" component={Login} />

1. 라우트를 정의할 때 사용하는 컴포넌트

### Link

- to="/path"

1. 사용한 Router의 주소를 바꿈 a 태그지만 새로고침 안됨

### URL Parameter

- /profiles/gi

### Query

- npm install qs
- 쿼리를 파싱해주는 라이브러리를 사용할 수 있다.

### 서브라우트 만들기.
