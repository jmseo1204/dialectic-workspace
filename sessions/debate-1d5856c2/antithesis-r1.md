---
id: antithesis-r1
role: antithesis
round: 1
session_id: debate-1d5856c2
topic: "Audit thesis_writing_plan for SNU ECE thesis format and strict low-level-planner-only rewrite v2"
replies_to: ["thesis-r1"]
pr_url: null
date: "2026-06-16"
---

# Antithesis: Audit thesis_writing_plan for SNU ECE thesis format and strict low-level-planner-only rewrite v2

## 핵심 반론
Thesis가 제시한 4가지 결함은 사실 확인 차원에서는 대부분 맞지만, "계획서가 부족하다"는 결론으로 가는 과정에서 서로 다른 성격의 위험을 동일한 무게로 합산하는 오류를 범하고 있다. 형식 규정(논거 1)은 `thesis_guideline.doc` 자체를 다시 펴보면 5분 내에 기계적으로 채울 수 있는 비-판단적 항목이고, Conclusion 대체 문장 부재(논거 3)는 "계획서가 산문을 대신 써줘야 한다"는, 디베이트 brief가 요구하지 않은 과도한 기준이며, Appendix 처리 보류(논거 4)는 침묵이 아니라 명시적으로 추적된 결정이다. 더 결정적으로, 논거 2에서 thesis가 "전제가 검증되지 않았다"고 주장한 §4.2.3의 단일 구절 삭제는 원문을 직접 대조한 결과 정확히 옳았다 — 오히려 thesis가 검사하지 않은 §4.2.2(Node Evaluation) 도입부에 거의 동일한 위험 문장이 남아 있다는, thesis 본인의 방법론이 놓친 더 정확한 반례가 존재한다. 즉 thesis의 비판 방향은 옳지만 진단의 정밀도가 부족하다.

## 반론 1 — 형식 규정 누락과 내용 분류 오류는 같은 등급의 위험이 아니다
SNU 표지·인준지·국문초록·페이지 번호 체계가 계획서에 없다는 thesis의 사실 지적은 정확하다. 그러나 이것이 "작성자가 원문을 다시 펴봐야 한다"는 디베이트의 1차 판단 기준과 같은 종류의 위험인지는 별개의 질문이다. 형식 항목은 `paper/thesis_guideline.doc`라는, `main_arxiv.tex`와 무관한 별도 문서를 한 번 펴서 그대로 옮기면 해결되는 체크리스트성 정보이며, 틀렸을 경우 최종 포맷팅 단계에서 즉시 발견·교정 가능하다. 반면 brief의 핵심 위험은 "HIGH-level 용어가 LOW-level 문장 속에 섞여 들어가는 것을 작성자가 원문 대조 없이 잡아낼 수 있는가"이며, 이는 한 번 출판 전에 발견하지 못하면 논문 전체의 scope 위반으로 남는 비가역적 위험이다. thesis는 이 두 위험을 "계획서의 완성도"라는 하나의 척도로 합산해 논거 1을 논거 2-3과 동등한 "반박 불가능한 결함"으로 제시하지만, brief의 출력 요구사항 1번("Check the SNU thesis guideline format requirements")은 형식 검증을 "계획서 자체가 갖추고 있어야 할 항목"이 아니라 "디베이트가 점검해야 할 항목"으로 규정한다. 형식 보강은 이번 디베이트의 amendment list에 한 줄 추가하면 충분하며, §3장 본론처럼 절 단위 재작성이 필요한 영역과 동급으로 취급할 근거는 약하다.

## 반론 2 — §4.2.3의 단일 구절 삭제는 실제로 정확했다; thesis가 검증하지 않은 §4.2.2에 더 정확한 반례가 있다
thesis는 "§4.2.3 'for the route-level orchestrator' 구절만 삭제하라는 지시의 전제 자체가 검증되지 않았다"고 주장했다. 그러나 `04_main_arxiv_flattened_with_inputs.tex` line 246을 직접 대조하면:

> "...This merged step keeps only a small frontier in the main loop while still surfacing candidate junctions early enough **for the route-level orchestrator**. Appendix~\ref{app:expansion-meeting-details} records the exact top-$K_{\mathrm{exp}}$ selection rule, child-promotion formula, and meeting criterion used to instantiate this step."

해당 문단에서 HIGH 용어는 정확히 마지막 종속절 하나("for the route-level orchestrator")뿐이며, 나머지는 frontier 관리·child promotion·meeting criterion이라는 순수 LOW 내용이고 인용된 부록(`app:expansion-meeting-details`)도 LOW-level 부록이다. 즉 계획서의 "구절만 삭제 후 유지" 지시는 이 절에 대해서는 사실 정확했다. thesis는 "검증되지 않았다"는 방법론적 비판을 했지만 본인이 원문을 대조하지 않았다.

반면 §4.2.2(Node Evaluation, `sec:node-evaluation`) 도입부 line 196은 다음과 같다:

> "Because different ordered tree pairs can require different bridge hypotheses, target selection must be pair-conditioned rather than globally shared. **Once the route-level orchestrator chooses an ordered source/counterpart pair $(i,j)$ to expand**, each source-side representative $\rho$ in $\mathcal{T}_i$ selects a target node $m\in\mathcal{V}_j$..."

이 문장은 §4.2.3과 거의 동일한 위험 문구("route-level orchestrator chooses...")를 포함하지만, 계획서의 §4.2.2 항목(제3장, "재정당화 문장" 부분)은 이 문장을 언급하거나 삭제 지시를 내리지 않고, 단지 새로운 도입 문장을 추가하라고만 적어 두었다. 즉 실제 결함은 thesis가 지목한 §4.2.3이 아니라 §4.2.2에 있다. 이는 thesis의 비판 방향("절 단위 지시가 위험하다")이 옳다는 것을 오히려 더 강하게 뒷받침하는 동시에, thesis 스스로도 "원문 대조 없이 결론을 내리지 말라"는 자신의 원칙을 §4.2.3 분석에서 지키지 못했음을 보여준다.

## 반론 3 — Conclusion에 "대체 문장"을 요구하는 것은 계획서(plan)와 초안(draft)의 경계를 넘어선다
brief의 요구 출력 6번은 "amendment list: concrete paragraphs, tables, equations, terminology rules, figure rules, and per-chapter writing instructions to add"라고 명시한다. 이는 "지침(instruction)"을 요구하는 것이며 "완성된 문장"을 요구하지 않는다. 그런데 thesis 논거 3은 계획서가 Conclusion 절을 위해 "원문 문장을 대체할 한 문장"을 제공하지 않았다고 비판한다. 그러나 실제 계획서 제5장 항목을 다시 보면, 이미 세 개의 구체적 주장과 그 근거가 명시되어 있다:

1. 데이터 효율성 — Q1 성공률(99.8/99.3/99.5%, giant +34.5pt)
2. 경로 효율성 — Q2(`tab:plan_length_bfs`, 15개 중 14개가 BFS 1.1배 이내)
3. 탐색 효율성 — Q3(`tab:planning_cost_ablation`, 9.5 vs 24.0~28.2 nodes)

이는 "결론이 무엇을 주장해야 하는가"에 대한 완전한 콘텐츠 사양(claim + evidence 매핑)이며, 작성자는 이를 산문으로 옮기기만 하면 된다. thesis가 요구하는 "대체 문장 자체"는 사실상 초안 작성이지 계획이 아니다. 디베이트가 평가해야 할 기준은 "작성자가 원문을 다시 읽어야 하는가"인데, 위 세 항목은 원문의 어떤 문장도 참조할 필요 없이 그 자체로 완결된 주장-근거 쌍을 제공하므로, "원문 재독 없이 쓸 수 있는가"라는 1차 기준은 이미 충족된다. 다만 "원문 결론 문장의 위험 어휘(coupling, route, re-solving)를 그대로 베껴 쓰지 말라"는 명시적 금지 규칙 한 줄을 추가하는 것은 합리적인 보강이며, 이는 thesis의 "결함"이라는 평가보다는 "경미한 명료화 보강"으로 재분류되어야 한다.

## 반론 4 — Appendix 보류는 누락이 아니라 추적된 결정이며, 본론 절들은 부록 디테일 없이도 자기완결적이다
thesis는 "Low-Level Planner State, Scoring, and Meeting Details" 부록(line 822)이 계획서에 전혀 언급되지 않았다고 지적한다. 그러나 계획서의 "Appendix 처리" 항목은 "이번 인터뷰 범위 제외 (별도 확인 예정)"이라고 명시적으로 적어 두었다 — 이는 침묵이 아니라 추적된 보류(tracked deferral)다. 더 중요한 것은, 본론 §4.2.1과 §4.2.3이 실제로 이 부록을 인용하는 방식을 확인하면 둘 다 "본문에서 이미 설명을 끝낸 뒤, 정확한 수식·튜플 유도는 부록을 보라"는 보충 참조일 뿐이라는 점이다:

- line 182 (§4.2.1): "...Appendix~\ref{app:planner-state-details} gives the **exact tuple**, the recurrence for $g(n)$, and the root-target construction..."
- line 246 (§4.2.3): "Appendix~\ref{app:expansion-meeting-details} records the **exact** top-$K_{\mathrm{exp}}$ selection rule, child-promotion formula, and meeting criterion..."

두 경우 모두 본문 문장 자체가 이미 완결된 서술이고, 부록은 "정확한(exact)" 수준의 세부 유도를 위한 선택적 참조다. 즉 본론 7p 분량의 §4.2.2/§4.2.3을 "유지" 지시만으로 작성하는 데 이 부록이 필수적이라는 thesis의 주장은 과장이다. 부록 자체가 LOW-level이라는 분류는 맞지만, 그 부록을 계획서에서 다루지 않았다고 해서 본론을 쓸 수 없는 것은 아니다 — 이는 부록 챕터를 쓸 때 필요한 작업이며, 계획서는 그 시점을 "별도 확인"으로 정확히 미뤄두었을 뿐이다.

## 반론 5 — 위험 용어 체크리스트의 부재는 계획서의 결함이 아니라 이번 디베이트의 산출물 그 자체다
brief의 요구 출력 7번은 "Flag any terms that are dangerous... (route, waypoint, anchor, orchestrator, online, pair-conditioned, Hamiltonian, mTSP, route composition, multi-tree)"라고 명시하는데, 이는 디베이트 참가자(thesis/antithesis/synthesis)가 생산해야 할 산출물로 설계되어 있다. thesis는 이 체크리스트가 `01_thesis_writing_plan.md` 안에 이미 존재하지 않는다는 사실을 "계획서의 결함"으로 제시했지만, 이는 순환 논증에 가깝다 — 애초에 이 디베이트의 목적이 그 체크리스트를 amendment로 만들어내는 것이기 때문이다. 계획서가 인터뷰 단계에서 이미 절별로 위험 용어 처리 결정을 개별적으로 내려두었다는 사실(§4.2.1 anchor index 단순화, §4.2.3 orchestrator 구절 삭제, §3.2 "repeatedly re-solves the route" 구절 삭제 등)은 오히려 위험 용어 인식 자체는 누락되지 않았다는 증거이며, 부족한 것은 "사전에 통합된 단일 표"라는 제시 형식(presentation format)일 뿐 내용적 판단의 부재가 아니다. 형식과 내용을 구분하지 않으면, 모든 절별 결정이 흩어져 있다는 이유만으로 "전체가 부재하다"는 과장된 결론에 이르게 된다.
