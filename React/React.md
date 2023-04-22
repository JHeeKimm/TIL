> React

- facebook에서 만든 javascript UI library
- 컴포넌트 기능:
  - 가독성
  - 재사용성
  - 유지보수
- npm : node.js로 만들어진 프로그램을 쉽게 설치할 수 있게 만들어주는 일종의 앱스토어
- React 설치 방법
  - (sudo) npm install -g create-react-app : npm은 프로그램을 설치하는 프로그램
  - npx create-react-app : npx는 create-react-app이라는 것을 인치로 설정해서 딱 한번만 실행시키고 지우는 것.(매번 설치하니 최신버전을 사용할 수 있겠지)
- 배포
  - npm run build : 불필요한걸 지운 빌드 디렉토리 생성.
  - npm install -g serve : serve라는 명령어를 통해서 어디에서나 웹서버를 설치할 수 있음
  - npx serve -s build : 한번만 실행시킬 웹서버를 다운받아서 실행시킬 때, 빌드 디렉토리를 다큐먼트 루트로 하겠다.
