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
