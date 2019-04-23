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

사용자는 PC 또는 스마트폰의 앨범이나 메모장에 기록된 명소 사진들을 본 시스템에 등록한다. 명소 저장 및 문자 추출 시스템에 의하여 해당 사진 내의 문자들이 추출된다. 추출된 문자 중 적절한 문자 내용을 선택하거나 수동으로 입력한다. 선택된 문자는 해당 명소의 제목이 되며, 동시에 위치 기반을 통해 주소와 함께 저장되어진다. 

<figure>
    <img src="/assets/img/conceptual1.PNG" alt="" style="width:630px;">
     <figcaption>Fig. 1. System Conceptual Diagram</figcaption>
</figure>

이렇게 저장되어진 명소들은 한 사용자에 의해서 수정, 삭제될 수 있으며 다른 사용자에게 공유되어진다. 또한 해당 게시물을 스크랩하거나 검색할 수도 있다. 이 명소들은 이후에 사용자의 위치와 근접해질 경우 스마트폰 알림으로 전송되어지며, 1년전 게시물이나 2년전 게시물처럼 잊혀진 게시물로 제공된다. 플랫폼의 제약없이 어떠한 디바이스로도 사용이 가능하다.

간단한 시나리오로 나타내면 다음 그림2와 같다.
<figure>
    <img src="/assets/img/conceptual.PNG" alt="" style="width:400px;" >
     <figcaption>Fig. 2. System Scenario</figcaption>
</figure>
OCR Engine (문자 추출 엔진)을 이용하여 캡쳐 사진의 글자들을 추출한다.
추출된 데이터를 이용해 자동 위치 주소 검색한다.
데이터가 사진, 글, 주소와 같은 형태로 저장한다.
여행지는 분류되어 저장되며, 근접 여행지 알림을 push 받을 수 있다.
<figure>
    <img src="/assets/img/configuration.png" alt="">
     <figcaption>Fig. 3. System Configuration Diagram</figcaption>
</figure>
* OCR 엔진을 통한 문자 추출과 위치기반을 통한 클라우드 시스템
* PWA (Progressive Web App)을 이용 하여 사용자 경험 향상을 목적으로 하고, URL 입력없이 웹 사이트에 접속
* 또한 Javascript로 구현한 후 모바일 언어로 푸시 알람 구현

<figure>
    <img src="/assets/img/modul.PNG" alt="" style="width:600px;">
     <figcaption>Fig. 4. System Module Configuration</figcaption>
</figure>

<dl>
<dt>구성도에 따른 주요 기능</dt>
</dl>
* 간편화 저장 
* 사용자가 필요할 시 편하고 쉽게 저장
스크린 샷을 통해 장소에 대한 위치 자동 검색
 - 사용자 스스로도 위치 등록이 가능, 제목과 태그와 같은 게시 글 형태로 저장
* 저장된 데이터 활용
 - 저장되어진 명소에 대한 상세정보 제공
* 이용된 데이터 활용
 - 이미 다녀온 명소에 대한 데이터 처리 필요
 - 좋았던 곳과 나빴던 곳, 또는 삭제 처리를 이용
 - 사용자는 점수를 달거나 리뷰를 달아 다녀온 곳을 기억할 수 있음
* 위치 알림 이벤트
 - 사용자가 저장한 명소가 실제 사용자 근처에 존재 할 때 PUSH 알림 제공
 - 알림을 줄 명소와 제어 할 데이터 선택 가능
* 공유 기능
 - 저장된 명소를 다른 계정의 누군가와 공유 가능
 
 
## 데이터베이스 설계
 
 사용자기반의 명소 저장 클라우드 시스템의 사용자 정보와 명소저장을 위한 데이터베이스의 ERD를 나타낸다. 테이블은 총 7개로 이루어지며 명소 엔티티를 중심으로 구성되어진다. 사용자 엔티티에는 아이디나 비밀번호 그리고 간단한 개인정보가 들어가있다. 명소 개체는 반드시 어떠한 사용자에 의해서 생성되어 진다. 식별은 명소 ID로 식별하고 이름, 주소, 스크랩 허용 유무, 검색 유무, 스크랩 유무와 저장되어진 날짜가 속해있다. 다른 계정의 사용자가 스크랩 한 Scrap 테이블과 한 명소에 대한 리뷰 데이터가 저장되는 review 테이블이 존재한다. 한 명소에 대해 여러개의 사진이 저장되므로 Strage_image 테이블이 별개로 존재한다. 명소와 관계짓고 있는 Scrap, Review,Image 테이블의 데이터들은 CASECADE 규칙에 의하여 사용자가 명소 삭제 시 함께 삭제되도록 지정되어있다.
 
<figure>
    <img src="/assets/img/erdiagram.png" alt="" style="width:600px;">
     <figcaption>Fig. 5. E-R Diagram</figcaption>
</figure>

## 사용자 Web 화면


<figure>
    <img src="/assets/img/web1.png" alt="" style="width:750px;">
     <figcaption>Fig. 6. Web 메인 화면</figcaption>
</figure>
<figure>
    <img src="/assets/img/web2.png" alt="" style="width:750px;">
     <figcaption>Fig. 7. Web 등록 화면</figcaption>
</figure>


<figure>
    <img src="/assets/img/web3.png" alt="" style="width:750px;">
     <figcaption>Fig. 8. 문자 추출 화면 </figcaption>
</figure>


## 사용자 App 화면


<figure>
    <img src="/assets/img/app.png" alt="" style="width:600px;">
     <figcaption>Fig. 9. PWA를 통한 APP화면</figcaption>
</figure>


## 비고

* 논문 2건 
<a href="/assets/img/ksci.pdf">KSCI Conference 2018</a>, 
<a href="/assets/img/icct.pdf">ICCT Conference 2018</a>


## 참고 API 및 관련기술

* <a href="https://cloud.google.com/functions/docs/tutorials/ocr">Google Vision API</a> - 참고 튜토리얼


* Promise 패턴 적용
<img src="/assets/img/promise.png" alt="" style="width:600px;">

<p><span class="dropcap">P</span>romise 패턴을 이용하여 비동기 방식의 콜백 문제 개선. </p>

프로미스는 주로 서버에서 받아온 데이터를 화면에 표시할 때 사용합니다. 일반적으로 웹 애플리케이션을 구현할 때 서버에서 데이터를 요청하고 받아오기 위해 아래와 같은 API를 사용합니다.
<img src="/assets/img/promise1.png" alt="" >

위 API가 실행되면 서버에다가 ‘데이터 하나 보내주세요’ 라는 요청을 보내죠. 그런데 여기서 데이터를 받아오기도 전에 마치 데이터를 다 받아온 것 마냥 화면에 데이터를 표시하려고 하면 오류가 발생하거나 빈 화면이 뜹니다. 이와 같은 문제점을 해결하기 위한 방법 중 하나가 프로미스입니다.

<dl>
<dt>Promise 패턴 적용</dt>
<dd>사용자 기반의 명소 저장 클라우드 시스템은 Google Vision API를 통해 사용자가 저장하고자 하는 이미지의 텍스트를 추출하는 기능을 주로 하고있다. 아래 그림에서는 메인 화면에서 다수의 사진을 등록한다. 등록되어진 사진들은 등록페이지로 넘어가는 동시에 사진 내 이미지 추출(OCR) 기능이 수행된다.</dd>
</dl>

<img src="/assets/img/si.PNG" alt="" style="width:660px;">
<img src="/assets/img/tutorial.PNG" alt="" style="width:660px;">

실제로 API를 요청하여 텍스트를 포험하는 이미지가 Cloud Storage에 업로드 되고, 트리거된 Cloud Functions는 Vision API를 사용하여 텍스트를 추출하고, 이를 구성된 번역 언어로 번역하도록 대기열에 추가된다.
트리거된 Cloud Functions는 Translation API를 사용하여 대기열에 추가된 텍스트를 번역하고, 이를 Cloud Storage에 저장하도록 대기열에 추가된다. 마지막으로 트리거된 Cloud Functions는 번역된 텍스트를 Cloud Storage에 저장된다.

이러한 과정을 통해 추출되는 문자들이 등록 페이지에 나열되기까지는 다소 시간이 걸린다. 그러나 페이지 넘김과 동시에 출력하려는 문자들이 아직 추출이 되지 않을 경우에는 데이터가 표시되지 않고 오류가 발생하거나 빈 화면이 뜬다.

<img src="/assets/img/si2.png" alt="" style="width:660px;">

이러한 문제를 해결하기 callback함수를 사용하거나 setTimeout함수를 이용해 시간을 끄는 것은 사용자에게 불편함을 미치거나 시스템 효율상 올바르지 않다. 그리하여 본 시스템에 Promise패턴을 이용하여 성능을 높인다.

{% highlight ruby %}

exports.processImage = (event) => {
  let file = event.data;

  return Promise.resolve()
    .then(() => {
      if (file.resourceState === 'not_exists') {
        // This was a deletion event, we don't want to process this
        return;
      }
      if (!file.bucket) {
        throw new Error('Bucket not provided. Make sure you have a "bucket" property in your request');
      }
      if (!file.name) {
        throw new Error('Filename not provided. Make sure you have a "name" property in your request');
      }
      return detectText(file.bucket, file.name);
    })
    .then(() => {
      console.log('File ${file.name} processed.');
    });
};
{% endhighlight %}

<!--
* <a href="/blog/featured-image/"><span>«&nbsp;Promise 패턴</span></a>
* <a href="/blog/code-snippet/"><span>«&nbsp;Google Vision API</span></a>
* <a href="/blog/figure-with-caption/"><span>«&nbsp;Progressive Web App</span></a>
-->
