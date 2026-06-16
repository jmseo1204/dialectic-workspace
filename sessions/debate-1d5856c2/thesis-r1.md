---
id: thesis-r1
role: thesis
round: 1
session_id: debate-1d5856c2
topic: "Audit thesis_writing_plan for SNU ECE thesis format and strict low-level-planner-only rewrite v2"
replies_to: []
pr_url: null
date: "2026-06-16"
---

# Thesis: Audit thesis_writing_plan for SNU ECE thesis format and strict low-level-planner-only rewrite v2

## 핵심 주장
`paper/thesis_writing_plan.md`는 LOW-level/HIGH-level 콘텐츠 분류와 핵심 수식 표기 단순화에서는 상당히 정교하지만, 그 자체로는 작성자가 원문 `main_arxiv.tex`를 다시 펴보지 않고 학사 논문을 끝까지 쓸 수 있는 수준에 도달하지 못했다. 구체적으로 (1) SNU 학사 학위논문 작성지침이 요구하는 표지/인준지/국문초록/목차/페이지 번호 체계 등 형식 규정이 계획서에 전혀 반영되어 있지 않고, (2) 본론(제3장)과 결론(제5장)에서 "유지" 또는 "trim 후 유지"로만 표시된 절들이 실제로는 HIGH-level 위험 용어(anchor, route, online, orchestrator 등)를 문장 단위로 내포하고 있어 절 단위 지시만으로는 안전하게 옮겨 적을 수 없으며, (3) Conclusion 원문 문장 자체가 "LOW+HIGH 결합이 핵심 기여"라고 명시적으로 선언하는데 계획서는 이를 일반적으로만 경고할 뿐 대체 문장을 제공하지 않고, (4) `app:guidance-injection`보다 더 LOW-level 핵심에 가까운 부록 — "Low-Level Planner State, Scoring, and Meeting Details"(원문 §822) — 의 존재 자체를 계획서가 언급하지 않는다. 이 네 가지는 모두 "계획서가 부족하면 작성자가 틀리게 추론할 것"이라는 엄격한 기준 하에 반드시 보강되어야 할, 반박하기 어려운 구체적 결함이다.

## 논거 1 — SNU 작성지침의 형식 요구사항이 계획서에 전혀 반영되지 않았다
`02_thesis_guideline_extracted_clean.txt`는 다음을 명시적으로 요구한다.

- 논문 기재 순서: 외표지 → 인준지 → 국문초록 → 목차(+표 목차, 그림 목차) → 본문 → 참고문헌 → (부록) → 영문초록 (국문 작성 기준)
- 외표지: 제목 21pt, 기타 16pt, 발간년도 표기, 중앙선 기준 좌우 대칭 배치
- 글자크기: 국문 10pt / 영문 11pt, 본문 두 줄 띄기(double spacing)
- 페이지 번호: 초록~표목차는 로마자 소문자, 본문~감사문은 아라비아 숫자
- 표/그림 제목 배치 규칙(표는 상단, 그림은 하단), 영문 비표제 시 영문 병기
- 참고문헌 인용은 본문과 같은 글자크기의 대괄호 표기, 본문에서 인용된 것만 기재

`01_thesis_writing_plan.md`를 전체 검색하면 분량(20p), 장별 분량 배분, 장 제목, 그리고 "Related Work 위치는 thesis_guideline 예시 구조에 부합"이라는 한 줄 언급만 존재한다. 표지·인준지·국문초록·키워드 개수(6개 이내)·목차/표목차/그림목차 작성·페이지 번호 체계·줄 간격·참고문헌 서식 중 단 하나도 계획서에 항목화되어 있지 않다. 이는 형식 위반으로 직결되는 결함이며, "계획서만 보고 쓸 수 있는가"라는 1차 판단 기준에서 명백히 불충분하다는 것을 보여주는, 반박 불가능한 사실이다.

## 논거 2 — "유지/trim 후 유지"로 표시된 절들이 문장 단위로 HIGH 용어를 내포한다 (제3장 사례)
계획서는 §4.2.1, §4.2.3, §4.2.4를 "유지" 또는 "구절만 삭제 후 유지"로 지시한다. 그러나 원문 §4.2(Anchor-chaining Tree Diffusion Planner, line 170–282)을 직접 대조하면, 계획서가 명시한 단일 문구 삭제로는 부족한 지점들이 있다.

- §4.2.1 Architecture-Level Design은 계획서가 "anchor 표기를 시작점/목표점 트리 두 개로 단순화"하라고 지시하지만, 원문에는 "for each anchor $a_i \in \mathcal{A}$" 외에도 트리 간 통신을 가정하는 변수명(`anchor pair`, 트리 인덱스 $i,j$를 포함하는 보조 정의)이 본문 곳곳에 등장한다. 계획서는 수식 1개($\mathcal{J}_{i\to j}$)의 치환만 명시했을 뿐, §4.2.1 산문 안에서 같은 인덱스 표기가 재등장하는 모든 위치를 특정하지 않았다.
- §4.2.3 Node Expansion에 대해 계획서는 "'for the route-level orchestrator' 구절만 삭제 후 유지"라고 지시한다. 이는 정확히 한 구절만 위험하다고 전제하는 것인데, 이 전제 자체가 검증되지 않았다. "Be strict: 계획서에 없으면 작성자가 올바르게 추론할 것이라 가정하지 말 것"이라는 디베이트 brief의 원칙을 적용하면, 계획서는 §4.2.3 전체 단락에서 "route" 또는 "orchestrator"가 등장하는 모든 문장을 나열하고 각각의 처리 여부를 표로 제시해야 하나 현재는 그렇지 않다.

즉 계획서의 "절 단위 지시(유지/trim)"는 작성자가 실제로 그 절의 전체 영어 문장을 한 줄씩 검사하지 않고는 안전하게 따를 수 없는 수준의 추상도에 머물러 있다.

## 논거 3 — 원문 Conclusion이 "LOW+HIGH 결합이 핵심 기여"라고 명시적으로 선언하는데, 계획서는 대체 문장을 제공하지 않는다
brief의 하드 제약은 "LOW+HIGH coupling이 contribution이라는 결론을 배제"하라고 명시한다. 원문 Conclusion(line 491)을 직접 인용하면:

> "ChronoForest addresses this setting by coupling an Anchor-chaining tree diffusion planner ... with an Online multi-tree orchestrator that re-solves the route from accumulated bridge evidence ... These results support the paper's central claim that long-horizon offline route composition benefits most from coupling temporal-distance-guided local bridge search with explicit online route re-solving."

이 문장은 한 단어씩 거의 전부가 위험 용어(coupling, orchestrator, route, re-solving)로 구성되어 있으며 마지막 문장은 정확히 "결합이 최선"이라는 금지된 주장 그 자체다. 계획서 제5장 항목은 "원문의 'low+high 결합이 최선'이라는 결론 문장과 Hamiltonian 관련 수치는 전부 제외"라고만 적어 두었을 뿐, 그 자리를 대체할 한 문장도 제시하지 않는다. 작성자가 이 문장을 어떻게 자연스럽게 LOW-only 결론으로 바꿔야 하는지에 대한 지침이 없으므로, 작성자는 원문을 다시 읽고 스스로 대체 문장을 만들어야 한다 — 이는 정확히 디베이트가 묻는 "원문을 다시 읽지 않고 쓸 수 있는가"에 대한 부정적 증거다.

## 논거 4 — 계획서가 언급하지 않은, 순수 LOW-level 부록의 존재
`04_main_arxiv_flattened_with_inputs.tex`의 부록 목록(line 822)에는 "Low-Level Planner State, Scoring, and Meeting Details"라는 섹션이 존재하며, 그 하위에 "Tree State and Target-Pointer Details"(825), "Pair-Conditioned Target Selection and Ranking Details"(873), "Expansion and Meeting Details"(968)가 포함된다. 이 섹션들은 제목부터 "Low-Level"이라고 명시되어 있어 분류상 명백히 LOW이며, §4.2.2(Target Selection)와 §4.2.3(Node Expansion)의 세부 구현 디테일을 직접 보충하는 내용이다.

계획서의 "Appendix 처리" 항목은 "이번 인터뷰 범위 제외 (별도 확인 예정)"라고만 적혀 있고, `tab:plan_length_bfs`/`tab:planning_cost_ablation` 두 표만 언급할 뿐 이 LOW-level 세부사항 부록 자체는 한 번도 등장하지 않는다. 본론 7p라는 계획서 최대 분량 장이 가장 비중 있게 다뤄야 할 §4.2.2/§4.2.3의 1차 출처 자료가 정작 계획서의 점검 대상에서 완전히 빠져 있다는 것은, "계획서만으로 본론을 쓸 수 있는가"라는 핵심 질문에 대한 구체적이고 반박하기 어려운 반증이다.

## 논거 5 — 위험 용어 목록이 brief의 8개 항목에 비해 계획서 내에서 체계적으로 추적되지 않는다
`00_debate_task_brief.md`와 `99_source_inventory.md`는 route(294회), Hamiltonian(25회), orchestrator(18회), waypoint(24회), mTSP(33회), multi-tree(17회), route re-solving(10회), Online Multi-Tree(9회) 등 출현 빈도까지 명시하며 위험 용어를 강조한다. 계획서는 일부 절에서 개별적으로 "waypoint/mTSP 언급 배제"라고 서술하지만, 위험 용어 전체를 모아 "어느 장/절에 등장하며 어떻게 처리하는가"를 정리한 단일 표나 체크리스트는 존재하지 않는다. 예컨대 "anchor"라는 용어는 §4.2.1뿐 아니라 제목("Anchor-chaining Tree Diffusion Planner")에도 등장하므로, 이 단어가 LOW 맥락(트리 확장 시작점)으로 안전하게 쓰일 수 있는 경우와 HIGH 맥락(anchor pair, anchor matrix — mTSP 관련)으로 위험한 경우를 구분하는 명시적 규칙이 필요하지만 계획서에는 없다. 용어가 등장하는 모든 위치를 사전에 분류해 두지 않으면, 작성자는 매 문장마다 직접 원문을 대조해 위험성을 판단해야 하므로, "다시 읽지 않고 쓸 수 있는 계획"이라는 목표에 미달한다.
