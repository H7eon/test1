# top 
## ps 
### jobs 
#### kill 
#####  매크로(q,@) 


# 1. top
*top*

top 명령어는 리눅스 시스템이 실행되고 난 후 부터 지금까지의**시간과 시스템에 로그인된 사용자수** 그리고 시스템 부하율을 표시하는 명령어인 uptime의 결과를 가장 상단에 표시해주며, 그 아래로 **프로세스 수치, CPU 정보, 메모리 정보**를 보여주고, 각 프로세스 별 **부하율과 상태**를 표시해줍니다.

## top 실행 후 명령어 옵션
|실행 후 명령어 옵션||
|---|---|
|-shift+p|CPU 사용률 내림차순|
|-shift+m|메모리 사용률 내림차순|
|-shift+t|프로세스가 돌아가고 있는 시간 순|
|-k|kill.k입력 후 PID 번호 작성. signal은 9|
|-f|sort field 선택 화면 -> q 누르면 RES순으로 정렬|
|-a|메모리 사용량에 따라 정렬|
|-b|Batch 모드로 작동|
|-1|CPU Core 별로 사용량을 보여줌|
|space bar|Refresh|
|-u|입력한 유저 소유의 Process만 표시|

## top 실행 전 명령어 옵션
|실행 전 명령어 옵션||
|---|---|
|-b|배치모드 옵션|
|-n|top 실행 주기를 설정|
|-p|process ID| 

### VIRT, RES, SHR
|||
|---|---|
|VIRT|프로세스가 사용하고 있는 virtual memory의 전체 용량, 프로세스에 할당된 가상 메모리 전체, SWAP + RES|
|RES|현재 프로세스가 사용하고 있는 물리 메모리의 양, 실제로 메모리에 올려서 사용하고 있는 물리 메모리|
|SHR|다른 프로세스와 공유하고 있는 shared memory의 양|

*top 와 ps의 차이점*

top은 **proc에서 일정 주기로 합산**해서 cpu 사용율을 출력한다.

# 2. ps
*ps*

**프로세스의 현재 상태를 보여주는 명령어이다.**

## 프로세스와 관련된 명령어 옵션
|명령어 옵션||
|---|---|
|-N|-A 옵션과 비슷하나, ps 명령을 위해 실행한 ps 프로세스만 제외하여 보여준다. (실행을 취소한다)|
|-a|세션 리더 및 터미널과 관련되지 않은 프로세스를 제외한 모든 프로세스를 보여준다.|
|-d|세션 리더를 제외한 모든 프로세스를 보여준다.|
|-e|커널 프로세스를 제외한 모든 프로세스를 보여준다|.
|T|현 터미널에서의 모든 프로세스를 보여준다.|
|a|한 터미널의 사용자 고유 프로세스를 보여준다.|
|r|현재 실행중인 프로세스를 보여준다.|
|x|터미널 없는 프로세스를 보여준다.|
|--deselect|-N 옵션과 같다.|

## 프로세스를 선택하여 선택한 목록만 보여주는 명령어 옵션
|명령어 옵션||
|---|---|
|-C|지정한 명령어 이름에 관련된 정보를 보여준다.|
|-G|지정한 RGID에 관련된 정보를 보여준다. (이름도 지원)|
|-U|지정한 RUD에 관련된 정보를 보여준다. (이름도 지원)|
|-g|지정한 세션 리더 혹은 그룹 이름에 관련된 정보를 보여준다.|
|-p|PID를 선택한다.|
|-s|세션에 속한 프로세스를 선택한다.|
|-t|tty를 선택한다.|
|-u|사용자 ID를 지정한다 (이름도 지원)|
|U|지정한 사용자의 프로세스를 보여준다.|
|p|프로세스 ID를 선택한다.|
|t|tty를 선택한다.|
|--Group| 실제 그룹이름이나 ID를 선택한다.|
|--User|실제 사용자이름이나 ID를 선택한다.|
|--group|유효 그룹이름이나 ID를 선택한다.|
|--pid|프로세스 ID를 선택한다.|
|--sid|세션 ID를 선택한다.|
|--tty|터미널을 선택한다.|
|--user|유효 사용자이름이나 ID를 선택한다.|
|-123|--sid의 의미이다.|
|123|--pid의 의미이다.|

### 프로그램 정보
|명령어 옵션||
|---|---|
|-V|버전 정보를 보여준다.|
|L|모든 포맷 지시자를 보여준다.|
|V|버전 정보를 보여준다.|
|--help|도움말을 보여준다.|
|--info|디버깅 정보를 보여준다.|
|--version|버전 정보를 보여준다.|

*ps 와 top의 차이점*

**ps는 ps한 시점에 proc에서 검색한 cpu 사용량이다.**

# 3. jobs

*jobs*

jobs는 **작업이 중지된 상태, 백그라운드로 진행 중인 작업 상태, 변경되었지만 보고되지 않은 상태** 등을 표시한다. 

**-백그라운드로 실행되는 작업목록(작업번호, 상태, 명령어)을 보여주는 리눅스 명령어**

**-여기서 작업번호는 PID와는 달리, 별도로 부여되는 백그라운드 작업목록 상의 번호이다.**

**-작업목록은 현재 쉘 세션에 딸린 것이며, 다른 세션과는 독립적이다. 현재 쉘 프로세스(bash)의 자식 백그라운드 프로세스들을 보여준다고 할 수 있다.**

**-리눅스 kill 명령어 뒤에 %작업번호를 입력하여 종료시킬 수 있다.**

## 상태
|상태||
|---|---|
|Running|작업이 진행중임|
|Done|작업이 완료되어 0을반환|
|Done(code)|작업이 종료되었으며 0이 아닌 코드를 반환|
|Stopped|작업이 일시 중단|
|Stopped(SIGTSTP)|SIGTSTP 시그널이 작업을 일시 중단|
|Stopped(SIGTTIN)|SIGTTIN 시그널이 작업을 일시 중단|
|Stopped(SIGTTOU)|SIGTTOU 시그널이 작업을 일시 중단|

## 명령어 옵션
|명령어 옵션||
|---|---|
|-l|프로세스 그룹 ID를 state 필드 앞에 출력|
|-n|프로세스 그룹 중에 대표 프로세스 ID를 출력|
|-p|각 프로세스 ID에 대한 한 행씩 출력|
|command|지정한 명령어를 실행|

# 4. kill
*kill*

kill 명령어는 대개 **프로세스를 죽일 때** 사용한다. 하지만 **내부적으로는 프로세스에 시그널을 보내 원하는 작업**을 하게 하는 명령어이다.

## 프로세스를 죽이는 방법

죽이려는 프로세스의 pid를 얻고 

-kill[pid]

-kill 명령어의 default 시그널은 TERM(15)인다.

## 명령어 옵션
|||
|---|---|
|-l|signal의 종류를 출력한다.|
|-s|특별히 보낼 시그널을 지정함. 시그널 번호나 시그널 이름을 저장함.|

### kill 과 ps의 명령어 조합
>1번-종료시킬 프로세스 리스트를 나열함.

>ps ax|grep httpd
>>2번-해당 프로세스들의 PID만 모음

>>ps ax|grep httpd|awk’{print$1}‘
>>>3번-PID 하나씩 kill 명령어에 매개변수로 넘겨서 다 종료시킴.

>>>ps ax|grep httpd|awk’{print$1}‘|xargs kill 또는 kill –9 ‘ps-ef|grep httpd|grep –v grep|awk’{print$1}‘’

# 5. 기본적인 매크로 사용 방법

**커맨드 모드 (esc 누른 상태) 에서**
1. 'q' 를 누르고 a~z 사이 문자로 매크로 recording 시작
2. 커맨드 모드로 돌아와서 'q'를 누르면 매크로 recording 끝
3. 매크로를 사용하려면 커맨드 모드에서 @+a~z 를 입력하면 됨

## 순서
>1. q + a       a키에 recording 시작
>>2. 반복을 위한 내가 원하는 동작
>>>3. q             recoding 종료
>>>>4. @a          1회 실행 or @@         방금 실행한 매크로 실행 or 10@a       매크로 10회 실행

### 매크로 문자열을 편집기에 그대로 출력하는 방법

- 첫 번째 방법: 편집 모드에서 ctrl + r, ctrl + r, 매크로 문자  를 순서대로 입력하면 그대로 출력된다.

- 두 번째 방법: 커맨드 모드에서 "매크로문자p 를 입력하여 래지스터로부터 바로 붙여넣기 한다. (ex: "ap, "bp, "cp, "dp, ...)

..
