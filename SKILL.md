---
name: one-shot-graph
description: |
  복잡한 사업·문제·상황을 한 장의 작동원리 그림으로 압축. 20프레임 + HTML 정적 시제품. **MOTION OFF — 정적만 출력, 템플릿은 보존.**
  P1: 원샷, 원샷그래프, 원그래프, 한장그래프, 한장프레임, 1장시각화, 사업본질그림, 작동원리, 플라이휠, 퍼널, Hook, Journey맵, Two-sided, Multi-Flywheel, Unit Economics트리, NSM트리, Capability Stack, Control Point, JTBD.
  P2: 그려줘, 한장으로, 시각화해줘, draw, visualize.
  P3: one-page diagram, framework visualization.
  P5: .html로, .md로.
  NOT: 일반차트(→design-skill), 디자인스타일링(→apple-design-style), UI설계(→ui-action-designer).
---

# One-Shot Graph

복잡한 현실을 **하나의 작동원리로 압축한 한 장 그림**(원샷그래프·한장그래프·한장프레임·시각화프레임·1장시각화·사업본질그림)을 산출. 20프레임 카탈로그 + HTML 시제품. Journey맵·플라이휠·퍼널 등 포함. 페이퍼엔진·디자인스킬은 무수정 융합.

> **⚠️ MOTION_MODE = OFF (현재 고정)**
> 시각화 안정화 단계 — 모션 작업은 당분간 수행하지 않음. 템플릿·motion-guide·절대규칙 등 자료는 전량 유지(재가동 대비). 출력물은 **정적 HTML/SVG만** 산출.

---

## 절대 규칙 (5개)

| # | 규칙 | 이유 |
|---|------|------|
| 1 | **본질 우선** — "이 사업·상황의 본질이 무엇인가" 답이 먼저, 프레임은 답에 맞춰 선택. 프레임이 본질을 강요하면 FAIL | 미사여구·도식미 거부 (형의 도그마) |
| 2 | **MOTION OFF (현재 고정)** — `@keyframes`·`animation`·`transition`(색/투명도 호버 제외) **출력 금지**. 모든 프레임 정적 렌더. 과거 규칙("모션은 본질 5프레임에만") 동결 — 재가동 시 복원 | 시각화 안정화 단계, 모션 품질 미검증 |
| 3 | **paper-engine·design-skill·apple-* 무수정** — one-shot-graph는 HTML 블록 일방향 공급자. 다른 스킬 본문 한 줄도 안 건드림 | 융합 충돌·이원 라우팅 차단 |
| 4 | **prefers-reduced-motion 동결** — MOTION OFF 상태라 실효 없음. 재가동 시 복원 (미디어 쿼리 폴백 필수, WCAG 2.1 AA) | 접근성·인쇄·옵시디언 호환 |
| 5 | **단일 .html 파일 디폴트** — CDN 0개 우선. D3·GSAP 등 외부 의존은 옵션이며 명시 호출시만 | github-deploy·옵시디언·이메일 호환성 |

---

## 실행 흐름

```
① 본질 질문 → ② 프레임 선택 → ③ 모드 분기 (DIAGNOSE/DESIGN/RENDER)
 → (RENDER 시) 디자인 스킬 선택·발동 → ③.5 모션 제거 훅 (@keyframes·animation grep 제거 + apple 병용 시 alias shim 주입) → ④ 정적 HTML 산출
```

### ① 본질 질문 (7대 질문 라우터)

| 질문 | 후보 프레임 |
|------|------------|
| 왜 존재? | JTBD |
| 왜 성장? | Flywheel · NSM 트리 · Multi-Flywheel |
| 왜 계속 쓰지? | Hook Model |
| 왜 돈 되지? | Unit Economics 트리 |
| 왜 우리가 이김? | Capability Stack · Control Point |
| 어디서 깨짐? | Funnel · Journey Map |
| 시장 어떻게 바꿈? | Value Chain · Unbundling |

→ 상세 카탈로그: `references/frames-catalog.md`

### ② 프레임 선택 (20프레임 3티어)

**MOTION OFF 상태** — 아래 "본질 모션" 컬럼은 **재가동용 참고**. 현재는 20프레임 전부 **정적 렌더**.

| 티어 | 프레임 | 본질 모션 (동결·참고) |
|------|--------|----------|
| **MOTION 필수 (5)** | 플라이휠·루프·퍼널·브리지·Multi-Flywheel | 회전·순환·흐름·전환·다중회전 |
| **MOTION 권장 (7)** | Hook·Two-sided·Journey·NSM트리·Unit Economics·가치사슬·생태계맵 | 펄스·양방향·감정곡선·드릴다운·진행 |
| **STATIC OK (8)** | 레이어·피라미드·매트릭스·포지셔닝·JTBD·Capability·Unbundling·Control Point | 호버 인터랙션만 |

→ 분류 근거: `references/frames-catalog.md` (출처·실증연구 포함)

### ③ 모드 분기

| 모드 | 트리거 | 산출 |
|------|--------|------|
| **DIAGNOSE** | "어떤 프레임 써야?", 상황만 입력 | 적합 프레임 1~3개 후보 + WHY 1줄씩 |
| **DESIGN** | 프레임 명시 + 빈 슬롯 채우기 요청 | 노드·엣지·축 명세 (md 표) |
| **RENDER** | 데이터 + 프레임 명시 | **디자인 스킬 선택 발동** → HTML 1장 (정적, 템플릿 호출) |

### ④ 산출 분기 매트릭스

| 분기 | 적용 | 용도 |
|------|------|------|
| HTML 단독 | one-shot-graph만 | 정적 1장·github-deploy (MOTION OFF) |
| md 인라인 | mermaid·div 폴백 | 옵시디언 reading mode (전 프레임 OK — 정적) |
| md+HTML 동시 | 본문 = md, 1장 그림 = .html 링크/iframe | paper-engine 산출물 융합 |
| +PDF | 정적 캡처 (현 상태 그대로) | IR·심사 정본 |

→ 분기 결정 룰: `references/output-routing.md`

---

## paper-engine·design-skill·apple-* 융합 (무수정)

**원칙:** one-shot-graph가 **HTML 블록·md 신호 발신** → 다른 스킬이 자동 cascade로 소비. 다른 스킬 SKILL.md 직접 검증·수정 ✗.

### 🎨 RENDER 전 디자인 스킬 선택 (필수)

**MOTION OFF = 시각 위계 전부를 디자인이 감당** → RENDER 착수 전 **디자인 스킬 1개 반드시 발동**. 스킬 미선택 RENDER = FAIL.

| 선택 | 기준 | 발동 스킬 |
|------|------|----------|
| **apple-box-design** | 박스·벤토·카드 위주 프레임 (레이어·피라미드·매트릭스·포지셔닝·JTBD·Capability Stack·Control Point·Unbundling) / IR·BP·임원보고 톤 / 블랙-화이트 극단 weight 원할 때 | `Skill("apple-box-design")` |
| **design-skill** | 노드+엣지 중심 프레임 (플라이휠·루프·퍼널·브리지·Multi-Flywheel·Hook·Two-sided·**Journey Map**·NSM트리·Unit Economics·가치사슬·생태계맵) / C9 시각화 라우팅 필요 / young-playful·일반 톤 | `Skill("design-skill")` |

**판단 순서:**
1. 프레임 종류 확인 (박스형 vs 관계형)
2. 톤·맥락 확인 (IR/임원=애플박스, 그 외=디자인)
3. 애매하면 **형에게 1회 역질문** ("애플박스 톤 / 디자인스킬 톤 중 어느 쪽?")
4. 선택 후 해당 스킬 발동 → HTML 블록 산출
5. **apple-box-design 병용 시 CSS 변수 alias shim 자동 주입** (`--osg-*` ↔ `--label-*`) → `references/skill-fusion.md` 참조

| 스킬 | 융합 방식 |
|------|----------|
| **paper-engine** | 산출물에 `[FRAME: flywheel](./frame_flywheel.html)` 링크 삽입 또는 V1~V10 시각소스 태깅 → design-skill C9 자동 발동 |
| **design-skill** | C9 시각화 라우팅이 자동 처리. one-shot-graph는 `<svg class="osg-flywheel">` 클래스만 발신 |
| **apple-design-style·apple-box-design** | `var(--label-info/caption/decor)` 3티어 변수 + `.dark` 클래스로 자동 역매핑 |
| **obsidian-markdown** | `![[frame.html]]` embed · `> [!info]` callout 활용. Reading mode 한계 시 외부 링크 |
| **github-deploy** | `.html` 산출물 단독 또는 `.md`+`.html` 동시 배포 (호출명 트리거) |
| **html-div-style** | div 래퍼 1층 + one-shot-graph 콘텐츠 2층 (충돌 ✗, 분리) |

→ 충돌 회피 룰·신호 명세: `references/skill-fusion.md`

---

## HTML 구현 표준 (정적)

**현재 MOTION OFF** — `@keyframes`·`animation` 출력 금지. 아래 표준은 정적 렌더 기준.

**디폴트 스택**: HTML5 + 인라인 SVG + 정적 CSS. CDN 0개.

**필수 패턴 (정적)**:
1. `viewBox` + `preserveAspectRatio` 반응형
2. 색상 3티어: `--osg-info` (정보), `--osg-caption` (라벨), `--osg-decor` (장식)
3. 색상/투명도 `:hover` 전환만 허용 (transform 애니 ✗)
4. 레이아웃·타이포·선 굵기·여백으로 위계 표현 (모션 대체)

**모션 관련 (동결·재가동용 보존)**:
- `transform-origin: center` · `prefers-reduced-motion` 폴백 · 본질 모션 1개 원칙
- D3.js (CDN, force layout 한정) — 현재 비활성
- GSAP·Lottie·Anime.js: 영구 금지

→ 모션 상세 가이드(동결·참고): `references/motion-guide.md`
→ 시제품 6종(모션 포함, 재가동 대비 보존): `assets/templates/{flywheel,funnel,hook,journey,two-sided,multi-flywheel}.html` — **현재 렌더 시 모션 제거·정적 추출하여 사용**

---

## 안티패턴 (FAIL 즉시)

| 안티패턴 | 대응 |
|----------|------|
| **현재 턴에 모션 출력** (`@keyframes`·`animation` 포함) | MOTION OFF 위반 → 정적 재생성. 호버 색/투명도 전환만 허용 |
| **템플릿을 모션 포함 그대로 복사** | 렌더 전 `@keyframes` 블록·`animation:` 속성 제거 의무 |
| **디자인 스킬 발동 없이 RENDER** | apple-box-design 또는 design-skill 중 1개 선택·발동 후 착수 (MOTION OFF = 시각 위계 = 디자인 의존) |
| 노드 15개+ 한 장에 욱여넣기 | 한 장 = 5~9 노드 (의사결정), 9~15 (시스템맵) 상한 |
| GSAP·Lottie 의존성 추가 | 디폴트 = CDN 0개. 의존성 명시 호출 없으면 ✗ |
| paper-engine SKILL.md 수정 | 무수정 원칙 위반. 신호·링크만 발신 |
| 옵시디언 Reading mode SVG 모션 강요 | (동결·참고) Reading mode 한계 인정 → 외부 호스팅 또는 정적 폴백 |
| 색상 인라인 (`style="color:red"`) | `var(--osg-*)` 경유 필수 (apple 융합) |

---

## 예시

**입력**: "C8 사업 본질을 한 장으로 보여주고 싶어"
**DIAGNOSE 출력**:
```
✅ 결론 · Multi-Flywheel 1순위 (크리에이터·팬·플랫폼 3루프 상호강화)
대안: Two-sided Market (단일 양면), Capability Stack (역량 강조)
```

**입력**: "Hook Model로 우리 앱 그려줘. 트리거=푸시, 액션=콘텐츠소비, 보상=좋아요, 투자=북마크"
**RENDER 출력**: `assets/templates/hook.html` 호출 → **모션 제거·4단계 순환 정적 HTML 1장** (MOTION OFF)

→ 추가 예시: `references/examples.md`

---

## Gotchas

| 함정 | 대응 |
|------|------|
| "예쁘게만 그려줘" 요청 | 본질 질문 1회 역질문 후 진행 (절대규칙 1) |
| "움직이게/역동적으로" 요청 | **현재 MOTION OFF 고지 후 정적 렌더**. 레이아웃·색·굵기·호버로 위계 표현 (절대규칙 2) |
| 템플릿 그대로 복사해 모션 함께 출력 | 렌더 직전 `@keyframes`·`animation:` 속성 제거 체크 |
| paper-engine 안에서 시각화 직접 그리기 시도 | one-shot-graph가 HTML 블록만 공급, paper-engine이 md 본문 담당 |
| 옵시디언에서 SVG 애니가 안 보임 | (동결) MOTION OFF 상태라 이슈 없음 |
| 같은 프레임 여러 후보 답답 | DIAGNOSE 모드는 1순위 명시 + 대안 1~2 (3개 초과 ✗) |
| 노드 데이터 부족 | 빈 슬롯 명시 후 DESIGN 모드 안내 ("이 자리에 뭐가 들어가야?") |

---

## 트리거 라우팅 (자동발동 5축)

1. **본질 질문** ("이 사업 뭐임", "왜 이김", "왜 성장")
2. **압축 요청** ("한 장으로", "한 그림으로", "원샷", "원그래프")
3. **진단 요청** ("어디서 새냐", "왜 안 돌아오냐")
4. **전략 발표 직전** (BP·IR·임원보고)
5. **20프레임 명사** 등장 (플라이휠·퍼널·Hook 등)

→ NOT: 일반차트·인포그래픽·디자인스타일링 → design-skill로 위임
