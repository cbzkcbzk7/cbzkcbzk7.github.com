---
title: BIKE MAP
categories:
- Java
tags:
- Java
gallery:
  - url: /assets/images/logind.png
    image_path: /assets/images/logind.png
    alt: "placeholder image 1"
    title: "Image 1 title caption"
  - url: /assets/images/logind.png
    image_path: /assets/images/logind.png
    alt: "placeholder image 2"
    title: "Image 2 title caption"

---

><b>자전거 여행루트 탐색과 동행찾기가 가능한 웹</b>
{% capture fig_img %}
![Foo]({{ "/assets/images/login.png" | relative_url }})
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
{% include gallery id="gallery" layout="half"%}
</figure>
내가 생각하는 나의 성격과 친구가 생각하는 나의 성격을 비교함으로써 겉으로 보이는 나의 모습이 어떠한지 파악해볼 수 있는 웹사이트입니다. 성격 검사 웹사이트는 무수히 많지만 이런 유형의 웹사이트는 전혀 없었고, 백 엔드 개발자와 협업하는 방법을 배울 수 있는 나름 가벼운 프로젝트였기 때문에 진행하게 되었습니다.
백 엔드 개발자와 협업하는 과정에 관해 많이 배울 수 있었던 프로젝트입니다. UI & UX 및 API 명세를 문서로 작성하여 소통하였습니다. 또한, 통신 과정에서 필요한 쿠키나 CORS 등의 개념에 대해서도 서로 많이 배울 수 있었습니다.
각종 애니메이션 효과와 canvas API 등을 활용하여 디자인에도 공을 많이 들인 프로젝트입니다. 또한, 디자이너 없이 직접 디자인을 구상하며 UI & UX에 대해서도 많이 고민해볼 수 있었습니다.
복수 페이지의 Next.js 웹사이트를 만들면서 라우팅, CSR, SSR, SSG에 대한 개념을 더욱 확실하게 익힐 수 있었던 프로젝트입니다.
* 주요 기능 : 자전거 여행 루트 탐색하기 / 동행 찾기 / 후기 게시판 / 정보 공유
* GitHub :	[https://github.com/cbzkcbzk7](https://github.com/cbzkcbzk7)																																				

|Front - end | Back - end | Toolkit   |  Deployment  |
| -------- | -------- | -------- | -------- 
| JSP, HTML, JavaScript, JQuery| JAVA, MyBatis, Spring Framework, Oralce | STS, Database Developer     | GitHub |