# Vim Tips for Beginners

## Overview
이 페이지는 vim 을 배우고 조금 익숙해진 사람들이 중간 이상단계로 vim을 쓰기 위해 배워야 할 tip들을 정리한 페이지 입니다.

## 

## Tips
### 일반
- `vim`에디터의 기본 전제는 사용자가 키보드를 올바르게 사용하고 있다는 가정하에 속도를 높일 수 있다. 타자가 느리거나 독수리 타법이라면 타자 버릇 부터 고쳐는 걸 권장한다. 
  - 익숙해지면 사람들이 왜 [해피해킹](https://namu.wiki/w/%ED%95%B4%ED%94%BC%20%ED%95%B4%ED%82%B9%20%ED%82%A4%EB%B3%B4%EB%93%9C) 같은 코딩 전용 키보드를 사는지 이해하게 된다.
- 처음 명령어가 익숙하지 않을 때는 `명령어 입력 모드`에서 `:h`를 통해 `help`를 잘 볼 수 있다.
  - 만약 특정 명령어에 대해 찾고 싶다면 `:h <찾고싶은 명령어>`를 입력하면 된다. 예를 들면 `:h G` 라는 식으로 검색이 된다.
- 의외로 모르는 사람이 많지만, 흔히 `vi 에디터`라고 하면 기존 unix의 대표적인 텍스트 편집기였고 지금쓰고 있는 `vim`으로 `vi improved`의 약자로 `향상된 vi에디터`를 의미한다. 실제로 둘은 기능적으로 꽤다르다.
- 모든 경우 우측과 아래로 명령어가 수행되면 `소문자` 반대로 좌측/위로 명령어가 발생하면 `대문자`로 입력해야 한다.
  - 대표적인 예로 다음 글자 찾기는 대문자 <kbd>f</kbd>이고, 이전 글자 찾기즈는 대문자 <kbd>F<kbd>가 사용된다.
- 필요한 경우 자주 <kbd>ESC</kbd>로 일반모드로 들어갈 필요가 있다. <kbd>u</kbd>를 통해 `되돌리기`를 할 경우 너무 많은 내용이 되돌아가지 않도록 해야 한다.
  - <kbd>u</kbd>의 변경 구간은 일반모드실행과 실행사이의 명령들이다.
  - 일반모드로 가는 명령은<kbd>ESC</kbd>외에도 많다. 대표적으로 <kbd>CTRL</kbd>+<kbd>\[</kbd>가 있다. 이는 입력모드에서 사용할 수 있다
  - 비슷한 방식으로 <kbd>CTRL</kbd>+<kdb>o</kdb>가 있다.
  - 이렇게 하는 이유는 <kbd>ESC</kbd>가 너무 멀리 있기 때문이다. 연습하는 것이 좀더 빠르게 타자를 칠 수있다.
- 명령행 모드 또는 `ex모드`라고 불리우는 모드의 진입은 <kbd>:</kbd>로 들어갈 수 있다.
  - 생각보다 다양한 기능을 제공한다. 예를 들면 `:tabnew`은 새로운 페이지를 생성하고 `:split`은 기존 화면을 분할한다.
  - 명령행 모드는 주소라는 개념이 있다. `.`은 현재 행 `숫자`는 해당 숫자 행, `1` 시작행 `$` 마지막 행, `.+3`같은 상대참조 주소도 사용가능하다.



- [vimgolf](http://www.vimgolf.com/)는vim을 연습하는 프로그램으로, 타수를 적게 치는 것을 목표로 vim을 연습한다. 


 

### 이동
- 기본 이동은 좌하상우순으로 <kbd>h</kbd><kbd>j</kbd><kbd>k</kbd><kbd>l</kbd>을 입력할 수 있다. 화살표 커서를 이용하지 않는 것을 권장한다.
- 단어간 이동은 우측이동은 <kbd>w</kbd> 좌측이동은 <kbd>b</kbd>이다.
  - 두 키워드와 함께 <kbd>a</kbd>를 함께 쓰면 단어 다음에 바로 입력할 수 있다.
  - 단어 끝이동은 <kbd>e </kbd> 를 눌러준다. 
- 줄로 바로 이동하기 위해서는 <kbd>:</kbd>를 누르고 이동하고 싶은 줄수를 입력하면 된다.
  - 같은 방법으로 <kbd>가고싶은줄</kbd>와 <kbd>G</kbd>를 쓰면 이동 가능하다.
- 맨 첫 줄로 이동하기 위해서는 <kbd>g</kbd>,<kbd>g</kbd>를 사용할 수 있다.
  - 또 다른 방법으로 명령어 문법인 `:1` 를 사용할 수 있다.
  - 맨 마지막으로 이동하지 위해서는 `:$`을 사용할 수 있다. `:$`후에 <kbd>z</kbd><kbd>z</kbd>를 쓰면 맨 마지막 페이지를 편하게 볼 수 있다.
- 작업이 너무 아래쪽에 있거나 너무 위에 있을 때는 <kbd>z</kbd>,<kbd>z</kbd>를 사용할 수 있다. 현재 커서를 화면 중간으로 옮기면서 보이는 화면 표시를 조절한다. 심심하면 눌러보자.
- 한 페이지씩 이동은 <kbd>CTRL</kbd>+<kbd>f</kbd>이고, 이전 페이지로의 이동은 <kbd>CTRL</kbd>+<kbd>b</kbd>

### 검색
- 문자를 검색할 때는 <kbd>/</kbd>를 사용한다. `/kbd`를 사용하면 해당 문서에서 `kbd`라는 단어를 찾는다.
  - 다음 단어로 이동은 <kbd>n</kbd>, 이전 단어로 이동은 <kbd>N</kbd>를 사용한다.

### 입력
- 현재 커서가 위치한 단어를 삭제하면서 입력을 하기 위해서는 <kbd>c</kbd>,<kbd>w</kbd>를 순차적으로 입력한다.
  - 단어를 찾는 <kbd>/</kbd> 명령과 이전 입력을 반복하는 <kbd>.</kbd>와 함께 사용하면 매우 유용하다.
  - 전체를 바꾸는 `/%s/대상단어/바꿀단어/g`가 있지만 개별로 확인하면서 바꾸고 싶다면 위 방법이 더 좋다.
- 새로운 문자를 입력하는 명령어는 매우 다양한데, 필요에 따라 기억하는게 좋다.
  - <kbd>o</kbd>는 아랫줄에 입력, <kbd>O</kbd>는 윗줄에 입력
  - <kbd>a</kbd>는 다음칸에 입력, <kbd>A</kbd>는 그줄 오른쪽 끝에 입력
  - <kbd>i</kbd>는 현재칸에 입력, <kbd>I</kbd>는 그줄 첫번째 칸에 입력
- 최고 유용한 도구는 <kbd>.</kbd>로 이전 명령을 반복한다.
  - 예를 들면 각줄에 `;`을 붙이고 싶다면 제일 첫 줄에서 <kbd>A</kbd>,<kbd>;</kbd>를 실행한다음, <kbd>k</kbd>,<kbd>.</kbd>을 반복하면 된다. 한칸 내려가면서 `A;`명령을 반복해준다.

### 편집
- 단어 맨끝에서 해당 단어를 지울려면 <kbd>x</kbd>의 연타 보다, <kbd>b</kbd>,<kbd>d</kbd>,<kbd>w</kbd>가장 타자수를 줄이는 방법이다. 다른 방법으로는 <kbd>d</kbd>a</kbd>w</kbd>도 있다.
  - <kbd>d</kbd>a</kbd>w</kbd>는 <kbd>.</kbd>명령과 함께 사용하기 최적화 되어 있다.
- 편집할때는 2단어 삭제 처럼 숫자를 확실히 이용해주자. 예를 들면  <kbd>d</kdb>, <kbd> 2 </kbd>, <kbd> w </kbd> 단어 두개를 한번에 지우는 명령어 이다.
- 문단 전체를 지울 때는 <kbd>d</kbd>,<kbd>a</kbd>,<kbd>p</kbd>를 사용해 줄 수 있다.
- 한번에 모든 글자를 대문자로 바꾸는 방법은 <kbd>g</kbd>U</kbd> 이고, 한번에 모든 글자를 소문자로 바꾸는 방법은 <kbd>g</kbd>, <kbd>u</kbd> 이다. 이후에 변환해주고 싶은 방향을 입력해주면 그 방향에 있는 모든 단어들을 한번에 대소문자로 변환한다.
- 단어를 끼워 넣기 모드에서 삭제할 수 도 있다. 장점이 있다면, 백스페이스를 누르지 않아도 된다는 것이다. 손가락이 한번 그렇게 움직이면 상당한 시간이 걸릴수도 있다. 단점이 있다면 백스페이스 누르는게 더 편한다는 것이다.
  - 편집모드 상에서 <kbd>CTRL </kbd>+<kbd>h</kbd>를 누르면 앞에 한 글자를 삭제한다. 백스페이스가 편한다.
  - 같은 상태에서 <kbd>CTRL</kbd>+<kbd>w</kbd>는 앞에 있는 단어 처음까지 다 지운다.
  - 같은 상태에서 <kbd>CTRL</kbd>+<kbd>u</kbd>는 현재를 기준으로 현재줄 처음까지 모든 것을 지운다. 가장 편한다.
- 복사 붙여넣기에서 복사 명령은 <kbd>y</kbd> 로 시작하여 레지스터에 저장한다.
  - 방향키와 숫자와 해당 방향에 해당하는 글자들을 레지스터에 넣을 수 있다.
  - 특정 지점까지 저장하기 위해서는 <kbd>y</kbd>,<kbd>t</kbd>, `저장하고자 하는 지점까지의 첫글자`
  - 붙여넣기는 일반모드에서 <kbd>p</kbd>를 사용할 수 도 있지만, 편집모드에서  <kbd>CTRL</kbd>+<kbd>R</kbd>,<kbd>0</kbd>을 이용할 수 있다.
- 또다른 방법으로 복사-붙여넣기를 하는 것으로 명령행 모드로 가능하다.
  - `:6t.`는 6번째 줄을 복사해서 현재 행 아래로 붙여넣기
  - `:t6` 현재 줄을 6번 째 행 아래로 붙여넣기
  - `:.t.+3` 현재 줄을 복사해서 현재 행에서 세번째 밑에 행에 붙여넣기 
  - 같은 방법으로 `t`를 `m` 으로 바꿔서 사용할 수 있다.
  
- 편집모드에서 끼워넣기 말고 덮어쓰기를 할 수 있는 명령도 있다. <kbd>R</kbd>를 쓰면 일반모드에서 바로 덮어쓰기를 할 수 있다. 특정 위치에 있는 글자를 바로 바꿀때 유용하다.
  - 한 문자에 대해서만 바꾸기 위해서는 <kbd>r</kbd>을 써줄 수 있다.
- 들여쓰기를 지정하기 위한 방법으로는 <kbd><</kbd>와 <kbd>></kbd>가 있다. 두 명령어와 함께 <kbd>.</kbd>를 함께 써주면 유용하다.
  - 적용되는 범위 지정은 DELETE나 기타 다른 방향키 지정 방법과 동일하다
- 편집할 때 많이 쓸 수 있는 방법중 하나가 `VISUAL MODE`이다.
- 기본 모드와 달리 여러줄이나 단어를 선택하는 모드이다. 마우스 드래그와 같은 효과가 난다.
  - 한 자를 선택할 때는 <kbd>v</kbd>, 줄 전체를 선택할 때는 <kbd>V</kbd> 그리고 블러을 따로 지정할 때는 <kbd>CTRL</kbd>+<kbd>V</kbd>사용한다.
  - 유용하게 쓸만한 기능중에 줄 전체에있는 글자를 바꾸기 위해서는 <kbd>V</kbd>, <kbd>r</kbd>,<kbd>-</kbd>등을 쓰면 한줄 전체를 `-`로 변환할 수 있다.
  - 위 기능은 비주얼 모드로 선택된 모든 블럭에 동일하게 적용하는 명령어로 꽤 요긴하게 쓸 수 있다.
  - 비슷한 방식으로 블록이 표시된 곳에서 <kbd>c</kbd>를 사용해서 제일 상단을 수정한 후, <kbd>ESC</kbd>를 쓰면 블럭이 표시된 모든줄의 글자가 변경된다.
  - 마찬가지로 글자 맨끝에 동일한 글자를 집어넣고 싶다면, 예를 들면 `;`를 넣을 때는 블럭모드를 만든다음에 <kbd>A</kbd>를 사용해서 넣어준후 <kbd>ESC</kbd>를 쓰면 맨끝에 모든 글자가 동일하게 들어간다.


## Referecnes
- [Outsider's Blog](https://blog.outsider.ne.kr/540)
- [Vim에서 ESC를 눌렀을 때 영문 상태로 전환하기](http://seorenn.blogspot.com/2011/04/vim-vim-esc.html)
- [Vim cheatsheet](https://vim.rtorr.com/lang/ko/)
