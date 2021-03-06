# FaceTimeCallerInfo
Apple scripts to show the notification of the caller information  on your Mac when your Mac shows FaceTime call notification.

Mac에서 FaceTime 전화 알림이 뜨면 발신자의 정보를 Mac에서 알림으로 보여줍니다. 

## 요구 사항
* FaceTime이 지원되는 Mac
* iPhone의 전화 수신시 발신자 정보를 확인하려면 연속성 기능으로 연결된 Mac과 iPhone 필요 ([https://support.apple.com/ko-kr/HT204681])

## 설치 방법
1. FaceTimeCallerInfo.applescript를 “Script Editor”로 연다.
2. “File-\>Export” 에서 File Format을 “Application”으로 선택하고, 저장 장소는 ​/Applications로 저장.
3. System Preferences를 실행. Security & Privacy -\> Privacy -\> Accessibility에 /Applications/FaceTimeCallerInfo.app을 추가.

## Dock에 아이콘 안보이게 하기
1. 앱을 실행하면 Dock에 아이콘이 뜨는데, 안뜨게 하려면 /Applications/FaceTimeCallerInfo.app을 오른쪽 클릭 -\> Show Package Contents 클릭 -\> Contents로 이동 -\> Info.plist 파일 수정해야 함.
2. XCode가 설치되어 있는 경우: Info.plist 파일을 더블 클릭 -\> 오른쪽 클릭 -\> Add Row 메뉴 클릭 -\> Key에 NSUIElement 입력, Type을 Number로, Value를 1로 입력 후 저장
3. XCode가 설치되어 있지 않은 경우: Info.plist를 Emacs나 VI 혹은 기타 Text Editor로 열어 아래와 같은 제일 마지막 두 줄 앞에 아래와 같이 추가

\</dict\>
\</plist\>

위의 두 줄 앞에 아래 두 줄 추가

\<key\>NSUIElement\</key\>
\<integer\>1\</integer\>

## App 종료하기
1. 위의 아이콘 안보이게 하기를 적용하지 않은 경우: Option-Command-ESC를 눌러 FaceTimeCallerInfo.app을 강제로 종료.
2. 위의 아이콘 안보이게 하기를 적용한 경우: Activity Monitory를 실행하여 FaceTimeCallerInfo.app을 강제로 종료.