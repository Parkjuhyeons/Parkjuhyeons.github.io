---
layout: post
title:  "사용자기반의 명소 저장 클라우드 시스템"
date:   2014-12-15
description: If you use the Web via SNS, you can save it using the program. At that time, the amount of storage may be lost until the information is stored in the timetable. Trying to point to a side, or saving ideas can be easily found. To solve this problem, we provide the project and user's storage cloud system.
---

<p>
    <span class="dropcap">S</span>NS를 이용 중이거나 웹 서핑 중에 마음에 드는 명소를 저장하고자 할 때, 사용자들은 스크린 샷을 찍거나 메모장에 기록하는 등 단순한 저장방법을 이용합니다. 이 때, 저장하고자 하는 명소의 정보가 일정한 시간이 지나 관리할 수 없을 정도가 되면 저장의 가치가 사라집니다. 가고자 하는 목적의 근처를 방문했을 때, 또는 생각이나 가고자 할 때에 저장해둔 데이터를 쉽게 찾기에는 어려움이 존재합니다. 이를 해결하기 위해서 본 프로젝트를 통하여 사용자 기반의 명소저장 클라우드 시스템을 제공하고자 합니다.</p>



<!--    Aenean lacinia bibendum nulla sed consectetur. Morbi leo risus, porta ac consectetur ac, vestibulum at eros. Cras mattis consectetur purus sit amet fermentum. Nulla vitae elit libero, a pharetra augue. Curabitur blandit tempus porttitor. Donec sed odio dui. Cras mattis consectetur purus sit amet fermentum.-->


<!--Nullam quis risus eget urna mollis ornare vel eu leo. Cras mattis consectetur purus sit amet fermentum. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor.-->

<!--
## Unordered List
* List Item
* Longer List Item
  * Nested List Item
  * Nested Item
* List Item
-->

<!--
## Ordered List
1. List Item
2. Longer List Item
    1. Nested OL Item
    2. Another Nested Item
3. List Item
-->

## 작품 개요 및 개발구성

<dl>
  <dt>이름</dt>
  <dd>사용자 기반의 명소 저장 클라우드 시스템</dd>
  <dt>플랫폼</dt>
  <dd>Web</dd>
  <dt>제작 언어</dt>
  <dd>Javascript, HTML, CSS</dd>
  <dt>서버</dt>
  <dd>Node.JS</dd>
  <dt>프레임워크</dt>
  <dd>Express</dd>
  <dt>API</dt>
  <dd>Google map API</dd>
  <dt>Library</dt>
  <dd>Google Vision API (OCR)</dd>
  <dt>운영체제</dt>
  <dd>Window</dd>
  <dt>DBMS</dt>
  <dd>MYSQL</dd>
  <dt>제작 기간</dt>
  <dd>2018-04-02 ~ 2018-06-02</dd>
  <dt>담당 업무</dt>
  <dd>프로젝트 설계 및 개발, 유지보수</dd>
</dl>


## 프로젝트 설계


<figure>
    <img src="/assets/img/conceptual1.PNG" alt="">
     <figcaption>Fig. 1. System Conceptual Diagram</figcaption>
</figure>
<figure>
    <img src="/assets/img/configuration.png" alt="">
     <figcaption>Fig. 2. System Configuration Diagram</figcaption>
</figure>
* OCR 엔진을 통한 문자 추출과 위치기반을 통한 클라우드 시스템
* PWA (Progressive Web App)을 이용 하여 사용자 경험 향상을 목적으로 하고, URL 입력없이 웹 사이트에 접속
* 또한 Javascript로 구현한 후 모바일 언어로 푸시 알람 구현
<figure>
    <img src="/assets/img/erdiagram.png" alt="">
     <figcaption>Fig. 3. E-R Diagram</figcaption>
</figure>


## 사용자 Web 화면


<figure>
    <img src="/assets/img/web1.png" alt="">
     <figcaption>Fig. 4. Web 메인 화면</figcaption>
</figure>
<figure>
    <img src="/assets/img/web2.png" alt="">
     <figcaption>Fig. 5. Web 등록 화면</figcaption>
</figure>


<figure>
    <img src="/assets/img/web3.png" alt="">
     <figcaption>Fig. 6. 문자 추출 화면 </figcaption>
</figure>


## 사용자 App 화면


<figure>
    <img src="/assets/img/app.png" alt="">
     <figcaption>Fig. 7. PWA를 통한 APP화면</figcaption>
</figure>


## 비고

* 논문 1건 <a href="/assets/img/ksci.pdf">KSCI 논문</a>

<figure>
    <img src="/assets/img/non.png" alt="">
     <figcaption>Fig. 8. KSCI 학회 눈문</figcaption>
</figure>

* 참고 API 및 패턴

** <a href="/blog/featured-image/"><span>«&nbsp;Featured Image</span></a>
** <a href="/blog/code-snippet/"><span>«&nbsp;Featured Image</span></a>
