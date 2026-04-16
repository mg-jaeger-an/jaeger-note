# Good Quality Convo (GQC) — Weekly Summary

**기간:** 2026-04-09 ~ 2026-04-16  
**채널:** #good-quality-convo (`C0ACMMGAM0B`)

---

## 1. Causal Analysis 1차 결과 공유 (Apr 14)

MGAI 팀이 "Plan Meetup on Tinder (PMT)"로 이어지는 Good Quality Convo 시그널에 대한 **1차 causal analysis**를 완료하고 결과를 공유했다.

### 주요 발견

PMT와 **인과 관계(causal relationship)**가 있는 시그널 3가지:

| Signal | 설명 |
|--------|------|
| `mutual_self_disclosure` | 양쪽 모두 자신에 대한 정보를 공유 |
| `niche_common_ground` | 니치한 공통 관심사 발견 |
| `rapport_balanced_questioning` | 균형 잡힌 질문-응답 (한쪽만 질문하지 않음) |

> 리포트: [exp002_plan_meetup_causal_dml.md (GitHub)](https://github.com/matchgroup-ai/good-quality-convo/blob/main/docs/experiment_reports/exp002_plan_meetup_causal_dml.md)

### 다음 단계

- GQC의 역할과 정의 재정립
- 기존 대화/밋업 관련 메트릭과의 관계 평가
- Phase 1의 마일스톤, 스코프, 성공 기준 정의

---

## 2. Signal Candidates 접근법 공유 및 팀 피드백 요청 (Apr 9)

Jaeger가 시그널 후보(Signal Candidates) 정의 방법론을 공유하고 팀에 인풋을 요청했다.

### 접근 방식

- **LLM 기반:** LLM 에이전트를 활용하여 시그널을 탐색하고 루브릭을 정의. 현재 정의를 정제 중.
- **도메인 지식 기반:** PMT 또는 양질의 CE로 이어진 대화를 분석하여 공통 패턴 식별.

### 루브릭의 중요성

- "good rapport"처럼 모호한 정의 지양
- 구체적 기준으로 분해: 예) "답변이 단답형(yes/no)이 아닌가", "한 사람만 계속 질문하지 않는가"

> 참고 문서: [Signals 탭 (Hub Doc)](https://docs.google.com/document/d/1vuiC6vFauKl1HLhFyU9elk8nqvFU2S8IRN4wpckSWgQ/edit?tab=t.k8kzz1ojsufx)

### 팀 피드백 (Ruicong, Steven, Young, Eden)

#### 명칭 관련
- Ruicong: "Constructs" 대신 **"signals"**로 통일하자 → 혼란 방지. 팀 동의.

#### Binary vs. Scalar
- Ruicong: scalar(3단계)보다 **binary** 라벨이 단순하고 효과적.
- Young: binary 선호에 동의. 일부 경계가 애매한 경우에 3단계가 필요할 수 있지만, 먼저 binary로 시작.

#### 전체 접근법에 대한 우려
- **Ruicong:** 시그널 정의에 뛰어들기 전에, 더 많은 사람이 직접 채팅 데이터를 라벨링하며 정성적 이해를 먼저 쌓아야 하지 않나?
- **Ruicong:** 시그널 정의가 부정확하면 하류(GQC 정의)까지 오차가 누적될 우려. 업스트림의 rigour가 아직 부족.
- **Steven:** 궁극적으로 어떤 모델을 만들 것인가? `P(good chat signals | earlier signals)` vs. `P(meetup | good chat signals)` — 큰 그림이 필요.

#### Eden의 전체 프레임워크 설명
```
Signal 탐색/정의 → Causal Analysis → GQC 정의 → GQC 검증(Retention, CE, PMT)
```
- 개별 시그널의 ATE를 측정하고, 유의미한 시그널들을 조합하여 GQC를 정의.
- 최종 목표: `P(GQC | swiper, swipee)` 모델을 만들어 4-way convo 대신 GQC 기반 추천.
- 1회 full iteration을 빠르게 돌려 전체 프로세스를 검증한 후, 시그널 정의를 정제하는 전략.

#### 합의 필요 사항
- CE를 primary experiment metric으로 사용할 것인지 alignment 필요.
- Good churn(좋은 이탈) 으로 인한 단기 retention 감소를 수용할 것인지 사전 합의 필요.

---

## 3. Meetup Metrics 워크스트림과의 연결 (Apr 14)

Shurain이 별도로 진행 중인 **Meetup metrics 미팅** 내용을 공유하며, GQC 프로젝트와의 연관성을 강조.

### 핵심 내용
- Meetup metrics 워크스트림이 GQC의 "Plan Meetup" 예측과 **직접적으로 관련됨**
- Ben의 제안: 데이터 리소스를 연결하여 분석 목적으로도 활용할 수 있도록 조기 alignment 필요
- 현재 DS 담당자가 아직 미배정 → Jayant에게 적절한 담당자 배정을 요청하기로 함

> 참고: [Meetup metrics 미팅 노트](https://docs.google.com/document/d/1asGhJgkQAzODl3dfLMllqvhxj6_CAo-YZBKFYAkn9aA/edit?tab=t.0#heading=h.exmlq37e10k)

---

## 4. 기타

| 날짜 | 내용 |
|------|------|
| Apr 9 | Melodie He의 **Respectfulness of Convos** 정의/측정 문서가 공유됨 ([link](https://docs.google.com/document/d/1vi6EwwyhoKh1CmjSZuIKYiIEhlnksGnz6FQKDpi9bXE/edit)) |
| Apr 9 | Steven Brotz가 ML 쪽 회의에 optional로 참여 요청 → 추가됨 |
| Apr 9 | 4/9 weekly sync 취소 (시그널 논의가 async로 처리 가능) |

---

## Action Items

| 담당 | 항목 | 상태 |
|------|------|------|
| Jaeger | GQC 스코프, 마일스톤, 타임라인 내부 논의 후 공유 | 진행 중 |
| Jaeger | Jayant에게 DS 담당자 배정 요청 | To Do |
| Young/Eden | Causal analysis 2차 iteration 준비 | 진행 중 |
| 팀 전체 | Signal 후보에 대한 아이디어/피드백 제공 | 지속 |
| 팀 전체 | CE를 primary metric으로 사용 + good churn 수용 여부 alignment | To Do |

---

## Notion MG AI Meeting Notes — GQC 관련 내용 (Apr 10–16)

**출처:** Notion > MG AI & AI Lab > MG AI meeting notes 데이터베이스

---

### 5-1. MG AI PM Weekly (Apr 14)

[Notion 링크](https://www.notion.so/341ce00cd35480649c42fcfad5d8cf2f)

PM Weekly에서 논의된 GQC 관련 사항:

- 인과분석에서 유의미한 signal을 찾았으나, **대화 길이가 늘어나서 PMT가 성사된 것인지, 단순히 대화가 길었기 때문에 PMT를 한 것인지** 구분이 안 됨.
- 현재 message index 기반 treatment window를 **time 기반으로 재정의**하여 재시도 예정.
- RBR(Risk-Based Retrieval) 실험에서 발견된 부작용(L7 match coverage -0.2%, resub cash -1.3%)과 sprinkle queue를 통한 SAA 노출 문제도 함께 언급됨.

> 팀 내부 피드백: "인과분석에 대한 테크니컬한 논의를 채널로 전파하는 과정에서 소화불량이 있었다"는 자성도 있었음.

---

### 5-2. Good Quality Convo Weekly Prep (Apr 14)

[Notion 링크](https://www.notion.so/342ce00cd354809d8e3dcd7f5ee1c55b)

GQC Weekly 미팅 준비 자료. **GQC가 기존 지표(n-way convo, CE, PMT) 대비 어떤 장점이 있는지** 평가하기 위한 분석 프레임을 정리.

#### 핵심 질문 3가지

| 질문 | 검증 방법 |
|------|-----------|
| GQC가 n-way convo와 구별되는 개념인가? | 같은 n-way strata 내 GQC high vs low의 PMT/Good CE 비율 비교 |
| GQC가 CE의 noise를 줄여주는가? | CE 내에서 GQC high vs low의 PMT/Good CE/ban contamination 비율 |
| GQC가 sparse PMT와 noisy CE 사이의 유용한 surrogate인가? | Coverage, PMT enrichment, ban contamination, precision-coverage tradeoff |

#### A/B 테스트 구상

- 실험 구조: `Control` vs `P(CE or PMT w/ non-banned)` vs `P(GQC)`
- 메트릭 고민: Retention은 Good churn과 상충 → PMT/CE 상승 + CE w/ banned 감소 조합으로 평가 가능하나, `P(CE or PMT w/ non-banned)`보다 GQC가 우월함을 보이기는 어려울 수 있음.

#### 분석 우선순위

1. GQC vs N-way → PMT, CE 인과분석
2. Good CE를 분리하여 추가 분석
3. GQC vs N-way vs CE → Retention 인과분석

---

### 5-3. GQC Scope/Milestone/Timeline (Apr 15)

[Notion 링크](https://www.notion.so/342ce00cd354800380d6c8bd31b3c72d)

GQC 프로젝트의 **스코프, 마일스톤, 타임라인**을 정의하기 위한 핵심 미팅. Jaeger, Juan, Harriet, Eden, Young 참여.

#### Phase 1 Goal 정의

> **GQC의 목표:** Meetup north star를 잘 serve하는, 추천에 쓸 수 있는, 대화 품질을 반영한 surrogate(직접적 이벤트가 아닌 대체 시그널)를 정의하는 것.

구체적으로 GQC가 만족해야 할 조건:
- `n-way convo`보다 outcome(PMT, Good CE)-aligned
- `PMT`보다 덜 sparse
- `CE`보다 덜 noisy
- 추천/랭킹에 넣었을 때 더 건강한 downstream outcome으로 이어질 가능성

#### Kill 조건

- Signal 정의를 정제해도 agreement/consistency가 낮아 GQC 정의 자체가 불안정
- Surrogate validity fail (같은 n-way 내 GQC high vs low 차이 미미, CE 내에서 GQC가 quality를 못 가름)
- `P(CE or PMT with non-banned)`가 더 단순하고 잘 작동하는데 GQC가 추가 장점을 못 보여줌

#### Phase 1 OKR (합의된 방향)

**Objective 1:** Meetup을 proxy하는 측정 가능한 추천 품질 metric 정의
- KR1: 추천 품질 metric (PMT + Good CE) 운영 정의 확정
- KR2: metric이 "meetup proxy로서 적합한가" 평가 방법 정의
- KR3: metric의 적합성 확인
- KR4: 라벨링 파이프라인 구축

**Objective 2:** N-way convo 대비 정의된 meetup metric을 더 잘 올릴 수 있는 chat 내 event 발견 및 검증
- KR1: Chat 내 event candidate set 확정
- KR2: Benchmark 정의 및 n-way 대비 uplift 확인
- KR3: Online recommendation 후보 1개 이상 선정 (또는 n-way 충분 근거 제시)

#### Background 논의 요약

- **문제 정의:** n-way convo에만 집중하면 추천하지 않아야 할 것이 추천되거나, 추천되어야 할 것이 누락될 수 있다는 의심.
- **Harriet:** 퀄리티를 왜 정의해야 하는지에 대한 배경 설명에 논리적 점프가 있음 (GenZ 여성 이탈 등의 구체적 배경 필요).
- **Juan:** Business impact를 봐야 하는데, 어떤 business impact를 볼지 정의되지 않으면 retention 논의와 순환 논리에 빠짐.
- **Eden:** Shuaiji의 원래 동기는 "기존 metric이 유저가 바라는 좋은 경험을 반영하지 못한다"는 것이었으나, 구체적 근거는 약했음.

#### Good CE Bucket 분류 (meetup proxy metric 정의용)

| Bucket | 정의 | Meetup 가능성 |
|--------|------|---------------|
| A. PMT | 앱 내 구체적 시간+장소 확정 | 거의 확실 |
| B. Good CE | CE + 대화 내 meetup artifact (시간/장소/intent) | 높음 |
| C. Neutral CE | CE + artifact 없음 + non-banned | **불확실 (핵심 문제)** |
| D. Abuser CE | CE + 한쪽 banned | 낮음 (scam/spam) |

---

### 5-4. Tinder GQC 인과분석 피드백 (Apr 14)

[Notion 링크](https://www.notion.so/342ce00cd35480449af7dbaea31636f2)

Favian(외부 causal inference 전문가)으로부터 받은 **인과분석 방법론 피드백** 미팅. Jaeger, Young, Eden, Favian 참여.

#### exp002/003 평가

- **exp002 (causal DML):** 큰 오류 없음. Weight 적용한 분석이 올바른 접근.
- **exp003 (mediator 분석):** **deprecated 결정.** `num_msgs`를 mediator로 보는 것이 부적절 — confounder에 결과 정보가 섞이는 문제.
- Message-based window는 당장 큰 문제 아니지만, time-based로 더블체크 권장.

#### Window Design 가이드라인

| 항목 | 결정 |
|------|------|
| Treatment window anchor | **Match 시점** (첫 메시지 시점은 bias 유발) |
| Buffer | 너무 작으면 coverage는 좋지만 논리적 근거로 설정해야 함 |
| Outcome window | Coverage 확보하되 너무 넓히지 말 것 |
| Effect maximize 기준 선정 | **금지.** Robustness check용으로 parameter를 움직여야 함 |
| PMT 라벨 기준 | Outcome window 내 **제안+수락 모두 존재**하는 경우. 최종수락이 이상적이나 coverage 낮으면 최초수락 가능 |
| Treatment/buffer 내 outcome 발생 시 | **Y=0 처리** (exclude하면 bias 발생) |
| `num_message`를 confounder로 | **불가.** 결과 정보 포함됨 |

#### 추후 분석 순서 합의

1. **비율 분석 (Surrogate Validity):** 같은 n-way 내에서 GQC high vs low의 PMT/Good CE 차이, CE 내 noise 감소, ban contamination 비교
2. **인과분석 #1:** (n-way vs GQC) → PMT or CE (time-based window)
3. **인과분석 #2 (sanity check):** (n-way vs GQC vs CE) → Retention
4. **미해결:** `P(CE or PMT w/ non-banned)` 대비 GQC의 business metric 우위 증거

#### Bias 관련 핵심 인사이트 (Eden)

> Time window를 첫 메시지 기준으로 잡으면 bias 발생: 매치 직후 바로 메시지를 보내는 행동 자체가 treatment와 outcome 모두에 영향을 주는 confounder임. 매치 이후 시간이 지날수록 4-way convo 비율이 줄어드는 survival rate 패턴이 이를 뒷받침.

---

## 관련 리소스

| 리소스 | 링크 |
|--------|------|
| Hub Doc | [Google Docs](https://docs.google.com/document/d/1vuiC6vFauKl1HLhFyU9elk8nqvFU2S8IRN4wpckSWgQ/) |
| Causal Analysis Report | [GitHub](https://github.com/matchgroup-ai/good-quality-convo/blob/main/docs/experiment_reports/exp002_plan_meetup_causal_dml.md) |
| Meetup Metrics 노트 | [Google Docs](https://docs.google.com/document/d/1asGhJgkQAzODl3dfLMllqvhxj6_CAo-YZBKFYAkn9aA/) |
| Respectfulness 문서 (Melodie) | [Google Docs](https://docs.google.com/document/d/1vi6EwwyhoKh1CmjSZuIKYiIEhlnksGnz6FQKDpi9bXE/) |
| Jira (GQC) | [RECSD-215](https://gotinder.atlassian.net/browse/RECSD-215) |
| WBS | [Google Sheets](https://docs.google.com/spreadsheets/d/1uqveVqY_36UYzKy8TJIfspkpVcxUcr4idqCsGnh3vW0/) |
| Notion: MG AI PM Weekly (Apr 14) | [Notion](https://www.notion.so/341ce00cd35480649c42fcfad5d8cf2f) |
| Notion: GQC Weekly Prep (Apr 14) | [Notion](https://www.notion.so/342ce00cd354809d8e3dcd7f5ee1c55b) |
| Notion: GQC Scope/Milestone/Timeline (Apr 15) | [Notion](https://www.notion.so/342ce00cd354800380d6c8bd31b3c72d) |
| Notion: GQC 인과분석 피드백 (Apr 14) | [Notion](https://www.notion.so/342ce00cd35480449af7dbaea31636f2) |
