css grid
----

```
grid-template-columns : 10px
grid-template-rows : 10px
```
 위의 경우 가로10px 세로10px 을 설정한 것.  css를 적용받는 박스가 아무리 많다해도 10x10 박스 하나만 생겨난다.
 <br>

```
grid-template-columns : 10px 15px
grid-template-rows : 10px 12px
```
 이럴 경우엔 박스가 2개 생겨나는데 10x10 다음은 15x10까지 한줄에 표시되고 줄바꿈이 일어나면서 15x10, 15x12가 만들어진다.
박스가 5개이상 존재할경우 표시가 안되고 박스는 4개까지만 만들어진다(이부분의 이유는 아직 알지못함. 2개만 적어서?)
<br>

```
grid-gap: 10px
```
 grid사이의 간격(상하좌우)
<br>
<br>

```
grid-template-columns : 10px 15px
grid-template-rows : 10px 12px
grid-auto-rows: 60px;
```
만약 박스가 4개이상 존재할 때 값을 준 4개 박스 외의 다른 모든 박스를 표시해주고 싶다면 grid-auto-rows 값을 줘서<br>
4번째박스를 초과하는 박스를 모두 생성할 수 있다. column값은 그대로 10px 15px가 반복되고 줄바꿈이 일어난다.<br>
<br>

```
grid-template-columns : 10px 15px
grid-template-rows : 10px 12px
grid-auto-rows: 60px;
grid-auto-flow: column;

Ex

ㅁㅁ
ㅁㅁ
ㅁㅁ 에서

ㅁㅁㅁ
ㅁㅁㅁ 으로 바뀜
```
grid-auto-rows는 기본적으로 row값으로 설정되있지만 column값으로 바꿀 수 있다.(flex-direction과 비슷함)<br>
grid-auto-flow: column 을 설정하면 grid-auto-rows에 준 값은 column값으로 바뀌면서 모든 박스가 2줄안에 표시된다<br>
즉, auto-row일땐 한줄에 박스2개만 생성되고 줄바꿈이 일어나던 게 auto-column값으로 바꾸면 옆으로 계속 생성되고 줄바꿈은 한번만 일어난다.<br>


