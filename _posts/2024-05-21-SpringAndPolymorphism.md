---
title: "[Spring] 스프링과 다형성"
categories:
  - SPRING
tags:
  - Spring
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

> <b>Spring<br><span style="color:red;">자바 언어 기반의 프레임워크</span></b><br><span style="font-size:15px">스프링은 객체 지향 언어가 가진 가장 큰 특징을 살려내는 프레임워크이다.</span>

<h3>왜 스프링과 다형성을 함께 사용하면<br>다형성의 장점이 극대화될까?</h3>
<span style="font-size:16.7px; font-style:nomal;">이전에 다형성에 대해 포스트했듯이 다형성의 가장 큰 특징은 변경과 확장에 유연하다.<br>링크 <br><span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>이 말은 컴포넌트를 유연하게 변경할 수 있다는 것이다.</b></span><br><br>실세계를 예로 들어보면<br>운전자와 자동차가 있다. 운전자는 자동차를 바꾸려고 한다.<br>이때 운전자는 부가티로 바꾸든 벤틀리로 바꾸든 포르쉐로 바꾸든 운전을 할 수 있다.<br>
</span>

<!-- ```html
<span style="font-size:16.7px; font-style:nomal;">
  자바를 공부하면서 처음 다형성을 접했을때는 이론적으로는 공부하고 사용법을
  익혔지만, 왜? 굳이^^?,,,<br /><br />인스턴스의 타입과 일치하는 타입의
  참조변수를 쓰는게 안헷갈리는 것 아닌가? 라는 의문을 가질 수 밖에 없었다.
  <br /><br />하지만 객체지향의 가장 중요한 요소라고하니
  <span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>일단</b></span>
  공부했었다. 나의 이러한 의문들은 스프링을 공부하게 되면서 해결이 되었다. (역시
  개발자은 나무보단 숲을 봐야한다고 하지만 낸들 쉽지않은걸 어쩌겠어요)
  <br /><br />
  그래서 오늘은 다형성에 대해 정리해보려고 한다.
</span>
``` -->

 <figure style="margin:-2em 0">
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
{% include gallery id="gallery"%}
</figure>
<br>
<span style="font-size:16.7px; font-style:nomal;">왜냐하면 운전자는 '자동차'라는 <b>역할</b>의 운전방법(사용법)을 알고 있기때문에 자동차가 <b>구현</b>된 부가티,벤틀리, 포르쉐의 사용법을 따로 익히지 않아도 되기때문이다.<br><br> <span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>정리하면 운전자와 구현체는 직접적인 연관이 없다는 말이다.<br>이렇게 '역할'과 '구현'을 분리하면 변경과 확장에 유연해지는 것이다.<br>운전자는 대상의 역할(인터페이스)만 알면되고 구현(구현체)과는 직접적인 연관이 없으므로 구현의 변경에는 영향을 받지않기 때문이다.</b></span>
</span>

<br><br><span style="font-size:20px;"><span style="box-shadow: inset 0 -10px 0 yellow; "><b>자바 언어의 다형성을 활용</b></span></span>
<br>

- 역할 = 인터페이스
- 구현 = 인터페이스를 구현한 클래스, 구현 객체

<span style="font-size:16.7px;">이제 실세계가 아닌 실무에서 보자면 <br> <b>모든 프로젝트는 완벽한 도메인을 거치고 개발을 시작하는 것이 아니다!</b> <br>대부분의 틀은 잡혔지만 세부 요구사항이 잡히지 않았을 때 개발자는 마냥 기다리고 있을 수는 없다.<br> <br><b>왜냐면....바쁘니까...</b><br> <br> 또, 요구사항 개발이 많이 진행된 사항에서 변경사항이 <span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>충!분!히!</b></span> 생길 수 있다.<br>이런경우 역할과 구현을 구분하여 개발을 했다면 변경에 유연하게된다.<br><br>좀 더 구체적인 예로 <br> 어떤 DB를 쓸지 정해지지 않은 상태로 개발을 시작하게됐다.<br><br>DB후보는 <span style="box-shadow: inset 0 -10px 0 #E1BEE7; ">MemoryMemberRepository</span> 와 <span style="box-shadow: inset 0 -10px 0 #D9FCDB; ">JdbcMemberRepository</span>인데 <span style="box-shadow: inset 0 -10px 0 #E1BEE7; ">MemoryMemberRepository</span>가 아마 될 것 같다해서 개발자는 구현체를 만들어서 대부분의 개발을 끝냈다. <br> 근데 갑자기 <span style="box-shadow: inset 0 -10px 0 #D9FCDB; ">JdbcMemberRepository</span> 를 쓰기로 확정됐다고 한다면? ㅎㅎㅎㅎ; <span style="box-shadow: inset 0 -10px 0 #E1BEE7; ">MemoryMemberRepository</span> 와 연결이 된 모든 파일들을 찾아서<span style="box-shadow: inset 0 -10px 0 #D9FCDB; ">JdbcMemberRepository</span> 로 변경해야 한다.<br><br>하지만 여기서 역할과 구현을 구분하여 다형성을 잘 활용했다면, 그러니까 인터페이스 설계를 제대로 했다면 그냥 갈아끼우면 된다.</span>

```java
public class MemberService {
		//	 인터페이스						구현체
 private MemberRepository memberRepository = new MemoryMemberRepository();

}
```

<span style="font-size:16.7px;"><span style="box-shadow: inset 0 -10px 0 #D9FCDB; ">JdbcMemberRepository</span> 로 변경해주세요!! </span>

```java
public class MemberService {
// private MemberRepository memberRepository = new MemoryMemberRepository();
   private MemberRepository memberRepository = new JdbcMemberRepository()

}
```

<span style="font-size:16.7px;">
구현체 부분만 <span style="box-shadow: inset 0 -10px 0 #D9FCDB; ">JdbcMemberRepository</span>로 변경해주면 되는것이다.<br><br>인터페이스 최고잖아,,, 다형성 최고잖아,,<br><br><span style="box-shadow: inset 0 -10px 0 yellow; "><b>하지만 중요한 역할인만큼 인터페이스의 변경이 생긴다면 <br>클라이언트,서버에도 큰 변경이 생기게 된다.</b></span><br><br>결국 인터페이스도 사람이 만드는것이고 완벽한 건 없기때문이다.
</span>

> 결론<br><b>인터페이스를 안정적으로 잘 설계하는 것이 중요하다.</b>

<br>

| 참고                      |     |
| ------------------------- | --- |
| 자바의 정석 - 남궁 성     |     |
| ---------------------     | --- |
| 스프링 핵심 원리 - 김영한 |     |

<br>
