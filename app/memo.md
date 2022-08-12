## 상단 상태바 지우기
- values/themes
    - <item name="android:windowFullscreen">true</item>

## manifets/AndroidManifest.xml
- 앱을 실행했을때 어떤 액티비티를 보여줄지 등 설정 가능
    - android:theme="@style/Theme.MaterialComponents.DayNight.NoActionBar">
        - 기본값으로 뜨던 액션바 제거
        - 또는 themes.xml parent 에서 직접 설정가능 (직접 설정을 수정 가능해서 더 좋은 방법임)
    - <activity android:screenOrientation="portrait">
        - 세로 화면으로 고정

### CardView
- 간편하게 컨테이너 스타일 레이아웃을 도와줌
- app:cardCornerRadius: 카드의 모서리 둥글기 조절

### 입력창 만들기
- TextInputLayout
    - 입력을 위한 레이아웃
        - AppCompatEditText
            - TextInputLayout 속에 만들어 Text 입력 가능하도록 도와줌
                - android:hint="Name"
                    - 사용자가 어떤 내용을 입력하면 좋을지 힌트를줌
                - android:inputType="textCapWords"
                    - inputType 은 사용자가 입력할 내용을 제한시키고, textCapWords 는 글자수 제한을 줌

### style="@style/Widget.MaterialComponents.TextInputLayout.OutlinedBox"
- OutlinedBox: 윤곽이 있는 직사각형으로 디자인 변경


### 페이지 이동
1. 새로운 activity 만듬
2. val intent = Intent(this, 이동할 엑티비티::class.java)
   startActivity(intent)
    - 위와 같은 형태로 작성해 intent 를 활용해서 페이지를 이동

## 코드 테스트 (locket)
- Log 객체를 활용해 테스트 코드를 작성하고, 하단 Logcat 을 통해 메시지를 볼 수 있다.