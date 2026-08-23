# AI 연구 에이전트를 통한 문화적 역량(Culture-in-Action)의 수치화

저자: 정호영

## 0. 표기 변경 안내

이전 판(2차 산출물)의 'FOL' 표기를, 일반적인 연구 논문에서 흔히 쓰는 형태로 전환했다. 대응 관계는 다음과 같다. 아울러 이번 판에서는 모든 수식을 LaTeX 기호 없이 순수 텍스트(÷, ×, ≤, ≥, Δ 등 일반 기호만 사용)로 다시 표기해, 문서 변환 시 깨지지 않도록 했다.

| 이전 표기 (FOL) | 새 표기 | 성격 |
|---|---|---|
| 앵커 논문의 FOL 0 | 결론(Conclusion, **C**) | 앵커 논문 자신의 최종 주장 |
| 앵커 논문의 FOL 0-1~0-9 | 전제 1~9(Premise, **P1~P9**) | 결론을 지지하는 근거 |
| 앵커 논문의 FOL 0-10 | 미검증 전제(Unwarranted Premise, **P10**) | 논문이 검증하지 않은 암묵적 전제 |
| 본 연구의 FOL 0 | 중심 연구질문(Central Research Question, **RQ**) | 본 연구가 던지는 질문 |
| 본 연구의 FOL 0-1~0-10 | 세부 연구질문 및 조작적 변수(**RQ1~RQ10** / **V1~V10**) | 측정 가능한 형태로 쪼갠 하위 질문·변수 |
| FOL 0-6′ | 개정된 변수(**RQ6′ / V6′**) | 취약점을 반영해 다시 정의한 변수 |
| FOL 1′ | 연구가설(Research Hypothesis, **H1**) | 최종적으로 검증하려는 예측 |

---

## 초록 (Abstract)

사회학자 Ann Swidler(Swidler, 1986)는 'Culture-in-Action' 이론을 통해 문화는 도구함(toolkit)이며 개인은 그로부터 역량을 길러 전략적 행위(strategies of action)를 구성한다는 틀을 확립했다. Wong-Villacres et al.(2020)은 이를 기초 이론으로 삼아 라틴계 이민자 부모 35명의 참여디자인(PD) 자료에서 역량·목표·구조적 제약의 관계를 질적으로 해부했다. 그러나 이 해부의 타당성은 오직 훈련된 연구자의 질적 해석 능력에만 근거한다는 한계를 가진다(앵커 논문 자신의 논증에서 검증되지 않은 전제, 3.1절 참조).

본 연구는 이 한계에서 출발해, 검색(Search)·근거추출(Grounding)·검증(Verification) 절차를 갖춘 AI 연구 에이전트가 이 질적 구성을 원문에 근거를 둔 수치 변수로 전환할 수 있는지를 묻는다. 앵커 논문의 논증에서 이 미검증 전제 하나를 교체하는 절차와, 독립적으로 세운 열 개의 조작적 변수를 앵커 논문의 실제 사례에 맞추어 재정식화하는 절차가 서로 다른 경로임에도 동일한 지점(결측 판별의 이분법적 한계)에서 만난다는 사실을 확인했다. 이 변수는 "정보의 있음/없음"이라는 이분법이 과소추출(false negative) 오류를 놓친다는 사실을 드러내며 3단계 신뢰도 함수로 개정되었다(V6′). 개정된 변수 체계를 앵커 논문의 두 전략 사례(Consejos, Closeness with teachers)에 수식으로 적용한 결과, 열 개 변수 모두 역추적 가능한 수치로 산출됨을 확인했다. 본 연구는 근거 없는 수치 생성(과잉추출, FP)뿐 아니라 정보 누락(과소추출, FN)까지 동시에 낮추는 것이 성공 기준이라는 가설(H1)을 제안하며, 완전한 실험적 검증은 향후 과제로 남긴다.

**키워드**: 문화적 도구함(Cultural Toolkit), 역량(Capacity), 전략적 행위(Strategies of Action), AI 연구 에이전트, 검색-근거추출-검증(S·G·V), 정량적 환각(Quantitative Hallucination)

---

## 0-1. 용어 설명

(1) **연구질문(Research Question, RQ)**: 논문이 답을 구하려는 물음. "가능한가?", "얼마나?"를 묻는다.
(2) **연구가설(Hypothesis, H)**: RQ에 대해 검증 가능한 형태로 미리 제시하는 예측.
(3) **조작적 변수(Operational Variable, V)**: RQ를 실제로 측정하기 위해 수식·규칙으로 정의한 값.
(4) **전제(Premise, P) / 결론(Conclusion, C)**: 논증을 구성하는 단위. 전제가 참이면 결론도 참이 되는 구조(삼단논법과 동일).
(5) 도구함(toolkit) / 역량(capacity) / 전략적 행위(strategies of action): Swidler 이론의 세 층위 — 도구함 = 문화가 제공하는 상징·이야기·관습의 연장통, 역량 = 그 연장통에서 실제로 꺼내 쓸 줄 아는 기술, 전략적 행위 = 그 기술들을 엮어 만든 반복적인 문제해결 습관.
(6) Settled(안정) / Unsettled(격변) 국면: 안정기에는 몸에 밴 습관대로 행동하고, 격변기에는 기존 습관이 안 통해 새로운 방법을 찾아 나선다.
(7) 검색(Search)·근거추출(Grounding)·검증(Verification), S·G·V: 검색 = 원문에서 관련 부분 찾기, 근거추출 = 찾은 부분을 인용하며 숫자로 바꾸기, 검증 = 그 숫자가 인용 부분과 맞는지 재확인하기.
(8) 과잉추출(False Positive, FP) / 과소추출(False Negative, FN): FP = 없는 것을 있다고 지어내는 오류, FN = 있는 것을 없다고 놓치는 오류.
(9) 주변수(Primary Variable) / 보조변수(Auxiliary Variable): 주변수 = 가설을 직접 검증하는 핵심 변수, 보조변수 = 그 전제조건이거나 결과를 종합하는 변수.
(10) 균등가정(Equal-Weight Assumption): 원문에 정확한 비중이 없을 때, 항목 수만큼 균등 배분한다고 미리 밝혀두는 것.

---

## 1. 서론

### 1.1 연구 배경

HCI(Human-Computer Interaction) 분야는 기술 기반 개입이 프로젝트 종료 이후에도 지속적으로 채택되도록 하는 문제를 오랫동안 다루어 왔으며, 이는 이미 존재하는 역량으로부터 설계가 시작되어야 한다는 원칙에서 출발한다(Kretzmann & McKnight, 1996; Moll, Amanti, Neff, & Gonzalez, 1992). 그러나 역량은 상황에 따라 자산도 되고 제약도 되는 유동적 성격을 가지므로, "어떤 역량을 어떤 설계 목적에 쓸 것인가?"라는 질문은 여전히 미해결로 남아 있었다(Cho, Herrera, Chaidez, & Uriostegui, 2019).

Wong-Villacres, DiSalvo, Kumar, & DiSalvo(2020)는 이 질문에 답하기 위해 Ann Swidler의 이론을 분석 관점으로 도입했다. 이 관점은 Bourdieu(1977)의 자본 이론이 지닌 구조결정론적 한계와, Suchman(1987)의 상황적 행위 이론이 지닌 지나치게 미세한 분석 단위 문제 사이에서 중간 지점을 취한다. Wong-Villacres 등(2020)은 이 렌즈를 저소득 라틴계 이민자 부모 35명과의 1개월 참여디자인(PD) 작업에 적용해, "Consejos"와 "Closeness with teachers"라는 두 전략을 역량·목표·구조적 제약의 관계로 해부했다.

### 1.2 연구의 출발점과 기여

이 해부는 풍부한 질적 통찰을 제공하지만 서술적(descriptive) 형태에 머문다. 앵커 논문 스스로도 이 해석의 타당성을 뒷받침하는 검증 절차를 제시하지 않으며, 그 근거는 훈련된 연구자의 질적 해석 능력에 의존한다(3.1절에서 이를 앵커 논문 자체의 논증 구조로 직접 보인다). 본 연구는 다음을 기여한다.

1. 앵커 논문 자신의 논증에서 가장 취약한 전제(P10)를 식별하고, 그 전제 하나만을 새로운 주장으로 교체하는 절차를 통해 연구 문제를 도출한다.
2. Swidler의 Culture-in-Action 개념을 조작적으로 정의된 열 개의 변수(V1~V10)로 분해하는 프레임워크를 제안한다.
3. 이 중 가장 취약한 변수(결측 판별, V6)를 반증 논리로 검토하여 3단계 신뢰도 함수(V6′)로 개정한다.
4. 개정된 변수 체계를 앵커 논문의 실제 사례에 수식으로 적용해 실행 가능성을 입증한다.

---

## 2. 관련 연구

### 2.1 실천이론과 문화사회학

Bourdieu(1977)는 자본(capital)의 축적 메커니즘이 이미 자본을 가진 집단에 유리하게 작동한다고 보았다 — 구조적 제약을 설명하는 데는 강력하지만 지나치게 결정론적이다. Suchman(1987)의 상황적 행위 이론은 개인의 행위성(agency)을 복원하지만 분석 단위가 지나치게 미세하다. Swidler(1986)의 culture-in-action 이론은 이 두 접근 사이의 중간 지점을 취한다.

### 2.2 자산기반 HCI 디자인

Kretzmann & McKnight(1996)과 Moll 등(1992)은 역량을 기반으로 설계가 시작되어야 한다는 원칙을 확립했다. Cho 등(2019)은 이를 HCI에 적용해 comadrazgo(여성 간 긴밀한 우정)를 자산으로 식별하는 SMS 시스템을 설계했다. Wong-Villacres 등(2020)은 이 계보 위에서, 맥락 속 역량을 설계에 연결하는 방법론적 공백을 Culture-in-Action 관점으로 제시한다.

### 2.3 AI 연구 에이전트와 정량적 환각

Lewis 등(2020)의 검색결합생성(RAG)은 검색 정보를 결합해 생성 내용의 출처를 제공할 가능성을 열었다. Yao 등(2023)의 ReAct는 추론과 행동을 교차시켜 환각과 오류 전파를 줄이는 방법을 제시했다. 그러나 Ji 등(2023)이 정리하듯, 언어모델에는 근거 없는 내용을 사실처럼 제시하는 환각이 구조적으로 내재한다.

---

## 3. 연구의 출발점: 앵커 논문의 논증 재구성과 최초 연구질문의 수렴

### 3.1 앵커 논문의 논증 구조: 전제-결론 재구성

앵커 논문 자체가 주장하는 바를 전제(Premise)-결론(Conclusion) 형식으로 재구성했다. 이는 삼단논법과 같은 형식으로, 각 전제가 참이면 결론도 참이 되어야 하는 구조다.

**결론(C)**: Swidler의 culture-in-action 관점은 "situated한 역량 중 무엇을 어떤 설계 목적에 활용해야 하는가"라는 문제를 분석하는 데 유효하다.

**전제 1~9 (P1~P9)** — 결론을 지지하는 근거:

| 전제 | 내용 |
|---|---|
| P1 | 자산기반 설계는 결핍이 아닌 이미 존재하는 자산·역량에서 개입을 시작해야 한다 |
| P2 | 역량은 situated한 성격을 가지므로, 어떤 역량을 어떤 목적에 쓸지는 미해결 질문이다 |
| P3 | Activity Theory, Bourdieu의 자본이론, Suchman의 situated action은 각각 한계가 있다 |
| P4 | Swidler의 관점은 구조적 제약과 개인의 창의적 행위성을 함께 조명하는 중간 지점을 제공한다 |
| P5 | 문화는 도구함이며, 개인은 이로부터 역량을 길러 전략적 행위를 구성한다 |
| P6 | 전략적 행위 단위로 접근하면 역량-목표-제약의 관계가 심층적으로 드러난다 |
| P7 | Settled 국면은 기존 역량이 목표를 결정하고, unsettled 국면은 도구함을 재검토한다 |
| P8 | 이 관점을 실제 PD 자료에 적용하면 두 전략(Consejos, Closeness)에서 관계가 드러난다 |
| P9 | 이 해부는 새로운 설계 방향을 도출하게 한다 |

**전제 10 (P10) — 미검증 전제**:

> 이 해석의 타당성은 훈련된 연구자의 질적 해석 능력에 근거하지만, 이를 독립적으로 재현하거나 수치로 교차검증하는 절차는 논문 전체에 걸쳐 제시되지 않는다.

P1~P9는 선행 연구 인용이나 실제 사례로 뒷받침되지만, P10은 논증 자체가 검증하지 않은 전제다. 해석이 유일하게 연구자 개인의 판단에만 의존한다면 사례·연구자 간 비교나 재현은 원칙적으로 불가능하다. 본 연구는 이 전제 하나만을 다음 명제로 교체한다.

> **대체 전제(P10′)**: situated capacities의 해석은 훈련된 연구자의 질적 해석에만 의존하지 않아도 된다. 검색·근거추출·검증(S·G·V) 절차를 가진 AI 연구 에이전트가 원문에 역추적 가능한 수치를 산출함으로써, 해석의 타당성을 검증 가능한 형태로 보완할 수 있다.

### 3.2 최초 연구질문 체계와의 수렴

이 절차와는 별개로, 본 연구는 초기에 다음과 같은 **중심 연구질문(RQ)**을 세웠다.

> **RQ**: AI 에이전트는 문화적 도구함·역량·전략처럼 본래 수치화하기 어려운 질적 현상을, 원문의 의미를 왜곡하지 않으면서 수치적 변수로 전환할 수 있는가?

이를 측정 가능한 형태로 분해한 열 개의 세부 연구질문(RQ1~RQ10) 가운데, "역량 부재를 정직하게 결측으로 처리하는가"를 묻는 **RQ6**이 가장 중요한 항목으로 지목되었다. 흥미로운 점은, 앵커 논문의 논증(3.1절)에서 식별한 미검증 전제(P10)와, 이 독립적인 탐색(RQ6)이 정확히 같은 문제 — 질적 해석·결측 판별의 타당성 검증 — 로 수렴한다는 사실이다. 서로 다른 두 경로가 같은 지점에 도달한다는 것은 이 지점이 우연이 아님을 시사한다.

---

## 4. 이론적 틀: Culture-in-Action의 재구성

Swidler(1986)의 이론은 세 요소로 구성된다. 도구함(toolkit)은 문화적 자원의 총체, 역량(capacity)은 그로부터 길러지는 습관·기술·스타일, 전략적 행위(strategies of action)는 역량을 동원해 조립한 목표 추구 방식이다. Settled 국면에서는 기존 역량과 전략의 가용성이 목표 선택을 결정하고, unsettled 국면에서는 도구함을 재검토하며 전략을 재구성한다. Wong-Villacres 등(2020)은 부모들이 학업 문제에 직면했을 때의 상태를 "unsettled times"라고 명명했는데, 이는 6장에서 볼 것처럼 이론적 구성개념이 실제 서술 안에 존재한다는 첫 단서가 된다.

---

## 5. 방법론: 조작적 변수와 산식

### 5.1 AI 에이전트의 세 기능 (S·G·V)

에이전트는 세 기능을 순서대로 수행한다: 검색(Search) — 근거추출(Grounding) — 검증(Verification).

### 5.2 열 개의 조작적 변수(V1~V10)와 산식

각 연구질문(RQ)을 측정 가능한 변수(V)로 정식화하고, 계산식을 명시한다. 모든 수식은 일반 텍스트 기호(÷, ×, ≤, ≥, Δ)만 사용해 표기했다. 각 변수마다 무엇을 왜 측정하는지에 대한 설명과 이해를 돕는 예시를 함께 붙였다.

**V1 — 도구함 다양성 지수 (Toolkit Diversity Index, DI)** [보조변수]

이해관계자가 하나의 문제를 해결하기 위해 몇 가지의 서로 다른 문화적 자원(도구함 요소)을 동원하는지를 측정한다. 값이 높을수록 그 사람(또는 집단)이 다양한 자원을 폭넓게 활용하고 있다는 뜻이다. 한 사람이 여러 요소를 동시에 언급하면 요소 수가 참여자 수보다 많아져 지수가 1을 넘을 수 있다.

```
DI = N_e ÷ N_p
```
- N_e: 원문에서 식별된 고유(서로 다른) 도구함 요소의 개수
- N_p: 그 요소들을 언급한 참여자의 수(한 사람이 여러 요소를 언급해도 1명으로 센다)

*예시*: 한 참여자가 "전화로 연락했다", "이웃에게 부탁했다", "가족에게 대신 시켰다"라는 세 가지 방법을 언급했다면 N_e = 3, N_p = 1이므로 DI = 3 ÷ 1 = 3.0이다. 이는 "한 사람이 도구함에서 세 가지 자원을 꺼내 썼다"는 뜻으로, 값이 클수록 대응 방식이 다채롭다는 것을 보여준다.

**V2 — 역량-도구함 연결강도 (Connection Strength, CS)** [주변수]

어떤 역량(예: 인내심)이 "도구함의 어떤 요소에서 비롯되었는가"를 원문이 얼마나 직접적으로 뒷받침하는지를 측정한다. 근거 문장이 역량을 언급한 문장에 가까울수록(문장거리가 0에 가까울수록) 연결이 강하다고 본다. "말은 했지만 근거가 먼 이야기"와 "역량을 말하자마자 바로 이유를 댄 이야기"를 수치로 구분해준다.

```
CS = 1 ÷ (d + 1)
```
- d: 역량이 언급된 문장과 그 근거(도구함 요소)가 언급된 문장 사이에 끼어 있는 다른 문장의 수

*예시*: "나는 인내심이 강해서 포기하지 않았다"처럼 역량과 근거가 한 문장에 붙어 있으면 d = 0, CS = 1 ÷ 1 = 1.0(가장 강한 연결). 두 문장이 떨어져 있으면 d = 2, CS = 1 ÷ 3 ≈ 0.33으로 낮아진다 — 문장이 멀어질수록 그 역량의 출처가 불분명해진다는 것을 반영한다.

**V3 — 안정국면 영향력 점수 (Settled-Phase Influence Score, SI)** [보조변수]

앵커 논문의 "settled(안정) 국면" — 위기 없이 일상적으로 행동하는 상황 — 에서, 특정 역량이 특정 전략(습관적 행동)을 얼마나 강하게 뒷받침하는지를 측정한다. 순수한 나눗셈이 아니라 "확언의 강도"에 따라 등급을 매기는 규칙 기반 점수다 — 원문이 얼마나 예외 없이 단정적으로 말하는가가 점수를 결정한다.

```
전칭 표현(all, every) + 공기       → SI = 1.0
준전칭 표현(most, almost all) + 공기 → SI = 0.9
부분 표현(some, a few)             → SI ≤ 0.5
```
- "공기(co-occurrence)"란 역량과 전략이 같은 문장 또는 바로 옆 문장에 함께 등장하는 것을 뜻한다.

*예시*: 원문이 "모든 참여자가 항상 이 전략을 썼다"처럼 "all"을 쓰면 SI = 1.0. "대부분의 참여자가 이 전략을 썼다"처럼 "most"를 쓰면, 예외가 있을 수 있음을 반영해 SI = 0.9로 살짝 낮춘다.

**V4 — 격변국면 재검토지수 (Unsettled-Phase Reconsideration Index, RI)** [주변수]

앵커 논문의 "unsettled(격변) 국면" — 위기가 닥쳐 기존 습관이 통하지 않는 상황 — 에서, 이해관계자가 실제로 "다른 방법을 찾아본다"는 신호를 얼마나 자주 드러내는지를 측정한다. 그 인물이 얼마나 뚜렷하게 새로운 전략을 탐색하는지를 문장 단위로 계량화한 것이다.

```
RI = N_m ÷ N_s
```
- N_m: 전략전환을 알리는 표현(예: "다시", "새로운 방법으로", "찾아보았다")이 포함된 문장의 수
- N_s: 해당 구간(문단)의 전체 문장 수

*예시*: 열두 문장짜리 문단에서 이런 표현이 세 번 등장하면 RI = 3 ÷ 12 = 0.25 — "이 문단의 약 4분의 1이 전략 재검토를 서술하고 있다"는 뜻이며, 값이 높을수록 격변기를 더 뚜렷하게 겪고 있음을 시사한다.

**V5 — 전략-역량 기여도 배분 (Contribution Allocation, w_i)** [보조변수, 균등가정]

하나의 전략(예: "교사와 친해지기")이 여러 역량(인내, 신뢰추구, 협상력 등)으로 이루어져 있을 때, 각 역량이 그 전략에 얼마나 기여하는지를 퍼센트로 나타낸다. 원문이 "어느 역량이 더 중요한지" 명시하지 않는 경우가 대부분이므로, 이때는 비중을 지어내는 대신 "모른다는 사실 자체"를 균등가정으로 명시한다.

```
w_i = 100% ÷ n     (i = 1, ..., n)
```
- n: 그 전략을 구성하는 것으로 식별된 역량의 개수

*예시*: 역량이 3개면 각각 100% ÷ 3 ≈ 33.3%씩 배분한다. 이는 "이 세 역량이 실제로 똑같이 중요하다"는 발견이 아니라 "원문에 비중이 없으므로 동일하게 취급했다"는 방법론적 선언이며, 반드시 그 사실을 함께 밝혀야 한다.

**V6 — 결측 판별 함수 (원판, 취약점)** [주변수]

원문에 특정 정보가 있는지 없는지를 AI가 정직하게 판별하는지를 검증하는 항목이다. 원판은 "있다/없다"의 이분법만 허용했는데, 이는 "확실히 언급되지는 않았지만 맥락상 충분히 짐작할 수 있는 정보"라는 회색지대를 놓치는 문제가 있다.

```
근거 존재 → M(x) = 값 산출
근거 부재 → M(x) = N/A
```

이 이분법은 과소추출(FN)을 은폐하므로, 아래 V6′로 개정한다.

**V6′ — 개정된 3단계 결측 판별 함수** [주변수, 개정판]

이분법의 문제를 보완하기 위해 "완전히 확실한 근거", "짐작할 수는 있지만 확신할 수 없는 근거", "근거가 전혀 없음"의 세 단계로 나눈다. 이렇게 하면 AI가 "모르겠다"고 대충 넘기는 것(과소추출)도, "있는 것처럼 지어내는 것"(과잉추출)도 모두 잡아낼 수 있다.

```
명시적 근거(전칭 표현 등)              → M'(x) = 1.0
암묵적 근거(구체적 서술, 강도수식어 없음) → M'(x) = c   (c는 0.5~0.8 범위)
근거 부재                             → M'(x) = N/A
```
- "명시적 근거"란 "all", "always"처럼 확정적으로 서술된 경우다.
- "암묵적 근거"란 구체적인 발화나 행동은 서술되어 있지만 그 강도(빈도·정도)를 나타내는 수식어가 없는 경우다. 이때 부여하는 신뢰도 c는 발화 근거가 전혀 없는 경우(0.3~0.4대)보다는 높고, 강도 수식어까지 갖춘 경우(0.8~1.0대)보다는 낮게 사례별로 판단해 매긴다.

성공 기준은 다음 두 오류율을 동시에 낮추는 것이다.

```
FPR = 근거 없이 생성된 값 수 ÷ 전체 생성 값 수
FNR = 놓친 추론 가능 정보 수 ÷ 전체 추론 가능 정보 수
```

FPR은 "지어낸 오류", FNR은 "놓친 오류"를 독립적으로 측정한다. 좋은 AI 에이전트는 이 둘을 동시에 낮춰야 한다 — FPR만 낮추면 응답을 회피해서 점수를 따는 부작용(N/A 남발)이 생기기 때문이다.

**V7 — 구조적 제약 가용률 (Availability Rate, AR)** [주변수]

정원·인원·예산처럼 물리적으로 정해진 한계(구조적 제약)가 실제 수요에 비해 얼마나 부족한지를 비율로 나타낸다. 비율이 낮을수록 그 제약이 역량의 발현을 심하게 가로막고 있다는 뜻이다. 원문에 두 수치가 모두 명시되어 있을 때만 계산하며, 하나라도 없으면 억지로 추정하지 않는다.

```
AR = N_avail ÷ N_demand
```
- N_avail: 원문에 실제로 서술된, 이용 가능한(성공한) 인원·횟수
- N_demand: 원문에 실제로 서술된, 그것을 원하는 전체 수요

*예시*: "하루 20명이 상담을 원하는데 교사는 시간이 없다"는 문장에서 N_demand = 20, 실제로 성공한 사례가 1건으로 서술되어 있다면 N_avail = 1, AR = 1 ÷ 20 = 0.05 = 5%. "수요의 5%만 충족된다"는 구조적 병목을 숫자로 드러낸다.

**V8 — 역량 양가성 점수 (Ambivalence Score, AS)** [주변수]

같은 역량(예: 고집스러운 인내심)이 어떤 맥락에서는 도움이 되고 어떤 맥락에서는 오히려 방해가 될 때, 이 양쪽의 균형을 −1(완전히 부정적)부터 +1(완전히 긍정적) 사이의 값으로 표현한다. 0에 가까울수록 그 역량이 자산과 제약으로 팽팽하게 맞서고 있다는 뜻이다.

```
AS = (N_pos − N_neg) ÷ (N_pos + N_neg)     [범위: −1 ≤ AS ≤ 1]
```
- N_pos: 그 역량이 긍정적으로 작용했다고 서술된 문맥의 수
- N_neg: 그 역량이 부정적으로(제약으로) 작용했다고 서술된 문맥의 수

*예시*: 긍정 문맥 1개, 부정 문맥 1개가 한 문장 안에 나란히 서술되어 있으면 AS = (1−1) ÷ (1+1) = 0 — 완전한 양가성을 뜻한다.

**V9 — 종합 목표부합도 (Composite Fit Score, FS)** [보조변수]

여러 역량과 여러 제약을 한꺼번에 고려했을 때, 그 사람(또는 전략)이 상위 목표에 얼마나 부합하는지를 단일 점수로 종합한다. 역량은 부합도를 높이고 제약은 낮추는데, 제약이 역량을 얼마나 상쇄하는지의 가중치(w_L)는 원문에 없는 경우가 많으므로 반드시 가정임을 밝히고 사용한다.

```
FS = (C − L×w_L) ÷ (C + L)
```
- C: 식별된 역량의 개수
- L: 식별된 제약의 개수
- w_L: 제약 하나가 역량 하나를 상쇄하는 정도(가중치). 원문에 없으면 본 연구는 0.5(절반)를 기본값으로 사용

*예시*: 역량 3개, 제약 2개, w_L = 0.5라면 FS = (3 − 2×0.5) ÷ 5 = (3−1) ÷ 5 = 0.4. "역량이 제약보다 많지만 완전히 압도하지는 못하는 중간 수준의 부합도"를 뜻한다.

**V10 — 개입 전후 변화량 (Pre/Post Intervention Delta, ΔFS)** [보조변수]

특정 기술적 개입(예: 새로운 앱 기능)이 도입되기 전과 후, 같은 산식(V9)을 각각 적용해 부합도가 얼마나 개선되었는지를 하나의 숫자로 보여준다. 양수면 개입이 긍정적으로 작용했다는 뜻이고, 음수면 오히려 악화되었다는 뜻이다.

```
ΔFS = FS_after − FS_before
```

*예시*: 개입 전 FS = 0.25, 개입 후 FS = 0.5라면 ΔFS = +0.25 — 개입이 부합도를 두 배로 끌어올렸다는 것을 의미한다.

주변수(V2, V4, V6′, V7, V8)는 S·G·V 기능을 직접 활용해 정확도·환각감소 목표를 곧바로 검증하며, 보조변수(V1, V3, V5, V9, V10)는 그 전제조건이거나 결과를 종합한다.

### 5.3 연구가설(H1)

> **H1**: 검색·근거추출·검증 절차를 갖춘 AI 연구 에이전트는 단순 언어모델 대비 FPR을 낮추는 동시에 FNR도 낮춘다. 단, FPR의 감소가 FNR의 증가(응답 회피)로 상쇄된 결과라면 이는 H1의 반증 사례로 간주한다.

---

## 6. 사례 적용: 산식에 실제 값 대입

본 절은 5장의 각 변수를 앵커 논문의 실제 원문 인용에 적용한다. 계산 결과만 제시하지 않고, 어떤 문장을 근거로 어떤 판단을 내렸는지를 함께 설명한다.

### 6.1 "Consejos" 전략 — V1, V2, V3

**V1 계산 (도구함 다양성)**: 부모들이 동원한 도구함 요소를 원문에서 다음 네 가지로 식별했다 — ① 가족 출신과 계급에 관한 서사("I tried to make them see where they come from...", Clara), ② superación(자기 성취) 담론("he needs to have a clearly defined goal...", Regina), ③ 개인적 실패-극복 서사("the best students... calling me a 'burro'...", Roberto), ④ 인내에 관한 신념("my strength is to be perseverant...", Regina). 이 네 요소를 언급한 사람은 Clara·Regina·Roberto 세 명이다(Regina가 ②와 ④ 두 요소를 함께 언급했으므로 요소 수가 참여자 수보다 많아진다).

```
DI = N_e ÷ N_p = 4 ÷ 3 = 1.33
```

*해석*: 1.33이라는 값은 "평균적으로 한 참여자가 한 개보다 조금 더 많은 도구함 요소를 동원했다"는 뜻이며, Consejos 전략이 단일한 자원이 아니라 여러 문화적 자원(가족서사, 성취담론, 실패극복담, 인내신념)을 복합적으로 엮어 만들어졌음을 보여준다.

**V2 계산 (연결강도)**: Roberto의 역량("academic resources can be mixed with values-based ones")과 그 근거가 되는 그의 개인 서사("the best students... calling me a 'burro'...")는 같은 문단, 서로 인접한 문장에서 등장한다. 즉 두 표현 사이에 다른 문장이 끼어 있지 않으므로 d = 0.

```
CS = 1 ÷ (d + 1) = 1 ÷ (0 + 1) = 1.0
```

*해석*: 1.0은 산식이 낼 수 있는 최댓값으로, Roberto의 역량이 그의 개인 경험담과 곧바로, 가장 직접적인 형태로 연결되어 있음을 뜻한다. 즉 "이 역량이 어디서 왔는가"라는 질문에 원문이 즉답을 주고 있는 경우다.

**V3 계산 (안정국면 영향력)**: 원문 "As most of our participants, Regina only used values-based resources... to craft consejos for motivating academic development"는 "most"라는 준전칭 표현을 쓰면서, 역량(values-based resources)과 전략(consejos)이 한 문장 안에 함께(공기) 나타난다.

```
SI = 0.9     (규칙: 준전칭 표현 + 공기 → 0.9)
```

*해석*: 0.9는 "전체는 아니지만 거의 모든 참여자"에게서 나타나는 강한 패턴임을 뜻한다. "all"이 아니라 "most"를 썼다는 점에서 1.0이 아닌 0.9로 한 단계 낮춰, 예외적 사례(Roberto처럼 다른 방식을 섞은 경우)가 존재할 가능성을 수치에 반영했다.

### 6.2 "Closeness with teachers" 전략 — V4, V5, V6′, V7, V8

**V4 계산 (재검토지수)**: 다음 문단(원문 그대로 인용)에 적용한다.

> "Lucia's experience illustrates our analysis. Like Lucia, many immigrant parents have developed distrust-based strategies for protecting their family and themselves. 'I don't like to confide my problems to anybody else than my husband, my children, and God,' she told us. This, however, tends to keep her isolated from diverse information that could help her family. When her nine y/o son started to show discipline and academic problems, she faced an unsettled time: 'Looking back, those were hard days. I had no idea what to do, and prayed to God for an answer.' In line with a culture-in-action's description of people's conscious, exploratory behavior during unsettled times, Lucia looked into her cultural toolkit and found a strategy she felt could work: attempting to negotiate information on a one-on-one interaction, in this case, with the teacher. This is a strategy we saw most of our participants leveraging for most of their information-seeking problems, from finding a new apartment, to finding solutions for medical problems."

이 문단을 마침표 기준으로 나누면(따옴표 안의 문장도 각각 센다) 총 8개 문장이 된다. 이 중 전략전환을 알리는 표현이 담긴 문장은 두 개다 — "she faced an **unsettled** time"과 "**looked into her cultural toolkit** and **found a strategy** she felt could work".

```
RI = N_m ÷ N_s = 2 ÷ 8 = 0.25
```

*해석*: 0.25는 이 문단의 4분의 1이 "기존 방식이 통하지 않아 새로운 전략을 찾는" 서술로 채워져 있다는 뜻이다. 특히 이 문단은 Swidler의 "unsettled" 개념을 원문이 그대로 인용한 대목이어서, 이론적 구성개념과 실제 서술이 정확히 겹치는 사례로 해석할 수 있다.

**V5 계산 (기여도 배분)**: Closeness 전략을 다음 세 역량으로 분해했다 — 인내와 용기("courageously, despite the fear of humiliation"), 권위자에 대한 신뢰 추구("secure a connection with a trusting figure of authority"), 협상 능력("negotiating information"). 원문에 세 역량의 상대적 비중은 나와 있지 않다.

```
w_i = 100% ÷ 3 ≈ 33.3%
```

*해석*: 이 33.3%는 "세 역량이 실제로 동등하다"는 근거가 아니라, "원문이 비중을 알려주지 않으므로 균등하게 처리했다"는 방법론적 선언이다. 이후 이 전략을 다른 방식으로 재분석할 근거가 나온다면 이 배분은 수정될 수 있다.

**V6′ 계산 (결측 판별)**: 세 가지 서로 다른 질문에 3단계 규칙을 적용했다.

```
M'("all our participants, at a certain point, had tried to get closer to teachers")
   = 1.0   (명시적 근거 — "all"이라는 전칭 표현이 그대로 쓰임)

M'(개별 참여자의 평균 교사 접촉 횟수)
   = N/A   (결측 — 원문 어디에도 이 수치가 없으므로 추정하지 않음)

M'(Melina가 다른 학습자원을 거부한 대목: "I first have to do what the teacher told me to do")
   = 0.6   (암묵적 근거 — 구체적 발화는 있으나 강도 수식어가 없음)
```

*해석*: 세 번째 판정이 5.3절에서 개정한 3단계 분류가 실제로 작동하는 지점이다. Melina의 발화는 태도가 구체적으로 서술되어 있어 완전한 결측(0)으로 처리하면 정보를 놓치는 것(과소추출)이 되지만, 강도를 나타내는 수식어("항상", "매번" 등)가 없어 완전한 확신(1.0)을 주는 것도 과잉추출의 위험이 있다. 0.6이라는 중간값은 이 두 오류 사이에서 균형을 잡은 것이다.

**V7 계산 (가용률)**: Esther의 발언 "teachers do not have the time to meet with 20 parents wanting to talk to them per day"에서 하루 대기 수요는 N_demand = 20이다. 원문이 실제로 성공 사례로 서술한 인원(개별 성공 사례로 언급된 Lucia, Melina 등)을 최소 1건으로 잡으면 N_avail = 1이다.

```
AR = N_avail ÷ N_demand = 1 ÷ 20 = 0.05 = 5%
```

*해석*: 5%는 "교사와의 친밀성을 통해 정보를 얻으려는 20명의 수요 중 실제로 충족되는 것은 극히 일부"라는 구조적 병목을 드러낸다. 다만 이 "1건"은 원문이 전체 성공 인원 수를 명시하지 않아 잡은 최소 추정치이므로, 실제 가용률은 이보다 높을 수 있다는 점을 함께 밝혀야 한다.

**V8 계산 (양가성)**: "perseverance helped many parents pursue a form of support for children, but it also blinded them from other opportunities"라는 한 문장에서, "helped... pursue a form of support"는 긍정 문맥 1개(N_pos = 1), "blinded them from other opportunities"는 부정 문맥 1개(N_neg = 1)로 센다.

```
AS = (N_pos − N_neg) ÷ (N_pos + N_neg) = (1 − 1) ÷ (1 + 1) = 0
```

*해석*: 0은 이 역량(perseverance, 인내)이 같은 문장 안에서 자산과 제약으로 정확히 팽팽하게 맞서고 있다는 뜻이다. 즉 "인내심은 좋은 것"이라는 단순한 결론을 내리지 않고, 원문이 실제로 서술한 양면성을 그대로 수치에 반영한 것이다.

### 6.3 종합 및 개입 전후 — V9, V10

**V9 계산 (종합 부합도)**: 원문이 직접 제시한 종합 사례를 사용한다 — "parents' capacities to solve the problem of social discomfort are control of their own space, appreciation of superación... and the ability to find online resources... Their limitations... are embarrassment and social fear. Juxtaposing both reveals that their overall goal is safe self-empowerment." 여기서 역량은 3개(자기 공간 통제, superación 추구, 온라인 자원 탐색 능력, C = 3), 제약은 2개(embarrassment, social fear, L = 2)다. 제약이 역량의 절반 정도 무게만 상쇄한다고 가정(w_L = 0.5, 원문에 없는 가정이므로 명시)한다.

```
FS = (C − L×w_L) ÷ (C + L) = (3 − 2×0.5) ÷ 5 = (3 − 1) ÷ 5 = 0.4
```

*해석*: 0.4는 "역량이 제약보다 수적으로 우세하지만(3개 대 2개), 제약이 완전히 무시할 수 없는 무게로 작용해 중간보다 조금 낮은 부합도에 머문다"는 뜻이다. 즉 "safe self-empowerment"라는 목표에 절반 정도 도달한 상태로 해석할 수 있다.

**V10 계산 (개입 전후 변화)**: 같은 산식을 Closeness 전략에 두 번 적용한다.

```
개입 전:  역량 2개(perseverance, trust-seeking), 제약 2개(교사의 시간 부족, 낮은 신뢰 평점)
          FS_before = (2 − 2×0.5) ÷ 4 = 1 ÷ 4 = 0.25

개입 후(원논문이 제안한 "intelligent agents embedded in existing
        parent-teacher communication channels"):
          이 개입이 "교사의 시간 부족" 제약을 상쇄한다고 보면 제약이
          1개(낮은 신뢰 평점)만 남음
          FS_after = (2 − 1×0.5) ÷ 3 = 1.5 ÷ 3 = 0.5

ΔFS = FS_after − FS_before = 0.5 − 0.25 = +0.25
```

*해석*: +0.25는 이 기술적 개입이 부합도를 0.25에서 0.5로, 정확히 두 배로 끌어올린다는 뜻이다. 이는 "교사의 시간 부족"이라는 구조적 제약 하나를 기술로 상쇄하는 것만으로도 부모의 목표 부합도가 유의미하게 개선될 수 있음을 수치로 보여준다.

---

## 7. 논의

6장의 적용 결과, 주변수(V2, V4, V6′, V7, V8) 모두 원문 근거로 역추적 가능한 수치를 산출했다. 특히 앵커 논문이 Swidler의 unsettled 개념을 문자 그대로 차용해 서술했다는 사실(6.2절)은, 이론적 구성개념이 실제 서술 안에 이미 존재함을 보여주는 가장 직접적인 증거이며, 3.1절에서 P10을 교체해 도출한 것과 동일한 방향의 결론이다. 동시에 V5·V9·V10에서 반복된 균등가정 표기는 이 프레임워크의 신뢰도가 결국 V6′의 정직한 결측 처리에 좌우된다는 한계를 보여준다.

## 8. 한계 및 향후 연구

본 연구의 사례 적용은 한 명의 분석자가 수기로 수행한 것이며, 검증 루프가 있는 에이전트와 없는 에이전트를 병렬 가동해 FPR·FNR을 통계적으로 비교하는 실험은 수행되지 않았다. 향후 연구는 이 비교 실험, 평가자 간 신뢰도 측정, 다른 전략 사례로의 일반화를 과제로 삼는다.

## 9. 결론

본 연구는 앵커 논문 논증의 미검증 전제(P10)를 교체하는 정식 절차와, 독립적으로 세운 연구질문(RQ6)이 동일한 지점으로 수렴함을 보였다. 열 개의 조작적 변수(V1~V10, V6′ 포함)를 수식으로 정의하고 실제 사례에 값을 대입해 실행 가능성을 입증했으며, FPR과 FNR을 동시에 낮추는 것이 성공 기준이라는 연구가설(H1)을 제시한다. 이 가설의 완전한 실험적 검증은 향후 과제로 남는다.

## 참고문헌

Bourdieu, P. (1977). *Outline of a Theory of Practice*. Cambridge University Press.

Cho, A., Herrera, R. G., Chaidez, L., & Uriostegui, A. (2019). The "Comadre" Project: An Asset-Based Design Approach to Connecting Low-Income Latinx Families to Out-of-School Learning Opportunities. In *Proceedings of the 2019 CHI Conference on Human Factors in Computing Systems*. ACM.

Ji, Z., Lee, N., Frieske, R., Yu, T., Su, D., Xu, Y., ... & Fung, P. (2023). Survey of Hallucination in Natural Language Generation. *ACM Computing Surveys*, 55(12), Article 248. https://doi.org/10.1145/3571730

Kretzmann, J., & McKnight, J. P. (1996). Assets-based community development. *National Civic Review*, 85(4), 23–29.

Lewis, P., Perez, E., Piktus, A., Petroni, F., Karpukhin, V., Goyal, N., ... & Kiela, D. (2020). Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks. In *Advances in Neural Information Processing Systems 33 (NeurIPS 2020)*. https://arxiv.org/abs/2005.11401

Moll, L. C., Amanti, C., Neff, D., & Gonzalez, N. (1992). Funds of knowledge for teaching: Using a qualitative approach to connect homes and classrooms. *Theory into Practice*, 31(2), 132–141.

Suchman, L. A. (1987). *Plans and Situated Actions: The Problem of Human-Machine Communication*. Cambridge University Press.

Swidler, A. (1986). Culture in action: Symbols and strategies. *American Sociological Review*, 51(2), 273–286. https://doi.org/10.2307/2095521

Wong-Villacres, M., DiSalvo, C., Kumar, N., & DiSalvo, B. (2020). Culture in Action: Unpacking Capacities to Inform Assets-Based Design. In *Proceedings of the 2020 CHI Conference on Human Factors in Computing Systems (CHI '20)*. https://doi.org/10.1145/3313831.3376329

Yao, S., Zhao, J., Yu, D., Du, N., Shafran, I., Narasimhan, K., & Cao, Y. (2023). ReAct: Synergizing Reasoning and Acting in Language Models. In *Proceedings of the 11th International Conference on Learning Representations (ICLR 2023)*. https://arxiv.org/abs/2210.03629
