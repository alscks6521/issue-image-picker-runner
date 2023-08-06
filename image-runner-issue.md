2023년 8월 6일
코드에서 참조할 것(referenced in code)

문제발생 : fluuter - image_picker 패키지를 이용해 ios 시뮬레이터로 앱 테스트 중에 일어난 
        "Runner 응용 프로그램이 예기치 않게 종료되었습니다" 문구에러.

원인 : ios 앱 접근 권한. 즉 "카메라 접근 권한 설정"을 안했기 때문.

해결방법 : ios에 대한 Info.plist 파일에 특정 명령어를 추가해주어야함.

        1. ios/Runner/Info.plist 파일 이동

        2. 해당 구역안에 명령어 추가.
        ...
        <dict>
                <!-- 추가해야 될 명령어들 -->

                <key>NSCameraUsageDescription</key>
                <string>Used to demonstrate image picker plugin</string>
                <key>NSMicrophoneUsageDescription</key>
                <string>Used to capture audio for image picker plugin</string>
                <key>NSPhotoLibraryUsageDescription</key>
                <string>Used to demonstrate image picker plugin</string>

                ...
        </dict>
        ...

참고 사이트 : https://www.inflearn.com/questions/308883/%EC%9D%B4%EB%AF%B8%EC%A7%80-%EC%B6%94%EA%B0%80-%EB%B2%84%ED%8A%BC-%EB%88%84%EB%A5%BC-%EC%8B%9C-%EC%95%B1%EC%9D%B4-%ED%8C%85%EA%B9%81%EB%8B%88%EB%8B%A4





