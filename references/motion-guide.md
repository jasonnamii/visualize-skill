# Motion Guide — HTML+SVG+CSS 표준

> ## ⚠️ [FROZEN] — MOTION OFF 상태
> 본 가이드는 **재가동용 참고자료**. 현재 one-shot-graph는 MOTION OFF 고정이며 아래 `@keyframes`·`animation` 예시 코드를 **출력물에 그대로 넣으면 안 됨**. 절대규칙 2 위반 = FAIL. 렌더 시점에는 정적 HTML만 산출.
>
> **재가동 시:** SKILL.md 절대규칙 2 해제 + 템플릿 주석 블록 복원 + 본 배너 삭제.

---

**디폴트 스택** (동결·참고): HTML5 + 인라인 SVG + CSS @keyframes. CDN 0개.

---

## 5대 필수 패턴

### 1. transform-origin 명시
SVG 기본 origin = viewport (0,0). 회전 시 반드시 명시:
```css
.osg-flywheel {
  transform-origin: center center;
  animation: rotate 20s linear infinite;
}
@keyframes rotate { to { transform: rotate(360deg); } }
```

### 2. viewBox + preserveAspectRatio 반응형
```html
<svg viewBox="0 0 400 400" preserveAspectRatio="xMidYMid meet"
     style="width:100%; height:auto; max-width:600px;">
```

### 3. prefers-reduced-motion 폴백 (필수)
```css
@media (prefers-reduced-motion: reduce) {
  .osg-flywheel { animation: none; }
  .osg-pulse { animation: none; opacity: 1; }
}
```

### 4. 모션 1개 원칙
한 프레임 = 본질 모션 1개. 부가 깜빡임·바운스·페이드 ✗.
- 플라이휠: 회전 1개만
- 퍼널: 흐름 1개만
- Hook: 펄스 1개만 (자동재생 X, 사용자 트리거)

### 5. 색상 3티어 변수
```css
:root {
  --osg-info: #1a1a1a;       /* 정보 - 본질 데이터 */
  --osg-caption: #6b7280;    /* 캡션 - 라벨·설명 */
  --osg-decor: #e5e7eb;      /* 장식 - 가이드라인 */
}
.dark, [data-theme="dark"] {
  --osg-info: #f5f5f5;
  --osg-caption: #9ca3af;
  --osg-decor: #374151;
}
```

→ apple-design-style·apple-box-design 변수 자동 호환.

---

## 의존성 룰

| 라이브러리 | 사용 | 사유 |
|-----------|------|------|
| HTML+SVG+CSS | **디폴트** | 의존성 0, 모든 환경 호환 |
| D3.js (CDN 1줄) | 옵션 — 생태계맵·Multi-Flywheel·Two-sided force layout | 8노드+ 동적 배치 필요시만 |
| GSAP | **금지** | 단순 회전·펄스에 과잉 |
| Lottie | **금지** | 외부 JSON 의존, github-deploy 호환성 ✗ |
| Anime.js | **금지** | CSS로 충분 |

---

## 옵시디언 호환

- **Edit mode**: SVG·CSS 애니 정상 작동
- **Reading mode**: 알려진 제약 — `<animate>` SMIL 미지원, CSS keyframe 일부 미작동
- **해결책**:
  1. Local HTML Embed 플러그인 사용
  2. github-deploy로 외부 호스팅 → wikilink로 외부 링크
  3. 정적 SVG 폴백 첨부

---

## github-deploy 호환

- 단일 .html 파일 (CSS·JS·SVG 인라인) → 그대로 배포
- D3 사용 시 CDN 1줄 (`https://d3js.org/d3.v7.min.js`)
- 인쇄용 미디어 쿼리 권장:
```css
@media print { .osg-flywheel { animation: none; } }
```

---

## 안티패턴 5개

| 안티패턴 | 결과 | 대응 |
|----------|------|------|
| `<animate>` SMIL | 옵시디언·일부 브라우저 미작동 | CSS @keyframes 사용 |
| `transform-origin` 미설정 | viewport (0,0) 기준 회전 = 화면 밖 | `center center` 명시 |
| `prefers-reduced-motion` 미체크 | WCAG 2.1 AA 위반 | 미디어 쿼리 폴백 필수 |
| 무한 루프 자동재생 | 인지 부하·접근성 | 사용자 트리거 또는 1회 재생 |
| 인라인 색상 (`#ff0000`) | apple 융합 깨짐·다크모드 ✗ | `var(--osg-*)` 사용 |

---

→ 원본 리서치: `VAULT/_skills research/one-shot-graph/2026-04-22_B_html-implementation.md`
→ 시각화 원칙: `VAULT/_skills research/one-shot-graph/2026-04-22_C_visualization-best-practices.md`
