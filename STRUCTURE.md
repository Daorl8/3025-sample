# STRUCTURE · 3025-sample

```
3025-sample/
├─ index.html                 단일 파일 (CSS·JS 인라인)
├─ wrangler.toml              name = 3025-sample → 3025-sample.lgt3232.workers.dev
├─ .assetsignore              img/·문서·index_*.html·미사용 파일 배포 제외
├─ tf-instrument.woff2        영문 제목 (Instrument Serif 정체, 라틴만)
├─ tf-instrument-italic.woff2 영문 제목 이탤릭 (앰버색 강조 줄)
├─ tf-pretendard.woff2        한글·본문 (Pretendard 300–600, 사용 글자만 → 글자 추가 시 재생성)
├─ tf-logo.webp               두 얼굴 선화 로고 (크림, 투명)
├─ tf-*.webp                  사진 24장 (room·turntable·wall = 히어로 크로스페이드)
├─ favicon.png / og-3025.jpg
├─ img/                       다올 제공 원본 118장 (배포 제외)
└─ CHANGELOG.md / STRUCTURE.md
```

## 섹션 순서 (v0.2 흑백)
헤더(`#head`, 스크롤 시 `.solid`) → 히어로(`#slides` + `#onair`) → `#about`(간판 재현 `.sign` + 소개글) → `#side-a`(글 고정 + 사진 묶음) → `#side-b`(`.full` 사진 가득 + `.row4`) → `#collection`(`.strip`은 wrap 밖) → `#studio`(사진 반 · 글 반) → `#visit` → 푸터.
- 되돌리기: `index_v011_amber.html` = 직전 금색 · 갈색 버전(CHANGELOG v0.2 참고).
- 사진 채도: `main img:not(.logo){ filter:saturate(.6) … }` 한 줄. 지우면 원래 색.

## 영업시간 수정 (3곳)
1. 스크립트 `plan` (분 단위: 7:30=450, 14:30=870, 17:00=1020, 22:00=1320 · 0=일 … 6=토)
2. `#visit .hours` 표 + Side A · Side B의 `.times`
3. head JSON-LD `openingHoursSpecification`

## 색 규칙
앰버 `--amber`은 강조 줄(이탤릭) · 버튼 · 작은 표시에만. 글자 기본은 크림, 보조는 `--soft`.

## 폰트 재생성
`pyftsubset … --name-IDs='*' --name-languages='*' --name-legacy` (LESSONS §24). Pretendard는 Variable을 instancer로 wght 300–600 자른 뒤 서브셋.
