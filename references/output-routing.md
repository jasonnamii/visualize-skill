# Output Routing — 산출 분기 결정 룰

**입력 컨텍스트** → **분기 결정** 매트릭스.

---

## 분기 결정 트리

```
1. 사용자가 형식 명시? (".html로", ".md로")
   YES → 명시 형식
   NO  → 2.

2. 모션 필수 5프레임?
   YES → HTML 단독
   NO  → 3.

3. paper-engine 산출물 안에서 호출?
   YES → md+HTML 동시 (링크 임베드)
   NO  → 4.

4. 옵시디언 컨텍스트?
   YES → md 인라인 (모션 없는 프레임만) + HTML 백업
   NO  → 5.

5. github-deploy 호출명 등장?
   YES → HTML 단독 + 배포
   NO  → 디폴트 = HTML 단독
```

---

## 분기별 산출 표준

### A. HTML 단독
- 파일명: `osg_{frame}_{topic}.html`
- 위치: `VAULT/{project}/` 또는 outputs
- 구조: 단일 .html (인라인 CSS·SVG·JS)
- 예: `osg_flywheel_c8.html`

### B. md 인라인 (정적 8프레임만)
- mermaid 또는 div 폴백
- 옵시디언 reading mode 호환
- 예:
  ```mermaid
  graph TD
    A[Job] --> B[Situation]
    B --> C[Outcome]
  ```

### C. md + HTML 동시
- md 본문 = paper-engine
- HTML 1장 = one-shot-graph
- 연결: `[1장 프레임 →](./frame_*.html)` 링크 또는 iframe
- github-deploy 동시 업로드

### D. PDF (정적 캡처)
- 모션 1프레임 추출 (CSS `animation-play-state: paused`)
- print media query 적용
- apple-design-style PDF 모드와 호환

---

## 옵시디언 한계 처리

**Reading mode SVG 모션 미작동 시**:
1. wikilink로 Edit mode 안내: `[[frame_flywheel.html|Edit mode에서 보기]]`
2. github-deploy 외부 호스팅 + 외부 링크
3. 정적 PNG 캡처 폴백 첨부

---

## github-deploy 도메인 라우팅

| 호출명 | 도메인 | 용도 |
|--------|--------|------|
| 형꺼·내꺼·제이슨나미 | works.jasonnamii.com | 형 본인 작업 |
| 피디님·pdkim·김형석 | works.pdkim.com/{subfolder} | 피디님 작업 |
| 최·choi·최남희 | works.choi.build/{subfolder} | 최 작업 |

→ github-deploy 스킬 SKILL.md 직접 참조.
