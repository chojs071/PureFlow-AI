# PureFlow AI — 디자인

## 1. 디자인 방향
**반도체 제조 시스템 + AI 분석 플랫폼 + ESG 대시보드**

목표:
> 미래형 반도체 제조 최적화 시스템을 실제로 조작하는 느낌.

화려한 게임 UI보다 전문적인 산업용 모니터링 시스템을 우선한다.

## 2. 스타일 키워드
- Semiconductor
- Clean
- AI
- Precision
- Data
- ESG
- Industrial
- Futuristic

## 3. 컬러
```text
Primary Navy #071A2E
AI Blue #00C2FF
ESG Green #22C55E
Background #F8FAFC
White #FFFFFF
Text Dark #0F172A
Text Muted #64748B
Border #E2E8F0
Pending Gray #94A3B8
```

## 4. 폰트
한국어: **Pretendard**
대체: **Noto Sans KR**

## 5. 버튼
### Primary
`AI 최적화 시작`
- Electric Blue
- 흰색 텍스트
- 12~16px padding
- 12px radius

### Secondary
`다음 공정`
- Border 기반
- 활성: Electric Blue
- 비활성: Gray

## 6. 시작 화면
```text
┌──────────────────────────────────────┐
│                                      │
│             PureFlow AI              │
│                                      │
│       AI 기반 초순수 최적화 시스템       │
│                                      │
│     품질은 유지하고                    │
│     불필요한 UPW 사용은 줄입니다.       │
│                                      │
│       웨이퍼 직경                     │
│       [ 200mm ] [ 300mm ]             │
│                                      │
│        [ AI 최적화 시작 ]             │
└──────────────────────────────────────┘
```

## 7. 핵심 UX 원칙
PureFlow AI는 **물을 많이 줄이는 시스템**이 아니라 **품질을 유지하면서 줄일 수 있는 물을 찾는 시스템**으로 보여야 한다.

항상 아래 흐름이 시각적으로 드러나야 한다.

```text
기존 조건
↓
오염도 분석
↓
후보 조건 생성
↓
예상 잔류 오염
↓
허용 기준 확인
↓
품질 기준 충족 후보만 유지
↓
최소 UPW 추천
```

## 8. 공정 진행 화면
상단:
`PureFlow AI  /  300mm`

진행 바:
`① ━━━ ② ━━━ ③ ━━━ [④] ━━━ ⑤ ━━━ ⑥`

상태:
- 완료 = Navy
- 현재 = Electric Blue
- 대기 = Gray

## 9. 현재 공정 카드
```text
┌────────────────────────────────────────────┐
│ 현재 공정                                   │
│ 식각 후 세정                                │
│ Post-Etch Clean + UPW Rinse                │
│                                            │
│ 오염도  ███████████████░░ 85/100          │
│                                            │
│ 기존 UPW              AI 추천 UPW          │
│ 120 L                 100 L                │
│                                            │
│ 절감량                절감률                │
│ 20 L                  16.7%                │
│                                            │
│ 예상 잔류 오염                              │
│ 8.4 × 10⁹ atoms/cm²                       │
│                                            │
│ 허용 기준                                  │
│ ≤ 1.0 × 10¹⁰ atoms/cm²                   │
│                                            │
│ ✓ 품질 기준 충족                           │
└────────────────────────────────────────────┘
```

## 10. 품질 표시 원칙
기존의 `품질 점수 97 / 100` 표현은 사용하지 않는다.

대신:
- 예상 잔류 오염
- 허용 잔류 오염 기준
- 품질 기준 충족 여부

를 표시한다.

### 상태 표현
```text
✓ 품질 기준 충족
```

```text
✕ 허용 기준 초과
```

후자는 최종 추천 조건이 될 수 없으며, 후보 탈락 상태임을 명확히 표시한다.

## 11. 잔류 오염 기준 카드
```text
┌───────────────────────────────┐
│ 세정 후 품질 검증              │
│                               │
│ 예상 잔류 오염                │
│ 8.4 × 10⁹ atoms/cm²          │
│                               │
│ 허용 기준                     │
│ ≤ 1.0 × 10¹⁰ atoms/cm²       │
│                               │
│ ✓ 기준 충족                   │
└───────────────────────────────┘
```

### 주의 문구
> ※ 허용 기준은 공정 및 오염물 종류에 따라 달라질 수 있으며, PureFlow AI에서는 문헌 기반 시뮬레이션 기준을 사용합니다.

`10¹⁰~10¹¹ atoms/cm²` 범위를 모든 공정에 공통 적용하는 것처럼 표현하지 않는다.

## 12. 후보 조건 비교
사용자가 AI가 왜 해당 UPW를 선택했는지 이해할 수 있도록 후보를 단계적으로 보여줄 수 있다.

```text
UPW     예상 잔류 오염       판정
120 L   6.2 × 10⁹            ✓
110 L   7.0 × 10⁹            ✓
100 L   8.4 × 10⁹            ✓
 90 L   1.3 × 10¹⁰           ✕
```

가장 낮은 UPW이면서 기준을 충족하는 후보를 AI 추천으로 강조한다.

## 13. 숫자 강조
AI 추천 UPW를 가장 강조한다.

절감량과 절감률은 Green으로 강조한다.

단, **절감량보다 품질 기준 충족 여부를 먼저 인지할 수 있도록** 품질 상태를 카드 상단 또는 핵심 영역에 배치한다.

## 14. 오염도 게이지
- 0~30 낮음
- 31~60 보통
- 61~89 높음
- 90~100 매우 높음

90 이상에서는:
`최소 세정시간 유지`

문구를 함께 표시한다.

## 15. AI 분석 애니메이션
```text
AI ANALYSIS

✓ 웨이퍼 상태 분석
✓ 오염도 분석
✓ 세정 조건 분석
→ 후보 조건 검증
○ 잔류 오염 계산
○ 최적 조건 선택
```

진행 단계에 pulse animation을 사용한다. 전체 2~4초 이내.

## 16. 공정별 비교 그래프
현재까지 완료된 공정만 표시한다.

표시 항목:
- 기존 UPW
- AI 추천 UPW
- 절감량

가능한 경우 품질 검증 상태도 함께 표시한다.

공정 완료 시 그래프가 하나씩 추가된다.

## 17. 최종 결과
핵심 숫자:
```text
기존 UPW
XXXX L

AI 최적화
XXXX L

총 절감
XXXX L

절감률
XX.X%

품질 기준 충족
XX / XX 공정
```

### 품질 검증 요약
```text
모든 추천 조건
✓ 허용 잔류 오염 기준 충족
✓ 품질 기준 미충족 조건 자동 제외
```

## 18. ESG 카드
```text
UPW 절감
XXXX L

전력 절감
XX kWh

탄소 절감
XX kgCO₂e
```

실제 계산되지 않은 값은 사실처럼 표현하지 않고 시뮬레이션 값임을 표시한다.

## 19. 공정별 결과 테이블
| 공정 | 기존 UPW | AI UPW | 예상 잔류 오염 | 허용 기준 | 품질 판정 | 절감량 | 절감률 |
|---|---:|---:|---:|---:|---|---:|---:|
| 공정 A | 120L | 100L | 8.4×10⁹ | ≤1.0×10¹⁰ | 충족 | 20L | 16.7% |
| 공정 B | 80L | 72L | 문헌 기반 값 | 문헌 기반 값 | 충족 | 8L | 10% |

모든 값은 계산 결과를 사용한다.

## 20. 아이콘
Lucide React:
- Droplets
- BrainCircuit
- Activity
- Gauge
- Cpu
- Database
- CheckCircle
- ArrowRight
- Factory
- Leaf
- Zap
- ShieldCheck

## 21. 반응형
Desktop 우선:
- 1440px
- 1280px
- 1024px
- 768px

Desktop에서는:
```text
좌측: 공정 진행
중앙: 현재 공정
우측: AI 분석 결과
```

## 22. 접근성
- 충분한 텍스트 대비
- 충분한 클릭 영역
- 색상만으로 상태를 구분하지 않음
- 아이콘/텍스트 병행
- 그래프 숫자 표시
- 키보드 접근 가능

## 23. 핵심 카피
### 시작
> 품질은 유지하고, 불필요한 UPW 사용은 줄입니다.

### AI 분석
> 현재 공정의 오염도와 세정 조건을 분석하고, 품질 기준을 유지할 수 있는 절감 조건을 탐색합니다.

### 검증
> 세정 후 예상 잔류 오염이 허용 기준을 충족하는지 검증합니다.

### 추천
> 품질 기준을 만족하는 후보 중 가장 적은 UPW 조건을 추천합니다.

### 결과
> 품질을 희생하지 않고, 줄일 수 있는 UPW를 찾아냈습니다.

### 프로젝트 설명
> 세정 후 허용 잔류 오염 기준을 유지하면서 기존 초순수 사용량을 어디까지 줄일 수 있는지 판단합니다.

## 24. 최종 디자인 원칙
PureFlow AI는 **물을 무조건 줄이는 시스템**처럼 보이면 안 된다.

반드시:
```text
기존 조건
↓
오염도 분석
↓
후보 조건 생성
↓
잔류 오염 검증
↓
품질 기준
↓
절감 가능량 판단
↓
AI 추천
```

의 흐름이 시각적으로 드러나야 한다.

**절감량보다 품질 유지가 먼저**라는 메시지를 전달한다.


# Appendix — 문헌 기반 세정 성능 모델

## 1. 모델의 역할
PureFlow AI는 실제 세정 성능을 측정하는 시스템이 아니다. 문헌에서 확인된 세정·린스 변수와 표면 오염 측정 방법을 근거로 **MVP용 surrogate model**을 구성하고, 품질 기준을 먼저 통과시킨 후보 중 최소 UPW 조건을 탐색한다.

## 2. 대표 공정
**BEOL Cu/Low-k Post-Etch Clean + UPW Rinse**

Post-etch wet clean은 Cu/low-k interconnection에서 etch residue와 Cu 관련 contamination을 제거하는 중요한 공정이다.

## 3. 품질 지표
**Cu surface contamination [atoms/cm²]**

MVP 1차 Gate:

```text
Cu ≤ 1.0 × 10¹⁰ atoms/cm²
```

이 값은 MVP용 보수적 Gate이며 모든 반도체 공정에 대한 보편적 공식 규격으로 표현하지 않는다.

## 4. 세정 성능 판단
세정 성능을 0~100 점수로 만들지 않는다.

```text
예상 잔류 Cu ≤ 허용 기준
→ 품질 기준 충족

예상 잔류 Cu > 허용 기준
→ 후보 탈락
```

## 5. MVP surrogate model
```text
R_pred =
R_floor
+
(R_initial - R_floor)
× exp(
    -K
    × t
    × (Q / Q_ref)^α
    × N^β
)
```

- `R_pred`: 예상 잔류 Cu [atoms/cm²]
- `R_initial`: 초기 Cu 오염
- `R_floor`: 모델상의 최소 잔류값
- `K`: 제거 속도 보정계수
- `t`: 유효 세정/린스 시간
- `Q`: UPW 유량
- `Q_ref`: 기준 유량
- `N`: cycle 수
- `α`: 유량 민감도
- `β`: cycle 효과

**K, α, β 및 공정별 초기값은 문헌의 직접 측정 계수가 아니라 MVP 시뮬레이션용 calibration parameter다.**

## 6. 문헌에서 모델 변수 선정의 근거
2025년 연구에서는 단일 웨이퍼 DIW rinse에서 금속의 wafer-surface adsorption을 조사했고, Cu의 adsorption ratio가 2.6~3.3%였으며 Cu adsorption이 공급 유량에 따라 달라지는 경향을 보고했다. 또한 금속 농도, rinse time, supply flow rate를 실험 변수로 다뤘다.

별도의 single-wafer rinse 모델 연구에서는 flow rate, wafer size, rotation speed 등의 영향을 공정 모델로 분석했으며, 물 사용량 최소화를 위한 rinse recipe 최적화 가능성을 제시했다.

Post-etch Cu/low-k 연구에서는 wet clean이 etch residue, Cu-related contamination, 그리고 전기적/신뢰성 특성에 영향을 줄 수 있음을 보여준다.

따라서 PureFlow AI의 모델 입력은 `세정/린스 시간`, `UPW 유량`, `cycle`, `wafer size`, `초기 오염 수준`으로 제한한다.

## 7. 추천 로직
```text
후보 조건 생성
↓
후보별 예상 잔류 Cu 계산
↓
허용 Cu 기준 초과 후보 제거
↓
남은 후보의 UPW 계산
↓
가장 낮은 UPW 선택
```

즉:

> **품질 검증이 UPW 최적화보다 먼저다.**

## 8. 모델 한계
이 모델은 실제 수율 예측, 실제 Fab recipe 추천, 실제 장비 제어에 사용하지 않는다. 실제 적용을 위해서는 공정별 실험 데이터로 `K, α, β` 등을 보정하고 별도 검증이 필요하다.

## 9. 참고 문헌
- Tsutano K. et al., ECS Journal of Solid State Science and Technology (2025), DOI 10.1149/2162-8777/add809.
- Tsang C.F. et al., Microelectronics Reliability 45 (2005), 517–525, DOI 10.1016/j.microrel.2004.07.007.
- Surface cleaning of small structures during spin rinsing of patterned substrates, Microelectronic Engineering 108 (2013), 57–65, DOI 10.1016/j.mee.2013.02.092.
- Experimental and Modelling Investigation of Re-Adhesion Mechanism of Detached Nanoparticles to Wafer Surface in Spin Rinse Process, ECS JSST (2020), DOI 10.1149/2162-8777/ab9fe9.
- Rinsing of high-aspect-ratio features on patterned wafers, IEEE TSM 30 (2017), DOI 10.1109/TSM.2016.2615857.

# 25. 개발용 기능 프롬프트

아래 프롬프트는 PureFlow AI의 실제 MVP 구현을 위해 Cursor, Claude Code, Gemini, ChatGPT 등의 코딩 AI에 전달할 수 있다.

## 25.1 전체 구현 프롬프트

```text
PureFlow AI라는 반도체 공정 초순수(UPW) 사용량 최적화 시뮬레이션 웹앱을 구현한다.

핵심 원칙:
1. 품질을 희생해서 UPW를 줄이지 않는다.
2. 공정별 허용 잔류 오염 기준을 먼저 확인한다.
3. 허용 기준을 초과하는 후보는 절대 추천하지 않는다.
4. 품질 기준을 충족하는 후보 중 UPW 사용량이 가장 적은 조건을 추천한다.
5. 실제 Fab 장비나 생산라인에 연결하지 않는다.
6. 모든 데이터는 문헌 기반 시뮬레이션 데이터라고 표시한다.
7. 실제 생산 수율이나 실제 장비 recipe를 예측한다고 표현하지 않는다.

대표 MVP 공정:
BEOL Cu/Low-k Post-Etch Clean + UPW Rinse

대표 품질 지표:
Cu surface contamination [atoms/cm²]

MVP 1차 품질 Gate:
Cu <= 1.0 × 10¹⁰ atoms/cm²

세정 성능 판정:
predictedResidualCu <= allowableCu

추천 로직:
후보 생성 -> 잔류 Cu 계산 -> 품질 기준 통과 후보만 유지 -> UPW 계산 -> 최소 UPW 후보 선택

화면은 전문적인 반도체 제조 시스템 + AI 분석 플랫폼 + ESG 대시보드 스타일로 구현한다.
```

## 25.2 시작 화면 구현 프롬프트

```text
PureFlow AI 시작 화면을 구현한다.

필수 요소:
- PureFlow AI 로고/타이틀
- "AI 기반 초순수 최적화 시스템"
- 핵심 문구: "품질은 유지하고, 불필요한 UPW 사용은 줄입니다."
- 웨이퍼 직경 선택: 200mm / 300mm
- "AI 최적화 시작" 버튼

상호작용:
- 200mm 또는 300mm 중 하나를 선택할 수 있다.
- 웨이퍼를 선택하지 않으면 최적화 시작 버튼을 비활성화한다.
- 시작 버튼을 누르면 AI 분석 화면으로 전환한다.

상태:
- 선택된 wafer는 Electric Blue 강조
- 선택되지 않은 wafer는 Border 스타일
- 버튼 클릭 시 분석 상태로 진입
```

## 25.3 AI 분석 애니메이션 구현 프롬프트

```text
AI 분석 진행 화면을 구현한다.

순서:
1. 웨이퍼 상태 분석
2. 오염도 분석
3. 세정 조건 분석
4. 후보 조건 생성
5. 잔류 오염 계산
6. 품질 기준 검증
7. 최적 조건 선택

각 단계는:
- pending
- active
- complete
상태를 가진다.

active 단계는 pulse animation을 사용한다.
complete 단계는 CheckCircle 아이콘을 사용한다.
전체 애니메이션은 2~4초 이내로 완료한다.

사용자에게 실제 AI 서버가 추론 중이라고 오해시키지 않는다.
"Simulation Analysis" 성격의 분석임을 유지한다.
```

## 25.4 공정 데이터 로딩 프롬프트

```text
공정 데이터를 simulation dataset에서 읽어오도록 구현한다.

각 process object는 최소한 다음 필드를 가진다.

{
  id,
  name,
  description,
  waferDiameter,
  contaminationScore,
  contaminationBand,
  baselineRecipe: {
    cleaningTime,
    rinseTime,
    flowRate,
    cycles
  },
  allowableOptimizationRange,
  initialCuAtomsCm2,
  allowableCuAtomsCm2,
  modelParameters: {
    R_floor,
    K,
    alpha,
    beta,
    Q_ref
  },
  reference
}

실제 생산라인 데이터처럼 표현하지 않는다.
데이터 출처 상태는 "Literature-based simulation data"로 표시할 수 있다.
```

## 25.5 세정 성능 계산 프롬프트

```text
후보 세정 조건의 예상 잔류 Cu를 계산하는 함수를 구현한다.

surrogate model:

R_pred =
R_floor +
(R_initial - R_floor) *
exp(
  -K *
  t *
  (Q / Q_ref)^alpha *
  N^beta
)

입력:
- R_initial
- R_floor
- K
- alpha
- beta
- t
- Q
- Q_ref
- N

출력:
- predictedResidualCu

단위:
atoms/cm²

주의:
이 모델은 MVP용 문헌 기반 surrogate simulation model이다.
실제 Fab의 검증된 물리식으로 표현하지 않는다.
```

## 25.6 후보 조건 생성 프롬프트

```text
기준 세정 조건과 공정별 허용 범위를 이용해 후보 조건을 생성한다.

최적화 변수:
- cleaningTime
- rinseTime
- flowRate
- cycles

규칙:
1. 기준 조건에서 허용된 범위 밖으로 벗어나지 않는다.
2. 한 번에 너무 큰 변화가 발생하지 않도록 단계적으로 감소시킨다.
3. 각 후보의 UPW 사용량을 계산한다.
4. 중복 후보는 제거한다.

예:
10분 / 8분 / 10L/min / 2회
9분 / 8분 / 10L/min / 2회
9분 / 7분 / 10L/min / 2회
8분 / 7분 / 9L/min / 2회
```

## 25.7 품질 Gate 프롬프트

```text
모든 후보를 UPW 절감량으로 비교하기 전에 품질 기준을 먼저 판정한다.

판정:
predictedResidualCu <= allowableCu

true:
- qualityPass = true
- 후보 유지

false:
- qualityPass = false
- 후보 탈락

절대로 qualityPass=false인 후보를 AI 추천 후보로 남기지 않는다.

UI에는:
- "✓ 품질 기준 충족"
- "✕ 허용 기준 초과"
를 표시한다.
```

## 25.8 AI 추천 프롬프트

```text
AI recommendation algorithm:

1. 후보 조건 생성
2. 각 후보의 predictedResidualCu 계산
3. allowableCu와 비교
4. qualityPass=true인 후보만 필터링
5. 각 후보의 UPW 계산
6. UPW 오름차순 정렬
7. 가장 작은 UPW 후보 선택

의사코드:

validCandidates = candidates
  .filter(c => c.predictedResidualCu <= c.allowableCu)
  .sort((a, b) => a.upw - b.upw)

recommendation = validCandidates[0]

validCandidates가 비어 있다면:
- 기존 기준 조건을 유지
- "절감 가능한 조건을 찾지 못했습니다." 표시
- 품질을 희생하는 추천은 하지 않는다.
```

## 25.9 UPW 계산 프롬프트

```text
UPW 사용량을 계산한다.

stepUPW =
flowRate × time × cycles

여러 단계가 존재하면:

totalUPW =
sum(step.flowRate × step.time × step.cycles)

단위:
L

절감량:
baselineUPW - recommendedUPW

절감률:
((baselineUPW - recommendedUPW) / baselineUPW) × 100
```

## 25.10 고오염 공정 예외 규칙 프롬프트

```text
contaminationScore >= 90인 경우:

- minimumCleaningTime 이하로 cleaningTime을 낮추지 않는다.
- 다른 최적화 변수는 공정별 허용 범위 안에서만 조절한다.
- 품질 기준은 동일하게 적용한다.

핵심:
고오염 상태라고 해서 품질 기준을 완화하지 않는다.
오히려 절감 범위를 보수적으로 제한한다.
```

## 25.11 현재 공정 카드 구현 프롬프트

```text
현재 공정 카드에 아래 정보를 표시한다.

1. 현재 공정명
2. 공정 설명
3. 오염도
4. 기준 UPW
5. AI 추천 UPW
6. 절감량
7. 절감률
8. 예상 잔류 Cu
9. 허용 Cu 기준
10. 품질 판정

예:

오염도
85 / 100

기준 UPW
120 L

AI 추천 UPW
100 L

절감
20 L
16.7%

예상 잔류 Cu
8.4 × 10⁹ atoms/cm²

허용 기준
≤ 1.0 × 10¹⁰ atoms/cm²

✓ 품질 기준 충족

"품질 점수 97/100"과 같은 임의 점수 UI는 사용하지 않는다.
```

## 25.12 후보 비교 테이블 구현 프롬프트

```text
사용자가 AI 추천의 근거를 이해할 수 있도록 후보 비교 테이블을 제공한다.

열:
- UPW
- 예상 잔류 Cu
- 허용 기준
- 품질 판정
- 선택 여부

예:

120 L | 6.2×10⁹ | ≤1.0×10¹⁰ | ✓ | -
110 L | 7.0×10⁹ | ≤1.0×10¹⁰ | ✓ | -
100 L | 8.4×10⁹ | ≤1.0×10¹⁰ | ✓ | AI 추천
90 L  | 1.3×10¹⁰ | ≤1.0×10¹⁰ | ✕ | 제외

품질 기준을 초과한 후보는 시각적으로 탈락 상태를 명확하게 표시한다.
```

## 25.13 다음 공정 프롬프트

```text
현재 공정 분석이 완료된 뒤 "다음 공정" 버튼을 활성화한다.

조건:
- 결과 계산이 완료되어야 한다.
- 추천 조건이 결정되어야 한다.
- 품질 기준 판정이 완료되어야 한다.

버튼 클릭:
- 현재 공정을 완료 상태로 변경
- 공정 진행 indicator 업데이트
- 다음 공정 카드 로딩
- 완료된 공정 결과를 누적한다.

마지막 공정에서는:
"최종 결과 보기" 버튼을 표시한다.
```

## 25.14 최종 결과 프롬프트

```text
모든 공정의 결과를 합산하여 최종 대시보드를 표시한다.

표시:
- 총 기존 UPW
- 총 AI UPW
- 총 절감량
- 총 절감률
- 품질 기준 충족 공정 수
- 전체 공정 수

공정별 테이블:
- 공정
- 기존 UPW
- AI UPW
- 예상 잔류 Cu
- 허용 기준
- 품질 판정
- 절감량
- 절감률

메시지:
"품질을 희생하지 않고, 줄일 수 있는 UPW를 찾아냈습니다."

단, 모든 추천 조건은 품질 기준을 충족해야 한다.
```

## 25.15 ESG 카드 프롬프트

```text
ESG 결과 카드에 다음을 표시한다.

- UPW 절감량
- 전력 절감량
- 탄소 절감량

주의:
실제로 계산된 값만 표시한다.
계산되지 않은 값은 시뮬레이션 값이라고 명시한다.

UPW 절감량은 실제 최적화 결과에서 직접 계산한다.
전력/탄소 값은 별도 simulation conversion factor가 정의된 경우에만 계산한다.
```

## 25.16 상태 관리 프롬프트

```text
애플리케이션 상태는 다음 단계로 관리한다.

START
→ ANALYZING
→ PROCESS_ACTIVE
→ PROCESS_COMPLETE
→ NEXT_PROCESS
→ FINAL_RESULT

각 process에는:
- baseline
- candidates
- validCandidates
- recommendation
- predictedResidualCu
- qualityPass
- savings
상태를 저장한다.

사용자가 브라우저를 새로고침해도 복구가 필요하면 local state 또는 session storage를 사용한다.
실제 DB는 MVP 범위에 포함하지 않는다.
```

## 25.17 오류 처리 프롬프트

```text
다음 상황을 안전하게 처리한다.

1. validCandidates가 0개
→ "현재 조건에서는 품질 기준을 유지하면서 UPW를 줄일 수 없습니다."
→ 기존 기준 조건 유지

2. 모델 계산 오류
→ 추천값을 임의로 생성하지 않는다.
→ 오류 상태를 표시한다.

3. 허용 기준 데이터 누락
→ 공정 최적화를 실행하지 않는다.
→ "품질 기준 데이터가 없어 최적화를 수행할 수 없습니다."

4. 필수 공정 데이터 누락
→ 해당 공정을 추천 대상에서 제외하지 말고 오류 상태로 표시한다.
```

## 25.18 접근성 구현 프롬프트

```text
접근성을 반드시 적용한다.

- 색상만으로 pass/fail을 표현하지 않는다.
- CheckCircle/ShieldCheck + 텍스트를 함께 사용한다.
- 버튼은 keyboard focus를 지원한다.
- 충분한 contrast를 유지한다.
- 그래프와 숫자에 text label을 제공한다.
- 상태 변화는 aria-live 또는 접근 가능한 방식으로 전달한다.
```

## 25.19 컴포넌트 구조 권장안

```text
App
├── StartScreen
├── WaferSelector
├── AIAnalysisScreen
├── ProcessProgress
├── ProcessSimulation
│   ├── ProcessHeader
│   ├── ContaminationGauge
│   ├── RecipeCard
│   ├── UPWComparison
│   ├── ResidualContaminationCard
│   ├── QualityGate
│   └── CandidateComparison
├── FinalDashboard
│   ├── SummaryCards
│   ├── ProcessComparisonTable
│   ├── UPWSavingsChart
│   └── ESGCard
└── shared
    ├── Button
    ├── Card
    ├── Badge
    └── StatusIndicator
```

## 25.20 구현 검증 체크리스트

```text
- [ ] 200mm / 300mm 선택 가능
- [ ] AI 분석 단계 애니메이션 동작
- [ ] 공정별 오염도 표시
- [ ] 기준 세정 조건 표시
- [ ] 후보 조건 자동 생성
- [ ] 후보별 예상 잔류 Cu 계산
- [ ] 허용 기준 비교
- [ ] 기준 초과 후보 자동 탈락
- [ ] 최소 UPW 후보 자동 선택
- [ ] 품질 점수 0~100 방식 제거
- [ ] 기존 UPW 계산
- [ ] AI UPW 계산
- [ ] 절감량 계산
- [ ] 절감률 계산
- [ ] 다음 공정 이동
- [ ] 최종 누적 결과
- [ ] 후보 비교 테이블
- [ ] 품질 기준 충족 표시
- [ ] 고오염도 90 이상 최소 세정시간 유지
- [ ] validCandidates=0 안전 처리
- [ ] 데이터 누락 안전 처리
- [ ] 실제 생산라인/장비 제어 없음
- [ ] 문헌 기반 simulation data임을 표시
```

## 25.21 개발 AI에 전달할 최종 한 문장

```text
PureFlow AI는 "물을 가장 많이 줄이는 시스템"이 아니라,
"품질 기준을 먼저 통과시키고 그 안에서 가장 적은 UPW를 찾는 시스템"으로 구현하라.
```
