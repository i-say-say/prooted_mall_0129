# Fruited Mall – Site Components & Content Spec

이 문서는 프루티드 자사몰의
페이지별 구성 요소(Component),
콘텐츠 역할,
실제 사용 카피를 정의한다.

Claude는 이 문서를 기준으로
자사몰 프로토타입을 구성한다.

---

## GLOBAL – Header Promotion Bar

[COMPONENT]
type: header-promotion-bar
page: global

[CONTENT]
label: 첫구매 할인
message: 첫구매 최대 60% 할인 + 5,000원 쿠폰

---

## HOME – Main Page

[PAGE] Home
[COMPONENT] Hero Carousel

---

### Carousel 1 – Brand Statement

[SLIDE]
title: 프루티드 브랜딩
headline: |
  슈퍼푸드 원물에서 찾은
  두피·헤어 솔루션, 프루티드
role: brand positioning

---

### Carousel 2 – First Purchase Offer

[SLIDE]
title: 첫 구매 혜택
headline: 가입 후 딱 한 번, UP TO 60%
description: |
  첫 구매 고객을 위한 단 한번의 기회
  5,000원 쿠폰 + 최대 60% 할인
cta:
  label: 혜택 받고 시작하기
  action: signup
role: conversion trigger

---

### Carousel 3 – Purple Booster Onion Shampoo

[SLIDE]
title: 퍼플부스터 양파샴푸
headline: 무안 적양파로 채우는 두피 탄력
description: |
  탈락 모발 수 개선 / 두피 탄력 개선
  뿌리볼륨까지 살아나는 보라빛 항산화 샴푸

  적양파 + 아사이베리 + 비트 등
  8가지 퍼플 슈퍼푸드 콤플렉스
cta:
  label: 퍼플부스터 샴푸 보기
  action: product_purple
role: product introduction

---

### Carousel 4 – Green Cleansing Kale Shampoo

[SLIDE]
title: 그린클렌징 케일샴푸
role: product introduction
note: 두피 진정 & 데일리 클렌징

---

### Carousel 5 – Yellow Mix Banana Egg Treatment

[SLIDE]
title: 옐로우믹스 바나나에그 트리트먼트
role: product introduction
note: 단백질 집중 케어 & 즉각적 윤기

---

## SHOP – Product Navigation

[PAGE] Shop

[SECTION]
title: 전체 상품 모아보기

[SECTION]
title: 첫구매 전용
description: 첫구매 1회만 적용되는 60% 할인

---

## SET ITEMS

[SET]
name: [입문] 슈퍼푸드 듀얼 스타터
composition: 퍼플 샴푸 1 + 그린 샴푸 1
description: 두 가지 두피 컨디션에 맞춘 입문 세트

[SET]
name: [Best] 에센셜 루틴
composition: 퍼플 샴푸 1 + 옐로우 트리트먼트 1
description: 뿌리는 퍼플, 결은 바나나

[SET]
name: [Fresh] 딥 클린 & 실키 리페어
composition: 그린 샴푸 1 + 옐로우 트리트먼트 1
description: 유분은 비우고 영양만 남기는 루틴

[SET]
name: [ALL] 프루티드 패키지
composition: 퍼플 1 + 그린 1 + 옐로우 1

[SET]
name: [Gift] 웰컴 투 슈퍼푸드 키트
description: 센스 있는 3단계 기프트

---

## SUPERFOOD STORY

[PAGE] Superfood Story

[SECTION]
title: Rooted in Superfood, Proven by Science

[SECTION]
title: Origin & Synergy
description: |
  국내산 무안 적양파를 비롯한 핵심 원료와
  20여 가지 자연 유래 부스터를
  최적의 비율로 배합

[SECTION]
title: Clinical Efficacy
description: |
  탈락 모발 수 감소
  두피 탄력 개선
  모발 인장 강도 개선

[SECTION]
title: Clean Formula
description: |
  설페이트 / 파라벤 / 실리콘 FREE
  한국 비건 인증

---

## PURPLE LINE

[LINE]
theme: Anti-Hair Loss & Antioxidant
hashtags: 탈모완화기능성, 두피탄력, 무안적양파
benefits:
  - 탈락 모발 수 개선
  - 두피 탄력 개선
recommendation: 힘없이 처지는 모발
product: 퍼플부스터 양파 샴푸

---

## GREEN LINE

[LINE]
theme: Soothing & Deep Cleansing
hashtags: 문제성두피해결, 수분진정, 그린클렌즈
benefits:
  - 두피 피지 감소
  - 수분량 증가
  - 붉은기 / 각질 개선
recommendation: 지성·민감성 두피
product: 그린클렌징 케일 샴푸

---

## YELLOW LINE

[LINE]
theme: Damage Repair & Protein
hashtags: 극손상모케어, 단백질폭탄, 물미역광채
benefits:
  - 큐티클 거칠기 개선
  - 모발 인장 강도 개선
recommendation: 극손상 모발
product: 바나나에그 트리트먼트

---

## ABOUT PROOTED

[PAGE] About prooted

[SECTION]
headline: Raw, Real, and Rooted.
subheadline: 잘 먹고, 잘 바르는 삶에 대하여.

[SECTION]
description: |
  우리는 식탁 위에서 에너지를 얻습니다.
  뿌리, 잎, 열매의 생명력을
  이제 머릿결에 올립니다.

[SECTION]
description: |
  가장 신선한 것이 가장 강력하니까.
  두피가 마시는 첫 번째 슈퍼푸드,
  회복의 여정을 시작하세요.
