# display: flex

아래 요소를 정렬할 수 있다.
justify-content: space-around, space-between 등을 주로 사용하여 정렬한다.<br>
align-items: 요소의 위, 아래, 양옆 간격을 맞춘다.(block요소로 인하여 줄바꿈이 일어난 아래 요소를 같은 줄로 맞춰줌.)
``` 
ex) 헤더를 만들 때

.header {
 display: flex; /* flex를 사용하여 아래 요소를 정렬하겠다 */
 justify-content: space-around /* 아래 요소의 간격을 동일하게 맞춰주겠다. */
 align-items: center /* 아래요소가 줄바꿈이 일어났을때 같은 줄로 맞춰주겠다. */
 width: 50%;
 margin: 0 auto; 
}

.header ul {
 list-style: none;
}

.header ul li {
 display: inline-block; /* 리스트 같은 블록에서 생성되게 해준다. 즉, float: left가 필요없음. */
}

```


