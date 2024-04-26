---
title: "[HashSset] 해시셋"
categories:
  - COLLECTIONS
tags:
  - HashSet
gallery:
  - url: "/assets/images/jvm.png"
    image_path: "/assets/images/jvm.png"
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

> <b>HashSset<br><span style="color:red;">Set인터페이스를 구현한 가장 대표적인 컬렉션</span></b><br><span style="font-size:15px">Set인터페이스의 특징대로 HashSet은 중복된 요소를 저장하지 않는다.</span>

<!-- <figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
{% include gallery id="gallery"%}
</figure> -->

> <h2><span style="font-size:16.7px;">HashSet</span></h2>

<span style="font-size:16.7px;">
HashSet에 새로운 요소를 추가할 때는 add메서드나 addAll메서드를 사용하는데, 만일 HashSet에 이미 저장되어 있는 요소와 중복된 요소를 추가하고자 한다면
이 메서드들은 false를 반환함으로써 중복된 요소이기 때문에 추가에 실패했다는 것을 알린다.
이러한 HashSet의 특징을 이용하면, 컬렉션 내의 중복 요소들을 쉽게 제거할 수 있다.
<br><br>
ArrayList와 같이 List인터페이스를 구현한 컬렉션과 달리 HashSet은 저장순서를 유지하지 않으므로 저장순서를 유지하고자 한다면 LinkedHashSet을 사용해야한다.
</span>

<span style="font-size:16.7px;"><span style="box-shadow: inset 0 -10px 0 yellow; "><b>1.Ex</b></span><br></span>

```java
public class HashSetEx1 {
    public static void main(String[] args){
        Object[] objArr = {"1", new Integer(1), "2", "2","3","3","4","4","4"};
        Set set = new HashSet();

        for(int i = 0; i < objArr.length; i++){
            set.add(objArr[i]); // HashSet에 objArr의 요소들을 저장한다.
        }

        // 요소 출력
        System.out.println("set = " + set);
    }
}

// 실행결과 [1, 1, 2, 3, 4]
```

<span style="font-size:16.7px;"><span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>중복된 값은 저장되지 않았다.</b></span><br>
'1'이 두 번 출력되었는데, 둘 다 '1'로 보이기 때문에 구별이 안 되지만, 하나는 String인스턴스이고 다른 하나는 Integer인스턴스로 서로 다른 객체이므로 중복으로 간주하지 않는다. Set을 구현한 컬렉션 클래스는 List를 구현한 컬렉션 클래스와 달리 순서를 유지하지 않기 때문에 저장한 순서와 다를 수 있다. 만일 중복을 제거하는 동시에 저장한 순서를 유지하고자 한다면 HashSet대신 LinkedHashSet을 사용해야한다.</span><br><br>

<br>

| 참고                  |     |
| --------------------- | --- |
| 자바의 정석 - 남궁 성 |     |

<br>
