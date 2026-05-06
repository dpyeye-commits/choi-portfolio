# 최재용 (Jaeyong Choi) 포트폴리오 — 다크 럭셔리 시네마틱

> 사용자 본인 다중 페르소나 통합 포트폴리오.
> 기존: https://dpyeye.wixsite.com/my-site-1 (Wix 미니멀·© 2021·Director of Photography만)
> 리빌드: 박사 + 교수 + 사업가 + 크리에이터 + 촬영감독 풀스택 권위 통합

---

## 디자인 토큰

### 컬러 (다크 럭셔리)
- **배경**: `#0A0A0C` (오프블랙·진한 검정 X 너무 plain)
- **카드**: `#13131A` (한 단계 밝은)
- **텍스트 메인**: `#F4F1EA` (워밍 화이트 — 차가운 #FFF X)
- **텍스트 서브**: `#A8A39A` (워밍 그레이)
- **액센트 골드**: `#C9A961` (샴페인 골드 — 천박한 노랑 X)
- **액센트 골드 hover**: `#E8C77E`
- **시네마 레드** (강조 — Director 정체성): `#A52A2A` (deep)
- **라인**: `#2A2A33`

### 타이포 (다중 권위 페어링)
- **헤드**: **Cormorant Garamond** (serif·박사·학술 권위) + Variable Pretendard (한국어 헤드)
- **본문**: **Pretendard Variable** (한국어·모던)
- **숫자·연도·랭킹**: **Cormorant SC** (Small Caps · 클래식)
- **모노**: **JetBrains Mono** (코드·스킬)

### 그림자 (다층 — AI틱 단일 그림자 X)
```
--shadow-1: 0 1px 2px rgba(0,0,0,0.4), 0 4px 12px rgba(0,0,0,0.3);
--shadow-2: 0 1px 2px rgba(0,0,0,0.5), 0 4px 12px rgba(0,0,0,0.4), 0 16px 48px rgba(201,169,97,0.10);
--shadow-gold: 0 0 0 1px rgba(201,169,97,0.3), 0 8px 24px rgba(201,169,97,0.15);
```

### 그라디언트 (단조 X · noise 적용)
- 시네마틱: `linear-gradient(135deg, #0A0A0C 0%, #1A1A24 50%, #0A0A0C 100%)` + SVG noise
- 골드 액센트: `linear-gradient(135deg, #C9A961 0%, #E8C77E 100%)`

---

## 9 섹션 절대 룰

| # | 섹션 | 의도 |
|---|---|---|
| 1 | Hero (시네마틱 풀스크린) | 권위 즉시 — 한국어 + 영어 이름 + 5 페르소나 |
| 2 | About (다중 권위 통합) | 박사·교수·사업가·크리에이터·촬영감독 5 카드 |
| 3 | Showreel (영상 갤러리) | Director of Photography 핵심 — Vimeo·YouTube 임베드 |
| 4 | Academic (박사·논문·발표) | 박사 권위 — 영상치유 연구·APA 7 인용 |
| 5 | Teaching (강의 학과) | 평택대·중부대 — 영상디자인·엔터테인먼트 |
| 6 | Business (GTIA·매주영상·인프런) | 사업가 권위 — B2B 텍스타일·1인 SaaS·강의 |
| 7 | Channels (영상치유lab·경제학) | 크리에이터 — YouTube 5+1 채널 |
| 8 | Tools·Skills (사용자 무기고) | 100+ AI 도구 풀스택 |
| 9 | Contact + 메일링 | 다중 채널 + 박사·강의·사업 분리 폼 |

---

## AI틱 안티패턴 6가드 (영구)

| # | 안티패턴 | 가드 |
|---|---|---|
| 1 | 보라/민트 | **샴페인 골드 #C9A961** + 시네마 레드 #A52A2A |
| 2 | 단일 그림자 | 3층 + gold glow |
| 3 | 동일 폰트 | Cormorant + Pretendard + JetBrains Mono 페어링 |
| 4 | 정적 페이지 | reveal IntersectionObserver + parallax + cinematic transitions |
| 5 | 단조 그라디언트 | 다중 + SVG noise |
| 6 | 균일 그리드 | 비대칭 + bento + cinematic full-bleed |

---

## 박사 본업 가드 (영구)

- **임상 단정 X** (영상치유 콘텐츠 카피)
- **자살 한국 미디어 가이드** 영구
- **트라우마 트리거 안전**
- **APA 7 한국어 인용** 학술 섹션 영구
- **자본시장법 가드** — INV 페르소나 X (포트폴리오에 주식 X)

---

## 모바일 우선

- 360px (한국 표준) → 768px → 1280px → 1920px
- Hero: 모바일 vertical full-bleed → 데스크탑 cinematic 16:9
- 메뉴: 모바일 햄버거 → 데스크탑 sticky horizontal
- 작품 갤러리: 모바일 1열 → 태블릿 2열 → 데스크탑 3열 비대칭

---

*기록: 2026-05-06 | 사용자 무기고 SKILL.md (landing-page-30min) 표준 준수 + 사용자 본인 다중 페르소나 통합*
