---
title: "[Collections framework] 컬렉션 클래스"
categories:
  - COLLECTIONS
tags:
  - 컬렉션
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

> <b>Collections(클래스)<br><span style="color:red;">컬렉션을 위한 메서드(static)을 제공</span></b><br><span style="font-size:15px">주의 : java.util.Collection은 인터페이스이고, java.util.Collections는 클래스이다.</span>

<!-- <figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
{% include gallery id="gallery"%}
</figure> -->

> <h2><span style="font-size:16.7px;">컬렉션의 동기화</span></h2>

<span style="font-size:16.7px;">
static Collections <b>synchronized</b>Collection(Collection c)<br>
static List&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>synchronized</b>List(List list)<br>
static Set&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>synchronized</b>Set(Set s)<br>
static Map&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>synchronized</b>Map(Map m)<br>
static SortedSet&nbsp;&nbsp;&nbsp;<b>synchronized</b>SortedSet(SortedSet s)<br>
static SortedMap <b>synchronized</b>SortedMap(SortedMap m)<br>
</span>

<span style="font-size:16.7px;"><b><span style="box-shadow: inset 0 -10px 0 yellow; ">사용하는 방법</span><br>
List syncList = Collections.synchronizedList(new ArrayList(...));</b></span>

<span style="font-size:16.7px;"><span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>멀티 쓰레드(multi-thread) 프로그래밍에서는 하나의 객체를 여러 쓰레드가 동시에 접근할 수 있기 때문에 데이터의 일관성(consistency)을 유지하기 위해서는 공유되는 객체에 동기화(synchronization)가 필요하다.</b></span><br> Vector와 Hashtabler과 같은 구버젼(JDK1.2 이전)의 클래스들은 자체적으로 동기화 처리가 되어 있는데, 멀티쓰레드 프로그래밍이 아닌 경우에는 불필요한 기능이 되어 성능을 떨어뜨리는 요인이 된다. 그래서 새로 추가된 ArrayList와 HashMap과 같은 컬렉션은 동기화를 자체적으로 처리하지 않고 필요한 경우에만 Collections클래스의 동기화 메서드를 이용해서 동기화처리가 가능하도록 변경하였다.</span><br><br>

> <h2><span style="font-size:16.7px;">변경불가 컬렉션 만들기(수정불가)</span></h2>

<span style="font-size:16.7px;">
static Set&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>unmodifiable</b>Set(Set s)<br>
static Map&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>unmodifiable</b>Map(Map m)<br>
static NavigableSet&nbsp;&nbsp;&nbsp;<b>unmodifiable</b>NavigableSet(NavigableSet s)<br>
static SortedSet&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>unmodifiable</b>SortedSet(SortedSet s)<br>
static NavigableMap&nbsp;<b>unmodifiable</b>NavigableMap(NavigableMap m)<br>
static SortedMap&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>unmodifiable</b>SortedMap(SortedMap m)<br>
</span>

<span style="font-size:16.7px;">컬렉션에 저장된 데이터를 보호하기 위해서 컬렉션을 변경할 수 없게, 즉 읽기전용으로 만들어야할 때가 있다.
주로 멀티 쓰레드 프로그래밍에서 여러 쓰레드가 하나의 컬렉션을 공유하다보면 데이터가 손상될 수 있는데, 이를 방지하려면 아래의 메서드들을 이용하자.</span><br><br>

> <h2><span style="font-size:16.7px;">싱글톤 컬렉션 만들기</span></h2>

<span style="font-size:16.7px;">
static List <b>singleton</b>List(Object o)<br>
static Set&nbsp;<b>singleton</b>(Object o)  // singletonSet이 아님<br>
static Map&nbsp;<b>singleton</b>Map(Object key, Object value)<br>
</span>

<span style="font-size:16.7px;"><span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>단 하나의 객체만을 저장<b><span>하는 컬렉션을 만들고 싶을 경우가 있다.</span><br><br>

> <h2><span style="font-size:16.7px;">한 종류의 객체만 저장하는 컬렉션 만들기(=지네릭스와 같은 기능)</span></h2>

<span style="font-size:16.7px;">
static Collections <b>synchronized</b>Collection(Collection c)<br>
static List&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>synchronized</b>List(List list)<br>
static Set&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>synchronized</b>Set(Set s)<br>
static Map&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>synchronized</b>Map(Map m)<br>
static SortedSet&nbsp;&nbsp;&nbsp;<b>synchronized</b>SortedSet(SortedSet s)<br>
static SortedMap <b>synchronized</b>SortedMap(SortedMap m)<br>
</span>

<span style="font-size:16.7px;"><b><span style="box-shadow: inset 0 -10px 0 yellow; ">사용하는 방법</span><br>
List list = new ArrayList();<br>
List checkedList = checkedList(list, String.class);</b><span style="font-size:15px">// list에 한 가지타입(String)만 저장 가입</span><br>
<b>checkedList.add("abc"); </b><span style="font-size:15px"> // OK. </span><br>
<b>checkedList.add(new Integer(3)); </b><span style="font-size:15px; color:red;">// error. ClassCastException발생</span>
</span>

<span style="font-size:16.7px;"><span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>컬렉션에 모든 종류의 객체를 저장할 수 있다는 것은 장점이기도하고 단점이기도 하다. 대부분의 경우
한 종류의 객체를 저장하며, 컬렉션에 지정된 종류의 객체만 저장할 수 있도록 제한</b></span>하고 싶을 때 사용한다. 지네릭스(generics)로 간단히 처리할 수 있는데도 이런 메서드들을 제공하는 이유는 호환성 때문이다. 지네릭스는 JDK1.5부터 도입된 기능이므로 JDK1.5이전에 작성된 코드를 사용할 때는 이 메서드들이 필요할 수 있다.</span><br><br>

<br>

| 참고                  |     |
| --------------------- | --- |
| 자바의 정석 - 남궁 성 |     |

<br>
