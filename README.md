# kendo-line-bot

## 라인봇을 만드는 순서
### 라인@ 계정 만들기
1. [라인 비즈니스센터](https://business.line.me/ko/)에 들어가기
2. [Messagin API](https://business.line.me/ko/services/bot)  선택하기
3. Developer Trial 시작하기를 누르고 모달팝업에서 오른쪽의 "업체선택" 버튼 누르기
4. 등록된 업체를 선택하거나 새로운 업체를 만든다.
5. 업체에 속한 새로운 계정을 생성한다. (사진, 이름, 업종입력)

### 라인@ 계정에서 Bot 기능 활성화
1. [LINE@ MANAGER](https://admin-official.line.me/)  페이지에 들어가 방금만든 계정을 선택한다.
2. 계정설정 -> Bot 설정에서 "API 켜기" 를 선택한다.
3. Webhook 사용을 **허용**으로 설정, 그룹 대화 참여 허용을 **허용**으로 설정한다. 

### Heroku 에 WebHook 용 계정생성
1. [heroku](https://dashboard.heroku.com/) 에 로그인 해서 Create new app 을 선택한다.
2. 앱 이름을 입력하고 생성한다.
3. deploy mehtod 를 github 를 선택한다.
4. Connect to GitHub 에서 WebHook 어플리케이션을 개발할 깃허브 저장소를 선택하여 연결시킨다.
5. Automatic deploys 를 활성화 시킨다.
6. setting 에서 Builspacks 항목의 값을 heroku/python 을 선택한다.
7. Resources 에서 web dynos 의 스위치를 켠다.

### 깃에 echo 예제를 가져오기
1. [line/line-bot-sdk-python] 에서 example/flask-echo 를 가져온다.
2. `web: python app.py` 라고 적힌 Procfile 을 만든다.
3. 커밋 후 푸시한다 (master에)

### WebHook 연결 설정
1. [LINE@ MANAGER](https://admin-official.line.me/)  페이지에 들어가 방금만든 계
정을 선택한다.
2. 계정설정 -> Bot 설정에 들어간다.
3. 상태 항목의 `LINE Developers` 아웃링크를 클릭한다.
4. Webhook URL 항목에 `{heroku 의 domain}/callback` 이라고 주소를 적는다.
5. Bot 설정의 Channel Secret 과 Channel Access Token 을 heroku app 의 setting -> Config Variables 에서 `LINE_CHANNEL_ACCESS_TOKEN`, `LINE_CHANNEL_SECRET` 라는 환경변수 키에 저장한다.
6. Webhook URL 항목의 verify 버튼을 눌러 성공하면 연동이 완료된 것이다.


 


