nginx를 소스설치 하는 과정에서 컴파일 후, make를 실행시키면 다음과 같은 에러가 종종 발생한다.

`error: macro "__TIME__" might prevent reproducible builds [-Werror=date-time]`

make가 경고를 오류로 착각하여 빌드를 실패하게 만드는 경우이므로 크게 신경쓸 필요가 없다. -Werror=date-time 옵션을 지우거나 컴파일 옵션을 하나 추가하기만 하면 된다.

`Werror=date-time 지우기 또는 -Wno-error=date-time 추가`

다시 설치를 수행하면 정상적으로 수행되는 것을 확인할 수 있다.