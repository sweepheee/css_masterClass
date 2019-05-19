# display: flex

아래 요소를 정렬할 수 있다. <br>
justify-content: space-around, space-between 등을 주로 사용하여 정렬한다.<br>
align-items: center 요소의 위, 아래간격을 맞춘다.(block요소로 인하여 줄바꿈이 일어난 아래 요소를 같은 줄로 맞춰줌.)
``` 
ex) 헤더를 만들 때

.header {
 display: flex; /* flex를 사용하여 아래 요소를 정렬하겠다 */
 justify-content: space-around /* 아래 요소의 간격을 동일하게 맞춰주겠다. */
 align-items: center /* 요소의 height값 center에 아래요소를 맞춤하겠다. 즉 수직중앙정렬. 아래요소가 줄바꿈이 일어났을때 유용하다. */
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

---

display: flex는 기본적으로 row에 축이 맞춰져있다.<br>
justify-content는 메인축 정렬을 의미하고<br>
align-items는 서브축 정렬을 의미한다.<br>
즉, 기본적으로 row에 메인축이 맞춰져있으므로 justify-content는 row방향(수평) 정렬, align-items는 column방향(수직) 정렬이다.
<br>
메인축과 서브축을 바꾸는 css가 존재한다.<br>
flex-direction : column 을 주게되면 메인축과 서브축이 변경이 된다. 하지만 굳이 필요없고 머리아프므로 특별한 경우가 아니면 사용하지않겠다.

---

display: flex와 같은 레벨에 flex-wrap: wrap 이라는 css를 줄 수 있다.<br>
해당 css는 디폴트값이 flex-wrap: nowrap 인데 이 코드는 화면을 늘리거나 줄였을때 요소들이 줄바꿈을 할 것인지<br>
혹은 줄바꿈을 하지않고 width값에 상관없이 줄어들거나 늘어날 것인지를 설정한다.<br>
nowrap의 경우 width가 줄어들기만할 뿐 줄바꿈이 일어나지 않고 wrap의 경우 width가 유지되면서 줄바꿈이 일어난다.


---

flex요소 안에 또 flex를 넣을 수 있다. <br>
즉, flex로 정렬된 박스가 있다고 예를들면 그 박스안의 글자의 위치를 처음, 중간, 끝 위치로 정렬이 필요하다면<br>
flex요소에 display:flex를 추가하여 정렬할 수 있다
```
.header { display: flex; }
.header ul { 
  display: flex;
  justify-content: center;
}




