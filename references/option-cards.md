# Option Cards — 대화창 옵션 카드 출고 템플릿

visualize-skill 절대규칙 4 (3·N×3 룰) 구현 레퍼런스.
형이 "시각화해줘·인포그래픽처럼·옵션 보여줘" 류 발화 시 본 템플릿으로 `mcp__visualize__show_widget` 1회 호출.

---

## 1. 규칙 요약

| 형 의도 | 카드 수 | 그리드 |
|---------|---------|--------|
| 시각화 위치 1개 (디폴트) | 3 | 1행 3열 |
| 시각화 위치 N개 (N≥2) | N×3 | N행 3열 |
| 명시 — "3군데 시각화" | 9 | 3행 3열 |
| 명시 — "10군데 시각화" | 30 | 10행 3열 |
| OPTIONS 모드 — 빠른 선택 | 3 | 1행 3열·논리 명세 ✗ |

**원칙**: 위치별로 3옵션은 **MECE**로 배치 (예: 정적/순환/선형 각 1개씩).

---

## 2. 카드 1장 5요소

| 요소 | 사양 |
|------|------|
| ① 번호+라벨 | "① Multi-Flywheel" — 1~2단어 |
| ② 소형 SVG 프리뷰 | viewBox="0 0 120 120" · 핵심 구조 1컷 · 무채색+액센트 1색 |
| ③ 1줄 설명 | 18자 내외 — "3루프 물림 · 시스템 가속" |
| ④ 위임 스킬 | "→ apple-canvas" 또는 "→ prism-design" 등 |
| ⑤ CTA | "'①번으로'라고 말씀" |

---

## 3. 위젯 HTML 표준 골격

```html
<style>
  .vs-grid { display:grid; gap:12px; padding:8px; }
  .vs-grid.g1 { grid-template-columns: repeat(3, 1fr); }
  .vs-grid.gN { grid-template-columns: repeat(3, 1fr); }
  .vs-row-label { grid-column: 1 / -1; font:600 11px ui-sans-serif,system-ui; letter-spacing:.08em; text-transform:uppercase; color:var(--text-secondary); padding:8px 4px 0; border-top:1px solid var(--border-default); }
  .vs-row-label:first-child { border-top:0; padding-top:0; }
  .vs-card { background:var(--bg-200); border:1px solid var(--border-default); border-radius:12px; padding:14px; display:flex; flex-direction:column; gap:8px; transition:transform .15s ease; }
  .vs-card:hover { transform:translateY(-2px); border-color:var(--accent-main-200); }
  .vs-num { font:700 11px ui-monospace,monospace; color:var(--accent-main-200); letter-spacing:.1em; }
  .vs-label { font:600 15px ui-sans-serif,system-ui; color:var(--text-100); }
  .vs-svg-wrap { background:var(--bg-100); border-radius:8px; padding:8px; display:flex; align-items:center; justify-content:center; min-height:96px; }
  .vs-svg-wrap svg { width:80px; height:80px; }
  .vs-desc { font:400 12px ui-sans-serif,system-ui; color:var(--text-200); line-height:1.4; }
  .vs-delegate { font:500 11px ui-monospace,monospace; color:var(--text-300); border-top:1px dashed var(--border-default); padding-top:6px; }
  .vs-cta { font:500 11px ui-sans-serif,system-ui; color:var(--accent-main-200); margin-top:auto; }
</style>

<div class="vs-grid g1">
  <!-- N행이면 각 행 위에 .vs-row-label 삽입 -->
  <div class="vs-card">
    <div class="vs-num">① OPTION</div>
    <div class="vs-label">Multi-Flywheel</div>
    <div class="vs-svg-wrap">
      <svg viewBox="0 0 120 120" xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-width="2">
        <circle cx="40" cy="50" r="22"/>
        <circle cx="80" cy="50" r="22"/>
        <circle cx="60" cy="86" r="22"/>
        <path d="M55 50 L65 50" stroke-linecap="round"/>
        <path d="M50 68 L55 78" stroke-linecap="round"/>
        <path d="M70 68 L65 78" stroke-linecap="round"/>
      </svg>
    </div>
    <div class="vs-desc">3루프 물림 · 시스템 가속</div>
    <div class="vs-delegate">→ apple-canvas / prism-design</div>
    <div class="vs-cta">'①번으로' 말씀</div>
  </div>
  <!-- 2·3번 카드 동일 골격으로 반복 -->
</div>
```

---

## 4. SVG 프리뷰 카탈로그 (20프레임)

각 프레임의 핵심 구조를 80×80 정사각에 1컷으로 압축.

### A. 순환·루프
- **Flywheel** — 4쿼터 원·화살표 시계방향
- **Loop** — 단일 큰 원·중간 화살표
- **Hook** — 4단계 원형 트리거·액션·보상·투자
- **Two-sided** — 두 원이 양쪽·중앙 거래선
- **Multi-Flywheel** — 3원 삼각 배치·교집점

### B. 선형·흐름
- **Funnel** — 4단 사다리꼴 점점 좁아짐
- **Bridge** — 좌우 박스·중간 화살표
- **Journey** — 물결선·5점·이모지 ✗
- **Value Chain** — 5단 박스 직선 연결

### C. 계층·구조
- **Layer** — 가로 3~4층 박스
- **Pyramid** — 삼각형 3단
- **Capability Stack** — 세로 4박스·상승 화살표
- **JTBD** — 사람 → Job → 결과 직선
- **Control Point** — 격자에 1점 highlight

### D. 분포·매핑
- **Matrix** — 2×2 사분면
- **Positioning Map** — 가로세로 축 + 4점
- **NSM 트리** — 상단 1·중단 3·하단 5 트리
- **Unit Economics 트리** — 상단 LTV/CAC·하단 분해

### E. 관계망·재편
- **Ecosystem Map** — 중앙 노드 + 4방 노드
- **Unbundling** — 큰 박스 → 4개 분리 박스

---

## 5. 9카드 (3위치) 패턴

```
위치 1: BP §market — Funnel · Bridge · Journey
위치 2: BP §moat   — Capability Stack · Control Point · Multi-Flywheel
위치 3: BP §growth — Flywheel · Loop · Two-sided
```

각 위치는 **MECE** (1개 정적 + 1개 순환 + 1개 선형 권장).

---

## 6. 30카드 (10위치) 패턴

10페이지 IR을 가정한 위치별 옵션:

| 위치 | 주제 | 옵션 1 | 옵션 2 | 옵션 3 |
|------|------|--------|--------|--------|
| p1 cover | 본질 1컷 | JTBD | Bridge | Unbundling |
| p2 market | 시장 크기·결 | Value Chain | Ecosystem | Positioning |
| p3 problem | 어디서 깨짐 | Funnel | Journey | Bridge |
| p4 solution | 답의 구조 | Layer | Capability Stack | JTBD |
| p5 product | 작동 원리 | Hook | Loop | Flywheel |
| p6 moat | 왜 우리 이김 | Control Point | Capability Stack | Multi-Flywheel |
| p7 GTM | 어떻게 퍼짐 | Loop | Funnel | Two-sided |
| p8 unit economics | 돈 되나 | UE 트리 | NSM 트리 | Pyramid |
| p9 traction | 성장 패턴 | Flywheel | Funnel | Bridge |
| p10 ask | 자본 → 어디 가치 | Bridge | Capability Stack | NSM 트리 |

---

## 7. CTA 후속 흐름

형이 "1번으로" 말하면:
1. visualize-skill OPTIONS 모드 종료
2. 선택된 프레임에 대해 DESIGN 모드로 진입 → 노드·엣지 명세
3. 풀 시각 출고는 카드의 ④ 위임 스킬 호출

위임 매핑:
- 1page 강도·랜딩 → `apple-canvas`
- 장문보고서·키노트덱 → `prism-design`
- 매거진·인터뷰 톤 → `editorial-design`
- 매니페스토·Supreme 톤 → `box-cut-design`
- 카탈로그·model card → `teenage-design`

---

## 8. 안티패턴

| 함정 | 대응 |
|------|------|
| 3카드 다 같은 그룹(예: 다 순환) | MECE 위반 — 정적/순환/선형 섞기 |
| SVG 없이 텍스트만 | 절대규칙 4 위반. 80×80 SVG 필수 |
| 30카드인데 위치 라벨 누락 | 위치별 row-label 헤더 필수 |
| 풀 HTML 페이지로 출고 | 풀시각은 위임 스킬. 본 스킬은 카드 위젯만 |
| 카드 4개 이상 한 위치에 | 3개 고정. 더 보고 싶으면 형이 "다른 옵션 3개" 추가 요청 |
