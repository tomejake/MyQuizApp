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

## 스크롤
- 전체 객체들을 ScrollView 로 감싸고, viewport 가 전부 보이도록 android:fillViewport="true" 옵션을 준다.

### tools:text="": 실행시 텍스트는 안보이지만 툴에서만 보임

### android:contentDescription : 이미지가 안보일 경우 사용자 편의를 위해 어떤 이미지인지 설명을 작성하는 옵션

### 높이나 너비를 0으로 지정한 경우: 가중치를 사용한다는 뜻

## ProgressBar
- 진행도를 나타내는 Bar
- 가중치로 디자인하면 쉽게 디자인 가능
- android:progress="0"에서 현재 진행도를 나타냄
- android:max="9" : max 값 지정 가능 (0~9까지로 지정하겠다는 의미)
- style 로 디자인 변경 가능
    - 예시: style="?android:attr/progressBarStyleHorizontal"
- android:indeterminate="false": 진행바가 움직이지 않도록 고정시켜줌
    - 다운로드 화면같은 경우는 고정시키지 않는게 좋음

## 이미지 불러오기
- ivImage?.setImageResource(Object.image)
    - setImageResource 를 활용, 비트맵이나 다른 방법도 존재함

### Typeface
- 표시되는 문자 모양의 기울임꼴 스타일을 시뮬레이션할지 여부를 확인

### ContextCompat
- Resource 에서 값을 가져오거나 퍼미션을 확인할 때 사용할 때 SDK 버전을 고려하지 않아도 되도록 (내부적으로 SDK 버전을 처리해둔) 클래스
``` kotlin
    background = ContextCompat.getDrawable(
            this,
            R.drawable.default_option_border_bg
        )
```
- 위와같은 느낌으로 사용

### 간편한 onClickListener
- onClickListener 를 상속받고 구현
- 이벤트가 존재하는 아이템만 onClickListener(this) 라고 지정해줌