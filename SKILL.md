---
name: visualize-skill
version: 1.0
description: |
  복잡한 사업·문제의 **본질을 한 프레임으로 압축**하는 논리 엔진. 20프레임 기반 본질질문→프레임선택→슬롯명세. 시각 산출 ✗. 트리거: 시각화스킬, 시각화, visualize-skill, visualize skill, 인포그래픽, infographic, 원샷, 원샷그래프, 한장프레임, 본질프레임, 프레임선택, 프레임진단, 작동원리, 플라이휠, 퍼널, Hook, Journey, Two-sided. NOT: 시각산출(→apple-canvas·prism-design·editorial-design·box-cut-design·teenage-design), UI(→ui-designer), 산업분석(→biz-skill).
---

# Visualize Skill — 비주얼라이즈 스킬

**복잡한 현실을 하나의 작동원리로 압축하는 논리 엔진.** 시각화·인포그래픽·원샷그래프·한장프레임·본질프레임·프레임선택·프레임진단 맥락에서 자동발동. 20프레임 카탈로그로 본질 질문에 맞는 프레임을 고르고, 그 프레임의 노드·엣지·축을 명세화한다.


## Skill Boundaries

- **하는 것** — 복잡한 사업·문제의 **본질을 한 프레임으로 압축**하는 논리 엔진.
- **안 하는 것** — 시각산출(→apple-canvas·prism-design·editorial-design·box-cut-design·teenage-design), UI(→ui-designer), 산업분석(→biz-skill).

**시각 산출은 하지 않는다.** 이 스킬의 산출물은 "이 사업은 Multi-Flywheel이다. 3루프는 X·Y·Z이고 연결점은 A·B"까지 + **대화창 옵션 카드**(아래 출고 규칙 참조). 실제 풀 그림은 별도 디자인 스킬(apple-canvas·prism-design·editorial-design·box-cut-design·teenage-design)이 담당.

---

## When to Use

- 사용자가 "시각화해줘", "인포그래픽처럼", "인포그래픽으로", "한장으로 정리", "도식화해줘", "그림으로 보여줘", "압축해줘", "프레임 골라줘", "본질 뽑아줘", "visualize", "diagnose", "pick frame" 같은 표현으로 발동
- 복잡한 사업·문제를 한 프레임으로 압축할 시점
- **안 쓸 때** — 시각산출(→apple-canvas·prism-design·editorial-design·box-cut-design·teenage-design), UI(→ui-designer), 산업분석(→biz-skill).


## Prerequisites

| # | 체크 | 미충족 시 |
|---|------|-----------|
| 1 | 대상·입력 명확 (스킬 발동 의도 확인) | 1줄 확인 후 진입 |
| 2 | references/ 폴더 접근 가능 | inline fallback |


## 절대 규칙 (4개)

| # | 규칙 | 이유 |
|---|------|------|
| 1 | **본질 우선** — "이 사업·상황의 본질이 뭔가" 답이 먼저, 프레임은 답에 맞춰 선택. 프레임이 본질을 강요하면 FAIL | 미사여구·도식미 거부 |
| 2 | **풀 시각 산출 ✗** — 노드·엣지·축의 **논리 명세** + 대화창 옵션 카드(SVG/HTML 소형 프리뷰 허용)까지만. 풀 HTML 페이지·풀 SVG 포스터·CSS 컴포넌트 ✗. 풀 시각 요청 시 apple-canvas·prism-design·editorial-design·box-cut-design·teenage-design 중 1개로 위임 | 논리와 풀시각 책임 분리. 본 스킬은 사고 도구 + 옵션 제시기 |
| 3 | **한 장 한계 존중** — 5~9 노드(의사결정) / 9~15 노드(시스템맵). 초과 시 프레임 분할 또는 계층 분리 요구 | 한 장에 못 담으면 "한 장 프레임" 아님 |
| 4 | **대화창 옵션 출고 강제 (3·N×3 룰)** — 발동 시 사용자 의도에 부합하는 시각화 옵션 **3개를 대화창 아티팩트(mcp__visualize__show_widget)로** 카드 형태 노출. 시각화 위치 N개 요구 시 N×3 카드(3→9·10→30) 출력. 카드 = 라벨·소형 SVG/HTML 프리뷰·1줄 설명·"이걸로 가시려면" CTA. 형이 1개 선택하면 후속 풀 시각은 위임 스킬이 처리 | 형 선택권 보장 + 카탈로그 인지 |

---

## 실행 흐름

```
① 본질 질문 확정 → ② 프레임 선택 → ③ 모드 분기
                                     ├─ DIAGNOSE (프레임 추천)
                                     └─ DESIGN (프레임 슬롯 명세)
```

---

## ① 본질 질문 (7대 질문 라우터)

사용자 입력 → 7대 질문 중 하나로 매핑. 매핑 안 되면 **역질문 1회**.

| 본질 질문 | 1순위 프레임 | 2순위 프레임 |
|----------|-------------|-------------|
| 왜 존재? | JTBD | — |
| 왜 성장? | Flywheel | Loop·NSM·Multi-Flywheel |
| 왜 계속 쓰지? | Hook | Journey |
| 왜 돈 되지? | Unit Economics | Capability Stack |
| 왜 우리가 이김? | Capability Stack | Control Point |
| 어디서 깨짐? | Funnel | Journey |
| 시장 어떻게 바꿈? | Value Chain | Unbundling |

→ 프레임 상세 논리: `references/frames-catalog.md`

---

## ② 프레임 선택 — 결정 트리

20프레임은 3축으로 분류된다. **시간성 · 관계형식 · 설명대상**.

```
1. 시간이 흐르는가?
   아니오 → 정지 구조
     · 상하 의존? → Layer / Pyramid / Capability Stack / JTBD
     · 2축 배치? → Matrix / Positioning / NSM트리 / UE트리
   예 → 2.

2. 되돌아오는가 (순환)?
   예 → 루프 구조
     · 1주체 자기강화? → Flywheel / Loop
     · 2주체 양면? → Two-sided
     · 여러 루프 물림? → Multi-Flywheel
     · 개인 습관 루프? → Hook
   아니오 → 3.

3. 단방향 흐름인가?
   예 → 선형 구조
     · 전환율? → Funnel
     · 감정·경험? → Journey
     · 전후 상태? → Bridge
     · 산업 흐름? → Value Chain

4. 관계망인가?
   예 → Ecosystem Map / Unbundling
```

**결합 가능:** 본질 질문이 2축이면 2개 프레임 결합 (예: Flywheel + Unit Economics = "왜 크며 왜 돈 되는가")

→ 결합 패턴: `references/frames-catalog.md §프레임 결합 패턴`

---

## ③ 모드 분기

| 모드 | 트리거 | 산출 |
|------|--------|------|
| **DIAGNOSE** | 상황·문제만 입력, 프레임 미지정 | 1순위 프레임 + WHY 1줄 + 대안 1~2개 + 맹점 + **3옵션 카드 위젯** |
| **DESIGN** | 프레임 지정 + 슬롯 채움 요청 | 노드·엣지·축의 **논리 명세** (md 표) + 빈 슬롯 식별 + 반례 경고 + **3옵션 카드 위젯** |
| **OPTIONS** | "옵션 보여줘"·"뭐 가능해" 트리거 OR 시각화 위치 N개 요구 | N×3 카드 위젯 (3→9·10→30). 카드별 라벨·프리뷰·CTA |

→ 모드별 예시: `references/examples.md`

---

## DIAGNOSE 산출 구조

```
✅ 결론 · {1순위 프레임} 1순위
논리: {왜 이 프레임이 본질에 맞는지 1~2줄}

대안:
· {대안 1} — {언제 대안이 더 나은지}
· {대안 2} — {언제 대안이 더 나은지}

⚠️ 맹점 · {이 프레임이 감추는 것 1개}
➡️ 다음 · {DESIGN 모드 전환 제안 또는 추가 질문}
```

---

## DESIGN 산출 구조

```
{프레임명} 명세

필수 조건:
· {이 프레임이 성립하려면 무엇이 참이어야 하는가}

노드 명세:
| 노드 | 역할 | 후보 채움 |
|------|------|----------|
| ... | ... | ... |

엣지/축:
· {노드 간 관계의 논리}

⚠️ 맹점 · {가장 약한 슬롯 또는 FAIL 조건}
➡️ 다음 · {다음 단계 — 지표 검증·시각화 위임 등}
```

---

## 옵션 카드 출고 규칙 (절대규칙 4 상세)

### 출고 규칙

| 조건 | 카드 수 | 출고 방법 |
|------|---------|----------|
| 디폴트(시각화 위치 1개) | **3 카드** | `mcp__visualize__show_widget` 1회. 3옵션 가로 그리드 |
| 시각화 위치 N개 (N≥2) | **N×3 카드** | 위치별 3옵션 그룹화. 3→9·5→15·10→30 |
| 형이 "옵션만 보여줘" | 카드만 (논리 명세 ✗) | OPTIONS 모드 |
| 형이 "1번으로 가" | 카드 ✗ + 위임 스킬 호출 | 풀 시각 출고는 5종 디자인 스킬 |

### 카드 1장 구성 (필수 5요소)

1. **번호 + 라벨** — "① Multi-Flywheel" 같은 단문
2. **소형 SVG 프리뷰** — 80~120px 정사각·핵심 구조 1컷
3. **1줄 설명** — "3루프 물림 — 왜 시스템적으로 가속하는지"
4. **위임 스킬** — "→ apple-canvas로 풀 출고 시"
5. **CTA** — "이걸로 가려면 '①번으로'"

### 위젯 표준 골격 (mcp__visualize__show_widget)

```
title: visualize_options_{topic}_{N}cards
loading_messages: ["옵션 카드 깎는 중", "프레임 후보 줄세우는 중"]
widget_code: HTML — flex grid (1행 3카드 · N행 시 N행 3열) + 카드별 inline SVG
```

상세 템플릿 · 9·30 카드 패턴 · CSS — `references/option-cards.md`

### 예시

| 형 발화 | 출고 |
|---------|------|
| "이 사업 시각화해줘" | 위치 1개 → **3카드** (Multi-Flywheel·Funnel·Capability Stack) |
| "BP에 3군데 시각화 넣어줘" | 위치 3개 → **9카드** (위치별 3옵션) |
| "IR 10페이지에 그래프 다 넣어줘" | 위치 10개 → **30카드** (페이지별 3옵션) |
| "옵션만 빨리" | OPTIONS 모드 → 3카드만, 논리 명세 ✗ |

---

## 프레임 카탈로그 (20개 요약)

| Group | 프레임 | 핵심 질문 |
|-------|--------|----------|
| **A. 순환·루프** | Flywheel | 왜 커질수록 빨라지나 |
| | Loop | 어떻게 자가 확산 |
| | Hook | 왜 돌아오나 |
| | Two-sided | 닭-달걀 어떻게 |
| | Multi-Flywheel | 왜 시스템적으로 가속 |
| **B. 선형·흐름** | Funnel | 어디서 새나 |
| | Bridge | 뭘 어떻게 바꾸나 |
| | Journey | 어디서 실망하나 |
| | Value Chain | 어디서 마진 나나 |
| **C. 계층·구조** | Layer | 몇 층 구조인가 |
| | Pyramid | 기반과 성과 |
| | Capability Stack | 왜 우리가 이김 |
| | JTBD | 왜 사나 (동기) |
| | Control Point | 어디 잡으면 먹나 |
| **D. 분포·매핑** | Matrix | 의사결정 축 |
| | Positioning Map | 시장 위치 |
| | NSM 트리 | 뭘 올려야 성장 |
| | Unit Economics 트리 | 돈 되나 |
| **E. 관계망·재편** | Ecosystem Map | 누가 누굴 움직이나 |
| | Unbundling | 시장이 어떻게 깨지나 |

→ 각 프레임 **정의·작동원리·구성요소·드러냄·감춤·변별점·선택조건·반례**: `references/frames-catalog.md`

---

## 안티패턴 (FAIL)

| 안티패턴 | 대응 |
|----------|------|
| 예쁜 프레임 먼저 고르고 본질 끼워맞추기 | 본질 질문 확정 후 프레임 선택 (절대규칙 1) |
| 풀 시각 산출 (풀 HTML 페이지·풀 SVG 포스터) | 논리 명세 + 옵션 카드까지만. 풀 시각 요청 시 5종 디자인 스킬 중 1개로 위임 (절대규칙 2) |
| 노드 15개 초과 한 장 | 계층 분할 또는 프레임 교체 (절대규칙 3) |
| 프레임 결합 3개+ | 2개 이하. 3개면 분할 장표 또는 프레임 재선택 |
| 유사 프레임 혼동 | 변별점 명시: Flywheel vs Loop·Two-sided vs 가치사슬 등 (frames-catalog.md §변별점) |
| 반례 무시 | 각 프레임 FAIL 조건 확인 (frames-catalog.md §반례/FAIL) |
| 정지 상황에 순환 프레임 강요 | 시간이 안 흐르면 Group C·D. 억지로 Flywheel ✗ |

---

## 트리거 라우팅 (자동발동 5축)

1. **본질 질문** ("이 사업 뭐임", "왜 이김", "왜 성장")
2. **압축 요청** ("한 장으로 정리", "프레임 하나로", "원샷", "본질만")
3. **프레임 추천 요청** ("어떤 프레임 써야", "뭐가 맞아")
4. **프레임 명사 등장** (플라이휠·퍼널·Hook·Multi-Flywheel 등 20개)
5. **전략 설계 직전** (BP·IR·임원보고 맥락 + 본질 압축 필요)

**NOT:**
- 풀 시각 산출·디자인 → apple-canvas·prism-design·editorial-design·box-cut-design·teenage-design
- 풀 차트·풀 인포그래픽 페이지 → 5종 디자인 스킬 중 1개
- UI 설계 → ui-designer
- 산업 분석 전반 → biz-skill

---


## §INV NO_WORK_LABEL
산출물·대화 작업 라벨 ZERO. → `shaper-skill/references/no-work-label.md`


## Output Path

| 산출물 | 경로 |
|---|---|
| 주 산출물 | `mnt/outputs/visualize-skill_{topic}_{YYYY-MM-DD}.md` |
| 형식 | .md로. |
| 리서치 결과 (해당 시) | `{VAULT}/_skills research/visualize-skill/{YYYY-MM-DD}_{topic}.md` |

## Reference Index

| 파일 | 내용 | 언제 |
|---|---|---|
| `references/examples.md` | DIAGNOSE/DESIGN 모드 예시 | 모드 분기 진입 시 |
| `references/frames-catalog.md` | 20프레임 정의·작동원리·결합·반례 | 프레임 선택·결합 시 |
| `references/option-cards.md` | 3·9·30 카드 위젯 템플릿·HTML 골격·SVG 프리뷰 패턴 | OPTIONS 모드 또는 절대규칙 4 출고 시 |


## Next Phase

본 스킬 작업 후 자연스럽게 이어지는 흐름:

- 풀 시각 출고 → `apple-canvas` (1page 강도·KPI한장·랜딩) / `prism-design` (장문보고서·키노트덱) / `editorial-design` (매거진·인터뷰·에세이) / `box-cut-design` (Supreme/Off-White 박스컷·매니페스토) / `teenage-design` (카탈로그·model card·release notes)
- 화면 UI 설계 → `ui-designer`
- 산업 패턴 분석 → `biz-skill`

## Failure Modes (Gotchas)

| 함정 | 대응 |
|------|------|
| "예쁘게 그려줘" | 본질 질문 1회 역질문. 풀 시각 요청은 5종 디자인 스킬 중 1개로 위임 명시 |
| "움직이게/역동적" | 본 스킬 범위 밖. 시각 산출 스킬로 위임 |
| "플라이휠로 그려줘" (무턱대고) | 플라이휠 성립 조건(루프 폐쇄·자기강화) 확인 먼저. 미성립 시 대안 프레임 제시 |
| 노드 데이터 없이 DESIGN 요청 | 빈 슬롯 명시 후 "이 자리에 뭐가 들어가야?" 역질문 |
| 유사 프레임 구분 애매 | frames-catalog.md 변별점 섹션 참조 (Flywheel↔Loop, Two-sided↔Multi-Flywheel 등) |
| 본질 질문이 2개 (성장+수익) | 프레임 결합 패턴 적용 (Flywheel + Unit Economics 등). 3개+면 분할 |
| DIAGNOSE만 원했는데 DESIGN 돌입 | DIAGNOSE 산출 후 "DESIGN으로 전환?" 1줄 제안, 컨펌 후 진행 |


## ❌ WRONG vs ✅ CORRECT

```
❌ WRONG: 트리거 단어만 보고 발동 — 본질·범위 확인 ✗ → 오발동·범위 이탈
✅ CORRECT: Skill Boundaries·When to Use 확인 후 발동 → 본질 작업만 수행
```
