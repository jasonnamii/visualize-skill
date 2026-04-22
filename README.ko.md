# one-shot-graph

복잡한 사업·문제·상황을 **하나의 작동원리로 압축한 한 장 그림**으로 산출. 20프레임 카탈로그 + 정적 HTML 시제품. 본질을 드러내는 1장 그림.

> ⚠️ **MOTION_MODE = OFF (현재 고정)** — 시각화 안정화 단계. 템플릿 내 모션 코드(`@keyframes`·`animation`)는 재가동 대비 전량 보존하되, 출력물은 정적 HTML/SVG만 산출.

## 하는 일

사업 상황을 입력하면 20프레임(플라이휠·퍼널·Hook Model·Journey Map·JTBD·Unit Economics 트리·Capability Stack 등) 중 본질에 맞는 것을 선택, 한 장 다이어그램으로 렌더.

3모드:

- **DIAGNOSE** — 상황 입력 → 적합 프레임 1~3개 후보 + WHY 1줄씩
- **DESIGN** — 프레임 명시 + 빈 슬롯 채우기 (노드·엣지·축 명세)
- **RENDER** — 데이터 + 프레임 → 정적 HTML 1장 (디자인 스킬 선택 발동 필수)

## 작동 원리

1. **본질 질문** — "왜 존재/성장/리텐션/수익/승리/깨짐/파괴" 7대 질문이 후보 프레임으로 라우팅.
2. **프레임 선택** — 20프레임 3티어(모션 필수 5·권장 7·정적 OK 8).
3. **디자인 스킬 cascade** — RENDER 직전 `apple-box-design`(박스·벤토) 또는 `design-skill`(노드+엣지) 중 1개 필수 발동하여 시각 위계 담당.
4. **정적 산출** — HTML + 인라인 SVG, CDN 0개 기본, `var(--osg-info/caption/decor)` 색상 토큰으로 apple cascade 호환.

## 융합 (무수정)

one-shot-graph는 **HTML 블록·클래스 훅 신호 일방향 공급자**. 다른 스킬(`paper-engine`·`design-skill`·`apple-box-design`·`apple-design-style`·`obsidian-markdown`·`github-deploy`·`html-div-style`)이 자동 cascade로 소비, 스킬 본문 수정 0.

apple-box-design 병용 시 **CSS alias shim**(`--osg-*` ↔ `--label-*`)이 자동 주입되어 다크 컨테이너 역매핑 정상 작동.

## 설치

Claude 스킬 플러그인 폴더에 넣거나, Claude Code·Cowork로 `.skill` 패키지 설치.

## 영문 버전

[README.md](README.md) 참조.

## 라이선스

MIT — [LICENSE](LICENSE) 참조.
