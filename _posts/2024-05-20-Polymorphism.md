---
title: "[Polymorphism] 다형성"
categories:
  - JAVA
tags:
  - Polymorphism
gallery:
  - url: "/assets/images/customer.jpg"
    image_path: "/assets/images/customer.jpg"
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

> <b>Polymorphism<br><span style="color:red;">객체지향개념의 중요한 특징 중 하나</span></b><br><span style="font-size:15px">조상클래스 타입의 참조변수로 자손클래스의 인스턴스를 참조할 수 있도록 한 것이다.</span>

<!-- <figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
{% include gallery id="gallery"%}
</figure> -->

<!-- > <h2><span style="font-size:16.7px;">다형성</span></h2> -->

```
  자바를 공부하면서 처음 다형성을 접했을때는 이론적으로는 공부하고 사용법을
  익혔지만, 왜? 굳이^^?,,,인스턴스의 타입과 일치하는 타입의
  참조변수를 쓰는게 안헷갈리는 것 아닌가? 라는 의문을 가질 수 밖에 없었다.

  하지만 객체지향의 가장 중요한 요소라고하니

  공부했었다. 나의 이러한 의문들은 스프링을 공부하게 되면서 해결이 되었다. (역시
  개발자은 나무보단 숲을 봐야한다고 하지만 낸들 쉽지않은걸 어쩌겠어요)

  그래서 오늘은 다형성에 대해 정리해보려고 한다.

```

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
<br>
<span style="font-size:20px;"><span style="box-shadow: inset 0 -10px 0 yellow; "><b>객체지향의 4가지 주요 특징</b></span></span>
<br>

- 캡슐화
- 추상화
- 상속
- 다형성

> 상속(inheritance)

<span style="font-size:16.7px;">
다형성은 상속과 깊은 관계가 있다.
먼저 <span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>'상속'이란, 기존의 클래스(클래스A)를 재사용하여 새로운 클래스(클래스B)를 작성할 수 있는 것</b></span>인데
A클래스를 B클래스가 상속받으면 B클래스는 A클래스의 멤버변수와 메서드를 그냥 사용하거나 오버라이딩해서 사용할 수 있다.
<br><br>
<span style="font-size:16.7px;">
실세계를 예를 들어 코드를 작성해봤다. <br>지금 커피 마시고 싶으니까 커피로 만들겠습니다.
</span>

```java
class EspressoMachine {

  int shot = 2;   // 기본 2샷
  boolean temperature; // 커피온도(hot/ice)
  public EspressoMachine() {}

  int extractEspresso(int shot) {
      return this.shot = shot;
  }

}

class Latte extends EspressoMachine{
  String chooseLiquid = "우유";
  public Latte(){}

  void makeDrink(){
      System.out.println("라떼");
      if(temperature){
          System.out.println("HOT");
      }else{
          System.out.println("ICE");
      }

      System.out.println("샷 [" + shot + "], [" + chooseLiquid + "] \n" );
  }

}

class makeDrinkTest{

  public static void main(String[] args) {

      Latte latte = new Latte(); // 객체 생성
      System.out.println("[주문번호 001]");
      makeOptions(latte, 2, true);
      latte.makeDrink();

      System.out.println("[주문번호 002]");
      makeOptions(latte, 3, false);
      latte.makeDrink();
  }

  static void makeOptions(Latte latte, int shot, boolean temperature){
      latte.extractEspresso(shot); // 부모 메서드를 사용
      latte.temperature = temperature; // 부모 멤버 변수를 사용
  }

}


// 실행결과

// [주문번호 001]
// 라떼
// HOT
// 샷 [2], [우유]

// [주문번호 002]
// 라떼
// ICE
// 샷 [3], [우유]

```

<span style="font-size:16.7px;">
상속은 위의 코드처럼 Latte타입의 Latte 인스턴스 객체를 생성 후, 참조변수 latte를 통해 상속받은 부모클래스인 EspressoMachine 클래스를 사용할 수 있다.
<br><br>
객체지향개념에서 다형성이란 <span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>'여러 가지 형태를 가질 수 있는 능력'을 의미하며, 좀 더 구체적으로 말하자면, '조상클래스 타입의 참조변수로 자손클래스의 인스턴스를 참조할 수 있도록 하였다'는 것이다.<br><br>
그냥 더 간단히 말하면 EspressoMachine em = new Latte(); </b></span>로 쓸 수 있다는 말이다.
<br><br>
그럼 처음의 의문으로 돌아가서 왜?? 굳이^^? 
<br><br>
다시 실세계를 예를 들어서 <br>손님이 커피음료 1000잔을 주문했다. 카페의 커피음료 종류는 50가지인데 <br>50종류 모두 섞어서 골고루 만들어달라고 한다.
</span><br><br>
<span style="font-size:15px;">1. 울면서 집에 간다</span><br><span style="box-shadow: inset 0 -10px 0 yellow; ">2. 만든다</span>

- 다형성이 없다면?
<!-- <span style="font-size:16.7px;">다형성이 없다면?</span> -->

```java
// 라떼
static void makeOptions(Latte latte, int shot, boolean temperature){
    latte.extractEspresso(shot);
    latte.temperature = temperature;
}

// 바닐라 라뗴
static void makeOptions(VanillaLatte vanillaLatte, int shot, boolean temperature){
    vanillaLatte.extractEspresso(shot);
    vanillaLatte.temperature = temperature;
}

// 카라멜 라떼
static void makeOptions(CaramelLatte caramelLatte, int shot, boolean temperature){
    vanillaLatte.extractEspresso(shot);
    vanillaLatte.temperature = temperature;
}

```

<span style="font-size:16.7px;">위처럼 makeOptions() 를 50번 오버라이딩해서 만들어야한다.<br>고작 매개변수 Latte latte 객체를 다른 커피음료 객체로 바꾸기 위해..<br>커피음료 종류가 100가지라면..? 500가지라면...? </span>

 <figure style="margin:-2em 0">
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
{% include gallery id="gallery"%}
</figure>

<span style="box-shadow: inset 0 -10px 0 yellow; ">1. 울면서 집에 간다</span><br><span style="font-size:15px;">2. 만든다</span><br><br>
<span style="font-size:16.7px;">하지만 여기서 다형성을 사용한다면 makeOptions() 하나로 모든 음료를 제조할 수 있게된다. <span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>EspressoMachine em = new Latte(); 쓸 수 있다는 것은 매개변수의 다형성이 가능하다는 말이다.메서드의 매개변수로 EspressoMachine em 받을 때 new Latte()를 넣어 줄 수 있다는 말이다.<b>

```java
						// 모두 EspressoMachine 를 상속받음
						// new Latte(), new VanillaLatte(), new CaramelLatte() ....etc
static void makeOptions(EspressoMachine em, int shot, boolean temperature){
    em.extractEspresso(shot);
    em.temperature = temperature;
}

다형성을 통해 EspressoMachine em 를 상속받은 모든 자식클래스가 들어올 수 있다

  public static void main(String[] args) {

    Latte latte = new Latte(); // 라떼
    System.out.println("[주문번호 001]");
    makeOptions(latte, 2, true);
    latte.makeDrink();

    System.out.println("[주문번호 002]");
    makeOptions(latte, 3, false);
    latte.makeDrink();

    VanillaLatte vanillaLatte = new VanillaLatte(); // 바닐라 라떼
    System.out.println("[주문번호 003]");
    makeOptions(vanillaLatte, 3, false);
    vanillaLatte.makeDrink();


    System.out.println("[주문번호 004]");
    makeOptions(vanillaLatte, 3, false);
    vanillaLatte.makeDrink();


    CaramelLatte caramelLatte = new CaramelLatte(); // 카라멜 라떼
    System.out.println("[주문번호 005]");
    makeOptions(caramelLatte, 4, false);
    caramelLatte.makeDrink();
}

```

<span style="font-size:16.7px;"> <span style="box-shadow: inset 0 -10px 0 #D9FCDB; "><b>다형성의 가장 큰 특징으로는 유연하고 변경이 용이하다는 것이다.</b></span>위의 코드처럼 새로운 커피가 출시되어도 공통 멤버인 makeOptions()는 변경할 필요도, 메서드를 추가할 필요도 없다.여기까지가 자바 객체지향의 다형성이다. <br><br>사실 다형성은 유연하고 변경에 용이해야하므로 구현체를 참조하는 것은 좋은 방향이 아니다.<br><br>그렇다면?<br>추상클래스나 인터페이스를 이용한 다형성을 사용하면 되는데 여기서 스프링과 함께 사용할 때 다형성의 장점은 극대화된다.<b><br>
[스프링과다형성 포스트:spring&polymorphism](https://cbzkcbzk7.github.io/spring/SpringAndPolymorphism/)

> 결론<br><b>다형성은 코드의 중복을 줄이면서 변경과 확장에 유연한 '객체 지향적인 코드'를 작성하는데 유용하다</b>

<br>

| 참고                      |     |
| ------------------------- | --- |
| 자바의 정석 - 남궁 성     |     |
| ---------------------     | --- |
| 스프링 핵심 원리 - 김영한 |     |

<br>
