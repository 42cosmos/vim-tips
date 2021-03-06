# . 커맨드를 입력해서 ; 콜론 붙여주기

프로그래밍을 하다 보면 반복적으로 수정해야 일이 매우 많다. 아래와 같은 예들이 있다.

- 들여쓰기를 반복해서 한다.
- 
- 코드 맨끝에 ; 콜론을 붙인다.

이를 지원하기 위한 vim 명령어로 `.`가 있다. `.`은 `일반모드`에서 쌓이는 명령 버퍼를 저장해뒀다가 다시 실행해주는 명령을 한다.
예를 들면 우리가 `맨 끝줄로 가서 ;를 붙인다.`라는 명령을 실행하기 위해서는 아래와 같은 명령어를 입력할 것이다.

`A;`

여기서 주의할 점이 있다.

- `A` 명령어 대신 `$a`를 쓸 수 있다.  두 동작을 한꺼번에 하는 매우 유용한 명령어니 기억하자

연습삼아 아래와 같은 코드에서 코드 맨 끝에 모두 `;`를 붙이는 데 매번의 커맨드가 필요한지 생각해보자
한 줄을 내리는 커맨드는 화살표가 아닌 `j`여야 한다. `j`와 `화살표 아래`는 같은 기능을 하지만 다르다. `j` 버퍼를 쌓지만 `화살표 아래`는 버퍼를 쌓지 않는다.

```javascript
var x, y, z
x = 5
y = 6
z = x + y
```

정답은 총 `8`번이다. 첫 번째 코드에서 편집모드에서 시작한다고 가정하고 `A;<ESC>j.j.j.` 를 입력하면 된다.
너무 많은 줄에 붙인다면 비효율적이겠지만 10줄 정도에서는 매우 효율적인 명령어다.
`.` 명령은 편집모드에서 사용되는 모든 명령어를 `buffer`에 저장했다가 한번에 쓰는 것이기 때문에 그 특징을 잘 이해해야 한다. 



