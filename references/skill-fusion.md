# Skill Fusion — paper-engine·design-skill·apple-* 무수정 융합

**핵심 원칙**: one-shot-graph는 **HTML 블록·신호 일방향 공급자**. 다른 스킬 SKILL.md 한 줄도 ✗.

---

## 융합 매트릭스

| 스킬 | one-shot-graph 역할 | 다른 스킬 자동 동작 |
|------|--------------------|--------------------|
| paper-engine | `[FRAME: {name}](./frame_*.html)` 링크 또는 `<svg class="osg-*">` 발신 | V1~V10 시각소스 태깅 → design-skill C9 cascade 자동 발동 |
| design-skill | `<svg class="osg-flywheel">` 클래스명만 발신 | C9 시각화 라우팅이 자동 처리 |
| apple-design-style | `var(--osg-info/caption/decor)` 3티어 변수만 사용 | `.dark` 클래스로 자동 역매핑 |
| apple-box-design | 박스 외곽은 apple, 내부 콘텐츠만 osg | 충돌 없음, 레이어 분리 |
| obsidian-markdown | `![[frame.html]]` embed 또는 `> [!info]` callout | wikilink·embed 문법 그대로 인식 |
| github-deploy | `.html` 단독 또는 `.md`+`.html` 동시 | 호출명 트리거 → 도메인 자동 라우팅 |
| html-div-style | div 래퍼 1층, osg 콘텐츠 2층 | 분리 — div는 컨테이너만, osg는 내부 |

---

## 호출 패턴

### A. paper-engine 산출물에 1장 그림 끼우기
```markdown
## 핵심 작동원리
[1장 프레임 보기 →](./frame_flywheel.html)

본문 텍스트 (paper-engine NYT 스타일)...
```
또는 inline iframe (옵시디언 한정):
```markdown
<iframe src="frame_flywheel.html" style="width:100%; height:500px; border:0"></iframe>
```

### B. design-skill cascade 자동 발동
one-shot-graph가 `<svg class="osg-flywheel">` 출력 → design-skill C9가 자동으로 스타일·반응형 적용.

### C. github-deploy 동시 배포
1. paper-engine으로 `report.md` 생성
2. one-shot-graph로 `frame_flywheel.html` 생성
3. github-deploy "내꺼로 배포" → 둘 다 works.jasonnamii.com에 업로드

---

## 충돌 회피 룰 (6개)

1. **paper-engine 역피라미드 vs design-skill 4층**
   → design-skill의 engine-4layer.md 우선순위 적용 (tone친화도 → 구조서열). one-shot-graph는 끼어들지 ✗

2. **apple inline 색상 선언**
   → `style="color:#xxx"` 절대 ✗. `var(--osg-*)` 또는 `var(--label-*)` 경유만

3. **obsidian 1층(이쁘니) + 2층(html-div) 혼용**
   → design-skill 이쁘니 우선 완성 후 html-div 추가. one-shot-graph는 1·2층 무관

4. **github-deploy 도메인 혼동**
   → 호출명으로 도메인 1회 확정 후 경로 고정. 서브폴더 CNAME ✗

5. **apple weight (XL 80px) vs C1 타이포 비율**
   → clamp 모바일 48px 자동 축소. one-shot-graph는 타이포 직접 강제 ✗

6. **옵시디언 라이트테마 색상 흡수**
   → `.md`용 불투명 값(`#efefef` 배경) 별도 준비

---

## 산출 분기 매트릭스

| 분기 | 적용 스킬 | 용도 |
|------|----------|------|
| HTML 단독 | one-shot-graph + design-skill + apple | 인터랙티브 대시보드 |
| .md 단독 | one-shot-graph (mermaid 폴백) + paper-engine + obsidian-markdown | 옵시디언 아카이빙 |
| HTML+.md 동시 | 전부 (분화) | 풀 다채널 배포 (github-deploy) |
| +PDF | + apple (pdf mode) | IR·심사 정본 |

---

## 무수정 보장 메커니즘

1. **신호 단계적 위임**: paper-engine §A~§E는 신호만 발신 → design-skill C9 자동 cascade. one-shot-graph는 클래스·링크만 추가
2. **클래스명·변수 고착**: `.osg-*` 클래스, `var(--osg-*)` 변수 → 다른 스킬 본문 수정 0
3. **산출물 분기 독립**: HTML/MD/PDF 각 분기 cascade 경로 독립 → 다른 분기 스킬 로드 불필요

---

## CSS 변수 Alias Shim (apple-box-design 융합 필수)

**문제**: one-shot-graph = `--osg-info/caption/decor` / apple-box-design = `--label-info/caption/decor` → 다크 컨테이너 진입 시 역매핑 불가 → 색상 미적용 렌더 깨짐.

**해법**: apple-box-design과 동시 사용 시 HTML `<style>` 블록 최상단에 **alias shim** 주입 (one-shot-graph 산출부에 자동 포함):

```css
/* one-shot-graph ↔ apple-box-design 변수 호환 shim */
:root {
  --osg-info: var(--label-info, #1a1a1a);
  --osg-caption: var(--label-caption, #6b7280);
  --osg-decor: var(--label-deco, #e5e7eb);
}
.dark, [data-theme="dark"] {
  --osg-info: var(--label-info, #f5f5f5);
  --osg-caption: var(--label-caption, #9ca3af);
  --osg-decor: var(--label-deco, #374151);
}
```

**발동 조건**:
- apple-box-design 스킬 발동이 감지되면 **무조건 shim 포함**
- 단독 렌더 시 shim 생략 가능 (폴백 값만으로 동작)

**design-skill 훅 부재 대응**: `.osg-flywheel` 등 one-shot-graph 고유 클래스는 design-skill C9에 미등록 → 템플릿 내 인라인 `<style>` 블록으로 자체 완결. C9에 위임하지 않고 one-shot-graph가 독립 스타일링 소유.

---

→ 원본 리서치: `VAULT/_skills research/one-shot-graph/2026-04-22_D_skill-fusion.md`
