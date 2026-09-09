# 시계열 예측 — **실행 가능한 공개 코드** 조사

갱신: **2026-09-09** (KST) · 레포: [`yongmini/time-series-forecasting`](https://github.com/yongmini/time-series-forecasting)  
목적: 논문 나열이 아니라 **클론해서 돌릴 수 있는 코드**. **공식(official) 리포**를 우선.

## 선정 규칙 (이번 조사)

- 활동·공개는 **2024년 이후**를 우선하고, 표에서는 **2025–2026**을 위에 둠.
- GitHub **`pushed_at` ≥ 2026-03-09** (조사일 기준 약 6개월)인 항목만 본표에 넣음. 예외는 *부록*.
- **라이선스**는 GitHub 표기 + LICENSE에 적힌 상용 제한을 함께 적음.
- 사전학습 가중치: README/컬렉션에서 확인된 Hugging Face(또는 릴리스)만.
- 논문만 있거나, 빈 리포, 검증 안 된 URL은 제외. **TSPulse**는 단독 레포가 아니라 **IBM Granite TSFM** 안에 포함.

스타·최근 커밋: GitHub API 스냅샷 **2026-09-09**.

---

## (1) 시계열 파운데이션 모델 (Time series foundation models)

| 이름 | 공개 시기 | 저자/기관 | 핵심 아이디어 (짧게) | 코드 URL | 사전학습 가중치 | 라이선스 | 최근 커밋 | Stars |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **TimesFM** (2.5 / **3.0** 포함) | 2024 (ICML); 3.0은 2026 발표 | Google Research | Decoder-only TSFM; 3.0은 네이티브 **다변량** 제로샷 | https://github.com/google-research/timesfm | HF [timesfm-release](https://huggingface.co/collections/google/timesfm-release-66e4be5fdb56e960c1e482a6); [`timesfm-3.0-pytorch`](https://huggingface.co/google/timesfm-3.0-pytorch), [`timesfm-2.5-200m-pytorch`](https://huggingface.co/google/timesfm-2.5-200m-pytorch) | **Apache-2.0** | 2026-09-07 | 32090 |
| **Chronos** / **Chronos-2** / Bolt | 2024; Chronos-2 ~2025 | Amazon Science | 시계열을 토큰화 → T5형 LM; Bolt는 경량화; Chronos-2가 최신 계열 | https://github.com/amazon-science/chronos-forecasting | [`amazon/chronos-2`](https://huggingface.co/amazon/chronos-2); Bolt/T5는 [`amazon/chronos-*`](https://huggingface.co/amazon) | **Apache-2.0** | 2026-09-08 | 5834 |
| **Moirai** / MoE / Moirai-2 (Uni2TS) | 2024–2025 | Salesforce AI Research | 범용 TS 트랜스포머; MoE 변형; LOTSA 사전학습 | https://github.com/SalesforceAIResearch/uni2ts | [`moirai-2.0-R-small`](https://huggingface.co/Salesforce/moirai-2.0-R-small); [Moirai 컬렉션](https://huggingface.co/collections/Salesforce/moirai-r-models-65c8d3a94c51428c300e0742) | **Apache-2.0** | 2026-06-02 | 1587 |
| **Toto 2.0** (+ Toto 1.0) | 2025–2026 | Datadog | 관측(observability) 중심 TSFM 스케일 패밀리 (4M→2.5B) | https://github.com/Datadog/toto | [Toto 2.0 컬렉션](https://huggingface.co/collections/Datadog/toto-20); 예: [`Toto-2.0-2.5B`](https://huggingface.co/Datadog/Toto-2.0-2.5B) | **Apache-2.0** | 2026-09-08 | 543 |
| **Granite TSFM / TTM / TSPulse** | 2024–2026 | IBM Granite | Tiny Time Mixers, **TSPulse**, PatchTSMixer, FlowState를 한 리포에 | https://github.com/ibm-granite/granite-tsfm ([`ibm/tsfm`](https://github.com/ibm/tsfm)) | [Granite TS 컬렉션](https://huggingface.co/collections/ibm-granite/granite-time-series-models); TTM [`granite-timeseries-ttm-r2`](https://huggingface.co/ibm-granite/granite-timeseries-ttm-r2); **TSPulse** [`granite-timeseries-tspulse-r1`](https://huggingface.co/ibm-granite/granite-timeseries-tspulse-r1) (코드: `tsfm_public/models/tspulse/`) | **Apache-2.0** | 2026-09-03 | 891 |
| **Time-MoE** | 2025 (ICLR’25) | Time-MoE 저자 | 십억 규모 **MoE** TSFM | https://github.com/Time-MoE/Time-MoE | [`TimeMoE-50M`](https://huggingface.co/Maple728/TimeMoE-50M), [`TimeMoE-200M`](https://huggingface.co/Maple728/TimeMoE-200M) | **Apache-2.0** | 2026-03-21 | 997 |
| **TiRex** | 2025 | NX-AI | 제로샷 / in-context 예측 (xLSTM 계열) | https://github.com/NX-AI/tirex | [`NX-AI/TiRex`](https://huggingface.co/NX-AI/TiRex) | **NXAI Community License** (대형 조직 상용 추가 조항 — LICENSE 필독) | 2026-09-08 | 300 |
| **TiRex-2** | 2026 | NX-AI | TiRex의 다변량·스트리밍 확장 | https://github.com/NX-AI/tirex-2 | [`NX-AI/TiRex-2`](https://huggingface.co/NX-AI/TiRex-2) | **Apache-2.0** | 2026-09-08 | 133 |
| **Timer / Sundial 계열** | 2024–2025 | THUML | 시계열용 generative pretrained Transformer | https://github.com/thuml/Large-Time-Series-Model | [`timer-base-84m`](https://huggingface.co/thuml/timer-base-84m), [`sundial-base-128m`](https://huggingface.co/thuml/sundial-base-128m); [컬렉션](https://huggingface.co/collections/thuml/time-series-foundation-models-67c80ace73299239b651d954) | **MIT** | 2026-03-22 | 1017 |

> **라이선스 주의:** 상용 전에 각 HF 모델 카드를 확인할 것. GitHub가 Apache-2.0이어도 **체크포인트 카드에 non-commercial 조항**이 붙는 경우가 있음 (TimesFM 일부 보고).

**부록·제외:** Lag-Llama (push 2025-06), MOMENT (push 2026-02-10, 약 7개월 — 부록). **TSPulse**는 단독 레포가 아니라 위 **Granite TSFM** 행에 포함.

---

## (2) Transformer 기반 모델

PatchTST, iTransformer, TimeMixer 등 **논문 전용 리포**는 상당수가 **6개월 이상 커밋 없음**. 실제로 돌리려면 유지보수 중인 라이브러리를 쓰는 편이 맞음.

| 이름 | 공개 시기 | 저자/기관 | 핵심 아이디어 (짧게) | 코드 URL | 사전학습 가중치 | 라이선스 | 최근 커밋 | Stars |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Time-Series-Library (TSL)** | 2023–2026 | THUML | 통합 학습/평가; 여러 Transformer 베이스라인 | https://github.com/thuml/Time-Series-Library | 보통 처음부터 학습 | **MIT** | 2026-04-18 | 12837 |
| **NeuralForecast** | 지속 | Nixtla | TFT, NHITS, Transformer 변형 등 | https://github.com/Nixtla/neuralforecast | 직접 학습 | **Apache-2.0** | 2026-09-08 | 4269 |
| **Large-Time-Series-Model** | 2024+ | THUML | Timer 등 generative Transformer (§1과 중복) | https://github.com/thuml/Large-Time-Series-Model | §1 참고 | **MIT** | 2026-03-22 | 1017 |

비활성 공식 논문 리포 (참고용; 실행은 TSL 권장): [PatchTST](https://github.com/yuqinie98/PatchTST) (2024-08), [iTransformer](https://github.com/thuml/iTransformer) (2025-07), [TimeMixer](https://github.com/kwuking/TimeMixer) (2025-10).

---

## (3) Linear / MLP 기반 모델

| 이름 | 공개 시기 | 저자/기관 | 핵심 아이디어 (짧게) | 코드 URL | 사전학습 가중치 | 라이선스 | 최근 커밋 | Stars |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Time-Series-Library** | — | THUML | DLinear / MLP형 베이스라인을 한 하네스에 | https://github.com/thuml/Time-Series-Library | 처음부터 학습 | **MIT** | 2026-04-18 | 12837 |
| **Granite TTM** | 2024–2026 | IBM | 소형 mixer형 사전학습 예측기 | https://github.com/ibm-granite/granite-tsfm | [Granite TS](https://huggingface.co/collections/ibm-granite/granite-time-series-models) | **Apache-2.0** | 2026-09-03 | 891 |
| **MLForecast** | 지속 | Nixtla | 지연(lag) 피처 + GBDT 등 | https://github.com/Nixtla/mlforecast | 데이터에 적합 | **Apache-2.0** | 2026-09-09 | 1276 |
| **StatsForecast** | 지속 | Nixtla | AutoARIMA, ETS 등 통계 모델 | https://github.com/Nixtla/statsforecast | 해당 없음 | **Apache-2.0** | 2026-09-09 | 4903 |

비활성 논문 코드: [LTSF-Linear/DLinear](https://github.com/cure-lab/LTSF-Linear) (2024-01); [pytorch-tsmixer](https://github.com/ditschuk/pytorch-tsmixer) (2023).

---

## (4) SSM / Mamba 기반 모델

| 이름 | 공개 시기 | 저자/기관 | 핵심 아이디어 (짧게) | 코드 URL | 사전학습 가중치 | 라이선스 | 최근 커밋 | Stars |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Time-Series-Library** | — | THUML | SSM/Mamba형 예측 구현 포함 | https://github.com/thuml/Time-Series-Library | 처음부터 학습 | **MIT** | 2026-04-18 | 12837 |
| **Mamba** (백본만) | 2023–2026 | State Spaces | Selective SSM 라이브러리 — **예측 레시피 자체는 아님** | https://github.com/state-spaces/mamba | TS 전용 가중치 아님 | **Apache-2.0** | 2026-07-22 | 18819 |

비활성 예측 논문 코드: [TimeMachine](https://github.com/Atik-Ahamed/TimeMachine) (2024-07, Apache-2.0), [S-D-Mamba](https://github.com/wzhwzhwzh0921/S-D-Mamba) (2025-05, SPDX 미설정). TSL 사용 또는 커밋 고정 권장.

---

## (5) 통합 벤치마크·라이브러리

| 이름 | 공개 시기 | 저자/기관 | 핵심 아이디어 (짧게) | 코드 URL | 사전학습 가중치 | 라이선스 | 최근 커밋 | Stars |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **GIFT-Eval** | 2024–2026 | Salesforce AI Research | TSFM / 제로샷 광역 평가 | https://github.com/SalesforceAIResearch/gift-eval | 해당 없음; Space [GIFT-Eval](https://huggingface.co/spaces/Salesforce/GIFT-Eval) | **Apache-2.0** | 2026-09-07 | 259 |
| **fev** (FEV-Bench) | 2025–2026 | AutoGluon | 신선·오염 저항형 평가 | https://github.com/autogluon/fev | 해당 없음 | **Apache-2.0** | 2026-09-04 | 171 |
| **Time-Series-Library** | — | THUML | 학술용 올인원 | https://github.com/thuml/Time-Series-Library | — | **MIT** | 2026-04-18 | 12837 |
| **GluonTS** | 지속 | AWS Labs | 확률적 시계열 툴킷 | https://github.com/awslabs/gluonts | 모델에 따름 | **Apache-2.0** | 2026-07-31 | 5234 |
| **StatsForecast** | 지속 | Nixtla | 통계 예측 | https://github.com/Nixtla/statsforecast | — | **Apache-2.0** | 2026-09-09 | 4903 |
| **NeuralForecast** | 지속 | Nixtla | 신경망 예측 | https://github.com/Nixtla/neuralforecast | — | **Apache-2.0** | 2026-09-08 | 4269 |
| **MLForecast** | 지속 | Nixtla | ML 예측 | https://github.com/Nixtla/mlforecast | — | **Apache-2.0** | 2026-09-09 | 1276 |
| **HierarchicalForecast** | 지속 | Nixtla | 계층 예측 조정 | https://github.com/Nixtla/hierarchicalforecast | — | **Apache-2.0** | 2026-09-04 | 758 |
| **Nixtla SDK** | 지속 | Nixtla | TimeGPT 클라이언트 포함 SDK | https://github.com/Nixtla/nixtla | TimeGPT = **호스팅 API** (공개 가중치 아님) | SDK **Apache-2.0**; TimeGPT는 **별도 ToS** | 2026-09-09 | 4002 |
| **Kats** | 지속 | Meta | 탐지·예측·피처 툴킷 | https://github.com/facebookresearch/Kats | — | **MIT** | 2026-08-19 | 6469 |

---

## 표 다음에

### (1) 지난 약 1년, 실제로 바뀐 것 — 5줄

1. TSFM이 논문 단계를 넘어 **설치·HF 가중치로 바로 쓸 수 있는 제품**이 됨 (TimesFM 2.5→3.0, Chronos-2, Moirai-2 계열, Toto 2.0, TiRex-2).  
2. 평가가 **의도적으로 갈라짐**: GIFT-Eval은 공통 무대이고, **fev 등 신선 벤치**는 오염·과적합 의심을 건다 — 리더보드 순위 ≠ 내 데이터.  
3. **스케일/MoE**를 공개로 실험 가능 (Toto 크기 사다리, Time-MoE).  
4. 과제 특화 Transformer는 **TSL / NeuralForecast 안에 살아 있고**, 2023–24 논문 리포 다수는 6개월 활동 기준을 못 넘김.  
5. **라이선스**: 대형 TSFM 대부분은 Apache-2.0; **TiRex v1**은 커뮤니티 상용 조항; TimeGPT는 API/ToS.

### (2) 제로샷·소수 데이터 숏리스트

| 필요할 때 | 여기서 시작 |
| --- | --- |
| 로컬 제로샷, Apache-2.0 | **TimesFM**, **Chronos-2**, **Moirai**, **Toto 2.0**, **TTM**, **TSPulse** (granite-tsfm) |
| in-context / 제로샷 대안 | **TiRex-2** (Apache-2.0) 또는 **TiRex** (LICENSE 확인) |
| MoE 사전학습 | **Time-MoE** |
| DL 거의 없이 고전 강함 | **StatsForecast** / **MLForecast** |
| 호스팅, 가중치 없음 | **TimeGPT** (Nixtla SDK) |

### (3) 학습 표현을 떼어 다른 과제에 쓰기

| 스택 | 재사용 이야기 |
| --- | --- |
| **MOMENT** (부록) | 예측·분류·이상·결측 등 **멀티태스크 TSFM**이 명시적; HF `AutonLab/MOMENT-1-*` |
| **Timer / Sundial** (THUML LTS) | generative 사전학습 계열; 임베딩 API를 가정하기 전에 task head 확인 |
| **Chronos / TimesFM / Toto / Moirai / TTM / Time-MoE / TiRex** | **forecast API 중심**; hidden state 재사용은 DIY |
| **Time-Series-Library** | 예측/결측/이상/분류 **학습 하네스** — 만능 임베딩 스토어는 아님 |
| **Kats** | 딥 파운데이션 임베딩보다 고전 피처·탐지 |

---

## 부록 — 6개월 활동 컷 밖이지만 알아둘 것

| 이름 | 코드 | 최근 커밋 | 왜 적나 |
| --- | --- | --- | --- |
| MOMENT | https://github.com/moment-timeseries-foundation-model/moment | 2026-02-10 | 멀티태스크 TSFM; MIT; HF AutonLab/MOMENT-1-* |
| Lag-Llama | https://github.com/time-series-foundation-models/lag-llama | 2025-06-06 | 초기 확률 TSFM; Apache-2.0 |
| PatchTST / iTransformer / TimeMixer / DLinear / TimeMachine / S-Mamba | §§2–4 참고 | 2024–2025 | 대표 논문; TSL로 실행하거나 커밋 고정 |

## 유지

배포 전에 `pushed_at`, 라이선스, HF ID를 다시 확인할 것. 공식 조직 리포를 우선. **검증된 실행 가능 항목만** 추가.
