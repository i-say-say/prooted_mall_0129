# 프루티드 자사몰 사이트맵

## 전체 구조 개요

```
프루티드 (fruited.co.kr)
│
├── 메인 (/)
│
├── SHOP (/shop)
│   ├── 전체상품 (/shop/all)
│   ├── BEST (/shop/best)
│   ├── NEW (/shop/new)
│   ├── 유형별
│   │   ├── 샴푸 (/shop/shampoo)
│   │   ├── 트리트먼트 (/shop/treatment)
│   │   ├── 헤어에센스 (/shop/essence)
│   │   └── 헤어팩 (/shop/hairpack)
│   ├── 고민별
│   │   ├── 탈모케어 (/shop/hairloss)
│   │   ├── 손상모케어 (/shop/damage)
│   │   ├── 두피케어 (/shop/scalp)
│   │   └── 보습케어 (/shop/moisture)
│   └── 세트/기획 (/shop/set)
│
├── SUPERFOOD STORY (/story)
│   ├── 퍼플콤플렉스 (/story/purple-complex)
│   ├── 아사이베리 (/story/acai)
│   ├── 블루베리 (/story/blueberry)
│   └── 슈퍼푸드 성분사전 (/story/ingredients)
│
├── BRAND (/brand)
│   ├── 프루티드 소개 (/brand/about)
│   ├── 브랜드 철학 (/brand/philosophy)
│   └── 클린뷰티 (/brand/clean-beauty)
│
├── COMMUNITY (/community)
│   ├── 공지사항 (/community/notice)
│   ├── 이벤트 (/community/event)
│   ├── 리뷰 (/community/review)
│   └── FAQ (/community/faq)
│
├── MEMBERSHIP (/membership)
│   ├── 등급 혜택 (/membership/benefits)
│   ├── 쿠폰함 (/membership/coupon)
│   └── 포인트 (/membership/point)
│
├── MY PAGE (/mypage)
│   ├── 주문조회 (/mypage/orders)
│   ├── 배송조회 (/mypage/delivery)
│   ├── 찜목록 (/mypage/wishlist)
│   ├── 1:1 문의 (/mypage/inquiry)
│   └── 회원정보 (/mypage/profile)
│
├── 장바구니 (/cart)
│
├── 결제 (/checkout)
│
└── 기타
    ├── 로그인 (/login)
    ├── 회원가입 (/signup)
    ├── 검색 결과 (/search)
    ├── 이용약관 (/terms)
    ├── 개인정보처리방침 (/privacy)
    └── 404 에러 (/404)
```

---

## URL 구조 설계 원칙

### 1. SEO 친화적 URL
- 한글 대신 영문 슬러그 사용
- 계층 구조 명확히 반영
- 2-3단계 깊이 유지

### 2. 상품 상세 페이지 (PDP)
```
/product/{product-slug}
예: /product/purple-booster-shampoo
```

### 3. 카테고리 페이지 (PLP)
```
/shop/{category-slug}
예: /shop/shampoo
```

### 4. 콘텐츠 페이지
```
/story/{content-slug}
/community/{type}/{post-id}
```

---

## 페이지 우선순위 (MVP)

### Phase 1 - 필수
- [ ] 메인 페이지
- [ ] 상품 목록 (PLP)
- [ ] 상품 상세 (PDP)
- [ ] 장바구니
- [ ] 결제
- [ ] 로그인/회원가입
- [ ] 마이페이지 (주문조회)

### Phase 2 - 브랜드 강화
- [ ] BRAND (소개)
- [ ] SUPERFOOD STORY
- [ ] 리뷰 페이지
- [ ] FAQ

### Phase 3 - 확장
- [ ] 멤버십 페이지
- [ ] 이벤트 페이지
- [ ] 고민별 카테고리
- [ ] 성분사전
