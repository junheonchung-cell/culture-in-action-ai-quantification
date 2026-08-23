# 검증 가능한 AI 연구 에이전트를 통한 문화적 역량(Culture-in-Action)의 수치화

경제학과 25학번 정호영 — AX 코딩캠프(2026학년도 여름계절) 연구 프로젝트

## 개요

Ann Swidler(1986)의 culture-in-action 이론과, 이를 HCI에 적용한 Wong-Villacres et al.(2020)의 앵커 논문을 기반으로, 검색·근거추출·검증(S·G·V) 절차를 갖춘 AI 연구 에이전트가 도구함·역량·전략적 행위라는 질적 구성을 원문 근거에 기반해 검증 가능한 수치로 변환할 수 있는지를 다룬 연구입니다.

핵심 기여:
1. 앵커 논문 자신의 논증에서 가장 취약한 전제(P10)를 식별하고 대체하는 절차로 연구 문제를 도출
2. Culture-in-Action 개념을 10개의 조작적 변수(V1~V10)로 분해하고 산식으로 정의
3. 가장 취약한 변수(결측 판별, V6)를 3단계 신뢰도 함수(V6′)로 개정
4. 개정된 프레임워크를 앵커 논문의 실제 사례(Consejos, Closeness with teachers)에 적용해 실행 가능성을 검증

## 폴더 구조

```
.
├── paper/        연구 산출물 (1차~3차 산출물, 최종본)
├── figures/      핵심 다이어그램 (연구 계보도, 변수-수식 모델링, 에이전트 설계도)
└── coursework/   AX 코딩캠프 제출 과제 (본인 작성분)
```

## paper/ 버전 안내

| 파일 | 설명 |
|---|---|
| `검증 가능한 AI 연구 에이전트를 통한 문화적 역량의 수치화_1차 산출물_정호영.pdf` | 최초 버전 — 도메인 일반적 FOL 가설로 시작 |
| `..._2차 산출물_정호영.pdf` | 앵커 논문(Wong-Villacres et al., 2020) 원문 확보 후 재정식화, 참여자 가명 오류 수정, 참고문헌 하이퍼링크 검증 |
| `..._3차 산출물_정호영.md` | FOL 표기를 연구질문(RQ)·가설(H)·조작적 변수(V) 체계로 전환, 모든 수식을 plain-text 안전 표기로 재작성 |
| `AI 연구 에이전트를 통한 문화적 역량의 수치화_정호영.pdf` / `.docx` | 최종본 |

## figures/ 다이어그램 안내

- **연구 계보도**: Swidler(1986) 이론 → 앵커 논문 → 연구 공백 → 본 연구로 이어지는 흐름
- **변수-수식 모델링**: 중심 연구질문(RQ) → 조작적 변수(V1~V10) → 연구가설(H1)로 수렴하는 구조
- **에이전트 설계도**: 검색(Search)→근거추출(Grounding)→검증(Verification) 파이프라인과 FPR·FNR 피드백 루프
- **AI 적용 연구 프로세스**: 이 연구를 작성하는 과정 자체에서 AI가 수행한 6단계 역할

## 참고문헌 (앵커 논문 및 핵심 인용)

- Swidler, A. (1986). Culture in action: Symbols and strategies. *American Sociological Review*, 51(2), 273–286. https://doi.org/10.2307/2095521
- Wong-Villacres, M., DiSalvo, C., Kumar, N., & DiSalvo, B. (2020). Culture in Action: Unpacking Capacities to Inform Assets-Based Design. *CHI '20*. https://doi.org/10.1145/3313831.3376329
- Ji, Z. et al. (2023). Survey of Hallucination in Natural Language Generation. *ACM Computing Surveys*, 55(12). https://doi.org/10.1145/3571730
- Lewis, P. et al. (2020). Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks. *NeurIPS 2020*. https://arxiv.org/abs/2005.11401
- Yao, S. et al. (2023). ReAct: Synergizing Reasoning and Acting in Language Models. *ICLR 2023*. https://arxiv.org/abs/2210.03629

## 참고

이 저장소는 개인 연구 초안을 정리한 것으로, 강의 멘토가 제작한 강의자료 원문은 저작권 존중을 위해 포함하지 않았습니다.
