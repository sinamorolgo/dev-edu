# 어드밴스드 패키징 MI에서 AI는 어떻게 쓰이고 있는가

## 2023–2026 패러다임 변화와 2025–2026 필독 논문 5편

| 항목 | 내용 |
|---|---|
| 조사 기준일 | 2026-07-19 |
| MI의 의미 | Metrology & Inspection, 계측 및 검사 |
| 대상 | HBM, 2.5D/3D integration, chiplet/interposer, fan-out wafer/panel-level packaging, wafer-to-wafer·die-to-wafer hybrid bonding |
| 핵심 질문 | 어떤 MI가 중요한가, AI를 어디에 어떻게 쓰는가, 2023–2026년에 도입 패러다임이 어떻게 변했는가, 2025–2026년에 무엇을 읽어야 하는가 |
| 근거 | 공식 roadmap·NIST 자료, peer-reviewed review, ECTC 2023–2026 MI 선별 문헌 247편의 엄격 재분류, SPIE·EPTC 추가 문헌, 공개 원문·초록 |
| 연계 보고서 | [어드밴스드 패키징에서 중요한 MI 조사](./advanced-packaging-mi-survey-report.md) |

> **한 줄 결론:** AI는 2023년의 개별 영상 판독기에서 출발해 2024년에는 전수검사·지속학습·설명 가능성으로 확장됐고, 2025년에는 합성데이터·물리제약·생성형 보고·공정예측을 결합했으며, 2026년에는 scatterometry, moiré alignment, X-ray acquisition처럼 **측정 원리와 촬영 전략 자체에 들어가는 computational metrology**로 이동하고 있다.

---

## 0. 의사결정자를 위한 핵심 요약

### 0.1 지금 AI가 실제로 하는 일

어드밴스드 패키징 MI에서 AI의 역할은 일곱 층으로 나뉜다.

1. **획득 최적화:** X-ray projection 수, sampling 위치, scan 조건을 검사 목적에 맞게 정한다.
2. **재구성·화질 향상:** sparse X-ray, SAM, optical 신호에서 유효 정보를 복원한다.
3. **검출·분할:** bump, pad, solder, void, particle, delamination을 찾고 픽셀·voxel 단위로 나눈다.
4. **정량 계측:** bond-line thickness, pad misalignment, solder extrusion, void ratio, Cu recess, overlay 같은 수치를 계산한다.
5. **가상계측:** 직접 측정하기 느리거나 파괴적인 bond strength, TSV stress, 재료·열화 상태를 센서·시뮬레이션 데이터로 추정한다.
6. **공정·수율 예측:** die shift, pattern distortion, overlay map을 이용해 뒤 공정의 yield와 최적 공정창을 예측한다.
7. **보고·원인 후보 생성:** 측정 결과를 요약하고 root-cause와 조치 후보를 제시한다. 이 마지막 층의 LLM은 계측기가 아니라 보조 해석기다.

전체 흐름은 다음과 같다.

**센서·scan → 재구성 → 검출·분할 → 계측값 → 수율·신뢰성 예측 → 공정 판단 → 보고·FA**

2023년에는 AI가 주로 가운데의 검출·분할에 있었다. 2026년에는 왼쪽의 센서·획득과 오른쪽의 공정 판단까지 범위가 넓어졌다.

### 0.2 가장 중요한 MI와 AI 우선순위

| 우선군 | 중요한 MI | 적합한 AI | 지금의 판단 |
|---|---|---|---|
| P0 | Hybrid-bond pre-bond surface: particle, residue, roughness, Cu recess/dishing, nanotopography | full-wafer optical CNN, scatterometry inverse ML, hybrid reference metrology, OOD detection | 접합 뒤에는 복구가 어렵고 sub-nm·고밀도 sampling이 필요하므로 가장 먼저 투자할 영역 |
| P0 | W2W/D2W overlay, die shift, rotation, tilt | moiré/IR regression, physics-generated synthetic data, uncertainty calibration | fine-pitch hybrid bonding의 직접 수율 CTQ |
| P0 | HBM·microbump·TSV의 buried void, open, misalignment, extrusion, delamination | 3D semi-supervised segmentation, synthetic data, continual/domain learning, super-resolution | AI 논문이 가장 많이 집중되는 영역이며 XRM의 해상도–FOV–시간 trade-off가 핵심 병목 |
| P1 | FOPLP die shift, pattern distortion, overlay yield | map-based ML, surrogate regression, active/Bayesian optimization | AI가 사후 검사에서 사전 수율예측으로 이동하는 대표 영역 |
| P1 | Warpage, residual stress, TSV KOZ, bond strength | FEA-generated training data, ANN surrogate, EBSD-to-stress ML, inverse model | 직접 측정 비용을 줄이는 virtual metrology 가치가 크지만 실물·외부 검증이 아직 약함 |
| P1 | SAM delamination·void·crack | physics-informed enhancement, self-supervision, defect segmentation | 물리적으로 그럴듯한 복원이 중요하며 image quality보다 defect POD를 봐야 함 |
| P2 | Package degradation와 PHM | unsupervised LSTM autoencoder, virtual sensor, probabilistic forecasting | 초기 열화 라벨이 희소한 상황에 적합하나 package-level 현장 데이터가 더 필요 |
| 보조층 | 자동 보고와 root-cause 후보 | grounded LLM/RAG, rule base, human sign-off | 보고시간은 줄일 수 있지만 pass/fail과 계측값의 진실 원천으로 쓰면 안 됨 |

P0–P2는 보편 규격이 아니라 [MAPT Roadmap 2.0](https://srcmapt.org/chapter10/), [IRDS 2024 Metrology](https://irds.ieee.org/images/files/pdf/2024/2024IRDS_MET.pdf), NIST 자료와 최근 논문의 반복 신호를 종합한 우선순위다. 실제 control plan은 제품 FMEA, 결함 크기, escape 비용, 장비 capability와 takt time으로 다시 정해야 한다.

### 0.3 2025–2026 필독 5편

| 순위 | 논문 | 대표하는 변화 | 핵심 근거 | 성숙도 |
|---:|---|---|---|---|
| 1 | [Efficient Visual Inspection Framework of HBM Bumps with Generative and Deep Learning AI](https://doi.org/10.1109/ECTC51687.2025.00161), 2025 | 모델 하나가 아니라 end-to-end 검사 시스템 | 불량 bump 식별 46% 향상, 25% label로 87% segmentation, 400개 이상 bump 보고 5분 이내 | Near-line 분석 실증; inline은 후속 목표 |
| 2 | [Inline Monitoring of Hybrid Bonding Cu Recess with VTS-ML](https://doi.org/10.1117/12.3091416), 2026 | reference metrology를 빠른 inline optical MI로 확장 | 15 wafer 학습, 별도 22 blind wafer, 최적 filter에서 blind R² 0.78·0.77 | Inline-capable metrology의 가장 구체적인 blind-wafer 검증 |
| 3 | [High-Precision Wafer-Level Bonding in Thin-3D: Moiré and Deep Learning](https://doi.org/10.1109/ECTC51846.2026.00207), 2026 | 측정 mark·물리 합성데이터·AI의 공동설계 | 실제 영상 정밀도 수십 nm 추정, 실제 3-layer stack 정렬 수백 nm | In-process demonstration |
| 4 | [AI-Powered Super-Resolution for Scalable and Efficient 3D X-Ray Inspection of 3D-Stacked HBMs](https://doi.org/10.1109/EPTC67330.2025.11392237), 2025 | AI가 X-ray resolution–throughput trade-off를 직접 줄임 | Industrial HBM data에서 acquisition time 최대 80% 감소 | HVM feasibility study; 세부 모델·POD는 미공개 |
| 5 | [Yield Prediction Technology in FOPLP Lithography](https://doi.org/10.1109/ECTC51687.2025.00030), 2025 | 사후 계측에서 사전 수율 의사결정으로 이동 | 초기 예측오차 1.2–2.7%, 판정 표준화 후 0.2–0.8% | Production substrate 기반 near-line predictive QC |

이 순위는 인용 수 순위가 아니다. 2026년 논문은 공개된 지 수개월밖에 되지 않아 citation maturity가 없다. **MI 중요도, 실제 패키지·wafer 검증, 방법론 전환성, HVM 연결성, 공개된 한계**를 기준으로 정성 평가했다.

- 딱 한 편만 읽는다면 1위 HBM end-to-end framework가 전체 AI inspection 흐름을 가장 잘 보여준다.
- 계측 엔지니어 관점에서 가장 강한 실증은 2위 VTS-ML의 blind-wafer 검증이다.
- 2026년 이후의 방향을 가장 잘 보여주는 논문은 3위 moiré alignment와 4위 X-ray super-resolution이다.

---

## 1. 무엇을 AI-MI 논문으로 보았는가

### 1.1 반드시 구분해야 할 네 범주

| 범주 | 정의 | 예 |
|---|---|---|
| 직접 AI-MI | 실제 검사·계측 신호를 학습 모델이 읽어 결함 또는 measurand를 출력 | XRM 3D segmentation, optical defect CNN, VTS spectrum→Cu recess |
| MI-to-control | 측정 결과와 공정 조건을 학습해 yield, 최적 recipe 또는 correction을 출력 | FOPLP overlay yield prediction, laser-dicing process-window RF |
| Virtual metrology | 실측·시뮬레이션·센서 데이터를 학습해 직접 보기 어려운 물리량을 추정 | bond strength ANN, EBSD grain→TSV stress, LSTM degradation score |
| AI-adjacent | digital twin, ROM, FEA, data fusion이라는 표현은 있지만 학습 모델이 확인되지 않음 | Modelica+CFD virtual sensor, one-way dashboard, 상관분석만 수행한 workflow |

또한 제목에 AI/HPC package가 들어가도 AI가 MI에 사용되지 않았다면 AI-MI 논문이 아니다. 반대로 random forest나 k-means처럼 오래된 방법도 실제 측정 데이터를 학습해 MI 출력을 만들면 AI/ML 범주에 포함했다.

### 1.2 로컬 ECTC corpus의 엄격 재분류

기존 MI 선별 corpus는 ECTC 2023–2026의 247편이다. 이 중 위의 엄격한 기준으로 학습된 모델이 확인된 논문은 다음과 같았다.

| 연도 | MI 선별 논문 | 엄격한 AI/ML-MI | 중심 |
|---:|---:|---:|---|
| 2023 | 60 | 2 | HBM 반지도 3D 계측, 다이싱 surrogate |
| 2024 | 65 | 3 | full-wafer CNN, continual learning, XAI |
| 2025 | 61 | 6 | HBM GenAI·synthetic data, FOPLP yield, PINN, VAE, ANN |
| 2026 | 61 | 6 | moiré alignment, computational X-ray, bond/stress virtual MI, in-situ anomaly |

이 수는 ECTC 전체 분야의 논문 점유율이나 산업 채택률이 아니다. MI 후보로 먼저 선별한 corpus 안에서 동일한 기준을 적용한 **내부 비교용 수치**다. SPIE의 VTS-ML, EPTC의 super-resolution·domain-adaptation 논문 등 외부 학회 문헌도 빠져 있다.

### 1.3 관련 서베이 논문은 있는가

AI만을 중심으로 2023–2026 advanced-packaging MI 전체를 체계적으로 비교한 단일 systematic review는 아직 찾지 못했다. 다음 자료를 조합하는 것이 가장 좋다.

1. [Volumetric Nondestructive Metrology for 3D Semiconductor Packaging: A Review](https://doi.org/10.1016/j.measurement.2023.114065) (Su et al., 2024): XRM, SAM, THz와 ML/AI를 buried 3D inspection 관점에서 가장 직접적으로 연결한다.
2. [Recent Progress in Structural Integrity Evaluation of Microelectronic Packaging Using SAM: A Review](https://doi.org/10.3390/s25247499) (Meshki Zadeh et al., 2025): SAM과 AI, signal processing, robotics, digital twin의 방향을 정리한다.
3. [Toward Digital Twins in 3D IC Packaging: A Critical Review of Physics, Data, and Hybrid Architectures](https://doi.org/10.3390/electronics15081740) (Datta et al., 2026): digital model·shadow·twin을 구분하고 closed-loop가 드물다는 점을 명확히 한다.
4. [2024 ECTC Special Session Report: Advancing Metrology for Next-Generation Microelectronics](https://tsapps.nist.gov/publication/get_pdf.cfm?pub_id=958598): NIST, Intel, TSMC, ASE, KLA 관점의 sub-micron NDI, inline MI, AI classification, 표준화 요구를 묶는다.
5. [MAPT Roadmap 2.0, Chapter 10](https://srcmapt.org/chapter10/): AI 논문 review는 아니지만 어떤 measurand를 우선해야 하는지 판단하는 산업 기준점이다.

---

## 2. 왜 어드밴스드 패키징 MI에서 AI가 필요한가

### 2.1 영상이 너무 크고 결함은 너무 드물다

HBM 한 개의 고해상도 XRM scan은 수백에서 천 장 규모의 slice와 거대한 3D voxel volume을 만든다. 정상 bump는 수백·수천 개지만 중요한 결함은 드물다. 사람이 모든 voxel을 보고 pad, solder, void를 분할하는 방식은 확장되지 않는다.

따라서 AI의 첫 역할은 반복적인 판독을 자동화하는 것이다. 그러나 단순 정상/불량 classification만으로는 부족하다. 공정 엔지니어가 필요한 것은 defect 위치뿐 아니라 BLT, misalignment, extrusion, void ratio 같은 **정량 계측값**이다.

### 2.2 고해상도와 takt time이 충돌한다

X-ray는 projection을 많이 찍을수록 3D reconstruction이 좋아지지만 시간이 길어진다. AFM은 sub-nm 표면을 잘 보지만 면적이 작고 느리다. SAM은 주파수를 올리면 해상도는 좋아지지만 penetration과 신호 품질이 달라진다.

AI의 가치가 가장 큰 지점은 이미 좋은 영상을 조금 더 예쁘게 만드는 일이 아니라 다음 trade-off를 줄이는 일이다.

- 적은 X-ray projection으로도 필요한 결함을 놓치지 않기
- 국부 AFM reference를 wafer-level optical sampling으로 확장하기
- 느린 FEA·파괴시험을 빠른 virtual metrology로 보완하기

### 2.3 실제 결함 label이 부족하다

rare defect는 의도적으로 만들기 어렵고, destructive ground truth는 비싸다. 그래서 2023년 반지도학습, 2025년 synthetic 3D XRM, 2026년 physics-generated moiré image가 연속해서 등장했다.

핵심은 합성데이터의 양이 아니라 **실제 결함 물리와 measurement transfer function을 얼마나 보존하는가**다. 합성 영상이 보기에는 그럴듯해도 실제 void·crack·misalignment의 POD를 높이지 못하면 MI 가치는 없다.

### 2.4 제품·장비·recipe가 계속 바뀐다

HBM 세대, bump geometry, stack depth, X-ray source, reconstruction recipe가 바뀌면 영상 분포도 바뀐다. 한 번 학습한 모델의 test accuracy가 높아도 양산에서 오래 유지된다는 뜻은 아니다.

따라서 2024년부터 다음 기술이 중요해졌다.

- continual learning
- domain adaptation
- uncertainty calibration
- out-of-distribution detection
- human fallback
- model·recipe version traceability

### 2.5 중요한 물리량은 직접 보기 어렵다

Bond strength, interfacial adhesion, TSV 주변 stress, 장기 열화는 직접 전수 측정하기 어렵거나 파괴적이다. 이때 simulation-generated data와 소수의 reference measurement로 surrogate를 만들면 빠른 virtual metrology가 가능하다.

다만 virtual metrology의 출력은 실측과 동일하지 않다. **예측값이라는 표지, 불확도, 적용 가능한 stack·recipe 범위, 주기적인 reference check**가 있어야 한다.

---

## 3. 2023–2026 AI 도입 패러다임 변화

### 3.1 전체 타임라인

| 연도 | 중심 질문 | 대표 AI | MI에서의 역할 | 아직 부족했던 것 |
|---:|---|---|---|---|
| 2023 | AI가 이 측정·검사를 할 수 있는가 | RF surrogate, contrastive·semi-supervised 3D DL | 특정 공정창 최적화, HBM buried feature 검출·계측 | scan time, 외부검증, lifecycle |
| 2024 | 현장에 넣고 데이터가 바뀌어도 유지할 수 있는가 | full-wafer CNN, continual learning, XAI | 전수검사, 신규 class 적응, operator workflow, edge-case 설명 | cross-tool validation, calibration, 표준 benchmark |
| 2025 | 데이터와 물리 부족을 어떻게 동시에 줄이는가 | synthetic data, GenAI/LLM, PINN, VAE, yield ML | 저라벨 검사, 물리제약 복원, inverse process, 사전 수율예측 | generative hallucination, 독립 defect metric, model disclosure |
| 2026 | AI를 측정기와 measurement strategy의 일부로 만들 수 있는가 | VTS inverse ML, physics-synthetic alignment, EDSR, ANN virtual MI, LSTM-AE | inline optical MI, acquisition co-design, latent measurand, in-situ PHM | true closed loop, traceable uncertainty, multi-lot HVM evidence |

이 표는 각 연도의 절대적인 최초를 뜻하지 않는다. 2023년에도 die-shift 측정에서 adaptive lithography까지 연결한 사례가 있었다. 여기서 말하는 변화는 연구의 **무게중심**이다.

### 3.2 2023: task-specific 판독기와 공정 surrogate

#### 대표 1 — HBM 3D XRM 반지도 계측

[Pahwa et al., 3D Defect Detection and Metrology of HBMs Using Semi-Supervised Deep Learning](https://doi.org/10.1109/ECTC51909.2023.00161)은 3D XRM에서 HBM의 Cu pillar, pad, solder, void를 검출·분할하고 BLT, solder extrusion, void-to-solder ratio, pad misalignment를 산출했다.

- contrastive representation과 clustering으로 label할 slice를 고른다.
- multi-view slice-and-fuse와 Mean Teacher 계열 반지도학습으로 적은 label을 활용한다.
- ECTC판 기준 object detection 최대 16%, 3D segmentation 6% 향상.
- BLT 평균오차 1.24 µm 미만, pad misalignment 0.753 µm.

더 상세한 peer-reviewed journal판은 [Wang et al., Sensors 23, 5470](https://doi.org/10.3390/s23125470)이다. journal판은 detection 최대 16%, segmentation 7.8% 향상과 평균 2 µm 미만의 주요 계측오차를 보고한다. 두 판본은 데이터 집계가 다르므로 수치를 섞으면 안 된다.

이 연구의 의미는 AI가 불량 유무만 말한 것이 아니라 **3D NDI → segmentation → µm metrology**를 연결했다는 데 있다. 반면 XRM 획득은 sample당 2–8시간이고 데이터는 비공개이며, 다른 scanner·package에 대한 외부검증은 없다.

#### 대표 2 — 측정값에서 공정창으로

[Raghavan et al., Laser Dicing Parameters Through Machine Learning](https://doi.org/10.1109/ECTC51909.2023.00032)은 6개 laser input, 10개 level, Latin-hypercube DoE와 조건별 15회 측정을 이용해 random-forest surrogate를 만들었다. dicing width와 die strength를 동시에 고려해 공정창을 찾았다는 점에서 초기 MI-to-control 사례다.

#### 중요한 예외 — 이미 feed-forward correction도 있었다

[TrueAdapt: AI Based Maskless Patterning to Compensate for Die-Shift in FOWLP](https://doi.org/10.1109/ECTC51909.2023.00388)은 inline optical image에서 AI가 die offset을 찾고 adaptive routing과 direct-write lithography로 보정했다. 10 µm-pitch daisy-chain wiring을 시연했지만 모델 구조, offset error, yield uplift가 공개 초록에 없어 정량 순위에서는 제외했다.

따라서 2023년을 단순히 “AI가 가능성을 시험한 해”라고만 부르면 불완전하다. 지배적인 흐름은 point solution이었지만, 일부 연구는 이미 측정→보정까지 연결하고 있었다.

### 3.3 2024: 정확도에서 운용·적응·신뢰로

#### Full-wafer hybrid-bond optical inspection

[Zhao et al., Deep CNNs for Automatic Detection of Defects Which Impact Hybrid Bonding Yield](https://doi.org/10.1109/ECTC51529.2024.00083)은 10/15 µm Cu pad, 40 µm pitch wafer를 5× dark-field optical microscope로 전수 scan하고 Xception 기반 두 CNN으로 defect 검출과 4-class 분류를 수행했다.

- 1차 CNN: test accuracy 97.2%, PR-AUC 0.936.
- false negative를 줄이도록 threshold를 정했을 때 precision 72%, recall 92%.
- 2차 CNN: test accuracy 95.5%.
- 작업자 시간은 host wafer에서 150→45분, die wafer에서 250→155분으로 줄었다.

가장 중요한 결과는 97% accuracy 자체가 아니다. 작업시간, recall, CPU throughput, 사람이 처리할 unknown defect를 함께 제시했다는 점이다. 이때부터 AI가 standalone model이 아니라 **operator workflow의 한 단계**가 된다.

#### Continual learning

[Chang et al., Continual Learning for Feature Segmentation of Buried Packages in 3D XRM](https://doi.org/10.1109/ECTC51529.2024.00314)은 과거 데이터를 모두 replay하지 않고 새 class·scan 조건을 학습하면서 기존 class를 보존했다. 저자 보고로 full retraining과 같은 수준의 성능을 유지하며 데이터 50%, 학습시간 60%를 줄였다.

공개 초록에는 class별 Dice, forgetting, cross-tool 검증이 없다는 한계가 있지만, MI 모델의 질문을 “한 번 잘 맞는가”에서 **새 제품에서도 유지되는가**로 바꿨다.

#### Explainable AI와 edge case

[Ghosh et al., Explainable AI Metrics for Advanced IC Packaging Inspection](https://doi.org/10.1109/ECTC51529.2024.00388)은 LIME, SHAP, counterfactual, Eigen-CAM을 적용하고 MPR·CRS라는 설명 평가 지표를 제안했다. saliency가 영상의 숫자 8을 microbump로 보는 spurious cue를 드러낸 점은 유용하다.

다만 advanced-package 원 영상이 4장뿐이고 PCB 데이터 의존성이 높다. 따라서 이 논문은 production benchmark가 아니라 **trustworthy-AI 문제를 선명하게 제기한 proof of concept**로 읽어야 한다.

### 3.4 2025: data-efficient, physics-aware, decision-oriented AI

2025년에는 서로 다른 네 흐름이 합쳐진다.

1. **Synthetic data와 저라벨 학습:** [3D HBM data augmentation](https://doi.org/10.1109/ECTC51687.2025.00277)은 annotation 요구량을 최대 90% 줄이면서 비교 가능한 bump segmentation과 더 나은 defect detection을 보고했다.
2. **End-to-end 검사 시스템:** [HBM visual inspection framework](https://doi.org/10.1109/ECTC51687.2025.00161)은 detection, segmentation, metrology, LLM report를 하나로 묶었다.
3. **Physics-informed reconstruction:** [PINN for SAM enhancement](https://doi.org/10.1109/ECTC51687.2025.00368)은 acoustic-wave equation을 loss와 평가 metric에 넣었다.
4. **공정 예측과 역설계:** [FOPLP yield prediction](https://doi.org/10.1109/ECTC51687.2025.00030)은 die-shift map에서 overlay yield를 예측했고, [cross-section VAE](https://doi.org/10.1109/ECTC51687.2025.00298)는 process condition→cross-section과 target shape→recommended condition을 양방향으로 다뤘다.

이 시점부터 AI는 사후 defect classifier를 넘어 **데이터 생산자, 물리 regularizer, 공정개발 보조자, 보고서 작성자**가 된다.

그러나 생성형 기능을 한 덩어리로 보면 안 된다.

- Synthetic training image는 학습 데이터다.
- Super-resolution image는 측정 신호의 추정 복원이다.
- VAE cross-section은 공정 결과의 예측이다.
- LLM report는 계측 결과의 언어적 요약이다.

네 결과의 검증법과 위험이 모두 다르다. 특히 LLM 문장은 물리적 측정 증거가 아니다.

### 3.5 2026: AI가 계측기와 측정전략 안으로 들어간다

2026년의 대표 변화는 다음과 같다.

- VTS spectrum과 AFM reference를 결합해 Cu recess를 inline optical 방식으로 추정한다.
- moiré mark·IR optics·physics-generated image·DL regression을 함께 설계한다.
- X-ray projection 수와 sampling pattern을 super-resolution·defect segmentation과 공동 최적화한다.
- nanoindentation·cohesive-zone FEA에서 W2W bond strength를, EBSD grain simulation에서 TSV stress·KOZ를 추정한다.
- RDS(on)·VSD 시계열을 unsupervised LSTM autoencoder로 학습해 초기 열화를 찾는다.

이를 단계로 쓰면 다음과 같다.

**AI 판독 → AI 계측값 추출 → AI virtual metrology → sensor·sampling·AI 공동설계 → 장기적으로 closed-loop process control**

다만 마지막 단계는 아직 일반화된 현실이 아니다. [Datta et al. 2026 critical review](https://doi.org/10.3390/electronics15081740)는 3D IC packaging 문헌의 대다수가 다음 두 수준에 있다고 평가한다.

- **Digital Model:** 오프라인 simulation, 자동 데이터 교환 없음.
- **Digital Shadow:** 실제 센서에서 모델로 단방향 자동 업데이트.

모델이 물리 공정에 자동으로 correction을 되돌려 보내는 양방향 digital twin은 드물다. 따라서 2026년 논문에 inline, real-time, digital twin이라는 단어가 있어도 자동 recipe correction까지 실증했는지 따로 확인해야 한다.

---

## 4. 중요한 MI별 AI 적용 방법

### 4.1 Hybrid-bond surface: Cu recess, roughness, particle

**왜 중요한가**

Cu recess가 너무 크면 anneal 후에도 Cu–Cu contact가 닫히지 않고, 너무 작거나 protrusion이 크면 dielectric 접촉과 표면 planarity가 깨질 수 있다. particle·residue·roughness는 interface void의 직접 원인이 된다. 접합 후에는 결함이 buried interface가 되므로 pre-bond에서 잡는 편이 가장 싸다.

**적합한 AI**

- Full-wafer optical CNN: particle, discoloration, pattern defect screen.
- Scatterometry inverse ML: AFM reference로 Cu recess 회귀.
- RHEED profile fitting: 넓은 면적의 roughness parameter 추정.
- OOD·uncertainty: 학습하지 않은 stain, scratch, pad geometry를 사람에게 보낸다.

**필수 검증**

- AFM/WLI/SEM reference와 blind-wafer correlation.
- bias, 3σ, repeatability, tool matching, GR&R.
- top/bottom wafer stack과 nominal pitch 변화에 대한 transfer.

### 4.2 Alignment와 overlay

**왜 중요한가**

Pitch가 작아질수록 같은 절대 오차가 pad overlap과 전기 수율을 빠르게 무너뜨린다. die shift, wafer distortion, X/Y/θ, local non-linear distortion을 동시에 관리해야 한다.

**적합한 AI**

- Moiré 또는 vernier image regression.
- Physics-generated synthetic mark image.
- Synthetic-to-real domain adaptation.
- Prediction interval과 calibration.

**필수 검증**

- Image-level prediction error와 실제 bonded-stack overlay를 분리.
- wafer 전면, lot 간, 장비 간 3σ.
- mark contamination, contrast drift, thermal drift.

### 4.3 HBM·microbump의 buried 3D defect

**왜 중요한가**

Stack 내부의 void, non-wet, missing bump, extrusion, misalignment는 표면 AOI로 볼 수 없다. XRM은 유력하지만 scan time과 annotation cost가 크다.

**적합한 AI**

- 3D detection·semantic segmentation.
- Semi-supervised, active learning, synthetic data.
- Continual learning과 cross-domain adaptation.
- Sparse-view reconstruction과 super-resolution.
- Quantitative post-processing으로 BLT, void ratio, misalignment 계산.

**필수 검증**

- 결함별 recall·false negative·POD.
- destructive cross-section 또는 FIB/SEM correlation.
- image-level PSNR/SSIM뿐 아니라 downstream defect metric.
- scanner, reconstruction recipe, HBM generation이 바뀐 external test.

### 4.4 FOPLP die shift와 overlay yield

**왜 중요한가**

Mold·cure 과정의 die shift와 panel distortion은 lithography overlay를 망가뜨린다. 뒤 공정을 끝낸 뒤 불량을 확인하면 고가 die와 공정비가 이미 투입돼 있다.

**적합한 AI**

- Panel-wide metrology map과 layout·field 정보를 결합한 yield model.
- Global, zone, site, die-by-die correction 전략 비교.
- Active/Bayesian optimization으로 yield–throughput sweet spot 탐색.

**필수 검증**

- train/test lot 분리와 production blind panel.
- 실제 inspection label의 판정 기준 통일.
- 자동 correction 전 rule-based safety envelope.

### 4.5 Warpage, stress, bond strength와 reliability

**왜 중요한가**

이들은 yield와 field reliability를 좌우하지만 온도·공정상태에 따라 변하고 직접 전수 측정이 어렵다.

**적합한 AI**

- FEA-generated data의 surrogate ANN.
- EBSD grain structure와 anisotropic simulation을 결합한 stress ML.
- Nanoindentation·cohesive-zone model 기반 bond-strength inverse model.
- Electrical time-series LSTM autoencoder.

**필수 검증**

- Simulation-only 성능과 physical validation을 분리.
- material lot, geometry, boundary condition 범위를 명시.
- 예측값의 불확도와 periodic destructive/reference audit.

---

## 5. 2025–2026 필독 논문 5편 상세 분석

### 5.1 1위 — HBM end-to-end AI inspection system

#### 논문

Richard Chang et al., [Efficient Visual Inspection Framework of High-Bandwidth Memory Bumps with Generative and Deep Learning AI](https://doi.org/10.1109/ECTC51687.2025.00161), IEEE ECTC 2025, pp. 920–926.

#### 이 논문이 묻는 질문

“3D XRM에서 bump를 찾는 모델 하나”가 아니라, scan 한 건을 넣으면 결함 위치, 정량 치수, 우선순위, 원인 후보와 보고서까지 만들 수 있는가?

#### 방법

- 고해상도 3D XRM의 transverse, sagittal, 3D view를 함께 사용한다.
- object detection과 semantic segmentation을 modular하게 연결한다.
- multi-view inference로 defective bump 식별을 보강한다.
- 3D metrology toolbox가 BLT, void-to-solder ratio, pad misalignment, solder extrusion 등을 계산한다.
- LLM이 계측 결과를 기반으로 보고서와 가능한 root-cause·조치 후보를 생성한다.
- Human-in-the-loop를 검사 흐름 안에 둔다.

#### 주요 결과

- defective-bump identification 46% 향상.
- 전체 label의 25%만 사용해 memory-bump segmentation accuracy 87%.
- 400개가 넘는 bump를 가진 한 scan의 종합 보고를 5분 이내 생성.

#### 왜 의미가 큰가

이 논문은 2025년의 패러다임을 가장 완전하게 보여준다. AI를 segmentation model 하나로 정의하지 않고 **검출 → 계측 → 분류 → 보고 → 사람 확인**이라는 검사 시스템으로 정의한다. 현장 도입에서 모델 accuracy보다 중요한 workflow integration을 보여준다.

#### 반드시 비판적으로 읽을 부분

- 46% 향상의 정확한 baseline과 전체 dataset 규모가 공개 초록에 충분하지 않다.
- 5분은 이미 획득된 scan의 분석·보고시간으로 읽어야 하며 XRM acquisition time까지 포함한다고 볼 근거가 없다.
- 단일 비공개 HBM dataset이므로 다른 HBM 세대와 scanner에 대한 external validation이 필요하다.
- LLM root-cause suggestion의 precision, calibration, evidence citation은 별도로 검증되지 않았다.
- LLM은 계측값을 생성하는 층과 분리하고 자동 disposition 권한을 주지 않아야 한다.

#### 읽을 때 볼 포인트

모델 architecture보다 각 단계 사이의 interface를 본다. 어떤 output이 물리 계측이고, 어떤 output이 heuristic 또는 언어 생성인지 분리해 읽는 것이 핵심이다.

---

### 5.2 2위 — VTS-ML을 이용한 hybrid-bond Cu recess inline monitoring

#### 논문

Pádraig Timoney et al., [Inline Monitoring of Hybrid Bonding Cu Recess with Vertical Traveling Scatterometry Machine Learning](https://doi.org/10.1117/12.3091416), Proc. SPIE 13981, 2026. [저자사 공개 원문 PDF](https://www.novami.com/wp-content/uploads/2026/04/13981-16-timoney-spie-alp-2026-vts-ml-cu-recess-final.pdf)

#### 이 논문이 묻는 질문

AFM처럼 정확하지만 느리고 국부적인 reference metrology를 이용해, 서로 다른 underlayer stack에서도 빠르게 Cu recess를 측정하는 inline optical model을 만들 수 있는가?

#### 방법

- Spectral interferometry signal을 vertical traveling scatterometry로 변환한다.
- VTS cutoff A–E를 바꿔 깊은 underlayer의 광학 기여를 제거하고 surface·near-surface signal을 분리한다.
- AFM으로 얻은 Cu recess를 reference label로 사용한다.
- 15 wafer, wafer당 5 die의 reference와 약 4 nm 범위로 regression model을 학습한다.
- 학습에 쓰지 않은 22 blind wafer에서 평가한다.
- Hybrid bonding의 top·bottom wafer처럼 underlayer stack이 다른 두 범주에 하나의 model을 적용한다.

#### 주요 결과

- Blind test에서 cutoff B의 R²는 0.78, cutoff C는 0.77.
- 깊은 underlayer 기여가 남은 cutoff A는 blind R² 0.34로 크게 나빠졌다.
- 같은 학습 데이터여도 물리적으로 적절한 signal window를 고르면 일반화가 크게 좋아졌다.

#### 왜 의미가 큰가

이 연구의 핵심은 ML regression 자체가 아니다. **측정물리로 nuisance signal을 먼저 제거하고, 제한된 AFM reference로 빠른 optical metrology를 교정**했다는 점이다. 느린 reference를 없애려는 것이 아니라, 소수 reference를 이용해 wafer-level sampling을 확장하는 hybrid metrology다.

또한 2026년 논문 중 드물게 blind wafer와 서로 다른 stack을 명시한다. “AI가 계측기 안으로 들어간다”는 말을 가장 구체적으로 보여준다.

#### 반드시 비판적으로 읽을 부분

- 15-wafer training set은 여전히 작다.
- R²는 상관성 지표이며 absolute bias, uncertainty, repeatability, GR&R을 대신하지 않는다.
- 비슷한 Cu-recess surface structure를 전제로 한 top/bottom stack generalization이다. 새로운 pitch·material·roughness 범위까지 보장하지 않는다.
- Production control limit 근처의 false accept·false reject와 장기 drift는 별도 검증이 필요하다.

#### 읽을 때 볼 포인트

Training R²가 높은 cutoff A가 blind test에서는 무너지고 B·C가 살아남는 대목을 본다. 좋은 AI-MI는 모델 크기보다 **signal selection과 blind validation**이 더 중요하다는 교훈이다.

---

### 5.3 3위 — physics-synthetic moiré deep-learning alignment

#### 논문

Chen-Chia Chang et al., [High-Precision Wafer-Level Bonding in Thin-3D: A Moiré Pattern and Deep-Learning Alignment Approach](https://doi.org/10.1109/ECTC51846.2026.00207), IEEE ECTC 2026, pp. 1245–1251.

#### 이 논문이 묻는 질문

실제 nm-scale alignment label을 대량으로 만들기 어려운 상황에서, mark와 image physics를 이용해 X/Y translation과 rotation을 동시에 예측할 수 있는가?

#### 방법

- 금속층에 concentric octagonal moiré grating을 넣는다.
- Near-field IR contrast inversion으로 buried mark를 읽는다.
- 물리 기반 moiré image generator로 다양한 offset·rotation의 synthetic image를 만든다.
- Synthetic image와 실제 IR image를 섞어 deep-learning regression model을 학습한다.
- 단일 mark에서 translation과 rotation을 동시에 출력한다.

#### 주요 결과

- Vernier label uncertainty를 고려하면 real-image precision이 수십 nm 수준으로 추정된다.
- 실제 3-layer active-device stack에서 interlayer alignment를 수백 nm 수준으로 유지했다.

#### 왜 의미가 큰가

이 논문은 단순히 기존 이미지를 CNN에 넣지 않는다. **alignment mark, IR contrast, physics simulator, synthetic data, DL model을 하나의 measurement system으로 공동설계**한다. 실제 label이 희소한 nm metrology에서 synthetic data를 사용하는 가장 설득력 있는 방식 중 하나다.

#### 반드시 비판적으로 읽을 부분

- Image-level prediction precision 수십 nm와 bonded 3-layer stack의 실제 alignment 수백 nm를 같은 수치처럼 말하면 안 된다.
- 공개 초록에는 정확한 MAE, 3σ, conventional mark 대비 개선폭이 없다.
- Wafer 전면 반복성, mark 오염, 장시간 drift, tool-to-tool transfer와 takt time을 더 검증해야 한다.
- Synthetic generator가 실제 optical aberration과 process variation을 충분히 포괄하는지 확인해야 한다.

#### 읽을 때 볼 포인트

Synthetic data를 단순 augmentation이 아니라 measurement design의 일부로 사용한 점, 그리고 prediction error와 final bonded-stack error 사이에 어떤 공정 오차가 추가되는지를 본다.

---

### 5.4 4위 — HBM X-ray super-resolution과 acquisition time 80% 절감

#### 논문

Yang Yu et al., [AI-Powered Super-Resolution for Scalable and Efficient 3D X-Ray Inspection of 3D-Stacked HBMs](https://doi.org/10.1109/EPTC67330.2025.11392237), IEEE EPTC 2025, pp. 1–7.

#### 이 논문이 묻는 질문

고해상도 X-ray의 긴 scan time을 줄이면서 HBM의 공간해상도와 downstream defect analysis에 필요한 정보를 유지할 수 있는가?

#### 방법

- Scan 수를 줄여 얻은 low-fidelity 3D X-ray volume을 사용한다.
- Deep-learning super-resolution network로 volume을 향상한다.
- Industrial HBM dataset에서 검사 scalability와 sample quality를 평가한다.
- 공개 초록은 구체적인 network architecture나 모델명을 밝히지 않는다. 따라서 이 2025년 방법을 EDSR라고 부르면 안 된다.

#### 가장 중요한 결과

- X-ray acquisition time을 최대 80% 줄였다.
- Spatial-resolution quality는 비교 가능한 수준으로 유지했다고 보고한다.
- Downstream defect analysis에 사용할 sample quality가 향상됐다고 보고한다.

80%는 AI inference 시간이 아니라 **X-ray acquisition-time 감소**다.

#### 왜 의미가 큰가

3D XRM의 가장 큰 산업 병목인 resolution–throughput trade-off를 정면으로 다루고, 최대 80%라는 acquisition 효과를 제시했다. AI의 가치가 영상 후처리 정확도에만 있지 않고 **검사 장비의 takt time을 바꾸는 데 있다**는 점을 가장 선명하게 보여준다.

같은 핵심 연구팀의 2026년 논문 [Efficiency Meets Fidelity](https://doi.org/10.1109/ECTC51846.2026.00242)는 이 연구선을 더 엄격하게 확장한다. 2026년판은 EDSR를 명시하고 projection 수와 sampling strategy를 체계적으로 바꾸며 background, fine foreground, scan-level defect segmentation을 함께 본다. 저자들이 공식적으로 후속편이라고 명시한 것은 아니므로, 여기서는 공통 저자·문제·방법의 연속성에 근거한 **후속 연구선이라는 해석**으로 한정한다.

#### 반드시 비판적으로 읽을 부분

- 공개 초록에는 모델명, dataset 수, projection 조건, train/test split, PSNR, SSIM, defect recall/POD와 latency가 없다.
- Super-resolution은 결함을 hallucinate하거나 실제 미세결함을 평활화할 수 있다.
- Comparable spatial resolution이 defect-size별 POD 보존을 뜻하지는 않는다.
- 80% acquisition 절감이 어떤 결함 크기와 scan recipe 범위에서 성립하는지 추가 검증해야 한다.
- False accept, destructive ground truth와 external scanner validation이 필요하다.

#### 읽을 때 볼 포인트

2025년 논문에서는 80% 효과의 실험 조건과 빠진 metric을 확인하고, 바로 2026년 Efficiency Meets Fidelity를 이어 읽는다. 2026년판이 보여주는 핵심은 background는 비교적 잘 복원돼도 fine foreground와 defect recovery는 sampling·projection density에 민감하며, 물리적으로 획득되지 않은 정보는 AI가 안정적으로 복구하지 못한다는 점이다.

---

### 5.5 5위 — FOPLP overlay yield prediction

#### 논문

John Chang et al., [Yield Prediction Technology: A Game Changer for Cutting Costs and Reducing Ramp Time in FOPLP Lithography](https://doi.org/10.1109/ECTC51687.2025.00030), IEEE ECTC 2025, pp. 136–141. [저자사 공개 원문 PDF](https://ontoinnovation.com/wp-content/uploads/2025/09/Yield-Prediction-Technology-in-FOPLP-Lithography.pdf)

#### 이 논문이 묻는 질문

Coating, exposure, development와 후처리를 모두 끝낸 뒤 overlay yield를 확인하지 않고, 초기 die-shift·distortion metrology에서 최종 overlay yield를 미리 예측할 수 있는가?

#### 방법

- Offline metrology로 panel의 die shift와 pattern distortion map을 측정한다.
- Exposure field, die layout, panel layout, overlay threshold와 공정 조건을 결합한다.
- ML algorithm으로 overlay error와 overlay yield를 예측한다.
- Global, zone, site, die-by-die correction 전략의 yield–throughput trade-off를 비교한다.
- 실제 yield는 별도 inspection tool 결과와 비교한다.

#### 주요 결과

- Production substrate의 초기 predicted-vs-actual yield error는 1.2–2.7%.
- 검사자의 ambiguous pattern 판정 기준을 표준화한 뒤 0.2–0.8%로 감소.
- 본문 한 예에서는 predicted yield 97.45%, actual yield 98.82%, 차이 1.37%p.

#### 왜 의미가 큰가

이 논문은 AI-MI가 defect를 더 잘 찾는 데서 멈추지 않고 **다음 공정의 경제적 결과를 미리 예측**하는 방향을 보여준다. 실제 production substrate와 HVM workflow를 다룬다는 점도 강하다.

더 중요한 교훈은 모델보다 label definition이다. 0.2–0.8%로 줄어든 핵심 계기 중 하나가 검사자의 ambiguous-pattern 판정을 표준화한 일이었다. 즉, 좋은 AI-MI는 먼저 measurand와 ground truth를 정렬해야 한다.

#### 반드시 비판적으로 읽을 부분

- ML model 종류, dataset 크기, train/test 분리, statistical baseline이 공개되지 않은 vendor case study다.
- Offline metrology 기반 near-line prediction이며 자동 recipe correction까지 닫힌 closed loop는 아니다.
- Operator standardization의 효과와 model improvement 효과가 분리돼 있지 않다.
- 다른 panel format·material·lithography tool에 대한 external validation이 필요하다.

#### 읽을 때 볼 포인트

화려한 model architecture가 없어도 HVM 가치가 클 수 있다는 점, 동시에 method disclosure가 부족하면 독립 재현성이 낮다는 점을 함께 본다.

---

## 6. Top 5 바로 아래의 중요 논문

### 6.1 Low-label HBM을 구현하려면

[An Efficient Data Augmentation and Semantic Segmentation Framework for 3D Defect Detection of HBMs](https://doi.org/10.1109/ECTC51687.2025.00277)

- Synthetic 3D XRM training data로 annotation 요구량을 최대 90% 줄였다.
- Bump segmentation은 최대 약 90% 수준의 comparable performance를 유지하고 defect detection을 개선했다고 보고한다.
- 생성모델 구조, defect별 recall, 실제 희귀 결함 분포의 fidelity가 공개 초록에 부족하다.

HBM model을 자주 재학습해야 한다면 Top 5의 FOPLP 논문과 바꿔 읽을 가치가 있다.

### 6.2 Physics-informed MI의 방향을 이해하려면

[Physics-Informed Neural Networks for SAM Image Enhancement with a Novel Physics-Constrained Metric](https://doi.org/10.1109/ECTC51687.2025.00368)

- Self-supervised encoder–decoder에 acoustic-wave PDE loss를 결합했다.
- SSIM 0.4815, PSNR 69.66 dB, PCRS 약 10⁻⁸을 보고했다.
- 저자도 over-smoothing, fine-detail 손실, 계산비용과 real-time 한계를 인정한다.
- 실제 void·delamination의 precision, recall, POD 향상은 검증하지 않았다.

아이디어는 매우 중요하지만 현재 evidence로는 production-ready top 5보다 **비판적으로 꼭 읽을 방향성 논문**에 가깝다. 학습 loss와 PCRS가 유사한 wave residual을 공유하므로 독립 검증인지도 따져봐야 한다.

### 6.3 공정 역설계를 보려면

[Prediction of Cross-Section Images and Optimization of Processes with Neural Network](https://doi.org/10.1109/ECTC51687.2025.00298)

- Regression과 VAE로 process condition→cross-section image를 생성한다.
- Target shape와 constraint에서 recommended process condition을 역으로 제안한다.
- 수일의 시행착오를 수초 예측으로 바꾼다고 보고하지만 공개 초록에는 accuracy와 외부 실증 수치가 없다.

### 6.4 Virtual metrology를 보려면

- [Nanoindentation-Based Analysis of W2W Bond Strength Using Cohesive Zone Modeling and ML](https://doi.org/10.1109/ECTC51846.2026.00128): simulation-generated data와 ANN으로 bond strength를 추정한다.
- [TSV Stress Prediction via ML Based on EBSD Grain Microstructure](https://doi.org/10.1109/ECTC51846.2026.00230): 실제 EBSD grain과 anisotropic simulation으로 Si stress·KOZ를 예측한다.
- 두 연구 모두 중요한 방향이지만 공개 초록에 정량적인 external physical validation이 부족하다.

### 6.5 Top 5 4번의 필수 후속

[Efficiency Meets Fidelity: A Computational Paradigm for 3D X-Ray Imaging of HBM Packages](https://doi.org/10.1109/ECTC51846.2026.00242), ECTC 2026

- EDSR를 명시하고 limited-angle·sparse-projection scan의 projection 수와 sampling strategy를 변화시킨다.
- Background quality와 fine foreground structure를 분리하고 scan-level defect segmentation까지 평가한다.
- Background는 비교적 일관되게 개선되지만 미세구조와 defect recovery는 physical sampling에 크게 의존한다.
- 공개 초록에는 정확한 PSNR·SSIM·Dice·recall·latency 수치가 없다.

2025년 논문이 HVM 효과를 제시했다면, 이 논문은 **무엇을 덜 찍어도 되고 무엇은 반드시 물리적으로 획득해야 하는가**를 묻는다.

---

## 7. AI 기술별 도입 판단

| AI 기술 | 가장 잘 맞는 문제 | 강점 | 가장 큰 위험 | 도입 조건 |
|---|---|---|---|---|
| Supervised CNN/3D segmentation | 반복 형상과 충분한 label이 있는 AOI·XRM | 높은 자동화·정량화 | rare class miss, domain shift | defect-level recall, blind lot, human fallback |
| Semi/self-supervised learning | unlabeled scan은 많고 annotation이 비싼 HBM·SAM | label 비용 절감 | pseudo-label 오류 증폭 | small trusted validation set, confidence threshold |
| Synthetic data·generative model | 희귀 결함·nm alignment label 부족 | 넓은 조건 탐색 | unreal defect, simulator bias | real-vs-synthetic gap, destructive ground truth |
| Continual/domain learning | HBM 세대·scanner·recipe 변화 | 재학습 비용 절감 | catastrophic forgetting, silent drift | frozen benchmark, rollback, old/new class audit |
| Super-resolution | X-ray·SAM의 time–resolution trade-off | acquisition 부담 완화 | hallucination·over-smoothing | defect POD, sampling co-design, raw data 보존 |
| Physics-informed ML | 데이터 희소·물리 위반 위험 | plausible solution space 제한 | 틀린 physics·boundary condition을 강제 | independent physical metric, parameter sensitivity |
| Surrogate·virtual metrology | 파괴적·느린 CTQ, FEA acceleration | 빠른 추정·what-if | 적용범위 밖 extrapolation | uncertainty, reference audit, applicability domain |
| LSTM autoencoder | label 없는 degradation time series | 초기 이상 탐지 | operating-condition shift를 failure로 오인 | condition stratification, alarm calibration |
| LLM/RAG | 보고·검색·원인 후보 | analyst time 절감 | hallucinated root cause | evidence-grounded output, no auto disposition |

### 중요한 원칙

**AI 기술은 MI 항목보다 먼저 고르면 안 된다.** 먼저 measurand, defect size, 필요한 POD, takt time과 reference method를 정하고 그 정보 병목을 줄이는 AI를 고른다.

예를 들어 void inspection 문제에 LLM을 붙이는 것은 우선순위가 아니다. 먼저 XRM acquisition, segmentation, defect-level POD를 해결한 뒤 LLM은 검증된 결과를 요약해야 한다.

---

## 8. 실제 도입 로드맵

### 단계 0 — 측정 정의와 ground truth

- Defect taxonomy와 pass/fail 기준을 문서화한다.
- 연속 measurand와 categorical defect를 분리한다.
- Reference method, uncertainty, destructive correlation 방법을 정한다.
- Lot, wafer, die, coordinate, recipe, tool, model version을 연결하는 data schema를 만든다.

FOPLP 논문이 보여주듯 operator label이 흔들리면 모델 개선보다 먼저 ground truth가 무너진다.

### 단계 1 — Offline assisted inspection

- AI가 candidate defect와 measurement를 제안하고 사람이 승인한다.
- 기존 raw image·signal과 AI output을 함께 보존한다.
- Accuracy 대신 defect-level recall, false call, bias, MAE, 3σ를 본다.
- Rare defect와 edge case를 active-learning queue로 보낸다.

### 단계 2 — Inline·near-line advisory

- Independent lot, tool, product generation으로 blind validation한다.
- Takt time, uptime, compute latency와 data transfer를 포함한다.
- OOD, drift, calibration, rollback을 운영한다.
- AI가 실패하거나 confidence가 낮으면 conservative rule 또는 human review로 fallback한다.

### 단계 3 — Guarded process feedback

- AI output은 먼저 recipe recommendation으로만 사용한다.
- 공정 safety envelope와 hard limit는 rule-based로 유지한다.
- 추천 전후의 causal evidence와 실제 yield uplift를 A/B 또는 controlled DoE로 확인한다.
- Model update와 recipe change에 approval·audit trail을 둔다.

### 단계 4 — Closed-loop twin

다음 조건을 모두 만족할 때만 자동 correction을 고려한다.

- Bidirectional automated data flow.
- Traceable reference와 uncertainty.
- Defect/POD·GR&R·process capability 검증.
- Drift·cybersecurity·rollback.
- Human override와 fail-safe.

2026년 현재 공개 packaging 문헌의 대부분은 단계 1–2, 일부가 단계 3의 recommendation 수준이다. 단계 4를 이미 일반적인 산업 현실로 표현하는 것은 과장이다.

---

## 9. 논문을 평가할 때 사용할 체크리스트

### 9.1 Dataset

- 실제 production wafer/package인가, fabricated test vehicle인가, simulation-only인가?
- Train/validation/test가 wafer·lot 단위로 분리됐는가?
- 다른 scanner, reconstruction recipe, package generation이 포함됐는가?
- Defect 수와 class imbalance가 공개됐는가?

### 9.2 Ground truth

- Label은 operator judgment, AFM, SEM/FIB, destructive cross-section, e-test 중 무엇인가?
- Label uncertainty와 inter-operator agreement를 측정했는가?
- Synthetic data가 실제 defect physics와 signal transfer를 보존하는가?

### 9.3 Metric

- Classification accuracy만 보고하지 않았는가?
- Defect-level recall, precision, false escape, POD가 있는가?
- Metrology면 bias, MAE, 3σ, uncertainty, GR&R이 있는가?
- Image enhancement면 PSNR/SSIM 외에 downstream defect metric이 있는가?

### 9.4 Generalization

- Blind wafer·lot인가?
- Tool-to-tool, product-to-product, recipe-to-recipe transfer가 있는가?
- OOD와 drift를 검출하는가?
- Continual learning 후 old class 성능을 확인했는가?

### 9.5 Manufacturing value

- Scan acquisition, inference, report 시간을 분리했는가?
- Coverage, throughput, uptime과 operator time을 측정했는가?
- Yield uplift 또는 escape-cost 감소를 실제 공정에서 확인했는가?
- Recommendation인가, 자동 correction인가?

### 9.6 Generative AI와 LLM

- 생성 이미지와 raw measurement를 명확히 구분하는가?
- Hallucinated/missing feature를 defect ground truth로 검사했는가?
- LLM 문장이 source measurement와 coordinate를 인용하는가?
- Human sign-off 없이 pass/fail·root cause를 확정하지 않는가?

---

## 10. 권장 읽기 순서

### 전체 그림을 먼저 잡을 때

1. [Su et al., Volumetric Nondestructive Metrology for 3D Semiconductor Packaging](https://doi.org/10.1016/j.measurement.2023.114065)
2. [MAPT Roadmap 2.0, Chapter 10](https://srcmapt.org/chapter10/)
3. [Datta et al., Toward Digital Twins in 3D IC Packaging](https://doi.org/10.3390/electronics15081740)

### AI-MI의 발전을 시간순으로 볼 때

1. [Wang et al. 2023, Robust Detection, Segmentation, and Metrology of HBM 3D Scans](https://doi.org/10.3390/s23125470)
2. [Zhao et al. 2024, Full-Wafer Hybrid-Bond Defect CNN](https://doi.org/10.1109/ECTC51529.2024.00083)
3. [Chang et al. 2024, Continual Learning for 3D XRM](https://doi.org/10.1109/ECTC51529.2024.00314)
4. [Chang et al. 2025, HBM End-to-End AI Inspection](https://doi.org/10.1109/ECTC51687.2025.00161)
5. [Chang et al. 2025, FOPLP Overlay-Yield Prediction](https://doi.org/10.1109/ECTC51687.2025.00030)
6. [Yu et al. 2025, HBM X-Ray Super-Resolution](https://doi.org/10.1109/EPTC67330.2025.11392237)
7. [Timoney et al. 2026, VTS-ML Cu Recess](https://doi.org/10.1117/12.3091416)
8. [Chang et al. 2026, Moiré Deep-Learning Alignment](https://doi.org/10.1109/ECTC51846.2026.00207)
9. [Yu et al. 2026, Computational 3D X-Ray](https://doi.org/10.1109/ECTC51846.2026.00242)

### 실무 도입 담당자가 먼저 볼 때

1. VTS-ML Cu recess: reference→inline 확장과 blind validation.
2. 2024 full-wafer CNN: recall, operator time, human fallback.
3. FOPLP yield prediction: label standardization과 production workflow.
4. HBM end-to-end framework: 검사 시스템 architecture.
5. Computational X-ray: 장비 recipe와 AI를 함께 평가하는 법.

---

## 11. 최종 판단

### 11.1 AI가 가장 먼저 들어가야 할 MI

1. **HBM·microbump의 3D XRM 분석:** 데이터 양과 annotation 병목이 크고 AI의 정량 효과가 가장 많이 축적됐다.
2. **Hybrid-bond pre-bond surface와 Cu recess:** 결함 예방 가치가 크며 VTS-ML처럼 reference metrology를 고속 sampling으로 확장할 수 있다.
3. **Hybrid-bond alignment·overlay:** fine-pitch 수율에 직접 연결되고 physics-synthetic data가 label 부족을 해결할 수 있다.
4. **FOPLP die-shift·overlay yield:** 계측값을 실제 공정 결정을 앞당기는 예측으로 바꿀 수 있다.
5. **Warpage·stress·bond strength virtual MI:** 잠재가치는 크지만 simulation-to-real validation을 더 강화해야 한다.

### 11.2 2023–2026 변화의 본질

- 2023: **AI가 검사 영상을 읽는다.**
- 2024: **AI를 전수검사에 넣고 변화에 적응시킨다.**
- 2025: **AI가 부족한 label과 물리를 보완하고 공정 결정을 돕는다.**
- 2026: **AI가 센서·mark·sampling·reference metrology와 함께 측정 시스템을 구성한다.**

가장 중요한 전환은 더 큰 neural network가 아니다. **AI 결과를 실제 measurand, defect POD, reference traceability, process action과 연결하는 것**이다.

### 11.3 당장 경계할 과장

- Digital twin이라는 이름만으로 closed loop라고 판단하지 않는다.
- Super-resolution image를 raw physical evidence처럼 취급하지 않는다.
- LLM root-cause 문장을 계측값이나 확정 원인으로 쓰지 않는다.
- R²와 accuracy를 GR&R, uncertainty, defect POD의 대체물로 쓰지 않는다.
- 한 제품·한 scanner의 random split 성능을 양산 일반화로 부르지 않는다.

현재 가장 현실적인 도입은 **AI-assisted inspection → reference-linked virtual MI → drift-aware inline advisory → guarded process feedback**의 순서다.

---

## 12. 참고문헌

### Review·roadmap·산업 기준

1. Y. Su et al., [Volumetric Nondestructive Metrology for 3D Semiconductor Packaging: A Review](https://doi.org/10.1016/j.measurement.2023.114065), Measurement 225, 114065, 2024.
2. H. Meshki Zadeh et al., [Recent Progress in Structural Integrity Evaluation of Microelectronic Packaging Using SAM: A Review](https://doi.org/10.3390/s25247499), Sensors 25, 7499, 2025.
3. G. Datta et al., [Toward Digital Twins in 3D IC Packaging: A Critical Review of Physics, Data, and Hybrid Architectures](https://doi.org/10.3390/electronics15081740), Electronics 15, 1740, 2026.
4. [MAPT Roadmap 2.0, Chapter 10 — Manufacturing and Process Development Metrology](https://srcmapt.org/chapter10/).
5. [IRDS 2024 Metrology](https://irds.ieee.org/images/files/pdf/2024/2024IRDS_MET.pdf).
6. [2024 ECTC Special Session Report: Advancing Metrology for Next-Generation Microelectronics](https://tsapps.nist.gov/publication/get_pdf.cfm?pub_id=958598).
7. [NIST IR 8577, Semiconductors and Microelectronics Standards Working Group Annual Report for 2024](https://nvlpubs.nist.gov/nistpubs/ir/2025/NIST.IR.8577.pdf).

### 2023–2024 기반 논문

8. R. S. Pahwa et al., [3D Defect Detection and Metrology of HBMs Using Semi-Supervised Deep Learning](https://doi.org/10.1109/ECTC51909.2023.00161), ECTC 2023.
9. J. Wang et al., [Robust Detection, Segmentation, and Metrology of HBM 3D Scans Using an Improved Semi-Supervised Deep Learning Approach](https://doi.org/10.3390/s23125470), Sensors 23, 5470, 2023.
10. S. Raghavan et al., [A Methodology to Optimize Laser Dicing Parameters to Maximize Dicing Quality Through Machine Learning](https://doi.org/10.1109/ECTC51909.2023.00032), ECTC 2023.
11. [TrueAdapt — AI Based Maskless Patterning to Compensate for Die-Shift in FOWLP](https://doi.org/10.1109/ECTC51909.2023.00388), ECTC 2023.
12. O. Zhao et al., [Deep Convolution Neural Networks for Automatic Detection of Defects Which Impact Hybrid Bonding Yield](https://doi.org/10.1109/ECTC51529.2024.00083), ECTC 2024.
13. R. Chang et al., [A Unified and Adaptive Continual Learning Method for Feature Segmentation of Buried Packages in 3D XRM Images](https://doi.org/10.1109/ECTC51529.2024.00314), ECTC 2024.
14. S. Ghosh et al., [Demystifying Edge Cases in Advanced IC Packaging Inspection Through Novel Explainable AI Metrics](https://doi.org/10.1109/ECTC51529.2024.00388), ECTC 2024.

### 2025–2026 핵심·추가 논문

15. R. Chang et al., [Efficient Visual Inspection Framework of HBM Bumps with Generative and Deep Learning AI](https://doi.org/10.1109/ECTC51687.2025.00161), ECTC 2025.
16. J. Chang et al., [Yield Prediction Technology in FOPLP Lithography](https://doi.org/10.1109/ECTC51687.2025.00030), ECTC 2025.
17. Y. Yu et al., [An Efficient Data Augmentation and Semantic Segmentation Framework for 3D Defect Detection of HBMs](https://doi.org/10.1109/ECTC51687.2025.00277), ECTC 2025.
18. S. Ghosh et al., [Physics-Informed Neural Networks for SAM Image Enhancement](https://doi.org/10.1109/ECTC51687.2025.00368), ECTC 2025.
19. K. Motojima et al., [Prediction of Cross-Section Images and Optimization of Processes with Neural Network](https://doi.org/10.1109/ECTC51687.2025.00298), ECTC 2025.
20. Y. Yu et al., [AI-Powered Super-Resolution for Scalable and Efficient 3D X-Ray Inspection of 3D-Stacked HBMs](https://doi.org/10.1109/EPTC67330.2025.11392237), EPTC 2025.
21. P. Timoney et al., [Inline Monitoring of Hybrid Bonding Cu Recess with VTS-ML](https://doi.org/10.1117/12.3091416), Proc. SPIE 13981, 2026.
22. C.-C. Chang et al., [High-Precision Wafer-Level Bonding in Thin-3D: A Moiré Pattern and Deep-Learning Alignment Approach](https://doi.org/10.1109/ECTC51846.2026.00207), ECTC 2026.
23. Y. Yu et al., [Efficiency Meets Fidelity: A Computational Paradigm for 3D X-Ray Imaging of HBM Packages](https://doi.org/10.1109/ECTC51846.2026.00242), ECTC 2026.
24. Y. Ozdemir et al., [Nanoindentation-Based Analysis of W2W Bond Strength Using Cohesive Zone Modeling and ML](https://doi.org/10.1109/ECTC51846.2026.00128), ECTC 2026.
25. Z. Pan et al., [TSV Stress Prediction via ML Based on EBSD Grain Microstructure](https://doi.org/10.1109/ECTC51846.2026.00230), ECTC 2026.

---

## 조사 한계

- IEEE conference paper 상당수는 공개 초록과 author-uploaded manuscript만 확인 가능해, 비공개 본문의 dataset split과 세부 architecture를 완전히 재현하지 못했다.
- 2026 ECTC·SPIE 문헌은 매우 최신이어서 독립 재현과 citation-based 영향력 평가가 아직 불가능하다.
- 기업 저자 논문은 HVM relevance가 높지만 model·dataset disclosure가 제한적인 경우가 있다.
- 공개 수치는 각 test vehicle과 장비 조건의 결과이며 universal equipment specification으로 해석하면 안 된다.
- 본 보고서는 AI-MI의 기술·방법론 우선순위다. 실제 양산 control limit와 sampling plan은 제품 FMEA, customer requirement, MSA와 공정능력 자료로 결정해야 한다.
