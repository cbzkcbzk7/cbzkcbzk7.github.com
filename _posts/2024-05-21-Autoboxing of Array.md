---
title: "[Autoboxing&Unboxing] 왜 배열에서 오토박싱이 적용되지 않을까?"
categories:
  - JAVA
tags:
  - java
gallery:
  - url: "/assets/images/car.jpg"
    image_path: "/assets/images/car.jpg"
    alt: placeholder image 1
    title: Image 1 title caption
#   - url: "/assets/images/pic2.png"
#     image_path: "/assets/images/pic2.png"
#     alt: placeholder image 2
#     title: Image 2 title caption
# gallery2:
#   - url: "/assets/images/pic4.png"
#     image_path: "/assets/images/pic4.png"
#     alt: placeholder image 4
#     title: Image 4 title caption
---

> <b>Autoboxing<br><span style="color:red;">기본형 값을 래퍼 클래스의 객체로 자동 변환</span></b><br><b>Unboxing<br><span style="color:red;">반대로 변환(래퍼 > 기본형)</span></b><br><span style="font-size:15px">JDK1.5부터 기본형과 참조형 간의 연산이 가능해진 이유이다.</span>

<h3>래퍼(wrapper)클래스<br></h3>
<span style="font-size:16.7px; font-style:nomal;">자바가 완전한 객체지향 언어가 아니라는 얘기를 듣는것은 8개의 기본형을 객체로 다루지 않기 때문이다. 하지만 보다 높은 성능을 얻을 수 있었다. <br><span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>때로는 기본형변수도 객체로 다뤄야 하는 경우가 있는데 이 때 사용되는 것이 래퍼(wrapper)클래스이다. </b></span><br><br>그래서 JDK1.5부터 컴파일러가 이런 기본형 변수를 자동으로 래퍼 클래스 객체로 바꿔주는 코드를 넣어주는데, 이러한 작업을 <span style="box-shadow: inset 0 -10px 0 yellow; "><b>autoboxing&unboxing</b></span>이라고 한다.<br><br>근데 나는 Arrays.asList()를 테스트하다가 배열은 autoboxing이 안되는 것을 발견해서 <br>왜? 라는 의문이 생겨 포스팅하려한다. <br>
</span>

```java
int[] arr = {1,2,3,4,5};
List list = Arrays.asList(arr);
// 에러는 안나지만 Object 타입으로 들어감
```

> <span style="font-size:16.7px; font-style:nomal;"><br>사실 생각해보면 '기본형을 객체로 바꿔주는 것'이 'autoboxing'인데 배열은 객체기때문에 안되는게 맞다.<br>그래도 기본형에서 객체로 오토박싱되고..Vector클래스나 ArrayList클래스에 기본형 값을 저장할때도 되는데 이건 왜 안해주지? 단지 궁금해서 찾아봤다.</span><br><br>

<span style="font-size:16.7px;"><b>단순한 이유로는 자바 디자이너가 그렇게 설계했고 JLS가 지정하는 방식이기때문이다!</b><br>아..그렇구나ㅎ<br>그래도 몇가지 더 분명한 이유를 찾자면 <span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>int[]를 Object[]로 변환하려면 배열의 모든 요소를 방문하고 변환하여야 한다. 이는 비용이 많이 드는 (O(N)) 작업이며, 일부 구문 뒤에 프로그래머에게 숨겨야하는 작업이 아니다.</b></span> 오토박싱 언박싱을 배열에 확장할 경우 이러한 해결하기 어려운 효율성과 개념적 문제들이 생기기때문이라고 한다.</span>

> 결론<br><b>편의성을 위해 오토박싱, 언박싱이 있지만 내부적으로 추가연산이 일어나므로 오토박싱,언박싱이 일어나지 않도록 타입연산이 잘 되도록 구현하는 것이 좋다</b>

<br>

| 참고                                                                                                     |     |
| -------------------------------------------------------------------------------------------------------- | --- |
| 자바의 정석 - 남궁 성                                                                                    |     |
| ---------------------                                                                                    | --- |
| [autoboxing of array](https://stackoverflow.com/questions/45918075/why-autoboxing-doesnt-work-in-arrays) |     |

<br>
