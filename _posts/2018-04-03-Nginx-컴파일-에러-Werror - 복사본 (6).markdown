nginx를 소스설치 하는 과정에서 컴파일 후, make를 실행시키면 다음과 같은 에러가 종종 발생한다.

`error: macro "__TIME__" might prevent reproducible builds [-Werror=date-time]`

하지만 이것은 make 컴파일 관련 오류이며, 크게 신경쓸 필요가 없다. 컴파일 옵션을 하나 추가하기만 하면 된다.

`-Wno-error=date-time`

다시 설치를 수행하면 정상적으로 수행되는 것을 확인할 수 있다.