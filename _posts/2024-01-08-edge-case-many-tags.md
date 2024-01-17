---
title: "[JAVA]자바란?(Java Programming Language)"
categories:
  - JAVA/Java
tags:
  - Java
gallery:
  - url: "/assets/images/java.png"
    image_path: "/assets/images/java.png"
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

> <b>자바란?<br>
> 자바는 썬 마이크로시스템즈(Sun Microsystems, Inc. 이하 썬)에서 개발하여 1996년 1월에 공식적으로 발표한
> <br><span style="color:red;">객체지향 프로그래밍 언어</span>이다.</b><br>

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
{% include gallery id="gallery"%}
</figure>

> <h3>자바언어의 특징</h3>

<h4>1. 운영체제에 독립적이다.</h4>
<span style="font-size:16.7px;">기존의 언어는 한 운영체제에 맞게 개발된 프로그램을 다른 종류의 운영체제에 적용하기 위해서는 많은 노력이 필요하였지만,자바에서는 그런 노력을 하지 않아도 된다.<br>
자바는 운영체제나 하드웨어가 아닌 자바가상머신(JVM)하고만 통신하고 JVM이 자바 응용프로그램으로부터 전달받은 명령을 해당 운영체제가 이해할 수 있도록 변환하여 전달한다.
그러므로 <span style="box-shadow: inset 0 -10px 0 #D9FCDB;"><b>자바는 운영체제에 독립적이지만 JVM은 운영체제에 종속적</b></span>이여서 썬에서는 여러 운영체제에  설치할 수 있는
서로 다른 버전의 JVM을 제공하고 있다.<br>(자바를 설치할 때 각 운영체제에 맞게 설치하여야하는 이유가 바로 이때문이다.)</span>

<h4>2. 객체지향언어이다.</h4>
<span style="font-size:16.7px;">
자바는 객체지향 프로그래밍언어(object-oriented programming language) 중의 하나로 <span style="box-shadow: inset 0 -10px 0 #D9FCDB;"><b>객체지향개념의 특징인 상속, 캡슐화, 다형성</b></span>이 잘 적용된 순수한 객체지향언어이다.
</span>

<h4>3. 자동 메모리 관리(Garbage Collection)</h4>
<span style="font-size:16.7px;">
자바로 작성된 프로그램이 실행되면,  <span style="box-shadow: inset 0 -10px 0 #D9FCDB;"><b>가비지컬렉터(garbage collector)가 자동적으로 메모리를 관리</b></span>해주기 때문에 프로그래머는 메모리를 따로 관리 하지 않아도 된다.
</span>

<h4>4. 멀티쓰레드(Multi-Thread)를 지원한다.</h4>
<span style="font-size:16.7px;">
일반적으로 멀티쓰레드의 지원은 사용되는 운영체제에 따라 구현방법도 상이하며, 처리 방식도 다르다.<br>
그러나 자바에서 개발되는 멀티쓰레드 프로그램은 시스템과는 관게없이 구현가능하며, 관련된 라이브러리(Java API)가 제공되므로
구현이 쉽다. 그리고 여러 쓰레드에 대한 스케줄링(scheduling)을 자바 인터프리터가 담당하게 된다.
</span>

<h4>5. 동적 로딩(Dynamic Loading)을 지원한다.</h4>
<span style="font-size:16.7px;">
보통 자바로 작성된 애플리케이션은 여러 개의 클래스로 구성되어 있다.  <span style="box-shadow: inset 0 -10px 0 #D9FCDB;"><b>자바는 동적 로딩을 지원하기 때문에 실행 시에 모든 클래스가 로딩되지 않고 필요한 시점에 클래스를 로딩하여 사용할 수 있다.</b></span><br>
그 외에도 일부 클래스가 변경되어도 전체 애플리케이션을 다시 컴파일하지 않아도 되며, 애플리케이션의 변경사항이 발생해도 비교적
적은 작업만으로도 처리할 수 있는 유연한 애플리케이션을 작성할 수 있다.
</span>
<br>

| 참고                  |     |
| --------------------- | --- |
| 자바의 정석 - 남궁 성 |     |

<br>
