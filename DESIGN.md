# meow-letter DESIGN.md

단일 페이지 인터랙티브 생일 편지. Type Mania 'Charmer' 리소그래프 포스터 세계를 사용자 레퍼런스로 고정(brief-pinned)한 Experience 서피스.

## 세계
- **구성**: 풀블리드 파스텔 패널을 포스터 한 장씩 세로로 쌓은 연작. 각 패널 하단에 헤어라인 + 영문/붓글씨 라벨 바(`MEOW MANIA ··· 편지 No.1`).
- **팔레트**: 세이지 `#d8dcc2` · 민트 `#dcebe2` · 라일락 `#e2d3ea` 순환, 잉크 `#211e19`. 전면 고정 종이 그레인 오버레이(feTurbulence, multiply).
- **일러스트**: 인라인 SVG 스트로크 드로잉(앉은 고양이·그루밍·노는 고양이·날개 고양이·토끼·별·꽃·케이크·실뭉치)에 `feDisplacementMap` 스크래치 필터(`#rough`/`#rough2`)로 손그림 질감. 모든 도상은 이 문법으로만 추가한다.
- **타이포**: 본문 Bookk Gothic Lt/Bd(눈누 jsdelivr woff2), 한글 디스플레이 Nanum Brush Script(기울인 초대형, 포스터 타이틀), 영문 라벨 Grenze Gotisch. 다른 페이스 추가 금지.

## 모션
- 엔터(줄바꿈) 단위 = 스크롤 리빌 1회. IntersectionObserver(threshold .15), 1회성.
- 리빌 3종: rise+deblur(`.reveal`), 도장 스탬프(`.reveal--stamp`, 타이틀·따랑해), 폴짝(`.reveal--pop`, 소품).
- 상시 모션: 별 twinkle, 소품 wiggle, 촛불 flick, 피날레 날개 고양이 fly. `prefers-reduced-motion` 전부 무효화.
- 인트로 봉투: 클릭 → 뚜껑 rotateX + 편지 상승 → 오버레이 페이드, 스크롤 잠금 해제(JS로만 잠금; no-JS는 인트로 숨김).
- 피날레 버튼 → 캔버스 색종이(파스텔 꽃잎 + 잉크 별, dpr≤2).

## 규칙
- 내용(편지 문구)은 한 글자도 수정 금지 — 오탈자·말투 전부 의도된 원문.
- 무료 리소스만: 웹폰트 CDN + 인라인 SVG. 빌드 도구·외부 JS 라이브러리 없음.
- 배포: GitHub Pages (oeozinni/meow-letter), `noindex` 유지.
