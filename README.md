# skills

코딩 에이전트와 함께 개발할 때 쓰는 규칙과 스킬 모음.
설계 · 검증 · 세션 기록의 각 단계에서 결정의 근거와 확인 결과를 파일로 남긴다.

## 구성

| 파일 | 읽히는 때 | 내용 |
| --- | --- | --- |
| [`AGENTS.md`](AGENTS.md) | 모든 작업 | 요구사항 · 범위 · 검증 · 위임 규칙 |
| [`lean-design`](.agents/skills/lean-design/SKILL.md) | 요구사항 정리 후 · 구현 | 설계안 비교 → 작업 그래프(`PLAN.md`) → 승인 후 그래프 순서대로 구현 |
| [`design-rationale`](.agents/skills/design-rationale/SKILL.md) | 마무리 단계 | `README` · `RATIONALE.md` (대안 · 선택 이유 · 트레이드오프) |
| [`session-wrap`](.agents/skills/session-wrap/SKILL.md) | 세션 종료 시 ("세션 정리해줘") | `progress.md` (매번 전체 갱신) |

늘 지켜야 하는 규칙은 `AGENTS.md` 에, 특정 시점에만 쓰는 절차와 문서 양식은 스킬에 둔다.
규칙은 스킬이 호출되지 않은 작업에도 적용되고, 스킬 본문은 호출될 때만 읽혀 컨텍스트를 아낀다.

## 흐름

```text
lean-design ──────────────────────────────▶ design-rationale ──▶ session-wrap
  ① 설계안 비교 → ② 작업 그래프 → ③ 실행
```

요구사항이 바뀌면 `lean-design` 이 영향받는 노드만 다시 계획한다.

## 참고

- superpowers `subagent-driven-development` — 작업을 작게 나누고 범위가 정해진 작업만 위임하는 방식. 작업마다 리뷰어를 두 단계로 붙이는 부분은 비용을 고려해 기본값에서 뺐다.
- 테스트 우선 개발 — 판정은 실행 결과(종료 코드)로 하고, 수정 전에 실패를 먼저 확인한다.
