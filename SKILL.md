---
name: one-shot-graph
description: |
  복잡한 사업·문제의 **본질을 한 프레임으로 압축**하는 논리 엔진. 20프레임 기반 본질질문→프레임선택→슬롯명세. 시각 산출 ✗.
  P1: 원샷, 원샷그래프, 한장프레임, 본질프레임, 프레임선택, 프레임진단, 작동원리, 플라이휠, 퍼널, Hook, Journey, Two-sided, Multi-Flywheel, Unit Economics, NSM트리, Capability Stack, Control Point, JTBD, Value Chain, Unbundling.
  P2: 압축해줘, 프레임 골라줘, 본질 뽑아줘, diagnose, pick frame.
  P3: one-page framework, mental model selection.
  P5: .md로.
  NOT: 시각산출(→design-skill/apple-box-design), UI(→ui-action-designer), 산업분석(→biz-skill).
---

# One-Shot Graph

**복잡한 현실을 하나의 작동원리로 압축하는 논리 엔진.** 원샷그래프·한장프레임·본질프레임·프레임선택·프레임진단 맥락에서 자동발동. 20프레임 카탈로그로 본질 질문에 맞는 프레임을 고르고, 그 프레임의 노드·엣지·축을 명세화한다.

**시각 산출은 하지 않는다.** 이 스킬의 산출물은 "이 사업은 Multi-Flywheel이다. 3루프는 X·Y·Z이고 연결점은 A·B"까지. 실제 그림은 별도 디자인 스킬(design-skill·apple-box-design)이 담당.

---

## 절대 규칙 (3개)

| # | 규칙 | 이유 |
|---|------|------|
| 1 | **본질 우선** — "이 사업·상황의 본질이 뭔가" 답이 먼저, 프레임은 답에 맞춰 선택. 프레임이 본질을 강요하면 FAIL | 미사여구·도식미 거부 |
| 2 | **시각 산출 ✗** — 노드·엣지·축의 **논리 명세**까지만. HTML·SVG·CSS·이미지 생성 ✗. 시각 요청 시 design-skill·apple-box-design으로 위임 | 논리와 시각 책임 분리. 본 스킬은 사고 도구 |
| 3 | **한 장 한계 존중** — 5~9 노드(의사결정) / 9~15 노드(시스템맵). 초과 시 프레임 분할 또는 계층 분리 요구 | 한 장에 못 담으면 "한 장 프레임" 아님 |

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
| **DIAGNOSE** | 상황·문제만 입력, 프레임 미지정 | 1순위 프레임 + WHY 1줄 + 대안 1~2개 + 맹점 |
| **DESIGN** | 프레임 지정 + 슬롯 채움 요청 | 노드·엣지·축의 **논리 명세** (md 표) + 빈 슬롯 식별 + 반례 경고 |

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
| 시각 산출 (HTML·SVG·이미지) | 논리 명세까지만. 시각 요청 시 design-skill로 위임 (절대규칙 2) |
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
- 시각 산출·디자인 → design-skill / apple-box-design
- 일반 차트·인포그래픽 → design-skill
- UI 설계 → ui-action-designer
- 산업 분석 전반 → biz-skill

---


## §INV NO_WORK_LABEL (산출물·대화 본질 보호)

| 항목 | 정의 |
|------|------|
| RULE | 산출물·대화 = 인간 언어. 작업 라벨 ZERO. (1만 페이지 1단어 = FAIL) |
| 판정 | "이 단어, 이 대화 밖 사람이 사전 없이 읽을 수 있나?" NO → 작업 라벨 → 금지 |
| ALLOW | 업계 전문용어(JTBD·MVP·KPI·NSM·LTV·CAC) · 고유명사 · 법조문 |
| CONVERT | 라벨 발견 → 실명·평문 풀어쓰기. 예) "20프레임·Hook·Journey·Two-sided·Multi-Flywheel·Capability Stack·Control Point·Value Chain·Unbundling" → 결과만 노출(프레임 코드 ✗·결과 본문 평문) |
| SELF_CHECK | 한장프레임 출력 직전에서 자체 스캔. 1개라도 발견 = 차단·재작성. paper-engine cascade 경유 시 INV 13 자동 적용 |

---

## Gotchas

| 함정 | 대응 |
|------|------|
| "예쁘게 그려줘" | 본질 질문 1회 역질문. 시각 요청은 design-skill 위임 명시 |
| "움직이게/역동적" | 본 스킬 범위 밖. 시각 산출 스킬로 위임 |
| "플라이휠로 그려줘" (무턱대고) | 플라이휠 성립 조건(루프 폐쇄·자기강화) 확인 먼저. 미성립 시 대안 프레임 제시 |
| 노드 데이터 없이 DESIGN 요청 | 빈 슬롯 명시 후 "이 자리에 뭐가 들어가야?" 역질문 |
| 유사 프레임 구분 애매 | frames-catalog.md 변별점 섹션 참조 (Flywheel↔Loop, Two-sided↔Multi-Flywheel 등) |
| 본질 질문이 2개 (성장+수익) | 프레임 결합 패턴 적용 (Flywheel + Unit Economics 등). 3개+면 분할 |
| DIAGNOSE만 원했는데 DESIGN 돌입 | DIAGNOSE 산출 후 "DESIGN으로 전환?" 1줄 제안, 컨펌 후 진행 |
