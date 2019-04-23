---
layout: post
title:  "최적 경로 여행 추천 시스템"
date:   2014-12-14
image: promise.png
description: 
In this project, we propose a system that shows optimal route, destination route and traffic information according to destination using shortest path algorithm. Through this, it is possible to share recommendation routes and reviews of travelers who have traveled.
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

## 데이터베이스 설계

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
