---
layout: post
title:  "최적 경로 여행 추천 시스템"
date:   2014-12-14
<!--image: promise.png-->
description: In this project, we propose a system that shows optimal route, destination route and traffic information according to destination using shortest path algorithm. Through this, it is possible to share recommendation routes and reviews of travelers who have traveled.
---

<p>최근 국내외로 여행을 하는 여행자들이 많이 늘어나고 있다. 자유여행을 가기 전 여행코스를 세우는 과정에서 일일이 위치를 검색해보거나 가까운 거리를 비교해보며 계획을 세워야 하는 불편함과 번거로움이 있다. 
이를 해소하기 위해서 본 프로젝트에서는 최단경로 알고리즘을 이용하여 목적지에 따른 최적의 경로, 목적지로 가는 방법 및 교통수단 정보를 알려주는 시스템을 제안한다. 이를 통하여 여행을 다녀왔던 여행객들의 추천경로나 후기 등을 공유 할 수 있다.
</p>
    
    
## 작품 개요 및 개발구성

<dl>
  <dt>이름</dt>
  <dd>최적 경로 여행 추천 시스템</dd>
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
  <dt>운영체제</dt>
  <dd>Window</dd>
  <dt>DBMS</dt>
  <dd>MYSQL</dd>
  <dt>제작 기간</dt>
  <dd>2017-06-05 ~ 2018-08-01</dd>
  <dt>담당 업무</dt>
  <dd>프로젝트 설계 및 개발, 유지보수</dd>
</dl>


## 프로젝트 설계

사용자가 가고자 하는 다수의 목적지를 알고리즘을 적용하여 최단 및 최적 경로를 제공된다. 사용자는 웹 또는 앱을 통해 Google 지도 내에서 목적지를 입력하고 그에 대한 최적의 경로를 이동수단과 함께 제공 받는다. 사용자가 이용했던 여행지 루트에 대한 데이터는 다른 사용자에게 제공되어지기 위해 또는 실 사용자가 조회하기 위해 저장되어진다. 이 때 계산되어지는 최적의 루트는 사용자가 선택한 mode(도보,대중교통,차량)에 의해 최단 거리로 제공된다.각 각의 목적지에 대한 이동 방법 또한 함께 제공된다.


<figure>
    <img src="/assets/img/g_con.png" alt="" style="width:580px;">
     <figcaption>Fig. 1. System Conceptual Diagram</figcaption>
</figure>

<dl>
<dt>구성도에 따른 주요 기능</dt>
</dl>

<figure>
    <img src="/assets/img/g_modul.PNG" alt="" style="width:580px;">
     <figcaption>Fig. 1. System Conceptual Diagram</figcaption>
</figure>

* 최적 경로 탐색 <br>
1.탐색 영역 둘러보기 (The Search Area) <br>
2.탐색 시작 (Starting the Search) <br>
3.경로 채점 (Path Scoring)<br>
4.계속 탐색하기 (Continuing the Search)

<figure>
    <img src="/assets/img/g_map.PNG" alt="" style="width:580px;">
     <figcaption>Fig. 1. System Conceptual Diagram</figcaption>
</figure>

<p>F = G + H
G - 시작점 A로부터 현재 사각형까지의 경로를 따라 이동하는데 소요되는 비용
H - 현재 사각형에서 목적지 B까지의 예상 이동 비용. 사이에 벽, 물 등으로 인해 실제 거리는 알지 못함. 그들을 무시하고 예상 거리를 산출. 여러 방법이 있지만, 이 포스팅에서는 대각선 이동을 생각하지 않고, 가로 또는 세로로 이동하는 비용만 계산.
F - 현재까지 이동하는데 걸린 비용과 예상 비용을 합친 총 비용입니다.</p>


<figure>
    <img src="/assets/img/mode.PNG" alt="" style="width:580px;">
     <figcaption>Fig. 1. System Conceptual Diagram</figcaption>
</figure>

* 각 목적지 간의 교통수단 서비스 기능 <br>
길 찾기 모드에서는 사용자에게 Driving, Walking, Bicycling, Transit 로 총 4가지 방법을 지원한다. 사용자가 원하는 모드를 선택 시 최단거리를 가는 각 목적지 사이를 모드에 대한 상세 방법을 제공 한다.   예를 들어 A->B->C에 대한 목적지를 Transit모드로 제공받게 될 경우, A->B에 대한 지하철 또는 버스에 대한 노선 정보와 정류소 정보를 조회할 수 있고, 추가로 환승해야 될 경우도 정보를 제공 받을 수 있다. 이처럼 최단 경로의 정보를 제공해 줄 뿐만 아니라 제공 되어진 경로 시스템 내에서도 각각의 목적지에 대한 상세 설명을 제공받을 수 있다. 긴 여행을 가는 사용자들에게는 추천 경로 제공뿐만 아니라 상세 설명까지 조회 가능하다.


## 시나리오 및 시스템 평가

• 1단계: 사용자가 로그인을 하면 이미 여행을 다녀온 여행자가 다른 사람에게 자신이 갔던 경로나 관광지를 추천하거나 공유하고 싶을 경우 글을 게시할 수 있다.<br>
• 2단계: 여행을 계획하고 있던 사용자는 이미 여행을 다녀온 여행객들의 후기를 보고 참고 할 수 있다.<br>
• 3단계: 사용자가 출발지와 마지막 목적지를 설정 해놓고 자신이 가고자하는 다수의 경유지를 입력하면 출발지에서 출발하여 모든 경유지를 방문하고 마지막 목적지까지 도착하는 최적의 경로를 제공해준다.<br>
• 4단계: 제공받은 경로가 마음에 든 경우 경로를 클릭하고, 목적지까지 가는 교통수단을 선택하면 선택한 수단에 맞는 정보를 제공받을 수 있다.


## 사용자 Web 화면

<figure>
    <img src="/assets/img/g_web.gif" alt="" style="width:580px;">
     <figcaption>Fig. 1. System Conceptual Diagram</figcaption>
</figure>

## 사용자 App 화면

<figure>
    <img src="/assets/img/g_app.png" alt="" style="width:580px;">
     <figcaption>Fig. 1. System Conceptual Diagram</figcaption>
</figure>
<figure>
    <img src="/assets/img/g_app2.png" alt="" style="width:580px;">
     <figcaption>Fig. 1. System Conceptual Diagram</figcaption>
</figure>

## 시연 영상 

<figure>
    <img src="/assets/img/video.gif" alt="" style="width:700px;" >
     <figcaption>Fig. 1. System Conceptual Diagram</figcaption>
</figure>

## 비고

* 논문 2건 
<a href="/assets/img/g_hci.pdf">HCI Conference 2018</a>, 
<a href="/assets/img/g_k.pdf">한국정보과학회 Conference 2018</a>


## 관련 기술

* <a href="https://cloud.google.com/maps-platform/?hl=ko">Google Map API</a> - 참고 튜토리얼

* a* 알고리즘 적용
<img src="https://www.101computing.net/wp/wp-content/uploads/A-Star-Search-Algorithm.png" alt="" style="width:600px;">

1. 최소가 되는 지점을 우선 탐색(우선 순위 큐)
2. 휴리스틱 추정값 사용
3. Open List/Closed List를 이용하여 노드 관리

<dl>
<dt>개념 설명</dt>
</dl>

1. 휴리스틱 추정 값

f(x) = h(x) + g(x)
-h(x) : 출발 노드 n으로부터 도착 노드 n까지의 경로 가중치 (새로운 사각형까지의 거리)
<img src="/assets/img/g_a.PNG" alt="" >
-g(x) : 노드 n으로부터 목표 노드까지의 추정 경로 가중치 (도착 노드까지의 예상 노드비용)

2. Open List, Closed List

-Open List : 검색 가능성이 있는 노드의 집합
-Closed List : 이미 검색이 끝난 지점들의 집합

3. 탐색 우선 순위

-Open List 내의 f(x) 가중치 값이 가장 작은 노드부터 탐색

<dl>
<dt>동작 원리</dt>
</dl>

{% highlight ruby %}

while pq_size
    node = pq.pop;
    if node == goal
        break;
    for next_node in (next_node_begin...next_node_end)
        pq.push(next_node, g(node) + cost + h(next_node));
        
print node

{% endhighlight %}
