css grid
----

```

grid-template-columns : 10px
grid-template-rows : 10px
/// 위의 경우 가로10px 세로10px 을 설정한 것.  css를 적용받는 박스가 아무리 많다해도 10x10 박스 하나만 생겨난다.

grid-template-columns : 10px 15px
grid-template-rows : 10px 12px
// 이럴 경우엔 박스가 2개 생겨나는데 10x10 다음은 15x10까지 한줄에 표시되고 줄바꿈이 일어나면서 15x10, 15x12가 만들어진다.
// 박스가 5개이상 존재할경우 표시가 안되고 박스는 4개까지만 만들어진다(이부분의 이유는 아직 알지못함. 2개만 적어서?)

```
