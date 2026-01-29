# 프로토타입 이미지 배치 계획

## 이미지 소스 경로
`/Users/say/프루티드/소개/Image/촬영본/`

## 이미지 매핑

### 제품 이미지
| 제품 | 소스 폴더 | 대표 이미지 |
|------|-----------|-------------|
| 퍼플부스터 양파 샴푸 | 퍼플샴푸 | 260123-prooted57601.jpg |
| 그린클렌징 케일 샴푸 | 그린샴푸 | 260123-prooted57595.jpg |
| 바나나에그 트리트먼트 | 옐로우트리트먼트 | 260123-prooted57608.jpg |

### 세트 이미지
| 세트명 | 소스 폴더 | 대표 이미지 |
|--------|-----------|-------------|
| 듀얼 스타터 (퍼플+그린) | 퍼플+그린 | 260123-prooted57620.jpg |
| 에센셜 루틴 (퍼플+옐로우) | 퍼플+그린+옐로우 | 260123-prooted57627.jpg |
| 딥클린 & 실키 (그린+옐로우) | 퍼플+그린+옐로우 | 260123-prooted57661.jpg |
| 프루티드 패키지 (전체) | 퍼플+그린+옐로우 | 260123-prooted57963.jpg |

### 감성/브랜드 이미지
| 용도 | 소스 폴더 | 이미지 |
|------|-----------|--------|
| 히어로 배경 | 감성컷 | 260123-prooted58075.jpg |
| 브랜드 페이지 | 감성컷 | 20260123_152911.jpg |
| 스토리 페이지 | 감성컷 | 20260123_153241.jpg |

## 수정 대상 페이지

### Version A
- [ ] index.html - 히어로 이미지
- [ ] shop/index.html - 제품 3개 + 세트 4개
- [ ] shop/purple-booster.html - PDP 갤러리
- [ ] shop/green-cleansing.html - PDP 갤러리
- [ ] shop/yellow-mix.html - PDP 갤러리
- [ ] story/index.html - 라인별 이미지
- [ ] story/purple.html - 제품 이미지
- [ ] story/green.html - 제품 이미지
- [ ] story/yellow.html - 제품 이미지
- [ ] brand/index.html - 브랜드 이미지

### Version B
- [ ] index.html - 히어로/제품 이미지
- [ ] shop/index.html - 제품 4개 + 세트 4개
- [ ] shop/purple-booster.html - PDP 갤러리
- [ ] shop/green-cleansing.html - PDP 갤러리
- [ ] shop/yellow-mix.html - PDP 갤러리
- [ ] story/index.html - 라인별 이미지
- [ ] story/purple.html - 제품 이미지
- [ ] story/green.html - 제품 이미지
- [ ] story/yellow.html - 제품 이미지
- [ ] brand/index.html - 브랜드 이미지

## 이미지 경로 설정
- Version A/B index.html에서: `../소개/Image/촬영본/[폴더]/[파일명]`
- Version A/B shop/에서: `../../소개/Image/촬영본/[폴더]/[파일명]`
- Version A/B story/에서: `../../소개/Image/촬영본/[폴더]/[파일명]`
- Version A/B brand/에서: `../../소개/Image/촬영본/[폴더]/[파일명]`

## 작업 순서
1. Version A 메인 페이지 이미지 교체
2. Version A Shop 페이지 이미지 교체
3. Version A PDP 페이지 이미지 교체
4. Version A Story/Brand 페이지 이미지 교체
5. Version B 동일 작업 반복
