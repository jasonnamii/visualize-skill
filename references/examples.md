# Examples — 모드별 사용 예시

---

## DIAGNOSE 모드

### 예시 1
**입력**: "C8 사업 본질을 한 장으로 보여주고 싶어"
**출력**:
```
✅ 결론 · Multi-Flywheel 1순위
이유: 크리에이터·팬·플랫폼 3개 루프가 상호강화 → 단일 플라이휠로는 본질 표현 부족

대안:
- Two-sided Market: 단순 양면 강조 시
- Capability Stack: 역량 우위 강조 시

➡️ 다음 · 채택 시 RENDER 모드로 전환 (3루프 노드 데이터 입력 요청)
```

### 예시 2
**입력**: "리텐션이 안 좋아. 어떤 프레임?"
**출력**:
```
✅ 결론 · Hook Model 1순위 (Trigger·Action·Reward·Investment 4단계 진단)
대안: Journey Map (이탈 포인트 시각화 우선시)

➡️ 다음 · Hook 4단계 중 어디 약한가? 답에 따라 RENDER 또는 DESIGN 모드
```

---

## DESIGN 모드

### 예시 3
**입력**: "Hook Model 빈 슬롯 채우고 싶어. 우리 앱 콘텐츠 큐레이션 서비스"
**출력**:
```
| 단계 | 빈 슬롯 | 추천 채움 |
|------|---------|----------|
| Trigger | 외부/내부 | 외부=푸시 알림 / 내부=지루함 감지 |
| Action | 최소 행동 | 한 번 스와이프로 콘텐츠 1개 소비 |
| Reward | 가변 보상 | 콘텐츠 품질 랜덤성 + 좋아요 카운트 |
| Investment | 사용자 투입 | 북마크·취향 학습·팔로우 |

➡️ 다음 · 채움 확정 시 RENDER → assets/templates/hook.html 호출
```

---

## RENDER 모드

### 예시 4
**입력**: "Hook으로 그려줘. T=푸시, A=콘텐츠소비, R=좋아요, I=북마크"
**출력**:
- `assets/templates/hook.html` 데이터 슬롯 채움
- 4단계 순환 + 사용자 클릭시 펄스 애니
- 색상: `var(--osg-info/caption/decor)` 자동 적용
- prefers-reduced-motion 폴백 포함

산출 위치: `outputs/osg_hook_curation.html`

### 예시 5
**입력**: "C8 Multi-Flywheel HTML로. 3루프: 크리에이터·팬·플랫폼"
**출력**:
- `assets/templates/multi-flywheel.html` 호출
- 3개 회전축 + 축간 연결선 펄스
- D3 force layout (CDN 1줄 추가)
- github-deploy "형꺼로 배포" 제안

---

## 안티 예시 (FAIL)

### ✗ 잘못된 예시 1
**입력**: "그냥 예쁜 도식 하나 만들어줘"
**잘못된 응답**: 임의 프레임 선택 후 출력
**올바른 응답**:
```
본질 질문 1회 — "이 도식이 무엇을 압축해서 보여줘야 합니까?"
- 작동원리? → Flywheel·Loop
- 누수 진단? → Funnel
- 위치 표현? → Positioning Map
```

### ✗ 잘못된 예시 2
**입력**: "포지셔닝 맵에 회전 애니 추가해줘"
**잘못된 응답**: 회전 추가
**올바른 응답**:
```
포지셔닝 맵 = STATIC OK 티어. 회전 모션은 본질과 무관 → chartjunk 위반.
호버 인터랙션(점 강조)으로 대안 제시.
```
