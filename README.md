### 개발 세팅 동일
### 디버거 설치 단축키
- ctrl + shift + D

#### firebase 설치 준비
- 시스템 당 첫번째 작업은 글로벌로 설치해야 한다.
- 구글 아이디 필요
### 본격적인 설치
`npm install -g firebase-tools`
- 글로벌 설치이므로 프로젝트 패키지와 관련 없다.
- 설치하면, `firebase` 라는 명령어를 사용할 수 있다.

`firebase --help`
`firebase --version`
위와 같은 간단한 조회 명령으로 정상적으로 명령이 되는지 확인

### 로그인
- cli이긴 하지만, 엄연히 계정 권한이 필요하니 로그인을 권장한다.

### 구글 계정 승인 처리
- 사용량과 오류보고 정보 수집 허용
- 엑세스 허용
- 이메일로 확인 문구 응답 확인

### 유지보수를 위해 프로젝트 디렉토리를 하위로 하나 만든다.
- 예제는 app이라는 디렉토리, 하위로 public 으로 구성
- 최초의 테스트이므로 index.html /public 에 h1태그만 작성함

### firebase 서비스에서 프로젝트 제작하기
- https://firebase.google.com/?hl=ko
- 프로젝트 시작하기 버튼을 통해 진입하면 "프로젝트 추가"를 버튼을 확인 할 수 있다.
- 임의의 프로젝트를 생성한다.
- 예제의 경우 firebase-practics라는 이름으로 작명했다.

### firebase 설치 시작
`firebase init` 명령을 진행하면, 몇가지 질문요청이 발생한다.
발생하지 않았다면, 다시 돌아가 로그인 관련 처리가 정상적으로 진행되었는지 확인한다.
질문의 내용은 다음과 같다.

? Are you ready to proceed? (Y/n) 
- 진행할 준비 됐니?
- Y 입력

( ) Realtime Database: Configure a security rules file for Realtime Database and (optionally) provision default instance    
 ( ) Firestore: Configure security rules and indexes files for Firestore
 ( ) Functions: Configure a Cloud Functions directory and its files
> (*) Hosting: Configure files for Firebase Hosting and (optionally) set up GitHub Action deploys
 ( ) Hosting: Set up GitHub Action deploys
 ( ) Storage: Configure a security rules file for Cloud Storage
 ( ) Emulators: Set up local emulators for Firebase products

 위와 같은 다양한 옵션 선택지를 보내주는데 여기에서 Hosting 부분중 첫번째를 선택한다.
 ( ) Hosting: Configure files for Firebase Hosting and (optionally) set up GitHub Action deploys
 - 스페이스바를 눌러 선택하고 엔터를 눌러 진행한다.
 - github를 통해 진행할 것인지를 물어보는 것으로 "Action" 이라는 github 배포서비스를 말하며 보통의 경우 github의 저장소를 firebase를 통해 서비스하고자 할때 사용하는 것으로 *optionally* 직접 처리하기 위해 깃허브 액션 기능을 사용하지 않아도 되는 항목을 선택한다.(추후에는 필요한 만큼 선택)

  > Use an existing project
  Create a new project
  Add Firebase to an existing Google Cloud Platform project
  Don't set up a default project

 - 웹 앱(firebase 사이트)에서 프로젝트를 생성했으므로, Use an existing project를 선택한다.
 - 정상적인 경우 프로젝트(내가 작명한)가 선택지로 나타난다.

 정상적으로 선택된다면 '기본 설정(configuration)' 작업이 진행된다.

### 호스팅을 위한 몇가지 설정

? What do you want to use as your public directory? *public*(이미 public 디렉토리를 만들었으으므로)
? Configure as a single-page app (rewrite all urls to /index.html)? *No*(이미 index.html을 만들었으므로)
? Set up automatic builds and deploys with GitHub? *No* (현재 연습은 github 연결 하지 않을 것이므로)
+  Wrote public/404.html
? File public/index.html already exists. Overwrite? *Yes*(초기 화면을 덮어써서 최초설정을 할 것이므로)
+  Wrote public/index.html

i  Writing configuration info to firebase.json...
i  Writing project information to .firebaserc...
i  Writing gitignore file to .gitignore...

+  Firebase initialization complete!

### 12. 로컬 테스트
`firebase serve`
- firebase 기본 서버 포트는 5000번 이므로 live server 확장플러그인이 활성화되어있으면 충돌이 일어날 수 있다.
- CLI에 간편하게 localhost 주소값을 확인 할 수 있다.
