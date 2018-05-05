#Ubuntu 의존성 패키지 문제 post-installation error code 1

오늘은 간단한 오류 픽스를 하나 기록하려고 합니다. 매우 간단하지만, 생각보다 삽질을 하는 경우를 많이 봤기 때문에 기록하려고 합니다.
<br>
저번에 이어서 설명을 해보자면, nginx 소스 설치 중간에 패키지 문제가 생겨서 다른 apt 패키지 설치를 진행할 때 다음과 같은 오류가 발생했다고 가정해보자.
`설치한 post-installation 스크립트 하위 프로세스가 오류 1번을 리턴했습니다:`
`nginx-full`<br>

보통 패키지 오류는 일명 '찌꺼기 파일'이 남아있거나, 패키지가 망가지는 경우에 종종 발생하므로 패키지 셋팅을 올바르게 잡을 필요가 있다.

`apt -f install`<br>
`dpkg-reconfigure nginx-full`<br>
`dpkg -l | grep nginx* -> 나오는 파일 전부 제거(apt remove --purge)`<br>

<br>세팅 후, 패키지가 올바르게 작동하는 것을 볼 수 있다.<br>
`apt install nginx-full`