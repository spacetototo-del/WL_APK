# 역도 세트 타이머 (WL_APK)

갤럭시 탭 가로 화면을 반으로 나눠, 왼쪽에 오늘 역도 프로그램, 오른쪽에 다음 세트와 시작까지 남은 시간을 크게 보여주는 개인용 안드로이드 앱입니다. 오프라인으로 동작하며 프로그램은 JSON 파일에서 읽습니다.

- 구현: Java 최소 Activity + WebView(`app/src/main/assets/index.html`)
- 프로그램: `app/src/main/assets/program.json` (앱 안의 "파일" 버튼으로 다른 JSON 가져오기 가능)
- 계획서: `apk_plan_lift_timer.md`

## 빌드
JDK 17, Android SDK(platform 34, build-tools 34), Gradle 8.7 이상 필요.

    gradle assembleDebug

결과물: `app/build/outputs/apk/debug/app-debug.apk` (디버그 서명, 개인용)

## 설치
APK를 태블릿으로 옮겨 "알 수 없는 앱 설치"를 허용하고 설치하거나, `adb install app-debug.apk`.

## 리허설(가상 시각)
    adb shell am start -n com.yongsun.lifttimer/.MainActivity --es t 07:29:50 --es speed 10
