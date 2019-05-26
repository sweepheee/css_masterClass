css grid
=====

<h2>1. grid-template-columns / grid-template-rows</h2>

<h3>1-1. 기본사용법</h3>

```
grid-template-columns : 10px
grid-template-rows : 10px
```
 위의 경우 가로10px 세로10px 을 설정한 것.  css를 적용받는 박스가 아무리 많다해도 10x10 박스 하나만 생겨난다.
 <br>
 <h3>1-2. 박스가 여러개일 때</h3>

```
grid-template-columns : 10px 15px
grid-template-rows : 10px 12px
```
 이럴 경우엔 박스가 2개 생겨나는데 10x10 다음은 15x10까지 한줄에 표시되고 줄바꿈이 일어나면서 15x10, 15x12가 만들어진다.
박스가 5개이상 존재할경우 표시가 안되고 박스는 4개까지만 만들어진다(이부분의 이유는 아직 알지못함. 2개만 적어서?)
<br>
<h2>2. grid-gap</h2>

```
grid-gap: 10px
```
 grid사이의 간격(상하좌우)
<br>
<br>

<h2>3. grid-auto-rows / grid-auto-columns</h2>

<h3>3-1. grid-auto-rows = 세로값을 자동으로 지정</h3>

```

grid-template-columns : 10px 15px
grid-template-rows : 10px 12px
grid-auto-rows: 60px;

```

만약 박스가 4개이상 존재할 때 값을 준 4개 박스 외의 다른 모든 박스를 표시해주고 싶다면 grid-auto-rows 값을 줘서<br>
4번째박스를 초과하는 박스를 모두 생성할 수 있다. column값은 그대로 10px 15px가 반복되고 줄바꿈이 일어난다.<br>
<br>
<h3>3-2. grid-auto-columns = 지정한 박스를 초과할 때 다음 박스를 표시할 방법.</h3>

```
grid-template-columns : 10px 15px
grid-template-rows : 10px 12px
grid-auto-columns: 60px;
grid-auto-flow: column;

Ex

ㅁㅁ
ㅁㅁ
ㅁㅁ 에서

ㅁㅁㅁ
ㅁㅁㅁ 으로 바뀜
```
grid-auto-columns는 기본적으로 row값으로 설정되어있어 column값으로 바꿔서 써야한다.(flex-direction과 비슷함)<br>
grid-auto-flow: column 을 설정하면 column값으로 바뀌면서 column값에 자동으로 준 값이 들어간다.

<br>
<br>

<h2>4. grid-template-areas</h2>

```
.container{
    grid-auto-rows: 60px;
    grid-template-areas: "header header header" "content content sidebar" "footer footer footer"
}
.box1 {
   grid-area: header // 주의 따옴표 없이 지정.
}
.box2 {
   grid-area: content
}
.box3 {
   grid-area: sidebar
}
.box4 {
  grid-area: footer
}
```
grid-template-areas는 문자로 지정한 이름값을 item에 grid-area: 이름 으로 지정해서 레이아웃을 짤 수 있다.<br>
위의 예제에서 grid-template-ares: "header ...."로 줬기때문에 grid-area: header로 지정된 박스가 가장 상단에 그 위치에 지정된다.



<br>
<h2>5. fr and repeat</h2>

<h3>5-1. fr = 가능한 자리를 차지해라</h3>

```

.box1, .box2, .box3, .box4 {
 //박스 4개 존재
 
 .grid_container {
  display: grid;
  grid-auto-rows: 60px;
  grid-template-columns: 1fr 2fr 1fr 2fr
 }

```
박스가 4개 존재하고 박스의 부모요소에 grid-template-columns값을 fr로 줄 수있다. <br>
4개의 박스니 4개의 fr값을 줬을때 준 값의 비율에 맞춰서 크기가 결정된다.<br>
즉, 1fr 2fr 1fr 2fr은 2,4번 박스의 크기가 1,3번 박스보다 2배크다.<br>

<h3>h-2. repeat() = 같은 값을 줄 박스설정</h3>

```

.box1, .box2, .box3, .box4 {
 //박스 4개 존재
 
 .grid_container {
  display: grid;
  grid-auto-rows: 60px;
  grid-template-columns: repeat(3, 1fr) 4fr;
 }

```
박스의 크기를 설정할 때 1~3번박스까지는 1fr, 4번 박스는 4fr크기를 줘라고 설정한 것. <br>
만약 박스가 네개지만 repeat(5, 1fr)와 같이 존재하지 않는 박스의 크기를 설정해도 빈 공간으로 동일한 크기의 빈 공간이 생기게 된다.
