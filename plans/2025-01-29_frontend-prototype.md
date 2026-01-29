# Implementation Plan: 프루티드 자사몰 프론트엔드 프로토타입

## Overview

프루티드 자사몰의 프론트엔드 프로토타입을 두 가지 디자인 방향으로 설계한다.
- **Version A**: 감성/하이엔드 (NARKA, Anillo 레퍼런스)
- **Version B**: 클린/정보전달형 (PO:DL, ViveLab 레퍼런스)

---

## Reference Design Analysis

### Version A 레퍼런스: NARKA + Anillo

| 요소 | NARKA | Anillo |
|------|-------|--------|
| 컬러 | Beige, Warm neutrals | Neutral, Cream white |
| 레이아웃 | Minimal, 50-100px padding | Full-screen hero, clean grid |
| 타이포 | Serif accent, thin weights | Premium sans-serif |
| 애니메이션 | Swiper fade, subtle parallax | Hover transitions, smooth scroll |
| 무드 | Lifestyle luxury, organic | Premium K-beauty, editorial |

**공통 특징**
- 여백 과감하게 사용 (80-120px)
- 이미지 중심, 텍스트 미니멀
- Serif 또는 가는 산세리프 조합
- 부드러운 전환 애니메이션
- 뮤트된 자연 컬러 팔레트

### Version B 레퍼런스: PO:DL + ViveLab

| 요소 | PO:DL | ViveLab |
|------|-------|---------|
| 컬러 | White + Dark text | Teal/Forest green + White |
| 레이아웃 | Modular grid, clear sections | 4-column product grid |
| 타이포 | Sans-serif hierarchy | Typekit premium fonts |
| 애니메이션 | Minimal, functional | Autoplay carousel, fade-in |
| 무드 | Quiet luxury, substance | Calming clinical, wellness |

**공통 특징**
- 정보 계층 명확 (가격, 성분, 효능)
- 화이트 스페이스로 가독성 확보
- 기능적 UI 컴포넌트
- 제품 이미지가 시각적 주역
- 전환 요소 (CTA, 뱃지) 명확

---

## Version A: 감성/하이엔드 프로토타입

### Design System

```
Colors:
  primary:     #4A3728 (Warm Brown)
  secondary:   #7B5E57 (Muted Mauve)
  accent:      #8B5A8B (Purple Berry)
  background:  #F8F5F2 (Warm Cream)
  surface:     #FFFFFF
  text:        #2D2D2D
  muted:       #8A8A8A

Typography:
  heading:     "Cormorant Garamond", serif (light 300)
  subheading:  "Pretendard", sans-serif (light 300)
  body:        "Pretendard", sans-serif (regular 400)
  accent:      "EB Garamond", serif (italic)

Spacing:
  section-y:   120px (desktop), 80px (mobile)
  container:   max-width 1400px, padding 60px
  grid-gap:    40px

Animation:
  duration:    0.6s - 1.2s
  easing:      cubic-bezier(0.25, 0.1, 0.25, 1)
  scroll:      Intersection Observer fade-up
```

### Page Components

#### HOME

```
┌─────────────────────────────────────────────────────────────────┐
│ [Promotion Bar] 작은 serif 텍스트, 언더라인 CTA                  │
├─────────────────────────────────────────────────────────────────┤
│ [Header] 로고 중앙, 메뉴 양쪽 분산                               │
│          SHOP  STORY    [LOGO]    BRAND  CART                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│           [HERO - Full Viewport]                               │
│                                                                 │
│           슈퍼푸드 원물에서 찾은                                │
│           두피·헤어 솔루션                                      │
│                                                                 │
│           P R O O T E D                                        │
│                                                                 │
│           ↓ Discover                                           │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [BRAND STATEMENT - 120px padding]                            │
│                                                                 │
│   "가장 신선한 것이                                             │
│    가장 강력하니까."                                            │
│                                                                 │
│   Raw, Real, and Rooted.                                       │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [PRODUCT GRID - 2 columns, large images]                     │
│                                                                 │
│   ┌─────────────────────┐  ┌─────────────────────┐            │
│   │                     │  │                     │            │
│   │  [Purple Line]      │  │  [Green Line]       │            │
│   │                     │  │                     │            │
│   │  두피 탄력           │  │  두피 진정          │            │
│   │  무안 적양파         │  │  그린 수퍼푸드      │            │
│   │                     │  │                     │            │
│   └─────────────────────┘  └─────────────────────┘            │
│                                                                 │
│              ┌─────────────────────┐                           │
│              │                     │                           │
│              │  [Yellow Line]      │                           │
│              │                     │                           │
│              │  손상 케어          │                           │
│              │  바나나 에그        │                           │
│              │                     │                           │
│              └─────────────────────┘                           │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [SUPERFOOD ORIGIN - Editorial Layout]                        │
│                                                                 │
│   ┌─────────────────────────────────────────────────┐         │
│   │  [무안 적양파 풀샷 이미지]                        │         │
│   │                                                 │         │
│   │         Origin Story                           │         │
│   │                                                 │         │
│   │         무안의 적양파가                          │         │
│   │         두피에 닿기까지                          │         │
│   │                                                 │         │
│   │                        → Read More             │         │
│   └─────────────────────────────────────────────────┘         │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [CLINICAL PROOF - Minimal]                                   │
│                                                                 │
│         Proven by Science                                      │
│                                                                 │
│    탈락 모발 수        두피 탄력        인장 강도              │
│       감소              개선             개선                  │
│                                                                 │
│    * 인체적용시험 결과 기준                                     │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [REVIEWS - Horizontal Scroll, Minimal Cards]                 │
│                                                                 │
│   "뿌리부터 달라지는     "두피가 숨쉬는      "결이 살아         │
│    느낌이에요"           것 같아요"          돌아왔어요"        │
│                                                                 │
│    ★★★★★ 김O희        ★★★★★ 박O진       ★★★★★ 이O수     │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [FOOTER - Minimal, Centered]                                 │
│                                                                 │
│              PROOTED                                           │
│                                                                 │
│   Shop  Story  Brand  Community                                │
│                                                                 │
│   Instagram  Kakao                                             │
│                                                                 │
│   © 2025 Prooted                                               │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

#### PDP (Product Detail Page)

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│   [HERO - Split Layout]                                        │
│                                                                 │
│   ┌─────────────────────┐  ┌─────────────────────┐            │
│   │                     │  │                     │            │
│   │                     │  │  Purple Booster     │            │
│   │   [제품 이미지]      │  │  Shampoo            │            │
│   │   Full Height       │  │                     │            │
│   │   Sticky Scroll     │  │  무안 적양파로       │            │
│   │                     │  │  채우는 두피 탄력    │            │
│   │                     │  │                     │            │
│   │                     │  │  ₩32,000           │            │
│   │                     │  │                     │            │
│   │                     │  │  [Add to Cart]      │            │
│   │                     │  │                     │            │
│   └─────────────────────┘  └─────────────────────┘            │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [INGREDIENT STORY - Editorial]                               │
│                                                                 │
│         8가지 퍼플 슈퍼푸드                                     │
│                                                                 │
│         적양파 · 아사이베리 · 블루베리                          │
│         비트 · 자색당근 · 오디                                  │
│         가지 · 흑미                                             │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [CLINICAL - Full Width Image + Text Overlay]                 │
│                                                                 │
│   탈락 모발 수 25% 감소                                         │
│   두피 탄력 18% 개선                                            │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [USAGE - Lifestyle Photography]                              │
│                                                                 │
│         How to Use                                             │
│                                                                 │
│         1. 두피에 충분히 도포                                   │
│         2. 1-2분 마사지                                         │
│         3. 깨끗이 헹굼                                          │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Key Design Decisions (Version A)

1. **Hero**: Full viewport, 중앙 정렬 타이포, 스크롤 유도 화살표
2. **Grid**: 2열 비대칭, 이미지 비율 4:5 또는 3:4
3. **Typography**: Serif heading + Sans body 믹스
4. **Color**: 베이지/크림 베이스, 퍼플 액센트 최소화
5. **Animation**: Scroll-triggered fade-up, 0.8-1.2s duration
6. **Interaction**: Hover시 subtle scale (1.02) + brightness

---

## Version B: 클린/정보전달형 프로토타입

### Design System

```
Colors:
  primary:     #1A1A1A (Black)
  secondary:   #6B4E9B (Brand Purple)
  accent:      #4CAF50 (Success Green)
  background:  #FFFFFF
  surface:     #F9F9F9
  text:        #333333
  muted:       #888888
  border:      #E5E5E5

Typography:
  heading:     "Pretendard", sans-serif (semibold 600)
  body:        "Pretendard", sans-serif (regular 400)
  caption:     "Pretendard", sans-serif (light 300)

Spacing:
  section-y:   80px (desktop), 60px (mobile)
  container:   max-width 1200px, padding 24px
  grid-gap:    24px

Animation:
  duration:    0.3s - 0.5s
  easing:      ease-out
  hover:       background-color transition
```

### Page Components

#### HOME

```
┌─────────────────────────────────────────────────────────────────┐
│ 🎁 첫구매 최대 60% 할인 + 5,000원 쿠폰                    [X]   │
├─────────────────────────────────────────────────────────────────┤
│ [LOGO]    SHOP  SUPERFOOD  BRAND  COMMUNITY    🔍  👤  🛒      │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [HERO CAROUSEL - Auto 4s, Pagination Dots]                   │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │                                                         │  │
│   │   슈퍼푸드 원물에서 찾은                                 │  │
│   │   두피·헤어 솔루션, 프루티드                             │  │
│   │                                                         │  │
│   │   [제품 보러가기 →]                                     │  │
│   │                                                         │  │
│   │   ○ ● ○ ○ ○                                            │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   BEST SELLERS                               [전체보기 →]       │
│                                                                 │
│   ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐         │
│   │ [BEST]  │  │ [NEW]   │  │         │  │         │         │
│   │ [Image] │  │ [Image] │  │ [Image] │  │ [Image] │         │
│   │         │  │         │  │         │  │         │         │
│   │ 퍼플    │  │ 그린    │  │ 옐로우  │  │ 듀얼    │         │
│   │ 부스터  │  │ 클렌징  │  │ 믹스    │  │ 스타터  │         │
│   │ 샴푸    │  │ 샴푸    │  │ 트리트  │  │ 세트    │         │
│   │         │  │         │  │         │  │         │         │
│   │ #탈모   │  │ #두피   │  │ #손상   │  │ #입문   │         │
│   │ #두피탄력│  │ #진정   │  │ #단백질 │  │ #세트   │         │
│   │         │  │         │  │         │  │         │         │
│   │ ₩32,000 │  │ ₩28,000 │  │ ₩26,000 │  │ ₩48,000 │         │
│   │ ⭐ 4.8  │  │ ⭐ 4.7  │  │ ⭐ 4.9  │  │ ⭐ 4.8  │         │
│   └─────────┘  └─────────┘  └─────────┘  └─────────┘         │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   고민별 추천                                                   │
│                                                                 │
│   [탈모케어]  [두피케어]  [손상케어]  [보습케어]                │
│       ↑ active                                                 │
│                                                                 │
│   ┌───────────────────────────────────────────────────────┐   │
│   │  탈모가 걱정되시나요?                                   │   │
│   │                                                         │   │
│   │  퍼플부스터 샴푸가 탈락 모발 수를 25% 줄여드립니다.     │   │
│   │                                                         │   │
│   │  [제품 보기 →]                                         │   │
│   └───────────────────────────────────────────────────────┘   │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   OUR PROMISE                                                   │
│                                                                 │
│   ┌─────────────┐  ┌─────────────┐  ┌─────────────┐          │
│   │     🔬      │  │     🌱      │  │     ✓      │          │
│   │             │  │             │  │             │          │
│   │  임상 검증   │  │  비건 인증   │  │ 클린 포뮬러  │          │
│   │             │  │             │  │             │          │
│   │ 인체적용    │  │ 한국비건    │  │ 설페이트    │          │
│   │ 시험 완료   │  │ 인증원      │  │ 파라벤 FREE │          │
│   └─────────────┘  └─────────────┘  └─────────────┘          │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   SUPERFOOD STORY                           [더 알아보기 →]     │
│                                                                 │
│   ┌─────────────┐  ┌─────────────┐  ┌─────────────┐          │
│   │ [퍼플 원료] │  │ [그린 원료] │  │ [옐로우원료]│          │
│   │             │  │             │  │             │          │
│   │ Purple      │  │ Green       │  │ Yellow      │          │
│   │ Complex     │  │ Complex     │  │ Complex     │          │
│   │             │  │             │  │             │          │
│   │ 항산화·탄력 │  │ 진정·클렌징 │  │ 단백질·윤기 │          │
│   └─────────────┘  └─────────────┘  └─────────────┘          │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   실제 사용자 리뷰                                              │
│                                                                 │
│   ⭐ 4.8 평균 평점  |  1,234개 리뷰                            │
│                                                                 │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │ "두피 간지러움이 사라졌어요"  ★★★★★                    │  │
│   │ 김O희 | 퍼플부스터 샴푸 | 2025.01.20                    │  │
│   └─────────────────────────────────────────────────────────┘  │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │ "뿌리볼륨이 확실히 살아났어요"  ★★★★★                  │  │
│   │ 박O진 | 퍼플부스터 샴푸 | 2025.01.18                    │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
│                         [리뷰 더보기 →]                        │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [FOOTER - 4 Column]                                          │
│                                                                 │
│   SHOP       BRAND       SUPPORT      FOLLOW                   │
│   ────       ────        ────         ────                     │
│   전체상품    소개        공지사항      Instagram               │
│   BEST       철학        FAQ          Kakao                    │
│   NEW        클린뷰티    1:1문의                               │
│                                                                 │
│   ─────────────────────────────────────────────────────────    │
│   고객센터 1588-0000  |  cs@prooted.co.kr                      │
│   평일 10:00-17:00 (점심 12:00-13:00)                          │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

#### PDP (Product Detail Page)

```
┌─────────────────────────────────────────────────────────────────┐
│ 홈 > SHOP > 샴푸 > 퍼플부스터 샴푸                               │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌─────────────────────┐  ┌────────────────────────────────┐  │
│   │                     │  │  [BEST] [탈모완화]              │  │
│   │   [제품 이미지]      │  │                                │  │
│   │                     │  │  퍼플부스터 양파 샴푸           │  │
│   │                     │  │  Purple Booster Onion Shampoo  │  │
│   ├─────────────────────┤  │                                │  │
│   │ [썸] [썸] [썸] [썸] │  │  ⭐ 4.8 (1,234개 리뷰)         │  │
│   └─────────────────────┘  │                                │  │
│                            │  #탈모완화 #두피탄력 #비건인증   │  │
│                            │  #설페이트FREE                  │  │
│                            │                                │  │
│                            │  ₩32,000  →  ₩25,600          │  │
│                            │  첫구매 20% 할인                │  │
│                            │                                │  │
│                            │  용량: ○ 500ml  ○ 1000ml       │  │
│                            │  수량: [-] 1 [+]               │  │
│                            │                                │  │
│                            │  ┌────────────┐ ┌────────────┐│  │
│                            │  │ 장바구니    │ │ 바로구매   ││  │
│                            │  └────────────┘ └────────────┘│  │
│                            │                                │  │
│                            │  💜 찜하기  📤 공유하기        │  │
│                            └────────────────────────────────┘  │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [핵심 효능 - 3 Column Cards]                                  │
│                                                                 │
│   ┌─────────────┐  ┌─────────────┐  ┌─────────────┐          │
│   │ 탈락 모발   │  │ 두피 탄력   │  │ 클린 포뮬러  │          │
│   │   25%↓     │  │   18%↑     │  │             │          │
│   │             │  │             │  │ 설페이트    │          │
│   │ *인체적용   │  │ *인체적용   │  │ 파라벤 FREE │          │
│   │  시험 기준  │  │  시험 기준  │  │             │          │
│   └─────────────┘  └─────────────┘  └─────────────┘          │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   [TAB NAVIGATION]                                              │
│                                                                 │
│   [상품설명]  [성분정보]  [리뷰 1,234]  [Q&A 56]  [배송/교환]   │
│       ↑ active                                                 │
│                                                                 │
│   ─────────────────────────────────────────────────────────    │
│                                                                 │
│   [상세 이미지 콘텐츠]                                          │
│   - 핵심 성분 소개                                              │
│   - 사용법                                                      │
│   - 추천 대상                                                   │
│   - 함께 쓰면 좋은 제품                                         │
│                                                                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   함께 보면 좋은 제품                                           │
│                                                                 │
│   ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐         │
│   │ [Image] │  │ [Image] │  │ [Image] │  │ [Image] │         │
│   │ 옐로우  │  │ 그린    │  │ 에센셜  │  │ 헤어팩  │         │
│   │ 트리트  │  │ 샴푸    │  │ 루틴    │  │         │         │
│   │ ₩26,000 │  │ ₩28,000 │  │ ₩48,000 │  │ ₩35,000 │         │
│   └─────────┘  └─────────┘  └─────────┘  └─────────┘         │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Key Design Decisions (Version B)

1. **Hero**: 캐러셀 with dots, autoplay 4s, 명확한 CTA 버튼
2. **Grid**: 4열 균일, 이미지 비율 1:1
3. **Typography**: Sans-serif only, weight로 계층 구분
4. **Color**: 화이트 베이스, 퍼플 브랜드 컬러 적극 활용
5. **Animation**: 0.3s transitions, hover 시 배경색 변화
6. **Information**: 가격/리뷰/태그 상시 노출

---

## Component Specifications

### Shared Components

| Component | Version A | Version B |
|-----------|-----------|-----------|
| Header | 중앙 로고, 양분 메뉴 | 좌측 로고, 우측 유틸리티 |
| Promo Bar | 언더라인 링크 스타일 | 배경색 + X 닫기 |
| Product Card | 이미지 중심, 정보 최소 | 정보 풀 노출 (가격/리뷰/태그) |
| CTA Button | Ghost 스타일, 언더라인 | Solid 배경, 명확한 contrast |
| Footer | 미니멀 중앙 정렬 | 4컬럼 정보형 |

### Responsive Breakpoints

```
Desktop:   1200px+
Tablet:    768px - 1199px
Mobile:    < 768px
```

### Animation Specifications

**Version A**
```css
.fade-up {
  opacity: 0;
  transform: translateY(40px);
  transition: all 0.8s cubic-bezier(0.25, 0.1, 0.25, 1);
}
.fade-up.visible {
  opacity: 1;
  transform: translateY(0);
}
```

**Version B**
```css
.card:hover {
  background-color: #F5F5F5;
  transition: background-color 0.3s ease-out;
}
.button:hover {
  background-color: #5E3D8B;
  transition: background-color 0.2s ease;
}
```

---

## Trade-offs Accepted

| 결정 | Version A | Version B |
|------|-----------|-----------|
| 정보량 | 적음 (감성 우선) | 많음 (기능 우선) |
| 스크롤 | 길어질 수 있음 | 압축적 |
| 전환율 | 브랜딩 → 장기 LTV | 즉시 구매 유도 |
| 개발 복잡도 | 높음 (커스텀 애니메이션) | 중간 (표준 컴포넌트) |
| 로딩 속도 | 이미지 최적화 필요 | 비교적 가벼움 |

---

## Out of Scope

- 백엔드 API 설계
- 결제/주문 플로우 상세
- CRM/마케팅 자동화 연동
- 관리자 페이지
- SEO 기술적 구현 (별도 문서 참조)

---

## Implementation Steps

### Phase 1: Foundation
1. Design System 구축 (컬러, 타이포, 스페이싱)
2. 공통 컴포넌트 개발 (Header, Footer, Button, Card)
3. 레이아웃 그리드 시스템

### Phase 2: Core Pages
4. HOME 페이지 (Hero, Product Grid, Reviews)
5. PLP 상품목록 페이지
6. PDP 상품상세 페이지

### Phase 3: Content Pages
7. SUPERFOOD STORY 랜딩
8. BRAND/About 페이지
9. COMMUNITY (리뷰, FAQ)

### Phase 4: Transaction
10. 장바구니
11. 결제 플로우
12. MY PAGE

### Phase 5: Polish
13. 애니메이션 적용
14. 반응형 최적화
15. 성능 최적화

---

## Verification

- [ ] 두 버전 모두 site-components.md의 콘텐츠 완전 반영
- [ ] 데스크톱/태블릿/모바일 반응형 확인
- [ ] 접근성 기준 충족 (WCAG 2.1 AA)
- [ ] 페이지 로딩 3초 이내
- [ ] CTA 클릭 영역 44x44px 이상
- [ ] 전환 퍼널 각 단계 추적 가능

---

## Appendix: Cafe24 Skin Recommendations

| Version | 추천 스킨 | 참고 브랜드 |
|---------|----------|------------|
| A (감성) | skin90 또는 커스텀 | NARKA |
| B (정보) | skin8 또는 skin18 | ViveLab, Mintree |

---

*Generated: 2025-01-29*
*Based on: site-components.md, navigation.md, pages.md, reference analysis*
