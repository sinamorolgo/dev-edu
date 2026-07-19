# ECTC 2023·2024 Metrology & Inspection 관련 논문 전수 정리

> 조사 기준일: 2026-07-19
> MI의 의미: **Metrology & Inspection(계측·검사)**
> 범위: ECTC 2023·2024 공식 프로그램 전체 777개 발표와 IEEE DOI·공개 초록 색인을 대조한 결과

## 결론

| 연도 | 핵심 MI | MI 인접 특성평가·고장분석 | 합계 | 공개 초록으로 내용 확인 |
|---:|---:|---:|---:|---:|
| 2023 | 27 | 33 | 60 | 58/60* |
| 2024 | 29 | 36 | 65 | 62/65 |
| **합계** | **56** | **69** | **125** | **120/125** |

\* ECTC DOI에 직접 연결된 공개 초록은 119편이다. 2023 S41-21은 같은 연구진의 후속 SPIE 논문 공개 초록으로 내용을 보완했다. 나머지 5편은 공개 초록을 찾지 못해 제목 기반 설명임을 각 항목에 표시했다.

## 포함 기준

- **핵심 MI:** 주된 기여가 새 계측·검사 장비나 측정법, AOI/비파괴 영상, 결함 검출·국소화, failure analysis, in-situ/inline monitoring, overlay·alignment metrology 또는 검사 AI인 논문.
- **MI 인접:** 주된 기여는 재료·공정·신뢰성·RF/열 성능이지만, 정량 특성평가나 고장분석이 결론을 성립시키는 핵심 수단인 논문.
- ECTC에는 공식 `MI` 논문 태그가 없다. 따라서 여기서 `전수`는 위 기준을 명시적으로 적용해 전체 프로그램과 공개 초록을 감사했다는 뜻이다.

## 조사와 검증 방법

1. 2023 공식 프로그램 386건과 2024 공식 프로그램 391건, 총 777개 기술 발표의 제목·저자·소속·세션을 대조했다.
2. metrology, inspection, measurement, characterization, microscopy, X-ray/XRM, Raman, EBSD, defect/fault/failure, monitoring, overlay/alignment 등 제목 신호로 1차 후보를 만들었다.
3. Crossref의 해당 IEEE conference container에서 DOI를 대조해 두 해 모두 367건씩, 총 734건을 공식 프로그램 발표와 연결했다.
4. DOI 734건 전체를 공개 초록 색인으로 다시 감사했으며 733건의 초록을 확보했다. 제목 필터 밖에 있던 AFM·DIC·CSAM·AOI·PAS 등 초록 신호도 재검토했다.
5. 초록을 읽어 핵심 MI·인접군·오탐으로 분류하고, 초록 원문을 복사하지 않은 한국어 핵심 요약을 작성했다.

주요 출처: [ECTC 2023 공식 Final Program](https://ectc.net/wp-content/uploads/2025/09/73-ECTCFinal-Web.pdf), [ECTC 2024 공식 Final Program](https://ectc.net/wp-content/uploads/2025/07/74-ECTCFinal-Web.pdf), [ECTC IEEE Xplore conference archive](https://ieeexplore.ieee.org/xpl/conhome/1000248/all-proceedings), [Crossref REST API](https://api.crossref.org/), [Semantic Scholar Academic Graph API](https://api.semanticscholar.org/api-docs/graph).

## 두 해의 흐름

- **2023:** 워페이지·잔류응력·본딩 강도·오버레이처럼 기본 공정 변수를 더 싸고 빠르게 재는 새 시험법이 중심이다. 동시에 HBM 3D 결함 계측, AOI crack-stop 판정, THz 하드웨어 지문처럼 AI·보안 검사로 범위가 넓어졌다.
- **2024:** 계측이 공정 뒤 사후분석에서 공정 중 in-situ·inline 감시로 이동했다. 가열 AFM, Raman, SEM-EBSD, XPS, PAS, embedded stress sensor가 대표적이다.
- **공통 방향:** 단일 장비 결과보다 전기시험·비파괴 영상·단면분석·시뮬레이션을 상관시키는 흐름이 강하다. 검사 AI도 단순 분류에서 적은 라벨 학습, continual learning, XAI 신뢰도 평가로 발전했다.

## ECTC 2023

### 핵심 MI (27편)

1. **S05-02 — [Addressing sub-Micron Thermal Warpage: Industrial Application on Semiconductor Devices](https://doi.org/10.1109/ectc51909.2023.00037)**
   - 세션: Session 05 - Underfilling and Chip-Package-Interaction
   - 초록 핵심: 투명·반투명 광학 패키지도 별도 표면 처리 없이 서브마이크론 열 변형을 재도록 OCT 기반 워페이지 계측법을 제안했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/e3b60dde1e338b9e0f4033651380a24bded65baa)

2. **S08-01 — [A New Vibration Test Method for Automotive and Consumer Electronic Devices: Calibration and Fatigue Test](https://doi.org/10.1109/ectc51909.2023.00056)**
   - 세션: Session 08 - Novel Reliability Test Methods
   - 초록 핵심: 5개 시험소에서 가속도·변형률·피로 파손을 교차 비교해 자동차·소비자 전자기기용 진동 시험의 교정성과 재현성을 검증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/aefd0da5f705d332c227b4829247a8aab7ba3c31)

3. **S08-02 — [Magnetic Force-Based Measurement Technique to Investigate the Effect of Lead-Free Solder Intermetallic Compounds (IMC) on Interconnect Reliability](https://doi.org/10.1109/ectc51909.2023.00057)**
   - 세션: Session 08 - Novel Reliability Test Methods
   - 초록 핵심: 솔더볼에 소형 자석을 붙여 비접촉 하중을 가하는 저비용 측정법으로 IMC 두께 증가에 따른 접합 강도 저하를 정량화했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/3f0af6fc40e3df5832d1ed6502510448493dc640)

4. **S08-03 — [Residual Stress Measurement of Build-Up Layer in Silicon Wafers](https://doi.org/10.1109/ectc51909.2023.00058)**
   - 세션: Session 08 - Novel Reliability Test Methods
   - 초록 핵심: 두께·온도별 칩 워페이지 측정값을 유한요소 모델과 역대조해 빌드업층의 잔류응력과 유효 물성을 추정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/154057d4552d6db2326198a353fca5d3d627c748)

5. **S08-04 — [Chip Level Evaluation of Wafer-to-Wafer Direct Bonding Strength with Bending test](https://doi.org/10.1109/ectc51909.2023.00059)**
   - 세션: Session 08 - Novel Reliability Test Methods
   - 초록 핵심: 기존 DCB가 보기 어려운 웨이퍼 중앙부까지 평가하도록 칩 단위 3점 굽힘과 파괴역학 해석을 결합한 직접접합 강도 측정법을 만들었다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/092caf273ded81ad9a7bc60d8c233eb847a9fb5d)

6. **S08-05 — [In-Situ Observation of Microscale Crack-Tip Strain Field Evolution in Underfill with Different Toughening Agents via SEM-DIC Coupled Method](https://ectc.net/wp-content/uploads/2025/09/73-ECTCFinal-Web.pdf)**
   - 세션: Session 08 - Novel Reliability Test Methods
   - 초록 핵심: 제목 기준: SEM 안에서 DIC를 함께 사용해 강화제가 다른 언더필의 미세 균열 선단 변형률장을 실시간 관찰하는 방법을 다룬다.
   - 초록 출처: 공개 초록 미확보 — 공식 프로그램의 제목·저자 기준으로만 수록

7. **S08-07 — [A Predictive Metallographic Means to Identify the Relative Risk of Failure for Plated Micro Vias](https://doi.org/10.1109/ectc51909.2023.00062)**
   - 세션: Session 08 - Novel Reliability Test Methods
   - 초록 핵심: 도금 마이크로비아 단면의 금속조직 특징을 이용해 열사이클 이전에 상대적 파손 위험을 가려내는 예측형 분석 절차를 제안했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/e5640a204b63a43a4f5b15035632fd9d117a3c9a)

8. **S10-06 — [New Methodology Assessment of Copper Trace and Solder Joint Fatigue Failures in Board-Level Random Vibrations for Automotive Applications](https://doi.org/10.1109/ectc51909.2023.00075)**
   - 세션: Session 10 - Packaging Interconnects
   - 초록 핵심: 보드 무작위 진동에서 구리 배선과 솔더 조인트의 피로 파손을 분리·평가하고 시험과 해석을 연결하는 새 방법론을 검토했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/da9476183d22ad367398ac555f5e3e959897ae51)

9. **S12-06 — [A Novel Approach to Measure and Characterize Radiation Patterns of Antenna-in-Package](https://doi.org/10.1109/ectc51909.2023.00089)**
   - 세션: Session 12 - mm Wave Antenna-in-Package and Arrays
   - 초록 핵심: Antenna-in-Package의 방사 패턴을 실제 사용 조건에 가깝게 측정·특성화하기 위한 새로운 장치 구성과 보정 접근을 제시했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/2b9bafef91b2fdae5cdf864e0eceb291978953ac)

10. **S17-04 — [Substrate Copper Trace Crack Characterization and Simulation](https://doi.org/10.1109/ectc51909.2023.00122)**
   - 세션: Session 17 - Advanced Reliability Modelling and Characterization
   - 초록 핵심: 기판 구리 배선 균열의 형상과 원인을 단면·재료 분석으로 특정하고 시뮬레이션과 대조해 파손 거동을 설명했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/1c2530e1d1b85154badf7febc637fcb515f80e0f)

11. **S22-03 — [A Technical Review on State of the Art In-Plane and Out-of-Plane Deformation Measurement Techniques for Microelectronic Packages](https://doi.org/10.1109/ectc51909.2023.00305)**
   - 세션: Session 22 - Large Substrate Process Integration Challenges
   - 초록 핵심: 마이크로전자 패키지의 면내·면외 변형을 재는 대표 기법들의 원리, 분해능, 적용 한계와 선택 기준을 체계적으로 비교했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/f5bb41a3456eaa76834de5c3ee247250e9dd4c9a)

12. **S22-06 — [Package Warpage of Whole Strip Evaluation with Interface Analysis in the Flip-Chip Die Bonding Process](https://doi.org/10.1109/ectc51909.2023.00158)**
   - 세션: Session 22 - Large Substrate Process Integration Challenges
   - 초록 핵심: 플립칩 다이 본딩 공정에서 스트립 전체 워페이지를 측정하고 계면 구조·재료 요인과 연결해 공정 변형을 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/bf387c8afa33b5c2c77ec1dc745096e0c4961b5a)

13. **S23-02 — [3D Defect Detection and Metrology of HBMs Using Semi-Supervised Deep Learning](https://doi.org/10.1109/ectc51909.2023.00161)**
   - 세션: Session 23 - Next Generation Quantum, AI, and Secure System Design
   - 초록 핵심: 적은 라벨만으로 학습하는 반지도 딥러닝을 3D HBM 영상에 적용해 결함 검출과 치수 계측을 동시에 수행했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/282334fc2be49e5fafecdbed9ac1899e75edcc4c)

14. **S32-05 — [Improving Warpage Characterization of Large Wafers in Fan-Out Packaging Technology](https://doi.org/10.1109/ectc51909.2023.00227)**
   - 세션: Session 32 - Thermo-Mechanical Modelling and Characterization
   - 초록 핵심: 팬아웃 대구경 웨이퍼의 실제 열·공정 변형을 더 정확히 포착하도록 워페이지 측정과 모델 상관 절차를 개선했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/947c47f30cd981ec5dda1f952da196843c521fe7)

15. **S34-04 — [Critical Dimension Scatterometry as a Scalable Solution for Hybrid Bonding Pad Recess Metrology](https://doi.org/10.1109/ectc51909.2023.00240)**
   - 세션: Session 34 - Bonding Assembly - Novel Packaging, Process, and Characterization
   - 초록 핵심: 하이브리드 본딩 패드 리세스를 비파괴·고처리량으로 재기 위해 임계치수 산란계측을 적용하고 기준 계측과 상관성을 검증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/f3202e975401993d70bfd75126bd56e528222c3a)

16. **S38-01 — [Advanced Overlay Metrology for CIS Bonding Applications](https://doi.org/10.1109/ectc51909.2023.00278)**
   - 세션: Session 38 - Interactive Presentations 2
   - 초록 핵심: CIS 웨이퍼 본딩용 오버레이 타깃과 측정법을 평가해 생산 웨이퍼에서 1 nm 수준의 총측정불확도를 보고했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/18da24458a837095aa9c101335856529d400498e)

17. **S38-02 — [Implementation of New Robustness Assessment Methodology for Crack Stop Constructions](https://doi.org/10.1109/ectc51909.2023.00279)**
   - 세션: Session 38 - Interactive Presentations 2
   - 초록 핵심: 표준 AOI에 전용 binning 판정을 추가해 crack-stop 구성요소별 칩핑·박리 억제 성능을 자동 비교하는 방법을 만들었다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/afcb42aedd22efa695bf1843221ee4553ebebb93)

18. **S38-06 — [50 nm Overlay Accuracy for Wafer-to-Wafer Bonding by High-Precision Alignment Technologies](https://doi.org/10.1109/ectc51909.2023.00283)**
   - 세션: Session 38 - Interactive Presentations 2
   - 초록 핵심: 다점 정렬 측정과 스테이지·본딩파 제어를 최적화해 연속 웨이퍼 본딩에서 약 50 nm 오버레이 정확도를 입증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/fdcfc379252dfa057e735e97be647c4f79e6a8c4)

19. **S38-23 — [Robust Edge Coupling Probe Applied in Wafer-Level Optical Testing](https://doi.org/10.1109/ectc51909.2023.00300)**
   - 세션: Session 38 - Interactive Presentations 2
   - 초록 핵심: 좁은 트렌치에도 접근하는 돌출형 광섬유 배열 프로브를 설계해 웨이퍼 상태에서 에지 커플러의 광손실을 안정적으로 측정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/cfefedb944c40cdfae7070cb69153e36f9c9d177)

20. **S38-30 — [Reliability and Failure Analysis of Chip-to-Substrate Cu-Pillar Interconnections with Nanoporous-Cu Caps](https://doi.org/10.1109/ectc51909.2023.00060)**
   - 세션: Session 38 - Interactive Presentations 2
   - 초록 핵심: 나노다공성 구리 캡 접합을 열노화·전자이동 시험과 파손 단면 분석으로 추적해 나노 표면막에서 시작되는 새 고장 메커니즘을 찾았다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/5422fb1154d817f07bd4a3b458742c43f23c2b4e)

21. **S39-03 — [Extracting Anisotropic Permittivity of PCB Substrate from VNA Measurement on a Rectangular Stripline Resonator Loaded with a Via Array](https://doi.org/10.1109/ectc51909.2023.00310)**
   - 세션: Session 39 - Interactive Presentations 3
   - 초록 핵심: 비아 배열을 넣은 직사각 스트립라인 공진기의 VNA 측정으로 PCB 기판의 이방성 유전율을 추출하는 방법을 제안했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/d1a7397c6a3a0965ec7c6b208760e31aeef5eee4)

22. **S40-08 — [A Thin-Film Reconfigurable SiC Thermal Test Chip for Reliability Monitoring in Harsh Environments](https://doi.org/10.1109/ectc51909.2023.00223)**
   - 세션: Session 40 - Interactive Presentations 4
   - 초록 핵심: 히터와 RTD를 재구성할 수 있는 SiC 열 시험칩을 제작해 고온 전력사이클 중 접합부 열저항 변화를 in-situ로 감시했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/52e53e6182de5f7c8a33e3ec9c70640c8db91faa)

23. **S40-12 — [Assessment Methods for the Characterization of Flux Material Systems Toward Water Absorption](https://doi.org/10.1109/ectc51909.2023.00346)**
   - 세션: Session 40 - Interactive Presentations 4
   - 초록 핵심: 기존 SIR보다 초기 수분 흡착에 민감한 AC 임피던스와 EIS를 비교해 플럭스 잔사의 흡수성·ECM 위험을 비파괴 선별했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/605f6c0be8627d5cebc1810f2489919d0a817f1d)

24. **S41-14 — [A High Precision Analysis Method Based on Thermal Test Chip for Thermal Characteristics of Thermal Interface Materials](https://ectc.net/wp-content/uploads/2025/09/73-ECTCFinal-Web.pdf)**
   - 세션: Session 41 - Student Interactive Presentations
   - 초록 핵심: 제목 기준: 열 시험칩을 기준 열원·온도 센서로 사용해 열계면재의 열 특성을 고정밀 분석하는 방법을 다룬다.
   - 초록 출처: 공개 초록 미확보 — 공식 프로그램의 제목·저자 기준으로만 수록

25. **S41-17 — [FISHI: Fault Injection Detection in Secure Heterogeneous Integration via Power Noise Variation](https://doi.org/10.1109/ectc51909.2023.00377)**
   - 세션: Session 41 - Student Interactive Presentations
   - 초록 핵심: 칩렛의 전원 잡음 변화를 근접 센싱하고 하드웨어 ML로 정상 패턴과 비교해 런타임 전력 fault-injection 공격을 탐지했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/98ade06376875614e34223ea12897c42e5ae2cb9)

26. **S41-21 — [Fingerprint Extrication with Near-Field Terahertz Time-Domain Spectroscopy (THz-TDS) for IC Hardware Assurance](https://ectc.net/wp-content/uploads/2025/09/73-ECTCFinal-Web.pdf)**
   - 세션: Session 41 - Student Interactive Presentations
   - 초록 핵심: 제목과 동일 연구의 공개 후속 원문 기준: 근접장 THz-TDS 스펙트럼에서 IC 고유 물리 지문을 뽑아 위변조·식별에 활용했다.
   - 초록 출처: [동일 연구진의 후속 SPIE 공개 초록](https://doi.org/10.1117/12.3027511)

27. **S41-26 — [Characterization of Packaging, Electronic, and Photonic Materials at Cryogenic Temperatures Using a Multi-Angle Backscattering Mueller-Matrix Ellipsometer](https://doi.org/10.1109/ectc51909.2023.00386)**
   - 세션: Session 41 - Student Interactive Presentations
   - 초록 핵심: 상용 반사 테이프를 이용한 다각도 return-path Mueller-matrix ellipsometer를 구성해 20 K까지 박막·패키징 재료를 측정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/8678a068280573d02aba9af23241f8162ee11222)

### MI 인접 특성평가·고장분석 (33편)

1. **S02-03 — [Effect of Surface Roughness of Polymer Dielectric Materials on Resolution of Fine Line Features](https://doi.org/10.1109/ectc51909.2023.00017)**
   - 세션: Session 02 - High-Performance Packaging Materials
   - 초록 핵심: 3D 프로파일러와 AFM으로 저유전 폴리머의 길이척도별 거칠기를 재고 미세 RDL 선폭 형성 결과와 상관시켰다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/0a05ff243472c5cadc32170bea47b3d0e3cf6e3e)

2. **S03-02 — [Fine Pitch Die-to-Wafer Hybrid Bonding](https://doi.org/10.1109/ectc51909.2023.00023)**
   - 세션: Session 03 - Advancements in Copper/Silicon-Oxide Hybrid Bonding
   - 초록 핵심: 7 µm 피치 D2W 하이브리드 본딩을 전기저항·CSAM·단면 현미경으로 교차 검사해 정렬 수율과 보이드 결함도를 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/91c0f3e056475d939bfa84802c80ac538114d2ba)

3. **S04-04 — [A Methodology to Optimize Laser Dicing Parameters to Maximize Dicing Quality Through Machine Learning](https://doi.org/10.1109/ectc51909.2023.00032)**
   - 세션: Session 04 - Assembly and Manufacturing Process Enhancement
   - 초록 핵심: 레이저 다이싱 폭과 다이 강도를 반복 측정해 학습한 랜덤포레스트 대리모델로 다이싱 품질의 공정창을 최적화했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/a23626b24906c5e1c8ffa9f4236093cc766c435a)

4. **S05-03 — [Optimization of 2.2D Underfill Process by Novel Methodology and Direct Observation of Capillary Underfill Process](https://doi.org/10.1109/ectc51909.2023.00038)**
   - 세션: Session 05 - Underfilling and Chip-Package-Interaction
   - 초록 핵심: 모세관 언더필의 이동 전면을 in-situ 관찰하고 3D CAE 예측과 대조해 디스펜싱 대기시간을 줄였다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/f3dbe039035946ce5355ba82a9810a15b6eadd73)

5. **S08-06 — [Experimental Identification of the Failure Modes and Failure Mechanisms of Fiber to Waveguide Couplings Under Cyclic Tensile Loading](https://doi.org/10.1109/ectc51909.2023.00061)**
   - 세션: Session 08 - Novel Reliability Test Methods
   - 초록 핵심: 광섬유-도파로 결합부를 반복 인장하며 12채널 삽입손실을 연속 측정해 박리·미끄럼·섬유 파단의 고장 모드를 분리했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/fdc07799a66f6515d5bb7d9ae0be3d7575dcc2e9)

6. **S11-01 — [Electromechanical and Thermal Characterization of Printed Liquid Metal Ink on Stretchable Substrate for Soft Robotics Multi-Sensing Applications](https://doi.org/10.1109/ectc51909.2023.00077)**
   - 세션: Session 11 - Additive Manufacturing and Packaging for Flexible Electronics
   - 초록 핵심: 신축 기판에 인쇄한 액체금속 잉크의 변형-전기 응답과 열·기계 특성을 측정해 소프트 로봇 센싱 적합성을 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/df9bcc9c45b677f3e79044c3e2a6f85141f35266)

7. **S11-03 — [Additively Manufactured Flexible Material Characterization and On-Demand “Smart” Packaging Topologies for 5G/mmWave Wearable Applications](https://doi.org/10.1109/ectc51909.2023.00079)**
   - 세션: Session 11 - Additive Manufacturing and Packaging for Flexible Electronics
   - 초록 핵심: 적층제조한 유연 소재의 전기·기계 물성을 특성화하고 5G/mmWave 웨어러블 패키지 설계에 반영했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/564f1885f233612bc3ee8bc23e87e04c4030b67d)

8. **S13-06 — [Thermal and Mechanical Characterization of Embedded PTCQ Packaging Test Chip Die](https://doi.org/10.1109/ectc51909.2023.00096)**
   - 세션: Session 13 - Wafer/Panel-Level and Advanced Substrate Technologies
   - 초록 핵심: 내장 PTCQ 시험칩의 온도·하중 응답을 실험과 열기계 해석으로 비교해 패키지 물성을 검증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/8ede6709f980b9c639fd6ca265a3f828c91cb714)

9. **S14-01 — [Characterization of 300 mm Low Temperature SiCN PVD Films for Hybrid Bonding Application](https://doi.org/10.1109/ectc51909.2023.00098)**
   - 세션: Session 14 - Advances in Heterogeneous Integration Bonding Technology
   - 초록 핵심: 300 mm 저온 PVD SiCN 막의 조성·표면·접합 관련 물성을 측정해 하이브리드 본딩 적용 가능성을 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/d17dc656c97edd4467bbb70be1e37290aa27b2b0)

10. **S14-07 — [Micro-Structure Analysis of Solder Joint Using Room Temperature Laser-Assisted Bonding (LAB) Process](https://doi.org/10.1109/ectc51909.2023.00104)**
   - 세션: Session 14 - Advances in Heterogeneous Integration Bonding Technology
   - 초록 핵심: 상온 레이저 보조 본딩으로 만든 솔더 조인트의 미세조직과 계면을 현미경·성분 분석으로 비교했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/5ca124484f08891f8e0cca64e033c0e3fe2b3c45)

11. **S18-05 — [Scalable Fiber-Array-to-Chip Interconnections with Sub-Micron Alignment Accuracy](https://doi.org/10.1109/ectc51909.2023.00130)**
   - 세션: Session 18 - Advanced Photonic Packaging and Interconnect
   - 초록 핵심: 파이버 배열-포토닉칩 결합에서 서브마이크론 정렬 정확도를 달성하고 광결합 손실·조립 재현성으로 성능을 검증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/fec9547fe9dbdd2260e899dc0d3b52295bb61435)

12. **S18-06 — [Realization, Multi-Field Coupled Simulation and Characterization of a Thermo-Mechanically Robust LiDAR Front End on a Copper Coated Glass Substrate](https://doi.org/10.1109/ectc51909.2023.00131)**
   - 세션: Session 18 - Advanced Photonic Packaging and Interconnect
   - 초록 핵심: 구리 코팅 유리기판 LiDAR 프런트엔드의 열·기계 거동을 다중물리 해석과 실험 특성화로 대조했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/f0b25f570598ea2e28d5f5e660fde563fe95d36a)

13. **S20-07 — [Investigation of Acceleration Factors for SnAgCu-Bi Solder Joints Under Various Temperature Cycling Test Conditions](https://doi.org/10.1109/ectc51909.2023.00146)**
   - 세션: Session 20 - Automotive/Board-Level Reliability
   - 초록 핵심: 서로 다른 온도사이클 조건에서 SAC-Bi 솔더 조인트의 수명·파손 결과를 비교해 시험 가속계수를 도출했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/43038479c3bf459b006a657d130f4f70aa2bd9b3)

14. **S23-07 — [Characterizations of Indium Interconnects for 3D Quantum Assemblies](https://doi.org/10.1109/ectc51909.2023.00166)**
   - 세션: Session 23 - Next Generation Quantum, AI, and Secure System Design
   - 초록 핵심: 3D 양자 어셈블리용 인듐 인터커넥트의 접합 형상, 전기적 연결성과 저온 적용 특성을 측정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/1e64da755881b701a35fe06dbed984faa6806333)

15. **S26-06 — [Effects of Twin Boundary and Precipitates on Board Level Reliability in Sn-Ag-Cu (SAC) Solder Joints Through EBSD Analysis](https://doi.org/10.1109/ectc51909.2023.00186)**
   - 세션: Session 26 - Materials Reliability
   - 초록 핵심: EBSD로 SAC 솔더의 쌍정경계·석출물과 결정방향을 지도화해 보드 신뢰성 차이의 미세조직 원인을 분석했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/1e59f732fb5b7ed8a6bc33713597ae7f95ac8cc6)

16. **S27-01 — [0.5 µm Pitch Next Generation Hybrid Bonding with High Alignment Accuracy for 3D Integration](https://doi.org/10.1109/ectc51909.2023.00188)**
   - 세션: Session 27 - Next Generation Wafer-to-Wafer Copper Bonding
   - 초록 핵심: 0.5 µm 피치 하이브리드 본딩의 정렬 오차와 전기적 접속 결과를 측정해 초미세 3D 적층 공정을 검증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/84f4aebe897579f6a285fd010b53bc07ec58ffe6)

17. **S27-03 — [0.5 µm Pitch Wafer-to-Wafer Hybrid Bonding with SiCN Bonding Interface for Advanced Memory](https://doi.org/10.1109/ectc51909.2023.00190)**
   - 세션: Session 27 - Next Generation Wafer-to-Wafer Copper Bonding
   - 초록 핵심: SiCN 계면의 0.5 µm 피치 W2W 본딩을 전기 검사와 비파괴·단면 분석으로 확인해 메모리 적층 수율을 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/20afaece73783eddf4c6901d86fcd57941f9b197)

18. **S27-04 — [Fine-Pitch 30 µm Cu-Cu Bonding Using Electroless Nano-Ag](https://doi.org/10.1109/ectc51909.2023.00191)**
   - 세션: Session 27 - Next Generation Wafer-to-Wafer Copper Bonding
   - 초록 핵심: 무전해 나노은을 이용한 30 µm Cu-Cu 본딩 계면을 현미경·전기·강도 시험으로 특성화했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/7afc3b80dabe04ceb95deab2f28e83707d449ec4)

19. **S28-03 — [Alignment Through Thick Si Layer for High Resolution Patterning on Bonded Wafers with Tight Overlay Margin Using Immersion Lithography](https://doi.org/10.1109/ectc51909.2023.00197)**
   - 세션: Session 28 - Process Enhancements in 3D, FOWLP, and TSV Technologies
   - 초록 핵심: 두꺼운 Si를 통과하는 정렬과 immersion lithography를 결합해 본딩 웨이퍼의 미세 패턴 오버레이 마진을 검증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/30f61af46a99b15086bc8b9eb506fac814d71ea3)

20. **S29-07 — [Thermal Characterization of 3-D Stacked Heterogeneous Integration (HI) Package for High-Power Computing Applications](https://doi.org/10.1109/ectc51909.2023.00208)**
   - 세션: Session 29 - AI-based Prediction for Heterogeneous Integration and Advanced Packaging
   - 초록 핵심: 3D 적층 이종집적 패키지의 온도 분포와 열저항을 실험·모델로 특성화해 고전력 컴퓨팅 열설계를 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/7a1b66dd73627d9e0854283b318af0f426a98624)

21. **S30-02 — [Effects of High-Temperature Exposure on the Thermo-Mechanical Behavior of Epoxy Molding Compound and Warpage of Molded Wafers](https://doi.org/10.1109/ectc51909.2023.00210)**
   - 세션: Session 30 - Trends in Encapsulants and Low Dk/Df Dielectrics
   - 초록 핵심: 고온 노출 전후 EMC의 열기계 물성을 측정하고 몰드 웨이퍼 워페이지 변화와 연결했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/3d05911ff04b481f03d8528d7b2c03bdcc09e64f)

22. **S32-03 — [Investigation of Cure Kinetics of Advanced Epoxy Molding Compound Using Dynamic Heating Scan: An Overlooked Second Reaction](https://doi.org/10.1109/ectc51909.2023.00225)**
   - 세션: Session 32 - Thermo-Mechanical Modelling and Characterization
   - 초록 핵심: 동적 가열 스캔으로 고급 EMC의 경화 반응을 분해해 기존 분석에서 놓친 두 번째 반응과 공정 영향을 확인했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/1463cb66a3bc4ba2ffb70226b769118938765b3c)

23. **S32-07 — [Fan-Out Embedded Bridge with TSV(FO-EB-T) Package Characterization and Evaluation](https://doi.org/10.1109/ectc51909.2023.00229)**
   - 세션: Session 32 - Thermo-Mechanical Modelling and Characterization
   - 초록 핵심: FO-EB-T 패키지의 구조·열기계·전기 성능을 실측과 해석으로 종합 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/10ceaddd0bb9915c4d35ef3d111868d142b5c13f)

24. **S34-02 — [Contamination-Free Cu/SiCN Hybrid Bonding Process Development for Sub-µm Pitch Devices with Enhanced Bonding Characteristics](https://doi.org/10.1109/ectc51909.2023.00238)**
   - 세션: Session 34 - Bonding Assembly - Novel Packaging, Process, and Characterization
   - 초록 핵심: 오염을 줄인 서브마이크론 Cu/SiCN 본딩을 단면·계면·전기 특성으로 확인해 공정 품질을 검증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/f11554fe2668925956f410b2bd5f76b84b327da5)

25. **S34-05 — [A Study of SiCN Wafer-to-Wafer Bonding and Impact of Wafer Warpage](https://doi.org/10.1109/ectc51909.2023.00241)**
   - 세션: Session 34 - Bonding Assembly - Novel Packaging, Process, and Characterization
   - 초록 핵심: SiCN W2W 본딩에서 웨이퍼 워페이지가 접촉·접합 결과에 미치는 영향을 형상 측정과 본딩 평가로 분석했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/c0299978914268c57a6ef16c5dc001dfa355c816)

26. **S35-03 — [Development of PMUT Array Packaging from Characterisation Prototypes to Customer Samples](https://doi.org/10.1109/ectc51909.2023.00246)**
   - 세션: Session 35 - Packaging and Materials for Flexible Medical Technologies
   - 초록 핵심: PMUT 어레이 패키징을 시제품에서 고객 샘플 단계로 확장하며 음향·전기·조립 특성을 비교했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/e55b7aab3573167f2419607f554f4cff7d2b0123)

27. **S36-03 — [Embedded mm-Wave Chiplet Based Module Using Fused-Silica Stitch-Chip Technology: RF Characterization and Thermal Evaluation](https://doi.org/10.1109/ectc51909.2023.00253)**
   - 세션: Session 36 - RF, Heterogeneous, and Chiplet Modules
   - 초록 핵심: 융합실리카 stitch-chip 기반 mmWave 모듈의 RF 인터커넥트와 열 성능을 측정·해석했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/58e109abaa033af31e78718821b36ddbe80bd851)

28. **S37-01 — [Investigation of Cu-to-Cu and Oxide-to-Oxide Bonding](https://doi.org/10.1109/ectc51909.2023.00258)**
   - 세션: Session 37 - Interactive Presentations 1
   - 초록 핵심: Cu-Cu·oxide-oxide 직접접합 계면을 현미경·재료 분석과 접합 성능으로 비교해 공정 조건의 영향을 조사했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/40a7db6a488d37159d54ede2d6e667c8b0deadef)

29. **S37-14 — [Electrical Characterization and Modeling of 2-µm and 1.5-µm Line-and-Space High-Density Signal Wiring in Organic Interposer](https://doi.org/10.1109/ectc51909.2023.00270)**
   - 세션: Session 37 - Interactive Presentations 1
   - 초록 핵심: 유기 인터포저의 2 µm·1.5 µm L/S 배선을 제작해 20 GHz까지 전송손실을 측정하고 모델과 상관시켰다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/fe2783ff22d57813a1c87d308a379faeea4b7906)

30. **S38-09 — [Effect of Chip Metallization and Process Parameters on the Die Attach Properties of Direct Bonded Power Devices](https://doi.org/10.1109/ectc51909.2023.00286)**
   - 세션: Session 38 - Interactive Presentations 2
   - 초록 핵심: 서로 다른 칩 금속화의 직접접합부를 굽힘·SAM·SEM으로 검사하고 전력사이클 후 고장 위치를 분석했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/2df547d4de6f29bc87d4a9959db7066cfcb263a7)

31. **S40-06 — [Simulation, Prediction, and Verification of the Corrosion Behavior of Cu-Ag Composite Sintered Paste for Power Semiconductor Die-Attach Applications](https://doi.org/10.1109/ectc51909.2023.00341)**
   - 세션: Session 40 - Interactive Presentations 4
   - 초록 핵심: Cu-Ag 소결 페이스트의 갈바닉 부식 모델을 전기화학 측정으로 검증해 입자 조합·소결도별 부식 위험을 예측했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/0b6ed89531927699e9508fd436456d454e268410)

32. **S40-07 — [Thermal Characterization and Management of GaN-on-SiC High Power Amplifier MMIC](https://doi.org/10.1109/ectc51909.2023.00342)**
   - 세션: Session 40 - Interactive Presentations 4
   - 초록 핵심: GaN-on-SiC MMIC의 IR 열영상과 열해석을 상관해 DC·펄스 구동의 채널 온도와 열저항을 정량화했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/81af68db9fb39e136126ba810992873027ccf7ff)

33. **S41-02 — [Grain Orientation and Prediction of Thermal Shock Fatigue of Sn-3Ag-0.5Cu Solder Joints for Fan-Out Wafer Level Packaging](https://doi.org/10.1109/ectc51909.2023.00362)**
   - 세션: Session 41 - Student Interactive Presentations
   - 초록 핵심: 열충격 후 SAC305 솔더의 결정방향·서브그레인 진화를 EBSD로 추적하고 피로수명 모델과 연결했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/88226a52c740198d3b45e9f069287223bce92280)

## ECTC 2024

### 핵심 MI (29편)

1. **S04-03 — [Effect of Lamination Process-Induced Residual Stress on the CTE of Advanced Prepregs Before and After Solder Reflow Process](https://doi.org/10.1109/ectc51529.2024.00031)**
   - 세션: Session 04 - Reliability of Advanced Substrates and Interconnects
   - 초록 핵심: moiré-hole drilling으로 적층 프리프레그 잔류응력을 재고 DIC로 리플로 전후 치수·CTE 변화를 추적했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/5e5e458c85b9604f42e6379e034e029942e38dc9)

2. **S04-05 — [Fatigue-Fracture Propensity Measurement and Competing Risk Model for FCBGA Interfaces Under Sustained Humidity and Temperature Exposure](https://doi.org/10.1109/ectc51529.2024.00033)**
   - 세션: Session 04 - Reliability of Advanced Substrates and Interconnects
   - 초록 핵심: 장기 온습도 노출 중 여러 FCBGA 계면의 파괴인성·균열성장률을 측정해 경쟁위험 고장 모델을 구축했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/8fdabf28891c1c896bd37e0ec1f8a50e1f08654c)

3. **S04-07 — [Characterization and Sensitivity Analysis of Piezoresistive Stress Sensor for Thermal and Mechanical Loads and Implementation for In-Situ Health Monitoring of Solder Bumps](https://ectc.net/wp-content/uploads/2025/07/74-ECTCFinal-Web.pdf)**
   - 세션: Session 04 - Reliability of Advanced Substrates and Interconnects
   - 초록 핵심: 제목 기준: 열·기계 하중용 압저항 응력센서를 교정·민감도 분석한 뒤 솔더 범프의 in-situ 건전성 감시에 적용한다.
   - 초록 출처: 공개 초록 미확보 — 공식 프로그램의 제목·저자 기준으로만 수록

4. **S05-05 — [Silicon-Based Membrane Pressure Sensor for Inline Monitoring of Pressure and Hermeticity of Small-Volume Bonded Packages](https://doi.org/10.1109/ectc51529.2024.00040)**
   - 세션: Session 05 - Digital Healthcare: Wearable Sensors, and Flexible Electronics
   - 초록 핵심: Pt strain gauge가 달린 Si 멤브레인 압력센서를 제작·교정해 소형 밀봉 패키지의 압력과 누설을 인라인 감시했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/a32750e060a56cdd2e277ed2a5dc30d571c85258)

5. **S08-07 — [Development of Double Cantilever Beam Technique for Wafer-to-Wafer Bond Energy Measurement](https://doi.org/10.1109/ectc51529.2024.00062)**
   - 세션: Session 08 - Sub-Micron Scaling in Wafer-to-Wafer Hybrid Bonding
   - 초록 핵심: 시편 다이싱 영향과 성공률을 검토한 DCB 절차를 개발해 fusion·hybrid W2W 본딩 에너지를 정량 측정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/65cea230fe67a8cc019f2775ad4293478e2fc9f5)

6. **S11-05 — [Novel Approach for 3D Defect Detection and Metrology of HBMs Using Minimum Labeled Data](https://ectc.net/wp-content/uploads/2025/07/74-ECTCFinal-Web.pdf)**
   - 세션: Session 11 - Next-Generation Artificial Intelligence, Quantum Computing, and Secure Packaging
   - 초록 핵심: 제목 기준: 최소 라벨 데이터로 3D HBM 내부 구조의 결함 검출과 치수 계측을 함께 수행하는 학습법을 제안한다.
   - 초록 출처: 공개 초록 미확보 — 공식 프로그램의 제목·저자 기준으로만 수록

7. **S12-02 — [Development of Real-Time Thermal Monitoring of GaN-based Power Inverter Modules Using Digital Twin](https://doi.org/10.1109/ectc51529.2024.00081)**
   - 세션: Session 12 - Artificial Intelligence and Advanced Modeling Approaches
   - 초록 핵심: 1D Modelica·CFD·ROM을 결합한 디지털 트윈과 가상센서로 GaN 인버터 모듈의 칩 온도를 실시간 추정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/799a925102344dbce88c1fd20f230a2cc64a859f)

8. **S12-03 — [Creep Parameters for Solder Interconnects by Nanoindentation Inverse-FEA Method](https://doi.org/10.1109/ectc51529.2024.00082)**
   - 세션: Session 12 - Artificial Intelligence and Advanced Modeling Approaches
   - 초록 핵심: 나노인덴테이션 creep 시험과 inverse FEA를 결합해 미세 솔더의 Norton 물성 파라미터를 추정·검증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/29f646400a08c2b2d2e62ac089c73a5c473d86c1)

9. **S12-04 — [Deep Convolution Neural Networks for Automatic Detection of Defects Which Impact Hybrid Bonding Yield](https://doi.org/10.1109/ectc51529.2024.00083)**
   - 세션: Session 12 - Artificial Intelligence and Advanced Modeling Approaches
   - 초록 핵심: 전 웨이퍼 광학영상을 두 단계 CNN으로 판독해 하이브리드 본딩 결함을 96~97% 정확도로 검출·분류했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/725acb6d1fcf554f8c5c496594cdf3896f00d63e)

10. **S13-05 — [X-Ray Photoelectron Spectroscopy (XPS) Investigations to Monitor the Surface Chemistry During Palladium-Free Colloidal Copper Activation](https://doi.org/10.1109/ectc51529.2024.00091)**
   - 세션: Session 13 - Next-Generation Substrate Manufacturing Technologies
   - 초록 핵심: 연속 공정 단계마다 XPS를 측정해 Pd-free 콜로이드 Cu 활성화 표면의 산화상태와 공기 노출 안정성을 추적했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/56d174d8321557e0b95b57b2ff4a9f075a0dec65)

11. **S19-05 — [Methodologies for Characterization of W2W Bonding Strength](https://doi.org/10.1109/ectc51529.2024.00129)**
   - 세션: Session 19 - 3D Integration Copper-Copper Hybrid Bonding
   - 초록 핵심: W2W 본딩 강도 측정법들의 시편 준비, 균열 관찰, 해석식과 적용 범위를 비교하고 공정별 평가 절차를 제시했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/0749c63553363c509f75a6281a2cc62b18a8bf06)

12. **S20-02 — [Observation of Thermal Expansion Behavior of Nanotwinned-Cu/SiO2 & Regular-Cu/SiO2 Hybrid Structure Via In-Situ Heating AFM](https://doi.org/10.1109/ectc51529.2024.00131)**
   - 세션: Session 20 - Novel High-Density 3D & Thru-Via Structures and Processes
   - 초록 핵심: 가열 AFM으로 nanotwinned-Cu와 일반 Cu 하이브리드 구조의 나노높이·열팽창 변화를 in-situ 비교했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/f39670dd765874318acb5fe0c3251d0e8b57198b)

13. **S20-05 — [Thermo-Mechanical Reliability Analysis and Raman Spectroscopy Characterization of Sub-micron Through Silicon Vias (TSVs) for Backside Power Delivery in 3D Interconnects](https://doi.org/10.1109/ectc51529.2024.00134)**
   - 세션: Session 20 - Novel High-Density 3D & Thru-Via Structures and Processes
   - 초록 핵심: 서브마이크론 TSV의 열기계 응력을 Raman spectroscopy로 지도화하고 신뢰성 해석과 상관시켰다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/a9cf374aefd5b68112f473ed893907d462bd097a)

14. **S23-07 — [High-Throughput Characterization of Nanoscale Topography for Hybrid Bonding by Optical Interferometry](https://doi.org/10.1109/ectc51529.2024.00157)**
   - 세션: Session 23 - Novel Bonding Technology for Advanced Assembly Substrates and Integration
   - 초록 핵심: 광간섭계를 이용해 하이브리드 본딩 표면의 나노스케일 topography를 빠르게 측정하고 처리량·반복성을 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/264ed39453dbc2f8bbabcf451f55d00f1fa0f3bc)

15. **S24-03 — [Simulation and Metrological Applications for RDL Patterning Development of Glass Substrate](https://doi.org/10.1109/ectc51529.2024.00160)**
   - 세션: Session 24 - Advances on Flex and Redistribution Layer Technologies and Warpage
   - 초록 핵심: 유리기판 RDL 패터닝 개발에서 시뮬레이션과 계측 데이터를 연결해 선폭·형상 공정창을 정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/3fed6e19839d92cc28ce0f06098bc97375ae7fb8)

16. **S24-04 — [Monitoring of Wafer Thinning Induced In-Die Mechanical Stress With Embedded Sensors for Heterogeneous Integration](https://doi.org/10.1109/ectc51529.2024.00263)**
   - 세션: Session 24 - Advances on Flex and Redistribution Layer Technologies and Warpage
   - 초록 핵심: 내장 응력센서로 웨이퍼 박막화 과정의 die 내부 기계응력을 단계별로 감시했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/16a31c688b06905ef99581e9f6ef1cb7a28b5f2e)

17. **S30-02 — [Investigating Sintering Mechanism of 100 nm Ag Nanoparticles via In-Situ SEM Observation and Phase Field Simulation](https://doi.org/10.1109/ectc51529.2024.00198)**
   - 세션: Session 30 - Process and Hybrid Bonding Modeling and Characterization
   - 초록 핵심: 100 nm Ag 나노입자의 소결 중 neck 성장과 미세조직 변화를 in-situ SEM으로 보고 phase-field 해석과 비교했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/b03d39ab1086a721186fb50c855f88f35bce67e5)

18. **S30-07 — [Measurement of the Interfacial Strength of Thin Metal Film by Laser Spallation Method for Advanced Wafer Level Package](https://doi.org/10.1109/ectc51529.2024.00204)**
   - 세션: Session 30 - Process and Hybrid Bonding Modeling and Characterization
   - 초록 핵심: 레이저 spallation 하중과 파동 해석을 이용해 웨이퍼급 얇은 금속막 계면 강도를 정량 측정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/bad6e8d9aeb5d50061a7ec4fdc049df85136c21f)

19. **S32-03 — [Copper Microstructure Effect on Electromigration Investigated by In Situ SEM EBSD Technique](https://doi.org/10.1109/ectc51529.2024.00214)**
   - 세션: Session 32 - Advancement in Copper Hybrid Bonding Technologies Common to Multiple Applications
   - 초록 핵심: in-situ SEM-EBSD로 Cu 결정방향과 전자이동 손상을 동시 추적해 미세조직-수명 관계를 분석했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/886e995c618175b529d5c2ea9b06a4a46a8cdbae)

20. **S36-06 — [Heat Dissipation Measurement in Flip-Chip Package Using Microfabricated Temperature Sensors on Lid](https://doi.org/10.1109/ectc51529.2024.00245)**
   - 세션: Session 36 - Thermal Management and Cooling Solutions
   - 초록 핵심: 플립칩 패키지 lid에 미세온도센서를 제작해 열원별 방열량과 온도 분포를 직접 측정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/7e211268e39cb1345c69d4d9a7afabd43bd9e82c)

21. **S37-20 — [Method to Evaluate the Adhesion Distribution on Wafers](https://doi.org/10.1109/ectc51529.2024.00267)**
   - 세션: Session 37 - Thermo-mechanical Stress and Reliability Analysis for Materials in Future Packaging
   - 초록 핵심: 웨이퍼 전면의 접착력 분포를 위치별로 평가하는 시편·측정 절차를 제안해 국부 약접합을 지도화했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/c89437904db2361eec2a4f9900e92ecdb89f4071)

22. **S37-26 — [Automated Solder Joint Failure Mode Analysis Based on Dry and Pry Image Processing](https://doi.org/10.1109/ectc51529.2024.00274)**
   - 세션: Session 37 - Thermo-mechanical Stress and Reliability Analysis for Materials in Future Packaging
   - 초록 핵심: dry-and-pry 뒤 얻은 솔더 조인트 영상을 자동 처리해 파손 모드를 분류하고 수작업 FA를 줄였다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/0af018ad02fcb556b40f61495e59146143575ece)

23. **S38-21 — [A Novel Method for LPDDR5 DRAM Jitter Measurement Through De-Embedding](https://doi.org/10.1109/ectc51529.2024.00295)**
   - 세션: Session 38 - Photonics, mm-Wave Applications & Emerging Technologies
   - 초록 핵심: 패키지·보드 채널 효과를 de-embedding해 LPDDR5 DRAM의 실제 jitter를 분리 측정하는 방법을 제안했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/063e8864e95b0aff7e6556f2417976ae2dd3ef82)

24. **S39-01 — [A Novel Detection Applied on Micro Defect in Bump Interface for 2.5DIC Package](https://doi.org/10.1109/ectc51529.2024.00301)**
   - 세션: Session 39 - Bonding Process and Analysis in Next-generation Interconnects
   - 초록 핵심: 기능검사로 찾지 못한 2.5DIC 마이크로범프 결함을 전기 fault isolation, micro-probing, FIB·성분분석 순으로 국소화했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/6243eb0286eac15cac180a6d67cce4c305f2d65c)

25. **S39-14 — [A Unified and Adaptive Continual Learning Method for Feature Segmentation of Buried Packages in 3D XRM Images](https://doi.org/10.1109/ectc51529.2024.00314)**
   - 세션: Session 39 - Bonding Process and Analysis in Next-generation Interconnects
   - 초록 핵심: 3D XRM 패키지 영상에서 이전 데이터를 다시 쓰지 않고 새 결함 클래스를 학습하는 continual segmentation으로 검사 확장 비용을 낮췄다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/874ae15d5758ce0096b09f7c57febf3181c41c19)

26. **S39-22 — [Analysis of Vacancies in Wafer-Bonding Interface Via Positron Annihilation Lifetime Spectroscopy](https://doi.org/10.1109/ectc51529.2024.00324)**
   - 세션: Session 39 - Bonding Process and Analysis in Next-generation Interconnects
   - 초록 핵심: positron annihilation lifetime spectroscopy로 본딩 계면의 미세 vacancy/gap 분포를 검출해 수분과 접합강도 형성 메커니즘을 설명했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/32d38de627a477db0ba2479b719b4c26003c31e9)

27. **S40-21 — [Overlay Challenges of Extremely Large Exposure Field, Fine Resolution Lithography Due to Alignment Solution Errors and a Solution Using Early Zone Corrections in Advanced IC Substrates](https://doi.org/10.1109/ectc51529.2024.00353)**
   - 세션: Session 40 - Materials, Manufacturing and Assembly Techniques in Advanced Packaging Solutions
   - 초록 핵심: 대면적 미세 RDL 노광의 정렬해 오차를 영역별로 분석·보정하는 early-zone correction으로 오버레이를 개선했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/63590a19674e97f297b8557ea432a0a428f1733e)

28. **S41-06 — [Fabrication and Testing of In-Line Structures for Non-Destructive Study of Solder Electromigration: Applications to SnBi Low Temperature Solder](https://doi.org/10.1109/ectc51529.2024.00368)**
   - 세션: Session 41 - Student Posters
   - 초록 핵심: 단면 절단 없이 반복 열노화·전자이동을 관찰할 수 있는 in-line SnBi 시험구조를 제작해 Bi 편석 속도를 측정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/574dbec0c414a87c2b52f0f5584ffe1862ecf86d)

29. **S41-27 — [Demystifying Edge Cases in Advanced IC Packaging Inspection Through Novel Explainable AI Metrics](https://doi.org/10.1109/ectc51529.2024.00388)**
   - 세션: Session 41 - Student Posters
   - 초록 핵심: 첨단 패키지 검사에서 XAI가 제시하는 이상 근거를 평가할 표준 지표를 제안해 드문 edge case의 설명 신뢰도를 다뤘다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/7a392ccc12346489d035519408c14d56df47625b)

### MI 인접 특성평가·고장분석 (36편)

1. **S03-07 — [Characterization of QSFP and OSFP CPO ELS Modules Employing an 8-channel CWDM TOSA in Practical Air-Cooling Conditions](https://doi.org/10.1109/ectc51529.2024.00028)**
   - 세션: Session 03 - Co-Packaged Optics
   - 초록 핵심: 8채널 CWDM TOSA를 넣은 QSFP·OSFP 외부광원 모듈의 온도·풍량별 소비전력과 광출력을 측정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/c918dbf9873cb729201b3c5b6f0da73adc5025a5)

2. **S04-06 — [Evaluation of Vapor Pressure Induced Debonding Failure in Fan-Out Package Under Reflow Condition](https://doi.org/10.1109/ectc51529.2024.00034)**
   - 세션: Session 04 - Reliability of Advanced Substrates and Interconnects
   - 초록 핵심: 4점 굽힘으로 Si-underfill 계면 인성을 재고 수분 증기압·팽윤·열응력별 debond 구동력을 비교했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/245280b0491b4a062020c7556302aeae708c6010)

3. **S06-07 — [Prediction of Moisture Absorption Characteristics Under Normal/Accelerated Preconditioning Condition in Multi-Chip Packages](https://doi.org/10.1109/ectc51529.2024.00048)**
   - 세션: Session 06 - Thermal-Mechanical Reliability Simulations
   - 초록 핵심: 4단·16단 멀티칩 패키지의 시간별 흡습량을 실험·확산 해석으로 대조해 가속 전처리 등가시간을 구했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/5a95ea707545f9bf43feffd9add0b8fd1a33f420)

4. **S09-07 — [Process Development and Characterization of Ru-Based UBM for In Bumps Integration for Quantum Computing Applications](https://doi.org/10.1109/ectc51529.2024.00068)**
   - 세션: Session 09 - Advanced Processes for Chip Stacking
   - 초록 핵심: Ru UBM 위 인듐 범프의 도금·식각 공정을 형태·계면·전기 분석으로 특성화했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/2fa278a3c50ee47988179620bb60e10ffcce68fe)

5. **S10-07 — [D2W Hybrid Bonding System Achieving High-Accuracy and High-Throughput With Minimal Configurations](https://doi.org/10.1109/ectc51529.2024.00074)**
   - 세션: Session 10 - Novel 3D Integration and Hybrid Bonding Solutions
   - 초록 핵심: 2200 UPH·100 nm 정렬 D2W bonder의 접합을 PAS, DCB, Kelvin/daisy-chain 측정으로 검증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/b791e580af646e72ea3cc9d379c0d14116e0739a)

6. **S12-05 — [Experimentally Validated Thermal Modeling Prediction for BEOL and BSPDN Stacks](https://doi.org/10.1109/ectc51529.2024.00084)**
   - 세션: Session 12 - Artificial Intelligence and Advanced Modeling Approaches
   - 초록 핵심: BEOL·BSPDN 열전달 모델을 시험차량 측정과 대조해 나노-마이크로 스케일 열저항 예측 정확도를 검증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/5436585ce0d844a4ed3dcbaefb10f130031f8e69)

7. **S13-06 — [Development of Glass Core Substrate With the Stress Analysis, Transmission Characteristics and Reliability](https://doi.org/10.1109/ectc51529.2024.00093)**
   - 세션: Session 13 - Next-Generation Substrate Manufacturing Technologies
   - 초록 핵심: 여러 TGV 구조의 유리 코어 기판을 응력·전송·신뢰성 측정으로 종합 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/412e53ac250cad64255cfd2641fee9e7efda31fa)

8. **S16-01 — [Structural Characterization of 2.5D System in Package Combined With High Bandwidth Memory for Enhanced Quality and Reliability](https://doi.org/10.1109/ectc51529.2024.00108)**
   - 세션: Session 16 - Reliability of High-Density and High-Power Packages
   - 초록 핵심: HBM을 결합한 2.5D SiP의 내부 구조와 조립 품질을 3D 구조 분석·신뢰성 시험으로 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/91e7f8d679594afdd600f4a9dbb46d0218cbeeb2)

9. **S16-04 — [Fusing Current Characterization of Various Cu RDL Designs in Wafer Level Packages](https://doi.org/10.1109/ectc51529.2024.00249)**
   - 세션: Session 16 - Reliability of High-Density and High-Power Packages
   - 초록 핵심: 여러 Cu RDL 설계의 전류 집중과 fusing 한계를 전기 시험·열관찰로 비교했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/80ab94cfe8f7627ae95c632c6be060b9fb9bd4b2)

10. **S18-06 — [RF Modelling and Characterization of TSVs and Inductive Links of Hybrid Bonded Devices](https://doi.org/10.1109/ectc51529.2024.00123)**
   - 세션: Session 18 - Radio Frequency Antenna-in-Package and Component Design
   - 초록 핵심: 하이브리드 본딩 TSV와 유도 결합 구조의 RF S-parameter를 측정하고 등가모델과 상관시켰다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/f3c33642a500904f33dcf3d129853334433f2527)

11. **S21-03 — [Temperature-Dependent Dielectric Characterization of Low Loss Thin Film Polymers up to Sub-THz Bands](https://doi.org/10.1109/ectc51529.2024.00139)**
   - 세션: Session 21 - Innovations in Polymer Packaging Materials
   - 초록 핵심: 저손실 박막 폴리머의 유전율·손실을 온도별·sub-THz 대역별로 측정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/29211b7dce6498db49ab67543491c0138e069e78)

12. **S22-05 — [Physical-Based Verification of High-Speed Channel Crosstalk and Correlation with BER Measurements](https://doi.org/10.1109/ectc51529.2024.00148)**
   - 세션: Session 22 - Signal & Power Integrity for Advanced Packages and Systems
   - 초록 핵심: 고속 채널 crosstalk 모델을 물리 시험차량과 BER 측정으로 검증해 상관 오차를 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/04abcc83dc14450c273836c4accaedfd6563c4fa)

13. **S24-06 — [Optimized Simulation Methodology of Warpage and Localized Stress Hotspot Prediction for Assembly Risk Assessment](https://doi.org/10.1109/ectc51529.2024.00162)**
   - 세션: Session 24 - Advances on Flex and Redistribution Layer Technologies and Warpage
   - 초록 핵심: 워페이지 측정·해석 상관을 바탕으로 조립 중 국부 응력 hotspot과 위험 부위를 빠르게 예측했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/2c47ddfa651494cc43c4b7d982c75a0af5332b31)

14. **S25-02 — [High Power Thermal Test Vehicle With 2-Phase Cooling for AI Datacenters, 5G RAN, and EDGE Compute Nodes](https://doi.org/10.1109/ectc51529.2024.00165)**
   - 세션: Session 25 - High-Performance Computing, Design Challenges, and Solutions
   - 초록 핵심: 고열유속 AI·5G 장치의 2상 냉각을 검증할 고전력 열 시험차량을 설계하고 온도·압력 응답을 계측했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/6a1a15456abf0d5c29ebf3bf9a8006614c226eeb)

15. **S25-03 — [Block Level and Package Level Thermal Assessment for Back Side Power Delivery Network](https://doi.org/10.1109/ectc51529.2024.00166)**
   - 세션: Session 25 - High-Performance Computing, Design Challenges, and Solutions
   - 초록 핵심: backside power delivery 구조의 블록·패키지 수준 온도와 열저항을 평가해 방열 병목을 비교했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/ec71c6ccedf70ebd77e9f2ac242735edc54092fc)

16. **S27-03 — [Reliability Analysis of Cu Sintered Die-Attach for SiC Power Devices: Mechanical, Electrical, and Thermal Evaluation](https://doi.org/10.1109/ectc51529.2024.00180)**
   - 세션: Session 27 - Advanced Die Bond and Board Level Reliability
   - 초록 핵심: SiC 전력소자의 Cu 소결 die-attach를 기계·전기·열 시험과 파손 분석으로 종합 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/052d0a3570f5ee9f334a7f67187be1dd1418fc87)

17. **S28-01 — [Fiber Array Attach for Co-Packaged Optics: High-Volume Production Process Control and Performance](https://doi.org/10.1109/ectc51529.2024.00185)**
   - 세션: Session 28 - Optical Interconnections
   - 초록 핵심: CPO 파이버 배열 접합의 대량생산 공정제어 항목과 광결합 성능·정렬 수율을 검증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/9fd9c641b42f25a1375bb7e76c48818ae00d2496)

18. **S28-04 — [High Power Performance Assessment of Low-Loss Spot Size Converter based on Self-Aligned Passive Fiber Attach Process](https://doi.org/10.1109/ectc51529.2024.00188)**
   - 세션: Session 28 - Optical Interconnections
   - 초록 핵심: self-aligned passive fiber attach를 적용한 저손실 spot-size converter의 고광출력 성능과 안정성을 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/01c7fce58ae91bcdfcc686d975e5102475593b66)

19. **S28-06 — [Characterization of 224 Gbps/lambda Interconnects in Co-Packaged Optics for Hyperscale Data Centers and AI/ML Clusters](https://doi.org/10.1109/ectc51529.2024.00316)**
   - 세션: Session 28 - Optical Interconnections
   - 초록 핵심: 224 Gbps/lambda CPO 인터커넥트의 광·전기·열 특성을 데이터센터 조건에서 측정했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/36435580276ba545288c9c7d468e9d185460aa26)

20. **S30-04 — [Fan-Out Embedded Bridge Structure for Co-Packaged Optics Characterization and Evaluation](https://doi.org/10.1109/ectc51529.2024.00201)**
   - 세션: Session 30 - Process and Hybrid Bonding Modeling and Characterization
   - 초록 핵심: CPO용 fan-out embedded bridge 구조의 조립 정밀도와 광·전기 성능을 특성화했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/d81fbfbd7cb33cf58299bf0f0fe373660f0a352b)

21. **S31-05 — [Analysis of Thin Flip Chip Chip-Scale Package Warpage Causes and Variations](https://doi.org/10.1109/ectc51529.2024.00209)**
   - 세션: Session 31 - Advances in Flip Chip and Chip Scale Packages
   - 초록 핵심: 얇은 FCCSP의 위치·공정별 워페이지를 측정해 주요 변동 원인과 상관 요인을 분석했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/06ca38e56d15689dccc7c0c9aafc6cc0d93b7ca8)

22. **S32-01 — [A Microstructural Investigation of Sub-1 µm Copper Bonding Contact Structures in Die-to-Wafer Hybrid Bonding](https://doi.org/10.1109/ectc51529.2024.00212)**
   - 세션: Session 32 - Advancement in Copper Hybrid Bonding Technologies Common to Multiple Applications
   - 초록 핵심: 서브-1 µm D2W Cu 접촉 구조의 단면과 결정립·계면을 미세조직 분석해 접합 상태를 평가했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/bba695c57500d07c6f0bfb88d84b5fc9954e7239)

23. **S35-05 — [Correlation of Mechanical and Microstructural Evolutions in Lead Free Solders Subjected to Various Thermal Exposures](https://doi.org/10.1109/ectc51529.2024.00237)**
   - 세션: Session 35 - Reliability and Current Stressing of Solder Interconnections
   - 초록 핵심: 열노출에 따른 무연솔더의 인장 물성·결정립 변화를 측정해 기계 열화와 미세조직 진화를 연결했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/2d9f123bade668bf81eaa7278d6f4616ffd25b05)

24. **S35-06 — [Pad Cratering and Pin Pull Strength for Large BGA and Connectors - How Are They Correlated?](https://doi.org/10.1109/ectc51529.2024.00238)**
   - 세션: Session 35 - Reliability and Current Stressing of Solder Interconnections
   - 초록 핵심: 대형 BGA·커넥터에서 pad cratering과 pin-pull 강도를 함께 측정해 두 시험 지표의 상관성을 검토했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/9546357b5e3e0985a500de2dddc4501a18452f97)

25. **S37-12 — [Electrical Characterization and Reliability Studies of Nano-TSV](https://doi.org/10.1109/ectc51529.2024.00258)**
   - 세션: Session 37 - Thermo-mechanical Stress and Reliability Analysis for Materials in Future Packaging
   - 초록 핵심: nano-TSV의 저항·누설과 스트레스 신뢰성 결과를 측정해 구조·공정별 열화를 비교했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/feed10c45097e28ee5ba1461f8973c1b2205bffc)

26. **S37-24 — [Study of Damage Development in Under-Bump Interconnects by Thermo-Mechanical Stress in Package Interconnects](https://doi.org/10.1109/ectc51529.2024.00272)**
   - 세션: Session 37 - Thermo-mechanical Stress and Reliability Analysis for Materials in Future Packaging
   - 초록 핵심: 열기계 하중 중 under-bump 인터커넥트 손상 진전을 단면·영상 분석으로 추적했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/5ea7ab89548f862845328a066dbdd567db1cabe4)

27. **S38-03 — [Quantifying Uncertainties in the Correlation of Simulations and Measurements Using the IEEE EPS Packaging Benchmark Suite](https://doi.org/10.1109/ectc51529.2024.00277)**
   - 세션: Session 38 - Photonics, mm-Wave Applications & Emerging Technologies
   - 초록 핵심: IEEE EPS 패키징 benchmark에서 시뮬레이션-측정 상관의 불확도 원인을 정량화했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/522a4d8699bb6e1610e1d459ad325eb02cc3f9a1)

28. **S38-20 — [Comprehensive Socket Characterization and Correlation for High-Speed Interface Testing System](https://doi.org/10.1109/ectc51529.2024.00294)**
   - 세션: Session 38 - Photonics, mm-Wave Applications & Emerging Technologies
   - 초록 핵심: 고속 인터페이스 시험용 소켓의 접촉·S-parameter를 종합 측정하고 모델·시스템 시험과 상관시켰다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/870088b7037f059f426e33c92b4396094101ba48)

29. **S39-06 — [Influence of Heat Treatment on the Quality of Die-to-Wafer Hybrid Bond Interconnects](https://doi.org/10.1109/ectc51529.2024.00306)**
   - 세션: Session 39 - Bonding Process and Analysis in Next-generation Interconnects
   - 초록 핵심: D2W 하이브리드 본딩 열처리 온도별 Cu 계면을 SEM·EBSD·IR로 비교해 접합 폐쇄와 결정방향 변화를 확인했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/f8628b220e93b77a018f3666d7b1ce94ee95345a)

30. **S40-01 — [Characterization of Warpage of Ultra-Low-K Dielectric Materials and Correlation With Modulus and Coefficient of Thermal Expansion](https://doi.org/10.1109/ectc51529.2024.00332)**
   - 세션: Session 40 - Materials, Manufacturing and Assembly Techniques in Advanced Packaging Solutions
   - 초록 핵심: 초저유전 폴리머층의 워페이지를 측정해 탄성률·CTE·표면거칠기와 미세 RDL 수율의 관계를 분석했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/4c8c06d4624f3e46a7412ffa042a54894e88291b)

31. **S40-04 — [Mechanical Characterization and Modeling of iSAC Lead-Free Solder](https://doi.org/10.1109/ectc51529.2024.00335)**
   - 세션: Session 40 - Materials, Manufacturing and Assembly Techniques in Advanced Packaging Solutions
   - 초록 핵심: iSAC 솔더의 온도·변형률속도별 인장 데이터를 측정해 Anand 파라미터를 추출하고 패키지 해석에 적용했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/b5a21a4c4a92e8692d8f7ba3479f69db98554788)

32. **S40-05 — [Novel SiO 2 Cables With Edge Launch Connectors for High Temperature RF Measurements](https://doi.org/10.1109/ectc51529.2024.00336)**
   - 세션: Session 40 - Materials, Manufacturing and Assembly Techniques in Advanced Packaging Solutions
   - 초록 핵심: 600°C용 SiO2 케이블·edge-launch connector를 제작해 반복 고온 노출 전후 RF 측정 성능을 검증했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/2d61be6e23fdc8baab47da46a537d0d6317eaa58)

33. **S40-20 — [Effect of Material Aging on the Reliability of an Automotive BGA Device Under Temperature Cycling Test Conditions](https://doi.org/10.1109/ectc51529.2024.00352)**
   - 세션: Session 40 - Materials, Manufacturing and Assembly Techniques in Advanced Packaging Solutions
   - 초록 핵심: 자동차 BGA의 장기 온도사이클 전후 재료 물성과 균열을 비교해 산화 노화가 파손의 주원인임을 분석했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/5c72c82a9e3333159fb91a6f5842985476d4ffd8)

34. **S40-28 — [Panel Level Plasma Etching Characteristics for Advanced Packaging](https://ectc.net/wp-content/uploads/2025/07/74-ECTCFinal-Web.pdf)**
   - 세션: Session 40 - Materials, Manufacturing and Assembly Techniques in Advanced Packaging Solutions
   - 초록 핵심: 제목 기준: 첨단 패키징용 패널급 플라즈마 식각의 공정 특성과 균일도를 평가한다.
   - 초록 출처: 공개 초록 미확보 — 공식 프로그램의 제목·저자 기준으로만 수록

35. **S41-08 — [Manufacturing and Characterization of Planar Transformers as Molded Interconnect Device Technology Component for an Industrial Production](https://doi.org/10.1109/ectc51529.2024.00370)**
   - 세션: Session 41 - Student Posters
   - 초록 핵심: 사출성형 MID 변압기를 제작해 인덕턴스·결합계수를 측정하고 CT로 ferrite core 균열을 확인했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/5a8eb30dffcabfeb79f3dbf6f588a8f155c151b1)

36. **S41-23 — [Creep Properties of SAC305 Solder Specimens that Mimic the Microstructures of a Micro Solder Ball: Measurement and BLR Prediction](https://doi.org/10.1109/ectc51529.2024.00384)**
   - 세션: Session 41 - Student Posters
   - 초록 핵심: 마이크로 솔더볼과 유사한 SAC305 시편을 만들어 결정립·IMC를 확인하고 creep 측정과 BLR 수명예측 절차를 제시했다.
   - 초록 출처: [Semantic Scholar 공개 초록 색인](https://www.semanticscholar.org/paper/561d1df7cc37a2652609cf1738a44d39f81ab192)

## 제목 키워드 오탐으로 제외한 대표 발표

아래 항목은 `image`, `monitoring`, `sensor`, `measurement` 같은 단어 때문에 자동 후보에 들기 쉽지만, 초록과 제목의 실제 목적이 semiconductor process metrology/inspection과 달라 제외했다.

- **2023-S07-05 — [Integrating Chiplets Using Chips First Ultra-High-Density Fan-Out with Maskless Laser Direct Imaging and Adaptive Patterning for High Performance Computing](https://doi.org/10.1109/ectc51909.2023.00053)**
  - 제외 이유: laser direct imaging은 RDL 노광·패터닝 공정이며 검사 영상이 아니다.
- **2023-S28-02 — [Exploring Capabilities of Maskless Lithography for Dual–Image Exposure in FO WLP](https://doi.org/10.1109/ectc51909.2023.00196)**
  - 제외 이유: dual-image exposure는 lithography 노광 공정이며 계측·검사가 아니다.
- **2023-S28-04 — [Recent Progress in the Development of High-Density TSV for 3-Layers CMOS Image Sensors](https://doi.org/10.1109/ectc51909.2023.00198)**
  - 제외 이유: CMOS image sensor 제품 공정 개발이며 inspection imaging이 아니다.
- **2023-S37-02 — [Doping-Selective Etching of Silicon for Wafer Thinning in the Fabrication of Backside-Illuminated Stacked CMOS Image Sensors](https://doi.org/10.1109/ectc51909.2023.00259)**
  - 제외 이유: backside-illuminated image sensor용 식각 공정이며 검사 논문이 아니다.
- **2023-S39-25 — [The Performance and Reliability of Screen-Printed Flexible Multilayer Leads for Wearable Vital Sign Monitoring Devices](https://doi.org/10.1109/ectc51909.2023.00332)**
  - 제외 이유: 생체신호 monitoring wearable 제품이며 반도체 패키징 공정 MI가 아니다.
- **2023-S41-23 — [Evaluation of Electromechanical Performance of a Flexible Hybrid Electronics Temperature Monitor](https://doi.org/10.1109/ectc51909.2023.00383)**
  - 제외 이유: 유연 온도 monitor의 제품 성능평가이며 패키징 공정 감시법이 아니다.
- **2024-S05-02 — [Ferrite-Based NFC Antenna and Sensor Package Module Development for Implantable Continuous Glucose Monitor](https://doi.org/10.1109/ectc51529.2024.00037)**
  - 제외 이유: 이식형 혈당 monitor용 안테나·센서 패키지 제품 개발이다.
- **2024-S05-04 — [Conformal Skin Patch for Dehydration Monitoring in Dementia Patients](https://doi.org/10.1109/ectc51529.2024.00039)**
  - 제외 이유: 치매 환자 탈수 monitoring용 skin patch 응용이다.
- **2024-S05-06 — [Using Flexible Hybrid Electronics on a Miniaturized Non-invasive Bio-optical Sensor For Hemoglobin Detection](https://doi.org/10.1109/ectc51529.2024.00041)**
  - 제외 이유: 헤모글로빈 검출용 bio-optical sensor 응용이다.
- **2024-S10-02 — [Development of 0.5 µm Pixel 3-Wafers Stacked CMOS Image Sensor With Through Silicon Deep Contact and In-Pixel Cu-Cu Bonding Process](https://doi.org/10.1109/ectc51529.2024.00070)**
  - 제외 이유: 3-wafer CMOS image sensor 제조 공정이며 검사 영상이 아니다.
- **2024-S17-02 — [A CMOS Nanosensing System for Continuous Brain Multianalyte Monitoring](https://doi.org/10.1109/ectc51529.2024.00113)**
  - 제외 이유: 뇌 대사물질 monitoring용 CMOS 센서 응용이다.
- **2024-S38-01 — [Conformal Dry Electrode for ECG Monitoring](https://doi.org/10.1109/ectc51529.2024.00275)**
  - 제외 이유: ECG monitoring용 dry electrode 응용이다.
- **2024-S38-23 — [Ultimate Wafer-Level Lens Integration and Optimization Using Microlenses and Metalenses for High-End Active Pixel Sensor Applications](https://doi.org/10.1109/ectc51529.2024.00297)**
  - 제외 이유: active pixel sensor용 lens integration이며 검사 장비가 아니다.
- **2024-S40-22 — [World’s Smallest, Membrane-Based Capacitive Differential Pressure Sensor- Package Structure, Material Selection, Assembly Challenges & Solutions](https://doi.org/10.1109/ectc51529.2024.00354)**
  - 제외 이유: 초소형 차압 sensor 제품·패키지 개발이다.
- **2024-S40-29 — [Development of a Reusable Smart-Catheter System for Improved Urinary Health Monitoring](https://doi.org/10.1109/ectc51529.2024.00361)**
  - 제외 이유: 요로 건강 monitoring용 catheter 응용이다.
- **2024-S40-30 — [Focal Extension - A Novel Lithography Technique in Direct-Write Laser Lithography to Enable Fine-Pitch Patterning Over Large Topography](https://doi.org/10.1109/ectc51529.2024.00362)**
  - 제외 이유: focal extension은 laser lithography 패터닝 기술이며 계측법이 아니다.

## 함께 제공되는 데이터

- `datasets/ectc-2023-2024-mi-paper-metadata.csv`: 포함 125편의 연도, 발표 ID, 분류, 제목, 세션, 전체 저자·소속, DOI, 초록 색인, 한국어 요약.
- `datasets/ectc-2023-2024-all-paper-audit.csv`: 공식 프로그램 전체 777건과 DOI·초록 신호 감사 결과.
- `datasets/ectc-2023-2024-mi-review-shortlist.csv`: 제목·초록 신호로 만든 검토 후보군.
- `datasets/ectc-2023-2024-mi-review-decisions.json`: 최종 포함 분류와 한국어 초록 핵심 요약.
- `notes/2023-ectc-73-complete-program-index.md`, `notes/2024-ectc-74-complete-program-index.md`: 두 해 전체 프로그램 검색용 색인.
