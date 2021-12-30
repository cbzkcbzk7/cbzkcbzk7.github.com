---
title: BIKE MAP
categories:
- Java
tags:
- Java
gallery:
- url: "/assets/images/pic1.png"
  image_path: "/assets/images/pic1.png"
  alt: placeholder image 1
  title: Image 1 title caption
- url: "/assets/images/pic2.png"
  image_path: "/assets/images/pic2.png"
  alt: placeholder image 2
  title: Image 2 title caption
gallery2:
- url: "/assets/images/pic4.png"
  image_path: "/assets/images/pic4.png"
  alt: placeholder image 4
  title: Image 4 title caption
---

><b>자전거 여행루트 탐색과 동행찾기가 가능한 웹</b>
{% capture fig_img %}
![Foo]({{ "/assets/images/pic5.png" | relative_url }})
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
{% include gallery id="gallery" layout="half"%}
{% include gallery id="gallery2"%}
</figure>


자전거를 이용하여 여행 루트의 탐색과 저장, 공유 및 평가를 통하여 사람들이 원하는 여행 루트를 찾을 수 있게 하고, 
여행 루트를 활용하여 함께 여행할 동행인을 구할 수 있는 웹사이트입니다.
화면구성을 위해 프로젝트에 대한 디자인을 전공을 살려 일러스트를 활용하여 구성하였습니다.
처음에는 모든 것을 만들어가야 한다는 것이 부담감으로 느껴졌습니다.
하지만 꾸준한 고민을 통해 하나씩 해결하는 과정을 겪고 완성도가 높아지는 프로젝트를 보면서 부담감은 성장감으로 바뀌었으며 시간이 지날수록 프로젝트의 완성도를 더 높일 수 있겠다는 자신감이 생겼습니다.
마지막까지 3차에 걸친 테스트케이스를 통해 
프로젝트를 직접 테스트하며 문제점을 찾고 해결하며 프로젝트를 마무리하였습니다.

시작부터 끝까지 프로젝트를 진행하며 개발단계에서부터 디자인까지 모두 참여하여 하나의 완성된 결과물을 만들어내는 경험을 하였습니다.
직접 개발의 모든단계를 거쳐 프로젝트를 완성시키며 설계의 중요성에 대해 배울 수 있었습니다.
또한, DB테이블 설계와 데이터에 대한 개념을 더욱 확실하게 익힐 수 있었던 프로젝트였습니다.


* 주요 기능 : 자전거 여행 루트 탐색하기 / 동행 찾기 / 후기 게시판 / 정보 공유
* GitHub :	[https://github.com/cbzkcbzk7](https://github.com/cbzkcbzk7)																																				

|Front - end | Back - end | Toolkit   |  Deployment  |
| -------- | -------- | -------- | -------- 
| JSP, HTML, JavaScript, JQuery| JAVA, MyBatis, Spring Framework, Oralce | STS, Database Developer     | GitHub |
