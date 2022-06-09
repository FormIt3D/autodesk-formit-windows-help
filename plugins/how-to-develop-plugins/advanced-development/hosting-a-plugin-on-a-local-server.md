# 로컬 서버에서 플러그인 호스팅

FormIt에서 복제된 플러그인을 미리 보려면 로컬 서버에서 해당 플러그인을 호스팅해야 합니다.

### **IDE에서 터미널 보기**

별도의 터미널 창 대신 Visual Studio Code 내에서 서버를 시작할 수 있습니다. \*\*\*\* 터미널을 열기 전에 Visual Studio Code에서 올바른 폴더가 열려 있는지 확인하십시오.

뷰 > 터미널(또는 바로 가기 Ctrl + \`)

![](<../../../.gitbook/assets/image (11).png>)

### HTTP 서버 설정

제대로 작동하는 HTTP 서버는 npm의 [http-server](https://www.npmjs.com/package/http-server)입니다.

[NodeJS](https://nodejs.org/ko/)가 아직 설치되어 있지 않은 경우, 먼저 NodeJS를 다운로드하여 설치해야 합니다.

다음 단계에서 오류가 발생하면 컴퓨터를 다시 시작하여 NodeJS 설치를 완료해 봅니다.

명령 프롬프트에서 다음을 입력하여 npm의 _http-server_를 전역으로 설치합니다(일회성 설정).

* `npm install http-server -g`

![](<../../../.gitbook/assets/image (47).png>)

### 로컬 서버 시작

설정이 완료되면 터미널에서 다음 명령을 실행하여 npm http-server를 시작합니다.

* `http-server`

![](<../../../.gitbook/assets/image (84).png>)

팁 1: 전역 또는 로컬로 설치된 http-server를 실행하는 데 문제가 있는 경우 npx를 통해 직접 실행하는 것이 도움이 될 수 있습니다.

* `npx http-server`

팁 2: Windows 10/11 사용자의 경우 새 컴퓨터에서 스크립트를 실행할 때 오류가 발생하면 설정이 비활성화되어 있기 때문일 수 있습니다. 이 문제를 해결하려면 다음을 수행합니다.

* PowerShell 스크립트를 관리자 권한으로 시작합니다.
* 다음과 같이 입력합니다. `Set-ExecutionPolicy RemoteSigned`

### FormIt 웹용 개발

FormIt 웹용으로 개발하려면 다음 명령을 대신 실행하면 됩니다.

* `http-server --cors`

![](<../../../.gitbook/assets/image (10).png>)

### 서버 확인

웹 브라우저에서 다음 주소로 이동하여 서버를 확인할 수 있습니다.

* http://localhost:8080

브라우저 창에 프로젝트 폴더 파일이 표시됩니다.

\*\*npm이 아닌 다른 웹 서버를 사용하는 경우 기본 주소/포트가 다를 수 있습니다.

![](<../../../.gitbook/assets/image (41).png>)
