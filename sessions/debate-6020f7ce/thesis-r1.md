---
id: thesis-r1
role: thesis
round: 1
session_id: debate-6020f7ce
topic: "Audit thesis_writing_plan for SNU ECE thesis format and strict low-level-planner-only rewrite"
replies_to: []
pr_url: null
date: "2026-06-16"
---

# Thesis: Audit thesis_writing_plan for SNU ECE thesis format and strict low-level-planner-only rewrite

## 핵심 주장

`paper/thesis_writing_plan.md`(이하 "계획서")는 현재 상태로는 원문(`main_arxiv.tex`, ChronoForest)을 다시 펴보지 않고 LOW-level-only 학사논문을 끝까지 써낼 수 없다. 계획서는 (1) SNU 전기·정보공학부 학사 학위논문 작성지침이 명시적으로 요구하는 서식 항목들(외표지·인준지·국·영문 초록 쌍방향 구조·주요어 개수·목차/표목차/그림목차·줄간격·폰트·페이지 번호 체계·참고문헌 표기 규칙)을 단 한 줄도 다루지 않고, (2) "문단(Para1/Para2)" 또는 "구절 하나만 삭제"와 같은 거친 단위로 HIGH 콘텐츠 제거를 지시하는데, 실제 원문은 같은 문단·같은 절 안에서 LOW와 HIGH 표현이 문장 단위로 교차 배치되어 있어 그 거친 단위로는 무엇을 남기고 무엇을 지울지 결정할 수 없다. 결과적으로 작성자는 계획서만으로는 정확한 절단선을 알 수 없고, 매 챕터마다 원문을 다시 읽고 직접 LOW/HIGH를 재분류해야 한다. 이는 디베이트 태스크 브리프가 명시한 판정 기준("원문을 다시 읽지 않고 쓸 수 있는가")에 정확히 위배되며, 계획서는 구체적인 보완이 있어야만 그 기준을 통과할 수 있다.

## 논거 1 — 학사 학위논문 작성지침의 서식 요구사항이 계획서에 전혀 반영되어 있지 않다

`02_thesis_guideline_extracted_clean.txt`는 다음을 명문화한다:

- 논문 기재 순서: "외표지, 인준지, 국문초록, 목차, 본문, 참고문헌, (부록), 영문초록" (국문 본문 기준) — 계획서에는 외표지·인준지·목차·표목차·그림목차에 대한 어떤 절도 없다. 계획서의 장 구성은 "제1장~제5장 + Abstract"뿐이며, 전체 논문에 필수적인 전/후 front-matter 구조 자체가 빠져 있다.
- 초록 작성요령(별표 3): "주요어(Keywords)는... 6개 이내로 선정", "학 번:" 표기 필수, 국문 초록 밑에는 국문 주요어, 영문 초록 밑에는 영문 keywords. 계획서의 "Abstract" 절(§105–111)은 문제/방법/결과 3문장만 정의하고, 주요어 6개 이내 선정 지시·학번 표기·국/영문 초록 두 개를 모두 작성해야 한다는 사실 자체를 언급하지 않는다.
- 본문 작성요령(별표 4): "본문은 두 줄 띄기(double spacing)를 기준으로 작성한다", "글자크기는 국문 10pt, 영문 11pt", "페이지는... 초록부터 표 목차까지 로마자 소문자, 본문부터는 아라비아 숫자로 표기". 계획서의 "0. 전역 결정"은 "총 ~20p 목표"라는 분량만 정하고 두 줄 띄기를 가정한 것인지 단일 줄 띄기를 가정한 것인지 밝히지 않는다. 두 줄 띄기는 같은 글자 수 기준 본문 분량을 사실상 줄여 보이게 하므로, 장별 분량 배분(제3장 ~7p 등)이 실제로 줄 띄기 규정을 반영해 산정된 것인지 알 수 없다 — 이는 단순 누락이 아니라 분량 배분 전체의 타당성을 흔드는 문제다.
- 참고문헌 작성요령(별표 7): 논문지/단행본을 서로 다른 항목 순서로 기재하라는 규정이 있으나 계획서는 참고문헌 처리 방식을 전혀 언급하지 않는다.

이 네 가지는 모두 "계획서에 없으면 작성자가 추론하지 않는다"는 디베이트 브리프의 엄격성 기준 그대로에 해당하는, 형식적이지만 누락하면 논문 심사에서 즉시 지적될 항목들이다.

## 논거 2 — "문단" 단위 지시는 같은 문단 내 LOW/HIGH 교차 배치를 처리할 수 없다

계획서 제1장 절(§27–31)은 "원문 Para2 'At the low level...' 문단 그대로 재사용 가능"이라고 적는다. 그러나 실제 원문 Introduction의 해당 문단은 다음과 같이 **하나의 문단 안에서** LOW와 HIGH가 이어진다:

> "These two levels are difficult for different reasons... **At the low level**, extending a short-horizon diffusion model through composition creates a trade-off between search efficiency and path efficiency... Existing diffusion-based and compositional planners mainly optimize plausible or goal-reaching generation rather than active path shortening [...]. **At the high level**, waypoint ordering requires comparing many anchor pairs even though the pairwise shortest-path matrix is unavailable a priori..."

"그 문단 그대로 재사용"이라는 지시는 이 문단의 전반부(LOW)와 후반부(HIGH)를 가르는 정확한 문장 경계를 제시하지 않는다. 작성자는 "At the high level" 문장이 시작되는 지점을 스스로 찾아 잘라내야 하며, 이는 원문을 다시 읽어야만 가능한 작업이다. 계획서가 "Para1 macroscopic, Para2 'At the high level...' 문단"이라는 표현으로 두 개의 분리된 문단처럼 서술한 것 자체가 원문 구조와 어긋난다는 점도, 계획서 작성 시 원문이 충분히 정밀하게 재검토되지 않았다는 증거다.

## 논거 3 — Related Work §3.2의 "구절 하나만 삭제" 지시는 실제 산재한 HIGH 표현을 누락시킨다

계획서(§45)는 "§3.2 Diffusion planners: 'repeatedly re-solves the route...' 구절 삭제 후 유지"라고만 적는다. 그러나 원문 §3.2(Diffusion planners for long-horizon composition) 전체에는 다음과 같이 최소 4곳에서 route-coupled 표현이 등장한다:

1. "their core contribution is a training paradigm rather than an explicit **route-cost-aware planner**"
2. "yet their main objective remains globally plausible long-horizon generation rather than explicit **route-cost-aware ordering**"
3. "but they still primarily optimize sampling-time exploration rather than **route-level re-solving from accumulated bridge evidence**"
4. "ChronoForest combines these strands by using short-fragment diffusion inside a tree-based planning loop that allocates limited search budget to collecting bridge evidence and **repeatedly re-solves the route from that evidence**. This shifts the comparison focus from plausibility alone to path efficiency and to the effect of new bridge evidence on **the current route objective**."

계획서가 지목한 구절은 이 중 4번 문장의 일부에 불과하다. 1, 2, 3번 문장과 4번 문장의 나머지 절반("This shifts the comparison focus... current route objective")은 계획서 지시에 따라 "삭제 후 유지"를 수행해도 그대로 남는다. 즉 계획서를 문자 그대로 따르면 HIGH 콘텐츠가 본문에 잔존하는 결과가 나온다 — 이는 추측이 아니라 텍스트 대조로 확인되는 사실이다.

## 논거 4 — §4.2.1 "표기 단순화"는 정당화 논리 자체의 HIGH 의존성을 가리지 못한다

계획서(§67)는 "§4.2.1 Architecture-Level Design: 유지 — 확정 (단, 다중 anchor 표기는... 시작점/목표점 트리 두 개로 단순화)"라고만 지시한다. 그러나 이 절의 정당화 문장은 표기보다 더 근본적으로 다중 anchor 설정에 의존한다:

> "Using multiple trees is beneficial because it broadens spatial coverage, enables **pair-specific target assignment for heterogeneous bridge hypotheses**, and reduces redundant denoising by reusing shared prefixes across related descendants."

"heterogeneous bridge hypotheses에 대한 pair-specific target assignment"이라는 이점은 여러 개의 ordered pair $(i,j)$가 동시에 존재하는 HIGH-level orchestrator 설정에서만 의미를 가진다. 단일 시작-목표 쌍에 양방향 트리 두 개만 있는 LOW-only 설정에서는 "pair-specific"이라는 표현이 가리킬 대상(복수의 pair)이 존재하지 않는다. 표기만 $\mathcal{A}\to\{\mathcal{T}_{\mathrm{src}},\mathcal{T}_{\mathrm{tgt}}\}$로 바꾸고 이 문장을 그대로 유지하면, "두 개의 트리뿐인데 pair-specific 할당이 왜 필요한가"라는 논리적 공백이 생긴다. 계획서는 이 문장이 재작성 대상인지조차 언급하지 않는다 — "유지 — 확정"이라는 표현은 오히려 이 문장도 그대로 둔다는 뜻으로 읽히므로 위험하다.

## 논거 5 — §4.2.2 Node Evaluation에는 계획서가 언급하지 않은 추가 삭제 대상 문장이 있다

계획서(§62–66)는 §4.2.2의 수식 $\mathcal{J}_{i\to j}\to\mathcal{J}$ 단일화와 "온라인 적응적 재선택" 도입 문장만을 다룬다. 그러나 원문 Node Evaluation 절의 도입부 자체가 HIGH-level 트리거로 시작한다:

> "Once **the route-level orchestrator chooses an ordered source/counterpart pair $(i,j)$ to expand**, each source-side representative $\rho$ in $\mathcal{T}_i$ selects a target node $m\in\mathcal{V}_j$..."

그리고 같은 절 말미에는: "the same $\mathcal{J}_{i\to j}$ is reused by **the route-level direct-bridge term in Section~\ref{sec:online-multi-tree-orchestrator}**" — 삭제 대상인 §4.3(Orchestrator)을 향한 교차 참조가 본문에 남는다. 계획서는 수식과 새 도입 문장만 지시하므로, 작성자가 원문을 재대조하지 않으면 "Once the route-level orchestrator chooses..."라는 문장 전체와 §4.3을 향한 forward-reference를 그대로 베껴 쓸 위험이 있다. 이는 99_source_inventory.md가 경고하는 "orchestrator"(18회), "route"(294회) 위험 용어가 계획서가 명시적으로 짚지 않은 위치에도 출현한다는 것을 보여준다.

## 논거 6 — Appendix 처리가 "범위 제외"로 미결인데 본문은 이미 특정 appendix 라벨을 인용한다

계획서(§115–117)는 "Appendix 처리: 이번 인터뷰 범위 제외 (별도 확인 예정)"이라고 명시한다. 그런데 같은 계획서의 제3장(§60)은 "Appendix~\ref{app:full-algorithm} 전체 알고리즘 참조만 유지"를, 제4장(§81–84)은 `tab:plan_length_bfs`(`app:stitch-bfs-validation`)와 `tab:planning_cost_ablation`(`app:planning-cost-support`)을 명시적으로 인용한다. 즉 본문 집필 지시는 이미 부록의 존재와 구조에 의존하고 있는데, 부록 자체의 LOW/HIGH 분류는 "추후 확인"으로 미뤄져 있다. 원문 부록을 직접 확인하면 분량과 위험도가 결코 작지 않다:

- `\section{Theoretical Justification of the mTSP Algorithm}`(원문 1086~2090행대, 12개 하위절: Problem Setting, Direct-Edge Assumptions, Floyd-Warshall Closure Error, **Route-Level Comparison Theorem**, Margin-Based Exact Recovery 등)은 전형적인 HIGH-only 수학적 부록으로, 계획서 어디에도 이름이 등장하지 않는다.
- 반면 `\section{Low-Level Planner State, Scoring, and Meeting Details}`와 `\section{Pruning and Representative Selection Details}`(약 822~1085행)는 계획서가 인용하는 `app:planner-state-details`, `app:pair-conditioned-ranking-details`, `app:expansion-meeting-details`에 해당하며 LOW 콘텐츠로 보인다.

계획서가 제3, 4장에서 부록을 인용하면서도 "부록 처리는 추후"라고 미결 처리한 것은, 본문 작성자가 인용 대상 부록 절의 LOW/HIGH 여부를 스스로 원문에서 찾아 확인해야 하는 상황을 만든다. 이는 디베이트 브리프 항목 5("plan이 각 챕터를 금지된 HIGH 콘텐츠 수입 없이 재작성할 충분한 detail을 주는가")가 정확히 묻는 실패 사례다.

## 논거 7 — Limitations 재작성 지시가 한 문장 내 LOW/HIGH 혼재를 다시 한 번 과소 절단한다

계획서(§94–96)는 원문 Limitations 첫 문장의 "and preserve a suboptimal tentative route until enough bridge evidence accumulates"만 HIGH로 지목해 삭제하라고 지시한다. 그러나 원문 Limitations 전체는 다음처럼 이어진다:

> "ChronoForest still depends on the quality of the learned temporal-distance prior... [LOW, 계획서가 인용한 부분] ... **Algorithmically, the online route module is evaluated only with small anchor sets and fixed-endpoint Hamiltonian updates**, so scaling to larger waypoint sets will likely require stronger pruning and more approximate combinatorial solvers. The theoretical analysis in Appendix~\ref{app:mtsp-theory} provides only a static sufficient justification for **the route-certification threshold and the current-route/off-route budget split**..."

계획서가 인용 범위로 다루지 않은 두 번째·세 번째 문장에는 "anchor sets"라는 LOW 어휘가 "Hamiltonian updates"라는 HIGH 어휘와 한 구(phrase) 안에 결합되어 있다("small anchor sets **and** fixed-endpoint Hamiltonian updates"). 계획서가 지정한 절단점(첫 문장 후반부만 삭제) 이후에 이 문장들이 자동으로 빠지는지 여부가 명시되어 있지 않으며, "anchor"라는 안전한 듯 보이는 단어가 HIGH 문맥에 재등장한다는 점에서 99_source_inventory.md가 요구한 "위험 용어 감시" 항목(anchor 자체는 위험 용어 목록에 없으나 이 사례가 보여주듯 LOW 용어도 HIGH 문맥에서 재오염될 수 있음)을 계획서가 다루지 못하고 있음을 보여준다.

---

이상 7개 논거는 모두 디베이트 태스크 브리프가 요구한 "추측하지 말고, 정확한 원문 절/문장과 정확한 대체 문구·지침을 짚으라"는 기준에 따라 원문과 계획서를 직접 대조한 결과다. 계획서는 전체 구조와 챕터 배분, 다수의 핵심 결정(표기 단순화, Q1/Q2/Q3 재구성, Limitations/Conclusion 재작성 방향)에서는 분명한 진전을 보였으나, 서식 요구사항 전체 누락과 문장 단위 절단선 부재라는 두 가지 체계적 결함 때문에 "원문을 다시 보지 않고 쓸 수 있는 계획서"라는 기준은 아직 충족하지 못한다.
