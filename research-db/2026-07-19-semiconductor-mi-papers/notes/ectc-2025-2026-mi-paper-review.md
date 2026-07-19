# ECTC 2025·2026 Metrology & Inspection 관련 논문 전수 정리

> 조사 기준일: 2026-07-19
> MI의 의미: **Metrology & Inspection(계측·검사)**
> 범위: ECTC 공식 프로그램의 모든 기술 발표 제목과, Crossref/IEEE DOI 및 공개 초록 색인을 대조한 결과

## 결론

| 연도 | 핵심 MI | MI 인접 특성평가·고장분석 | 합계 | 내용 확인 가능한 초록 |
|---:|---:|---:|---:|---:|
| 2025 | 22 | 39 | 61 | 60/61* |
| 2026 | 30 | 31 | 61 | 60/61 |
| **합계** | **52** | **70** | **122** | **120/122** |

\* 2025 S06-03은 ECTC 프로그램에는 있으나 프로시딩 목차가 `N/A`이고 ECTC DOI가 없다. 같은 제목·저자의 2026년 저널판은 ECTC 초록 수에 포함하지 않고 별도 참고로만 표시했다. S41-05는 IEEE DOI는 있으나 Semantic Scholar 초록이 없어 OpenAlex 색인으로 보완했다. 2026 S41-03은 공식 프로그램에만 남아 있고 IEEE 프로시딩 DOI·공개 초록을 찾지 못했다.

## 포함 기준

- **핵심 MI:** 논문의 주된 기여가 새로운 계측·검사 장비, 측정법, 비파괴 영상, 결함 검출·국소화, failure analysis, in-situ monitoring, overlay/alignment metrology 또는 검사 AI인 경우.
- **MI 인접:** 논문의 주된 기여는 재료·공정·신뢰성·RF/열 성능이지만, 정량 특성평가나 고장분석이 결과를 성립시키는 핵심 수단인 경우.
- ECTC에는 공식 `MI` 논문 태그가 없다. 따라서 `all`은 위의 명시적 기준에 따른 전수 분류이며, 단순히 제목에 `image`, `characteristics`, `monitoring` 같은 단어가 있다는 이유만으로 넣지 않았다.

## 조사와 검증 방법

1. 2025 공식 프로그램 391건과 2026 공식 프로그램 423건, 총 814개 기술 발표 제목을 세션·저자와 함께 색인했다.
2. 제목에서 metrology, inspection, measurement, characterization, microscopy, X-ray, Raman, defect/fault/failure, monitoring, overlay/alignment 신호를 1차 추출했다.
3. Crossref에서 2025 conference container 379개, 2026 container 416개 DOI 레코드를 대조했다.
4. DOI 레코드 795개의 공개 초록을 다시 검색해 제목만으로 빠진 후보를 감사했다.
5. 초록을 직접 읽고 핵심 MI·인접군·오탐으로 재분류한 뒤, 초록 원문을 복사하지 않고 한국어로 요약했다.

주요 출처: [ECTC 2025 공식 Final Program](https://ectc.net/wp-content/uploads/2025/06/75-ECTCFinal-Web.pdf), [ECTC 2026 공식 Final Program](https://ectc.net/wp-content/uploads/2026/05/76-ECTCFinal-Web.v2.pdf), [ECTC IEEE Xplore conference archive](https://ieeexplore.ieee.org/xpl/conhome/1000248/all-proceedings), [Crossref REST API](https://api.crossref.org/), [Semantic Scholar Academic Graph API](https://api.semanticscholar.org/api-docs/graph).

## 두 해의 흐름

- **2025:** Raman·EBSD·BLS/LFR·DIC 같은 재료/응력 계측과 HBM bump·3D X-ray·SAM 검사 AI가 함께 부상했다. 기존 FA가 놓치는 10 nm급 RDL 결함이나 subtle bond failure를 여러 장비로 단계적으로 좁히는 correlative workflow가 두드러진다.
- **2026:** `고해상도`만이 아니라 `고속·전수·in-situ·비파괴`가 중심으로 이동했다. 100% chiplet overlay, RHEED 실시간 roughness, photon-counting nano-CT, BCDI, SEM-in-air, acoustic-emission warpage monitoring이 대표적이다.
- **공통 방향:** 검사 throughput을 높이기 위해 AI가 영상 복원·segmentation·anomaly detection·overlay estimation에 들어가고, 물리 제약·digital twin·simulation data로 실제 라벨 부족을 보완한다.

## ECTC 2025

### 핵심 MI (22편)

1. **S04-05 — [Yield Prediction Technology: A Game Changer for Cutting Costs and Reducing Ramp Time in FOPLP Lithography](https://doi.org/10.1109/ectc51687.2025.00030)**
   - 세션: Session 04 - Large Package Manufacturing and Panel Level Processing
   - 공개 영문 초록 기반 한국어 요약: panel의 die shift와 pattern distortion을 offline metrology로 측정한 뒤 ML과 공정 파라미터를 결합해 FOPLP lithography overlay 오차와 수율을 조기 예측한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/4746bcf2a00e491a72f89cafa411baa42509f4c2)

2. **S06-03 — [Peridynamics Enabled Digital Image Correlation for Small Scale Defect Detection](https://ectc.net/wp-content/uploads/2025/06/75-ECTCFinal-Web.pdf)**
   - 세션: Session 06 - AI - ML and Emerging Modeling Methods
   - 후속 저널판 초록 기반 참고 요약: DIC로 얻은 전변위장에 비국소 변형률 적합성 연산과 MARS 회귀를 결합해 마이크로미터급 균열의 위치·형상·전파 경로를 검출한다. ECTC 원고는 프로시딩에 실리지 않았고, 같은 제목의 2026년 저널판 초록으로 내용을 확인했다.
   - 초록 출처: [ECTC 초록 미확보 · 동일 제목 후속 저널판 참고](https://experts.azregents.edu/en/publications/peridynamics-enabled-digital-image-correlation-for-small-scale-de/)

3. **S10-04 — [Reliability and Microstructure Characterization of Through-Silicon Vias (TSV) at Different Aspect Ratios Using EBSD-Raman Spectroscopy](https://doi.org/10.1109/ectc51687.2025.00071)**
   - 세션: Session 10 - High Reliability Applications
   - 공개 영문 초록 기반 한국어 요약: 직경 3 µm TSV의 종횡비 4:1·7:1·10:1을 EBSD와 Raman으로 비교했으며, 종횡비가 커질수록 주변 Si의 최대 잔류응력은 약 -100 MPa에서 -20 MPa로 줄지만 평균 Cu 결정립 크기는 거의 변하지 않았다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/affbabf3638c21119dd6f9788fde954be8aa7d40)

4. **S11-04 — [Advanced Metrology Suite for Linking Residual Stress to Fundamental Properties of Thermoset Packaging Materials](https://doi.org/10.1109/ectc51687.2025.00078)**
   - 세션: Session 11 - Emerging Trends: Towards High Speed, Secure, Reliable, and Sustainable Packaging
   - 공개 영문 초록 기반 한국어 요약: 열분석·레올로지·경화수축·발생응력 측정을 묶은 계측 스위트로 액상 봉지재의 기본 물성과 경화 중 잔류응력 발생을 연결한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/5136a5a9d9879983217c6c978619f54b73715b0b)

5. **S18-03 — [In-Situ Confocal Raman Spectroscopy Assisted Interfacial Residual Stress Characterization in SiC Chip Sintered on AMB Substrate With Nanocopper Paste](https://doi.org/10.1109/ectc51687.2025.00126)**
   - 세션: Session 18 - Simulations and Validation on Reliability Challenges of High Performance Packages
   - 공개 영문 초록 기반 한국어 요약: 공초점 Raman으로 SiC/소결 Cu 계면 잔류응력을 비접촉·비파괴 측정했으며, 칩 중앙부에 약 -139~-165 MPa의 압축응력이 집중됨을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/786fa14e6ad1edc63091d7ba9d2472ad19173e8d)

6. **S22-02 — [Optimization of Alignment Model and Metrology During Backside EUV Lithography Patterning for CFET Technology](https://doi.org/10.1109/ectc51687.2025.00153)**
   - 세션: Session 22 - Heterogeneous Integration Using Bridge and 3D Stacking
   - 공개 영문 초록 기반 한국어 요약: CFET 후면 EUV 공정에서 정렬 모델·샘플 밀도·계측 시간과 overlay 성능의 절충을 비교해 4 nm 미만 overlay 가능성을 제시한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/4cde8f83c4fa4cb445f810d94f3adca1e67ac8af)

7. **S22-03 — [Assessing Queue Time in D2W Hybrid Bonding Through Precise Bond Strength Measurements](https://doi.org/10.1109/ectc51687.2025.00154)**
   - 세션: Session 22 - Heterogeneous Integration Using Bridge and 3D Stacking
   - 공개 영문 초록 기반 한국어 요약: D2W hybrid bonding의 대기시간이 길어지면 계면 수분 증발과 미세 갭 증가로 접합강도가 떨어짐을 정밀 강도 측정, 접촉각, TDS, 제타전위로 확인했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/2cd9755b098324b14568555afddb987fdd420e62)

8. **S23-03 — [Efficient Visual Inspection Framework of High-Bandwidth Memory Bumps With Generative and Deep Learning AI](https://doi.org/10.1109/ectc51687.2025.00161)**
   - 세션: Session 23 - AI Enabled Innovations in Advanced Packaging Technologies
   - 공개 영문 초록 기반 한국어 요약: HBM 3D 스캔을 다중 시점 AI로 검사하고 LLM 기반 보고서를 자동 생성해 불량 bump 식별을 46% 개선했으며, 25% 라벨만으로 87% 분할 정확도와 5분 이내 전수 보고를 달성했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/844e44a0dd8278c51cf365e6572624d19faa4337)

9. **S24-07 — [Validated Methodology for Accurate Simultaneous Measurement of Elastic Modulus and CTE of BEOL Materials for Improved Advanced Package Performance Prediction](https://doi.org/10.1109/ectc51687.2025.00172)**
   - 세션: Session 24 - Advanced Characterization and Modeling of Next Generation Packaging Materials
   - 공개 영문 초록 기반 한국어 요약: 온도 의존 박막응력 측정으로 SiNx 박막의 탄성률과 CTE를 동시에 구하고, 125~2000 nm 두께 범위에서 nanoindentation 결과와 일치함을 검증했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/f0bea9fb5f89b9256ea545937de9ae9451e77380)

10. **S28-06 — [First Proof of 3D-IC Power Plane Defect Localisation via Frequency Domain Spatial Heat Mapping](https://doi.org/10.1109/ectc51687.2025.00199)**
   - 세션: Session 28 - Reliability of Heterogeneous Integrated (HI) Packages
   - 공개 영문 초록 기반 한국어 요약: 3D-IC 전원면의 주파수영역 return-loss 차이로 결함 위치 확률 heat map을 만들고 spiral scan을 적용해 failure-analysis scan 시간을 약 한 자릿수 규모로 줄이는 개념을 입증했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/7c3678dca3b086101ac28c8cb38d4690e12c2b62)

11. **S32-02 — [Are Voids Restricted to Cu-Cu bonding Interface? Truth Revealed by CEY-Scanning Transmission X-Ray Microscopy](https://doi.org/10.1109/ectc51687.2025.00222)**
   - 세션: Session 32 - Design, Materials, Metrology & Standards for Next Generation Interconnections
   - 공개 영문 초록 기반 한국어 요약: CEY-STXM을 이용해 hybrid bonding 미세접합의 void와 delamination을 위치별로 관찰한 결과, 결함이 Cu-Cu 계면에만 국한되지 않고 다른 Cu 포함 계면에도 존재함을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/83f4ed55a4171cfb40b04d9ea824e806e1d9a243)

12. **S37-18 — [Raman and X-ray Imaging Based Thermo-Mechanical Characterization of Metal-Embedded Chip Assembly](https://doi.org/10.1109/ectc51687.2025.00273)**
   - 세션: Session 37 - Interactive Presentations 1
   - 공개 영문 초록 기반 한국어 요약: in-situ Raman 응력 맵과 FEA로 금속 매립 칩 구조를 비교해 Cu-diamond heat spreader가 CTE와 탄성률을 조절하여 interposer와 die의 응력 집중을 낮춤을 확인했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/49e00936be03321b7c90c32ad122d8117494ca08)

13. **S37-22 — [An Efficient Data Augmentation and Semantic Segmentation Framework for 3D Defect Detection of HBMs](https://doi.org/10.1109/ectc51687.2025.00277)**
   - 세션: Session 37 - Interactive Presentations 1
   - 공개 영문 초록 기반 한국어 요약: 소량의 라벨로 3D XRM 합성 데이터를 만들고 HBM 결함을 분할해 주석량을 최대 90% 줄이면서 유사한 bump 분할 성능과 더 나은 결함 검출을 유지했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/d212646ca9a5b7bd28228bb57a554d6892411283)

14. **S37-25 — [Mitigation of Wafer-to-Wafer Bonding Distortions Through Accelerated Simulations and Measurements](https://doi.org/10.1109/ectc51687.2025.00280)**
   - 세션: Session 37 - Interactive Presentations 1
   - 공개 영문 초록 기반 한국어 요약: 가속 W2W bonding 시뮬레이션과 overlay 측정을 결합해 bonding recipe·입사 wafer 형상·gap이 왜곡에 미치는 영향을 찾고 chuck bow 보상 조건을 제안했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/42e2e4568d1598b81ac44a08c72385411556e8a9)

15. **S38-08 — [A Dual Mode BLS/LFR Microscope for Local Mechanical Property Imaging for Semiconductor Packaging Materials](https://doi.org/10.1109/ectc51687.2025.00288)**
   - 세션: Session 38 - Interactive Presentations 2
   - 공개 영문 초록 기반 한국어 요약: BLS와 저주파 Raman을 전환하는 비접촉·비파괴 현미경으로 epoxy 경화 중 modulus 변화와 Tg를 추적하고, 경화도가 다른 영역의 기계 물성 지도를 만들었다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/5552de64c01494f6e5b144e03995e6d8da250432)

16. **S39-09 — [Accelerating Root Cause Identification of Subtle Bonding Failures With Microwave Induced Plasma](https://doi.org/10.1109/ectc51687.2025.00316)**
   - 세션: Session 39 - Interactive Presentations 3
   - 공개 영문 초록 기반 한국어 요약: curve trace에서 드러나지 않는 미세 wire-bond 불량을 microwave-induced plasma로 변색시킨 뒤 optical image와 lifted ball bond를 대응시켜 root-cause 탐색을 가속한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/eccee28e429f8f50f36056e18c9d724faed55f83)

17. **S39-30 — [Novel Fault Isolation Methodology Applied on Nano-Scale Defect in Fine Line RDL for Advanced Fan-Out Package](https://doi.org/10.1109/ectc51687.2025.00337)**
   - 세션: Session 39 - Interactive Presentations 3
   - 공개 영문 초록 기반 한국어 요약: plapping, lock-in thermography, 3D X-ray, FIB, 원소분석을 순차 결합해 일반 FA로 보이지 않던 fine-line Cu RDL의 10 nm급 결함을 국소화하는 절차를 제시한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/e0e0df5fce58e0108fe48948949bd4a3935b5eb1)

18. **S40-14 — [Characterization of Interfacial Fracture Strength in Hybrid Bonded Wafers: A Novel Approach for High-Resolution Spatial Profiling](https://doi.org/10.1109/ectc51687.2025.00351)**
   - 세션: Session 40 - Interactive Presentations 4
   - 공개 영문 초록 기반 한국어 요약: 300 mm hybrid-bonded wafer를 strip으로 절단해 확장 razor-blade 시험과 optical profilometry를 반복함으로써 wafer 전역의 계면 파괴강도 프로파일을 만들었고 중앙이 가장자리보다 약 20% 높음을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/a0833a9b2815ce44cdf8733e43c6eb94b6fa9862)

19. **S41-07 — [Physics-Informed Neural Networks for SAM Image Enhancement With a Novel Physics-Constrained Metric for Advanced Semiconductor Packaging Inspection](https://doi.org/10.1109/ectc51687.2025.00368)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: 음향파 전파 법칙을 loss에 넣은 PINN으로 SAM 영상을 복원하고 물리 정확도를 평가하는 PCRS 지표를 제안해 SSIM·PSNR과 결함 가시성을 개선했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/7a46ef3b6ad2cf88c1bfd169bbf6c0f54e1eda48)

20. **S41-28 — [Imaging Assisted Dual Sided Light Coupling Technique for Propagation Loss Estimation of Waveguide Interconnects](https://doi.org/10.1109/ectc51687.2025.00389)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: 입·출력 포트를 바꿔 얻은 산란광 영상을 정규화해 fiber 결합 효율과 길이 방향 편차의 영향을 줄이는 빠른 waveguide propagation-loss 추정법을 제시했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/bb2d18ddc311a095bfeb24e0b220a4278ca9342e)

21. **S41-31 — [Reliable Bonding Strength Measurement of SiCN/ SiCN Films by Four-point Bending Methodology](https://doi.org/10.1109/ectc51687.2025.00392)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: SiCN/SiCN 접합을 4-point bending과 MVCCT로 평가해 2.33 J/m² 이상의 접합에너지와 mode-I 지배 파괴를 확인하고, 시편 폭·속도·시험 한계를 정리했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/4398321aa5a66016a1e1d17e3eb5242d5222dc98)

22. **S41-33 — [Measurement of Thermal, Humidity, Solder and Aging Effects of Mechanical Stress and Silicon Circuit Electrical Performance in Quad Flat Packages](https://doi.org/10.1109/ectc51687.2025.00394)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: 칩 내 piezoresistive stress sensor로 QFP의 절대 패키지 응력과 soldering·습도·열사이클 aging에 따른 응력 및 회로 성능 변화를 실험적으로 측정했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/d7ba62630a9aff65b34417e36a930a0670d017b2)

### MI 인접 특성평가·고장분석 (39편)

1. **S02-04 — [Optical and Electrical Characterization of a Compact Universal Photonic Engine](https://doi.org/10.1109/ectc51687.2025.00015)**
   - 세션: Session 02 - Co-Packaged Optics
   - 공개 영문 초록 기반 한국어 요약: TSMC COUPE의 wafer-level 광·전기 특성을 측정해 grating-coupler 삽입손실 1.2 dB 이하, 1 dB bandwidth 약 25 nm, wafer 내 중심파장 편차 ±1.7 nm를 보고했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/0f43f172cd7b80a25ce2c459471ad5e708348772)

2. **S03-01 — [Morphological Microstructure Characterization and Optimization of Nanocrystalline Copper Deposition for Fine-Pitch Hybrid Bonding Cu/SiO2 at Low Temperature.](https://doi.org/10.1109/ectc51687.2025.00019)**
   - 세션: Session 03 - Hybrid Bonding Materials and Processing for Advanced Packaging
   - 공개 영문 초록 기반 한국어 요약: 300 mm 도금 조건과 waveform을 조정해 0.6~10 µm fine-pitch 구조에 void 없는 nanocrystalline Cu를 형성하고 저온 hybrid bonding용 미세조직 안정성을 평가했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/9057e9df84dde611612f43b3fe3f4934e19fa875)

3. **S03-05 — [Characterization of Self-Nanoparticulated Cu-Cu Interconnection for Low-temperature Hybrid Bonding](https://doi.org/10.1109/ectc51687.2025.00023)**
   - 세션: Session 03 - Hybrid Bonding Materials and Processing for Advanced Packaging
   - 공개 영문 초록 기반 한국어 요약: Cu pad 표면을 자체 nanoparticle 층으로 바꾸는 SNP 처리의 bondability를 250°C와 350°C 열압착 조건에서 평가해 저온 Cu-Cu 직접접합 가능성을 검토했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/0ab421b576b5d8a7bdfc1c93b4b77ef642398127)

4. **S04-06 — [Glass-Core Advanced Packaging Substrate Post-Dicing Die Strengths Comprehensive Comparisons for Different Singulation Methods - Dicing Induced SeWaRe Failures Re-Visited Ten Years Later](https://doi.org/10.1109/ectc51687.2025.00031)**
   - 세션: Session 04 - Large Package Manufacturing and Panel Level Processing
   - 공개 영문 초록 기반 한국어 요약: 여러 blade·laser singulation 조건의 glass die 3-point bending을 비교해 edge chip·Ra보다 recipe별 stress concentrator가 강도를 좌우하고 dielectric edge pull-back이 SeWaRe를 억제함을 확인했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/193097c9eaa48804ac48ca57e3d12473d3d34715)

5. **S05-04 — [Power Integrity and Circuit Characteristics of Integrated Voltage Regulator (IVR) in CoWoS® Advanced Packaging Technology](https://doi.org/10.1109/ectc51687.2025.00036)**
   - 세션: Session 05 - Advanced Design for Heterogeneous Integration
   - 공개 영문 초록 기반 한국어 요약: CoWoS-R에 IVR을 내장했을 때 위치별 PDN과 power-integrity 변화를 비교하고 다상화로 생기는 output overshoot 완화 방안을 제안했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/166b51bac5d521c7156b7efe95c13383cfde74de)

6. **S08-01 — [2 µm Pitch Direct Die-to-Wafer Hybrid Bonding Using Surface Protection During Wafer Thinning and Die Singluation](https://doi.org/10.1109/ectc51687.2025.00054)**
   - 세션: Session 08 - Novel Structures and Processes for Chip-to-Wafer Hybrid Bonding
   - 공개 영문 초록 기반 한국어 요약: D2W 공정에 inorganic protective layer를 넣어 thinning·singulation 후에도 Cu recess 약 2 nm를 유지하고 TEM으로 SiCN/Cu 계면과 80~95% 이상의 전기 수율을 확인했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/41102f0889d291abebf98e6b5d2498650813598e)

7. **S09-07 — [First Demonstration of Superior Characteristics of Co-Co Bonding With Passivation Structure at Low Thermal Budget for Advanced Packaging and Ultra-Fine Pitch Applications](https://doi.org/10.1109/ectc51687.2025.00067)**
   - 세션: Session 09 - Co-Packaged Optics and Hybrid Bonding Innovations for HI
   - 공개 영문 초록 기반 한국어 요약: SAT·SEM·전기측정·XPS depth profile로 Ag passivation Co-Co 접합을 평가해 약 10^-7 Ω·cm²의 접촉저항과 저온 접합 가능성을 확인했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/2f4278c57c06e51853b161981dcf8c7a19761293)

8. **S10-06 — [The Role of Polymer Shrinkage and Oxidation in Thermal Aging Induced Crack Formation in Glass Fiber Reinforced Printed Circuit Boards](https://doi.org/10.1109/ectc51687.2025.00073)**
   - 세션: Session 10 - High Reliability Applications
   - 공개 영문 초록 기반 한국어 요약: FTIR, laser-scanning microscopy, roughness 측정, SEM을 결합해 PCB 열노화 시 polymer oxidation·수축이 fiber 계면 debonding과 crack 성장을 유발함을 밝혔다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/647fda88ea506c17d602236bd90008cd3d5caea6)

9. **S11-05 — [Predictive Modeling of IMC Growth in BGA Component Solder Joints Using Artificial Neural Networks Under Rework and Temperature Cycling Conditions](https://doi.org/10.1109/ectc51687.2025.00079)**
   - 세션: Session 11 - Emerging Trends: Towards High Speed, Secure, Reliable, and Sustainable Packaging
   - 공개 영문 초록 기반 한국어 요약: rework와 thermal cycling 조건의 IMC 성장 데이터를 ANN으로 학습하고 SEM 단면 측정과 비교해 BGA·PCB 측 IMC 높이를 높은 상관도로 예측했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/54ba9946fb44fc6a58e9ed085144c867d961602d)

10. **S11-06 — [Parameter Degradation Monitoring and Controller Adaptation Using Digital Twin](https://doi.org/10.1109/ectc51687.2025.00080)**
   - 세션: Session 11 - Emerging Trends: Towards High Speed, Secure, Reliable, and Sustainable Packaging
   - 공개 영문 초록 기반 한국어 요약: buck converter의 digital twin과 particle-swarm 추정으로 노화에 따른 수동소자 파라미터 drift를 추적하고 controller 값을 재조정하는 방법을 제안했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/88b83db797142e5b40c34d7c6b79ad076dc2b58a)

11. **S18-01 — [Simulation and Experimental Validation of Microstructure Evolution of Sintered Ag Layer During Thermal Aging Using a Hybrid Potts-Phase Field Model](https://doi.org/10.1109/ectc51687.2025.00124)**
   - 세션: Session 18 - Simulations and Validation on Reliability Challenges of High Performance Packages
   - 공개 영문 초록 기반 한국어 요약: Kinetic Monte Carlo 기반 grain growth와 phase-field pore migration을 결합해 200°C aging 중 sintered-Ag 미세조직 변화를 모사하고 실험과 성장 경향을 비교했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/e47ba79b34a248c232a8326b276717daa1dbfd97)

12. **S18-07 — [Isothermal Shock Testing and Failure State Analysis on Flip-Chip Interconnects](https://doi.org/10.1109/ectc51687.2025.00130)**
   - 세션: Session 18 - Simulations and Validation on Reliability Challenges of High Performance Packages
   - 공개 영문 초록 기반 한국어 요약: -40°C·상온·125°C shock 중 strain과 solder-joint 저항을 실시간 측정하고 단면분석으로 IMC 인근 균열의 시작·전파·완전 파단을 추적했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/7774991c3015345b0ebfb9478bb0814f9d24f7de)

13. **S19-06 — [Inter-Die Gap-Filling With Varying Aspect Ratio (AR) Using PECVD Oxide for 3D Packaging: Model Prediction and Experimental Validation](https://doi.org/10.1109/ectc51687.2025.00136)**
   - 세션: Session 19 - Chiplet Integration and Advanced Thermal Solutions
   - 공개 영문 초록 기반 한국어 요약: 다양한 inter-die gap 종횡비에서 ultra-thick PECVD oxide의 충전 성능을 실험해 안전한 공정창을 찾고 gap-fill 예측 모델을 제시했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/c21e1ab793ddcfacb1c60d65d4ca0cf0de471a1b)

14. **S19-07 — [Modeling and Validation of an Integrated Package Solution (iPaS) for Next Generation Power Supply Systems](https://doi.org/10.1109/ectc51687.2025.00137)**
   - 세션: Session 19 - Chiplet Integration and Advanced Thermal Solutions
   - 공개 영문 초록 기반 한국어 요약: iPaS capacitor-array sheet의 횡방향 연결을 포함한 회로모델을 impedance와 transient 측정에 맞춰 검증해 차세대 PDN 설계에 쓸 수 있게 했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/52cdcc823d5a97c1d88e1944e5f2f3234c13e078)

15. **S24-01 — [Characterization of Moisture Diffusion Properties of ABF and Mold Compounds in Molded Package With High Copper Density Substrate](https://doi.org/10.1109/ectc51687.2025.00166)**
   - 세션: Session 24 - Advanced Characterization and Modeling of Next Generation Packaging Materials
   - 공개 영문 초록 기반 한국어 요약: 세 종류 ABF와 두 mold compound의 네 온습도 조건 흡·탈습 질량을 측정해 diffusivity, saturation concentration, activation energy를 산출했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/f60d1650add25ed3e5b3a59c195eab9537576481)

16. **S24-03 — [Nanoindentation Based Methodology to Characterize the Adhesion Strength of Dielectric Bond Interfaces](https://doi.org/10.1109/ectc51687.2025.00168)**
   - 세션: Session 24 - Advanced Characterization and Modeling of Next Generation Packaging Materials
   - 공개 영문 초록 기반 한국어 요약: dielectric bond interface를 노출한 뒤 다점 nanoindentation과 세 가지 해석법, cohesive-zone FEM을 사용해 Young's modulus와 접합강도를 통계적으로 평가한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/2ae4c4912f89b7b4d96b46a517473469c98bc061)

17. **S24-06 — [Physics-Based Modeling With Nanoindentation on the Mechanical Reliability of TGV Substrates Under Annealing Effects](https://doi.org/10.1109/ectc51687.2025.00171)**
   - 세션: Session 24 - Advanced Characterization and Modeling of Next Generation Packaging Materials
   - 공개 영문 초록 기반 한국어 요약: nanoindentation·EBSD·DIC로 anneal 전후 TGV-Cu 물성과 대면적 warpage를 측정하고 elastoplastic/creep FEA로 응력-변형과 maskless lithography 조건을 추정했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/59759fa6965aeb1ef6c4fecab187656df98ccdbc)

18. **S27-03 — [Characterization of PVD Backside Metal Adhesion for Improved Thermal Management in Heterogeneous Integration](https://doi.org/10.1109/ectc51687.2025.00189)**
   - 세션: Session 27 - Thermal Management and Material Solutions for High Performance 2.5D and 3D Packaging
   - 공개 영문 초록 기반 한국어 요약: Si와 EMC 위 일곱 종류 backside metallization stack의 adhesion과 MSL 후 delamination을 비교해 열관리용 PVD stack과 전처리 조건을 선별했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/f44d125f02680dee3076e7bd8b9bd56f81e9b628)

19. **S30-02 — [Crystal Plasticity-Based Modeling and Experimental Validation of the Influence of Microstructures and Grain Boundary Junction Types on the Cu-Cu Bonding Interface.](https://doi.org/10.1109/ectc51687.2025.00208)**
   - 세션: Session 30 - Simulations on Advanced Package Processing - Hybrid Bonding, Chip Stacking and Wafer-to-Wafer
   - 공개 영문 초록 기반 한국어 요약: 관찰과 crystal-plasticity FEM을 결합해 Cu 결정방향·grain-boundary 접합형태와 압력이 hybrid-bonding void 폐쇄에 미치는 영향을 분석했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/4283d26cb7859509a0b3d5039cdc00f450a7a1ff)

20. **S32-01 — [Process Development and Characteristics of Small-Diameter (&lt;3 µm), Cobalt-Filled Through Silicon Vias (TSVs) For High-Density 3D Chip Stacking](https://doi.org/10.1109/ectc51687.2025.00221)**
   - 세션: Session 32 - Design, Materials, Metrology & Standards for Next Generation Interconnections
   - 공개 영문 초록 기반 한국어 요약: 3~5 µm Co-TSV를 AFM·SEM·Raman으로 평가해 anneal 후 pump-out이 55 nm 미만, 등가응력이 75 MPa 미만임을 보고했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/3069c4ce9a815c7fa06d063dd1b14a2fe0e4cc1b)

21. **S35-01 — [3D Vertical Glass Stacking for 6G Communications - Interconnect Fabrication and Broadband Characterization](https://doi.org/10.1109/ectc51687.2025.00242)**
   - 세션: Session 35 - High-Performance Antenna and RF Design
   - 공개 영문 초록 기반 한국어 요약: 다층 glass 3D stack의 수직 TGV 전이를 DC~220 GHz에서 측정해 200 GHz에서 약 0.3 dB 손실을 보이고 panel warpage도 함께 평가했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/1e690531d45baa7719e1e3677e376aacbd7aaca2)

22. **S36-01 — [Warpage Simulation and Experimental Validation of The X-Dimension Fan-Out Integration-Bridge (XDFOI-B) Wafer Level Packaging Process](https://doi.org/10.1109/ectc51687.2025.00249)**
   - 세션: Session 36 - Modeling Driven Packaging and Process Advancements
   - 공개 영문 초록 기반 한국어 요약: XDFOI-B 전 공정 warpage를 element birth/death FEA로 계산하고 제조 데이터와 대조해 75% 이상 정확도를 보이며 저감 변수들을 제시했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/6e3b5b0f4e435ea531e12487e0963a5f47c9f598)

23. **S37-07 — [Comparison of Mechanical Response and Failure Characteristics of Selected SnAgCu-Based High-Temperature Solder Alloys](https://doi.org/10.1109/ectc51687.2025.00262)**
   - 세션: Session 37 - Interactive Presentations 1
   - 공개 영문 초록 기반 한국어 요약: 세 고온 무연 solder alloy를 monotonic·creep·fatigue와 미세조직 분석으로 비교해 SAC305보다 creep 저항은 높지만 파단연성은 낮은 원인을 설명했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/0aa198d37a4ddc7946d0551ab22c2757cc69f43a)

24. **S37-09 — [A Novel Methodology for Characterizing and Validating Viscoelastic and Thermal Expansion Properties of Polymer Films](https://doi.org/10.1109/ectc51687.2025.00264)**
   - 세션: Session 37 - Interactive Presentations 1
   - 공개 영문 초록 기반 한국어 요약: NiDMTA nanoindentation, shadow moiré, FEA를 묶어 polymer film의 viscoelastic Prony parameter와 CTE를 구하고 24시간 relaxation으로 모델을 검증했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/7824285f0d931ce8d16120681e287df637aaa088)

25. **S37-11 — [Characterization of Coupled Mechanical and Electrical Behavior of Porous Conductive PDMS-CNT/ Graphene Based Foams Under Multidirectional Strain for Flexible/Stretchable Electronics](https://doi.org/10.1109/ectc51687.2025.00266)**
   - 세션: Session 37 - Interactive Presentations 1
   - 공개 영문 초록 기반 한국어 요약: CNT·graphene을 넣은 porous PDMS foam을 다축 radial stretch 장비로 시험해 flexible sensor용 기계·전기 결합 특성 분석 기반을 만들었다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/aec8b18e7d057ce293034ba5c579a4cabe622fa2)

26. **S37-21 — [Thermal Characterization of HBMs Integrated via Hybrid Bonding](https://doi.org/10.1109/ectc51687.2025.00276)**
   - 세션: Session 37 - Interactive Presentations 1
   - 공개 영문 초록 기반 한국어 요약: hybrid-bonded HBM의 DSF와 inter-die gap-fill 공정흐름을 열적으로 비교해 molding이 없고 얇은 die를 쓰는 IDGF가 더 낮은 thermal resistance를 보임을 보고했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/4fde47a4367366f65cf624bdbddc79aef6a9df88)

27. **S38-01 — [Flexible Glass Electrical Characterization Using Aerosol Jet Printing](https://doi.org/10.1109/ectc51687.2025.00281)**
   - 세션: Session 38 - Interactive Presentations 2
   - 공개 영문 초록 기반 한국어 요약: aerosol-jet printed resonator로 flexible Willow glass를 6~30 GHz에서 측정해 평균 Dk 5.68, loss tangent 0.0065를 얻었다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/6d9539f0cc0d4bd879e3fc1b069345d1f1037ef5)

28. **S38-18 — [Prediction of Cross Section Images and Optimization of Processes With Neural Network](https://doi.org/10.1109/ectc51687.2025.00298)**
   - 세션: Session 38 - Interactive Presentations 2
   - 공개 영문 초록 기반 한국어 요약: 공정 조건에서 단면 이미지를 생성하고 목표 단면에서 역으로 조건을 추천하는 regression+VAE 시스템으로 수일 걸리던 cross-section 시행착오를 수초 예측으로 줄인다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/b2655d4fa95e5c950fdb4c6ef236f5c2b717461f)

29. **S38-23 — [Advanced Characterization of the Cure Kinetics of a Liquid Encapsulant](https://doi.org/10.1109/ectc51687.2025.00303)**
   - 세션: Session 38 - Interactive Presentations 2
   - 공개 영문 초록 기반 한국어 요약: DSC, FTIR, rheo-Raman을 함께 사용해 liquid encapsulant의 전체 cure kinetics, 화학반응, 시간 의존 기계물성을 계측하고 권장 cure schedule의 불완전 경화 가능성을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/6f57a09e88896e8a6fde339e1a51ad672df32cdd)

30. **S39-15 — [A High Throughput Low-Temperature Copper-Copper Thermal Compression Bonding Scheme Using Tin Passivation](https://doi.org/10.1109/ectc51687.2025.00322)**
   - 세션: Session 39 - Interactive Presentations 3
   - 공개 영문 초록 기반 한국어 요약: 5 nm Sn overlayer를 쓴 Cu-Cu 열압착을 TEM과 FIB-SEM으로 확인해 200°C에서도 100 N 이상의 die shear와 적은 void를 달성했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/229d1a0560b89feadfbae2c296743ed704f5f861)

31. **S39-21 — [Development and Characterization of Electrodeposited Tin-Indium Alloy Microbumps for Low Temperature Assembly](https://doi.org/10.1109/ectc51687.2025.00328)**
   - 세션: Session 39 - Interactive Presentations 3
   - 공개 영문 초록 기반 한국어 요약: 45~55 wt.% In의 eutectic 근처 Sn-In microbump를 전기도금하고 150°C 미만 reflow와 초기 bonding test로 저온 조립 가능성을 확인했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/d6a40463c60ee3137f2dda6665f2def45e81b57e)

32. **S39-23 — [Impact of Temporary Substrates and Adhesives on Die-to-Wafer Overlay](https://doi.org/10.1109/ectc51687.2025.00330)**
   - 세션: Session 39 - Interactive Presentations 3
   - 공개 영문 초록 기반 한국어 요약: collective D2W bonding에서 glass/Si carrier, thermoset/thermoplastic adhesive, placement·bonder 조건별 overlay 오차 기여를 비교해 polymer glass carrier의 정렬 한계를 지적했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/e3fbfdd221e405f126dfc0643866a02ff0de73a0)

33. **S40-09 — [Characterization of FOWLP Process Using Temporary Bonding Material on Carrier With Very Low Die Shift](https://doi.org/10.1109/ectc51687.2025.00346)**
   - 세션: Session 40 - Interactive Presentations 4
   - 공개 영문 초록 기반 한국어 요약: 두 EMC의 CTE·Tg·modulus와 temporary bonding material 조합을 비교해 blanket mold의 warpage와 embedded-die의 die shift를 좌우하는 물성을 정리했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/8b94639832746d3543c93e0530f16cde49bd5986)

34. **S40-24 — [Mechanical Strength and Pad Cratering Risk Determination of High-Speed PCBs via Physical Testing and Numerical Simulation](https://doi.org/10.1109/ectc51687.2025.00361)**
   - 세션: Session 40 - Interactive Presentations 4
   - 공개 영문 초록 기반 한국어 요약: 상온·100°C solder-ball shear 시험과 동일 구조 FEM을 결합해 PCB laminate의 pad-cratering 시점과 고유 fracture stress를 추출한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/42334aa7780ef29b71fc9ad2ba1abf48bb3d2a76)

35. **S41-01 — [Characterization of the Mechanical and Thermal Properties of SAC+Bi Phases in Hybrid SAC/LTS Solder Joints](https://doi.org/10.1109/ectc51687.2025.00362)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: SAC+Bi 혼합상의 SEM/EDS, DSC, tensile, creep 특성을 Bi 농도별로 측정해 15~20% 이상에서 phase segregation과 기계물성 저하가 커짐을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/79eca6af2e6de6c090aab8f43cc57eaa4c5b3871)

36. **S41-05 — [Design, Fabrication and Characterization of a 3D-Printed Radix-Based Array Antenna for 5G mmWave Applications](https://doi.org/10.1109/ectc51687.2025.00366)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: 3D-printable Radix 소재로 patch antenna를 만들고 PCB 시편과 비교해 30 GHz 부근 impedance matching과 열·습도 노출 후 RF 안정성을 평가했다. 초록은 OpenAlex 색인에서 보완했다.
   - 초록 출처: [OpenAlex 초록 색인](https://openalex.org/W4411688961)

37. **S41-16 — [Characterization of Dielectric Materials Beyond Room Temperature Using the Lab-Developed Temperature Split Cavity (TSC) Method](https://doi.org/10.1109/ectc51687.2025.00377)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: Temperature Split Cavity와 TCC로 2~20 GHz dielectric 특성을 -150~200°C 범위까지 확장 측정하고 1 MHz capacitor 결과로 신뢰성을 검증했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/4f9f139d2b1cc74efe87c29d560082515bb13bd8)

38. **S41-18 — [High-Frequency Multi-Chip RF Module Enabled by Fused-Silica Stitch-Chip Technology: RF and Interconnect Characterization](https://doi.org/10.1109/ectc51687.2025.00379)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: fused-silica stitch-chip으로 LNA와 switch die를 연결한 K/Ka-band module을 측정해 gain 저하 1 dB 미만과 12 dB 이상 return loss를 확인했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/e0ef6a6d1143abebc0a017fb5c47781b15896082)

39. **S41-30 — [Thermal Characterization and Benchmarking of Aluminum Ribbon Ceramic (ARC) Substrates in mmWave/RF Packaging Applications](https://doi.org/10.1109/ectc51687.2025.00391)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: ARC substrate 시험차량을 6 W까지 가열해 via 최적화 glass package보다 5배 이상 높은 허용 power density와 3.64배 높은 유효 thermal conductance를 보고했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/be86ea898ab40db48cbc83bbd4d83d064c2609d6)

## ECTC 2026

### 핵심 MI (30편)

1. **S09-05 — [In-Situ Cure Monitoring of EMC by Fiber Bragg Grating and Dielectric Sensors with Molecular Dynamics Validation for Accurate Warpage Prediction](https://doi.org/10.1109/ectc51846.2026.00068)**
   - 세션: Session 09 - Advances in Thermal Materials and Encapsulation
   - 공개 영문 초록 기반 한국어 요약: dielectrometry로 gelation, FBG로 post-gel cure shrinkage를 실시간 측정하고 MD·DMA·FEM을 결합해 EMC warpage 예측을 97.96% 정확도로 검증했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/e59baf134c22adab9c0821bed73bbc4b6a40ccfa)

2. **S14-04 — [Influence of Metal Surface Characteristics on Auto Focus Reference Position and Pattern Fidelity in Fine-Pitch RDL Applications](https://doi.org/10.1109/ectc51846.2026.00102)**
   - 세션: Session 14 - RDL and Fan-Out Interconnections
   - 공개 영문 초록 기반 한국어 요약: on-axis optical autofocus로 resist 아래 Cu roughness·reflectivity 변화에 따른 focus actuator 응답과 pattern fidelity 영향을 빠르게 측정한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/b6f5d4e960e78e53cbad3226ba7ba02169938a0b)

3. **S18-01 — [Pushing the Envelope in Mechanical Characterization of Copper in Hybrid-Bonding Patterns for Advanced Packaging: From Instrumented Indentation to Multimodal Atomic Force Microscopy](https://doi.org/10.1109/ECTC51846.2026.00127)**
   - 세션: Session 18 - Hybrid Bonding: Advanced Processing and Modeling
   - 공개 영문 초록 기반 한국어 요약: 1·5 µm nanoindentation과 30 nm급 AFM contact-resonance/indentation을 결합해 hybrid-bonding Cu의 길이척도별 소성 시작과 yield stress를 계측하고 분석용 open-source software를 제공한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/b00d07bc6ce390f3ffdd8e0bc26817fb9c8e1cf7)

4. **S18-02 — [Nanoindentation-Based Analysis of Wafer-to-Wafer Bond Strength Using Cohesive Zone Modeling and Machine Learning](https://doi.org/10.1109/ectc51846.2026.00128)**
   - 세션: Session 18 - Hybrid Bonding: Advanced Processing and Modeling
   - 공개 영문 초록 기반 한국어 요약: nanoindentation cohesive-zone FEA로 대규모 학습데이터를 만들고 ANN이 delamination energy와 기하·물성에서 W2W bond strength를 빠르게 추정하게 했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/078566c69aa0945a615c92bda4baeb874f8fbd2c)

5. **S20-01 — [Hybrid Bonding Surface Roughness Characterization: A RHEED Approach With High Speed and Atomic Scale (sub-nm) Sensitivity at Wafer Level](https://doi.org/10.1109/ectc51846.2026.00141)**
   - 세션: Session 20 - Performance Analysis and Metrology of High-Bandwidth Electrical and Optical Interconnects
   - 공개 영문 초록 기반 한국어 요약: RHEED 산란 profile과 analytic/AI fitting으로 wafer-level hybrid-bonding 표면의 RMS roughness·correlation length·roughness exponent를 AFM보다 넓고 빠르게 실시간 추출한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/8d34567993f0c3d5c052441426ab50366bb76266)

6. **S20-03 — [Novel Metrology For Experimentally Visualizing Cu-Cu Bonding Induced Thermal Stress](https://doi.org/10.1109/ectc51846.2026.00143)**
   - 세션: Session 20 - Performance Analysis and Metrology of High-Bandwidth Electrical and Optical Interconnects
   - 공개 영문 초록 기반 한국어 요약: 한쪽 Si를 glass로 바꾼 Cu-Cu test structure에 Raman을 적용해 bonding 후 bump 주변 tensile residual-stress의 공간 구배와 주기성을 직접 시각화했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/ffce07a36270179279d24c2f12798b555d1f3ad3)

7. **S22-06 — [Time-Resolved 3D X-ray Imaging of Electromigration Void Evolution in 2.5D Package](https://doi.org/10.1109/ectc51846.2026.00160)**
   - 세션: Session 22 - Reliability of High Current and High Power Packaging Solutions
   - 공개 영문 초록 기반 한국어 요약: micro-CT X-ray microscopy로 2.5D microbump의 electromigration void 생성·균열 성장·재료 이동을 sub-micron 3D로 실시간 비파괴 관찰한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/7920e930239aff69fb8866f8f8aa8f68fd8f44e1)

8. **S24-05 — [In-Situ Anomaly Detection for Power MOSFET’s Degradation Based on Unsupervised LSTM-Autoencoder](https://doi.org/10.1109/ectc51846.2026.00173)**
   - 세션: Session 24 - AI and Machine Learning for Electronics Packaging
   - 공개 영문 초록 기반 한국어 요약: RDS(on)과 body-diode 전압 시계열을 unsupervised LSTM autoencoder로 학습해 label 없이 power-MOSFET의 약한 초기 열화와 고장 전조를 탐지한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/d5c1aa825d5f30f8b2e5ff8da427ec5c4da2eee6)

9. **S27-01 — [Non-Destructive Characterization of Laser-Induced Molecular Modification in Glass for Selective Etching to Fabricate Through-Glass Vias (TGV) in Advanced Packaging](https://doi.org/10.1109/ectc51846.2026.00190)**
   - 세션: Session 27 - Innovation in Glass and Dielectric Materials for Heterogeneous Integration
   - 공개 영문 초록 기반 한국어 요약: Raman·AFM·micro-CT·holotomography·nanoindentation을 묶어 selective-laser-etching glass의 분자변형과 결함을 비파괴 분석하고 TGV etch selectivity 예측 기반을 만든다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/51d267bfd38cd607953969363a08c3244d0dfbd3)

10. **S29-04 — [High-Precision Wafer-Level Bonding in Thin-3D: A Moiré Pattern and Deep-Learning Alignment Approach](https://doi.org/10.1109/ectc51846.2026.00207)**
   - 세션: Session 29 - Innovation in Metallization, Alignment, Additive Manufacturing, and Low Temperature Interconnection
   - 공개 영문 초록 기반 한국어 요약: octagonal moiré mark, IR contrast inversion, physics synthetic data와 실제 영상을 섞은 deep learning으로 단일 mark에서 translation·rotation을 수십 nm 정밀도로 추정했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/05ad10d6ac68d6d92bda5bfc7cf55a9ea379a2e3)

11. **S31-02 — [Enabling Scalable Die-to-Wafer Hybrid Bonding Through Die Distortion Correction and Grid Measurement](https://doi.org/10.1109/ectc51846.2026.00219)**
   - 세션: Session 31 - 3D Integration, TSV, and Hybrid Bonding Innovations
   - 공개 영문 초록 기반 한국어 요약: singulation·placement·bonding 단계마다 고정밀 grid를 측정해 die distortion 기여를 분리하고 simulation correction으로 80 nm 미만 D2W overlay 가능성을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/dae2c379c625e1bcfdf8f51f50d8cf11dc4759dd)

12. **S32-06 — [TSV Stress Prediction via Machine Learning Based on EBSD Grain Microstructure](https://doi.org/10.1109/ectc51846.2026.00230)**
   - 세션: Session 32 - Solder and Through Via Interconnections: Material & Process Innovations
   - 공개 영문 초록 기반 한국어 요약: EBSD로 복원한 annealed Cu-TSV grain structure와 결정 이방성 simulation data를 ML로 학습해 주변 Si stress와 KOZ를 빠르게 예측한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/2f30a41aa4003ee5360cfbb5785ac2d8d833bd26)

13. **S34-01 — [3D Analysis of Hybrid Copper Bonding Through X-Ray Photon-Counting Nano-CT Imaging](https://doi.org/10.1109/ectc51846.2026.00239)**
   - 세션: Session 34 - Optimizing Power Delivery, Thermal Management, and Metrology Solutions for Next-Generation Devices
   - 공개 영문 초록 기반 한국어 요약: photon-counting nano-CT와 iterative reconstruction으로 hybrid-Cu bond를 239.3 nm 해상도로 3D 촬영해 RDL과 submicron void를 비파괴로 구분했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/c453c136492fad46793dc04f717ef6ae26d91fe3)

14. **S34-04 — [Efficiency Meets Fidelity: A Computational Paradigm for 3D X-Ray Imaging of HBM Packages](https://doi.org/10.1109/ectc51846.2026.00242)**
   - 세션: Session 34 - Optimizing Power Delivery, Thermal Management, and Metrology Solutions for Next-Generation Devices
   - 공개 영문 초록 기반 한국어 요약: 저각도·희소 X-ray scan에 EDSR super-resolution을 적용해 projection 수와 sampling 방식이 HBM 구조 복원과 defect segmentation에 미치는 영향을 정량화했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/65ca1a2fcb2544f5d31e104a7f6138b9548d2507)

15. **S34-07 — [An Innovative Automated Tracing Method for Defect Identification in Advanced FOCoS-Bridge Package](https://doi.org/10.1109/ectc51846.2026.00245)**
   - 세션: Session 34 - Optimizing Power Delivery, Thermal Management, and Metrology Solutions for Next-Generation Devices
   - 공개 영문 초록 기반 한국어 요약: O/S·I/V localizing, 자동 lapping, AI 3D-XRM, fiducial 기반 FIB/SEM/EDS를 연계해 FOCoS-Bridge 내부 microbump 불량의 첫 cross-section 성공률과 root-cause 분석 속도를 높인다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/e3121b5902e7f09b4010b484ff54b1b689b0224b)

16. **S35-02 — [A Real-Time Resistance Monitoring Architecture for Prognostics and Health Management of Electronic Packages](https://doi.org/10.1109/ectc51846.2026.00247)**
   - 세션: Session 35 - Reliability of Advanced Automotive, AI, and Interconnect Packaging Solutions
   - 공개 영문 초록 기반 한국어 요약: 768채널 daisy-chain resistance를 2분 주기로 수집·저장·예측해 open-circuit threshold 이전의 고장확률을 실시간 산출하는 deployable PHM architecture를 제시한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/ec0b7b35ae0034088b2677a93c129a86110262cb)

17. **S35-04 — [Enhanced Fault Localization Approach for Advanced Packaging with RDL Interconnection Nano-Defects](https://doi.org/10.1109/ectc51846.2026.00249)**
   - 세션: Session 35 - Reliability of Advanced Automotive, AI, and Interconnect Packaging Solutions
   - 공개 영문 초록 기반 한국어 요약: 복잡한 FOCoS fine-line RDL의 nm급 open defect를 전기 fault localization과 3D X-ray·FIB 분석으로 좁혀 conventional wide-area scan의 시간 문제를 줄이는 FA 흐름을 제안한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/726fe06b2d8d72fad59f2d64827db62227566218)

18. **S37-05 — [Methodology for Root Cause Analysis of 3D Multi-Chip Module Severely Damaged in Data Center Application](https://doi.org/10.1109/ectc51846.2026.00264)**
   - 세션: Session 37 - Interactive Presentations - Thermo-Mechanical Stress and Reliability Analysis for Materials in Future Packaging
   - 공개 영문 초록 기반 한국어 요약: 심하게 손상된 3D multi-chip module에 전기·물리 fault-isolation 기법을 단계별로 적용해 wafer saw에서 유입된 결함을 root cause로 규명했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/a1340ff0ad5e666a888465fa90c18b840b86547a)

19. **S38-10 — [Real-Time Lock-in Thermography and X-Ray CT for Early Failure Detection in Large-Size Packages](https://doi.org/10.1109/ectc51846.2026.00297)**
   - 세션: Session 38 - Interactive Presentations - Photonics, mmWave Applications, and Emerging Technologies
   - 공개 영문 초록 기반 한국어 요약: lock-in thermography와 X-ray CT를 열사이클 단계별로 적용해 large package의 초기 고장 위치를 비파괴 추적하고 소형 test coupon으로 Cu-bump 미세결함 해상도 한계를 보완했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/a1a0266d128a59fac193c247cdde56c72379f27e)

20. **S38-22 — [A Digital Image Correlation-Based Research Platform for Cure Shrinkage and Thermal Expansion Measurements on Epoxy Test Materials](https://doi.org/10.1109/ECTC51846.2026.00309)**
   - 세션: Session 38 - Interactive Presentations - Photonics, mmWave Applications, and Emerging Technologies
   - 공개 영문 초록 기반 한국어 요약: NIST가 DIC 기반 epoxy CTE와 유효 cure-shrinkage 계측 platform의 setup·calibration·분석 절차를 제시한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/ef442d5d0fc40386837a912a313ddad412a62a73)

21. **S38-26 — [A Switchable Longitudinal & Shear BLS Microscope for Comprehensive Modulus Imaging of Semiconductor Packaging Materials](https://doi.org/10.1109/ectc51846.2026.00313)**
   - 세션: Session 38 - Interactive Presentations - Photonics, mmWave Applications, and Emerging Technologies
   - 공개 영문 초록 기반 한국어 요약: backscatter와 off-axis BLS를 전환해 longitudinal·Young's·shear·bulk modulus와 Poisson ratio를 비접촉 영상화하고 nanoindentation·DMA와 비교했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/b65dba299b5f8ccfd1ac3a3e44dc7cc7580c1057)

22. **S39-26 — [Exploring Cu-Cu Hybrid Bonding Failure Mechanisms under Current Stress via 3D Focused Ion Beam Tomography](https://doi.org/10.1109/ectc51846.2026.00347)**
   - 세션: Session 39 - Interactive Presentations - Bonding Processes and Analysis in Next Generation Interconnects
   - 공개 영문 초록 기반 한국어 요약: FE-SEM과 3D-FIB nanotomography로 0.8~4 µm Cu/SiO2 hybrid bond를 current stress한 뒤 pad·via·line 내부 미세조직과 electromigration failure를 3D 분석한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/f021a41bef3fe61f94b79d00de15ec8a27b16ad5)

23. **S39-31 — [High-Throughput Metrology of CMP-Treated Surface Topography Using Fizeau Interferometry for Hybrid Bonding](https://doi.org/10.1109/ectc51846.2026.00352)**
   - 세션: Session 39 - Interactive Presentations - Bonding Processes and Analysis in Next Generation Interconnects
   - 공개 영문 초록 기반 한국어 요약: 300 mm wafer CMP topography를 Fizeau interferometry로 고속 측정해 높은 Cu density와 큰 alignment mark가 erosion·void·bulge-out을 키우며 100 µm mark가 더 양호함을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/192b257c4d5545d897afc55b05c0df161733b00a)

24. **S39-33 — [Advanced Metrology for Heterogeneous Chiplet Integration with High-Speed 100% Bond Overlay Measurement](https://doi.org/10.1109/ectc51846.2026.00354)**
   - 세션: Session 39 - Interactive Presentations - Bonding Processes and Analysis in Next Generation Interconnects
   - 공개 영문 초록 기반 한국어 요약: stage 이동 중 이미지를 획득하는 C2W overlay metrology로 sampling이 아닌 chiplet 100% 측정과 높은 throughput을 동시에 노린다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/fc1726a1da5be88bd1e87e6533e1082dd588dc85)

25. **S41-03 — [Study of Moisture Analysis Technology Based on Fan-out Package](https://ectc.net/wp-content/uploads/2026/05/76-ECTCFinal-Web.v2.pdf)**
   - 세션: Session 41 - Student Interactive Presentations
   - 요약: 작성하지 않음 — 확인 가능한 공개 초록이 없어 제목만으로 내용을 추정하지 않았다.
   - 초록 출처: 공개 초록 미확보 — 공식 프로그램의 제목·저자만 확인

26. **S41-04 — [Location-Dependent Microstructure and Mechanical Properties Evolution of TGV-Cu via an EBSD-Nanoindentation Co-Localization Characterization](https://doi.org/10.1109/ectc51846.2026.00395)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: thermal shock 0~2100 cycle의 TGV-Cu를 EBSD와 nanoindentation으로 같은 위치에서 추적해 grain growth·dislocation·hardness의 위치별 비단조 변화와 via mouth 응력집중을 밝혔다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/d5760ca77da5f77360121d5a53511baaf1bbf308)

27. **S41-14 — [Next-Generation Scanning Electron Microscope for Advanced Packaging: Coating-Free, Ambient, and Ready-to-Use](https://doi.org/10.1109/ectc51846.2026.00405)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: graphene membrane으로 진공 electron optics와 대기 시료를 분리한 open-chamber SEM-in-air가 coating 없이 약 100 nm 해상도로 solder/Cu 계면과 국부 결함을 촬영함을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/0e5201324ebef54baae497c91ed393b2473bfa39)

28. **S41-23 — [High-Resolution Nanoscale X-Ray Imaging for Non-Destructive Inspection of Copper Grains in Fine-Pitch Pads for Hybrid Bonding](https://doi.org/10.1109/ectc51846.2026.00430)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: synchrotron BCDI로 fine-pitch Cu grain을 약 6 nm 해상도로 비파괴 복원해 150 nm급 grain의 0.1~0.5% 압축 strain과 결정결함을 3D 정량화했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/ab2cecd5058e9390d056de6a3a6563239cdf80e4)

29. **S41-24 — [Advanced Acoustic Emission (AE) Sensing and Analytics Scheme for In-situ Warpage Characterizations of Flip-Chip Packaging](https://doi.org/10.1109/ectc51846.2026.00414)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: piezo excitation과 acoustic-emission sensor로 flip-chip thermal cycling 중 구조응답을 수집해 warpage 변화를 실시간·비파괴 추론한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/3a7a51e7cdc539f26079a3ce9fb8419f5c223247)

30. **S41-33 — [A Novel Hierarchical Global Multi-Scale Network for X-Ray Image Enhancement in Packaging](https://doi.org/10.1109/ectc51846.2026.00423)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: 5초급 저품질 X-ray를 HGMSN multi-scale/hierarchical fusion으로 향상해 검사 시간을 17배 줄이면서 고품질에 가까운 영상을 얻는다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/50dcf7d6f96bcc2ae7e54e63ca341a455950d7cb)

### MI 인접 특성평가·고장분석 (31편)

1. **S08-03 — [Characterization of Bonding Behavior and Void Formation in Chip-on-Wafer Hybrid Bonding](https://doi.org/10.1109/ectc51846.2026.00059)**
   - 세션: Session 08 - Die-to-Wafer Hybrid Bonding: Current Advancements and Future Directions
   - 공개 영문 초록 기반 한국어 요약: CoW hybrid bonding의 초기 bonding-front angle을 조절해 8×12 mm die의 void-free yield를 2.8%에서 99%로 높이고 ultra-thin/heterogeneous 구조에도 적용했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/0d2d19104988fff629241b5d960bef8648df6a36)

2. **S10-07 — [Predictive Reliability Modeling of Hybrid Bonding Through Warpage and Interfacial Defect Correlation](https://doi.org/10.1109/ectc51846.2026.00077)**
   - 세션: Session 10 - Reliability of Large Body High Performance Computing and AI Packaging Solutions
   - 공개 영문 초록 기반 한국어 요약: shadow-moiré full-field warpage와 SEM defect inspection을 연결해 pre-bond deformation이 void·delamination·불완전 bond로 이어지는 관계를 모델링한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/4534da0226ace95e958ee65e8e106d86ea152367)

3. **S12-02 — [Micro/Nanostructural Stress Characterization for Advanced 3D Integration Technologies](https://doi.org/10.1109/ectc51846.2026.00086)**
   - 세션: Session 12 - Characterization and Modeling for Process and Multi-Domain Analyses
   - 공개 영문 초록 기반 한국어 요약: piezoresistive sensor, 4-point-bending calibration, FEM inverse analysis로 µTSV와 buried power rail의 intrinsic stress를 비파괴 추정해 구조 축소 시 응력 증가를 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/cfca00dbc810950aecee9ec744e3bfe100c9f120)

4. **S12-07 — [Experimental and Computational Fracture Strength Characterization at BEOL Structure Sharp Corners for Chip-Package Interaction Reliability Assessment](https://doi.org/10.1109/ectc51846.2026.00091)**
   - 세션: Session 12 - Characterization and Modeling for Process and Multi-Domain Analyses
   - 공개 영문 초록 기반 한국어 요약: BEOL sharp corner 시편의 4PB load와 enriched isogeometric analysis를 결합해 pre-crack 가정 없이 corner-specific GSIF와 generalized J-integral을 산출했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/e129a2d8c192f147495fc179635c536397671f7a)

5. **S13-01 — [Process Development and Thermal Characterization of Micropillar Direct-to-Silicon Liquid Cooling Solution on CoWoS-R Platform](https://doi.org/10.1109/ectc51846.2026.00092)**
   - 세션: Session 13 - Advances in Thermal Design and Characterization
   - 공개 영문 초록 기반 한국어 요약: 3.3-reticle CoWoS-R의 direct-to-silicon micropillar cooling을 구축해 6 LPM·40°C water에서 5 kW 이상을 방열하고 helium leak·MSL4로 sealing 신뢰성을 확인했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/59ae5cf17a867535cf47d79a7c045207ddcf43c4)

6. **S14-05 — [Study of SeWaRe Failure in a Glass-Core Substrate with Redistribution Layers](https://doi.org/10.1109/ectc51846.2026.00103)**
   - 세션: Session 14 - RDL and Fan-Out Interconnections
   - 공개 영문 초록 기반 한국어 요약: 1 mm glass core·single-side 6-RDL의 dicing 후 SeWaRe와 Cu/dielectric delamination을 관찰하고 sequential fabrication+dicing simulation으로 crack energy-release 조건을 설명했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/27f970d64ce0a76f255763c1f266e8818a30cadd)

7. **S17-04 — [Fabrication and Experimental Characterization of Embedded Multi-Terminal Capacitors With Ultra-Low Parasitics for Integrated Vertical Power Delivery](https://doi.org/10.1109/ectc51846.2026.00123)**
   - 세션: Session 17 - Digital Twin and AI in Advanced Packaging and Interconnect Security
   - 공개 영문 초록 기반 한국어 요약: glass에 매립한 multi-terminal DTC를 1-port·2-port VNA로 측정해 vertical current path의 ESL 0.5 pH 미만, ESR 5 mΩ 미만을 추출했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/80a3e5998a8eb313b95e65263655493d3e187c22)

8. **S18-05 — [System-Level Thermal Characterization of Hybrid Cu Bonded HBM on 2.5D Advanced Packaging](https://doi.org/10.1109/ectc51846.2026.00131)**
   - 세션: Session 18 - Hybrid Bonding: Advanced Processing and Modeling
   - 공개 영문 초록 기반 한국어 요약: HCB와 TCB HBM의 chip-to-server thermal model을 실제 test vehicle로 검증해 HCB의 hotspot·thermal crosstalk 감소와 허용전력 증가를 정량화했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/d4ea709909aa189789e67ec76c131e9c130441da)

9. **S20-04 — [Vertical Interconnects Characterization for 448 Gbps/lane Co-Packaged Optics Using Double-Sided Probing Method](https://doi.org/10.1109/ectc51846.2026.00144)**
   - 세션: Session 20 - Performance Analysis and Metrology of High-Bandwidth Electrical and Optical Interconnects
   - 공개 영문 초록 기반 한국어 요약: double-sided probing으로 SUB-VIA·TMV·TSV·TGV를 최대 110 GHz까지 직접 S-parameter 측정해 448 Gb/s PAM4 CPO 전이 중 TGV가 가장 낮은 손실을 보임을 확인했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/f733b9cf3eec93c502a084c1376741b9a6a51fa5)

10. **S26-05 — [Process Integration for 300-nm-Pitch Hybrid Bonding with SiCN: 50nm Bonding Overlay, Fine-Grain Cu Metallurgy, and Reliability Assessment](https://doi.org/10.1109/ectc51846.2026.00187)**
   - 세션: Session 26 - Advanced Wafer-to-Wafer Hybrid Bonding
   - 공개 영문 초록 기반 한국어 요약: 300 nm pitch W2W test vehicle에서 90% 이상 수율에 약 50 nm overlay가 필요함을 구하고 fine-grain Cu로 210°C 저온 bonding과 신뢰성을 검증했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/2ba2aa309d99efcbc2866a4f12a08ab6cbc49fb1)

11. **S26-06 — [Synchrotron-Based Characterization of Cu/SiCN Pretreatment for Hybrid Bonding via Ozone/Ethylene Radical Activation](https://doi.org/10.1109/ectc51846.2026.00188)**
   - 세션: Session 26 - Advanced Wafer-to-Wafer Hybrid Bonding
   - 공개 영문 초록 기반 한국어 요약: ESR과 synchrotron AR-XPS로 ozone-ethylene-radical 처리가 SiCN dangling bond를 종결하고 Cu oxide를 유한 두께 Cu(OH)2로 바꾸는 과정을 분석했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/846eecde50cc7c52e6bee40dbe7acd1f18af6eb0)

12. **S30-03 — [Experimental Characterization of Thermal Transport in Cu/Sn-Diamond Microbumps](https://doi.org/10.1109/ectc51846.2026.00213)**
   - 세션: Session 30 - Thermal Management and Cooling Simulation
   - 공개 영문 초록 기반 한국어 요약: miniaturized Ångström method와 high-resolution IR thermography로 Cu/Sn-diamond microbump 층의 면내 유효열전도도 500~600 W/(m·K)를 측정했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/21048b8671a8bef5d4c7c114af1740bebab9a480)

13. **S31-06 — [Wafer Bonder and Lithography Co-Optimization for Sub-5nm Post-Bonding Overlay in Backside Power Delivery Architectures](https://doi.org/10.1109/ectc51846.2026.00223)**
   - 세션: Session 31 - 3D Integration, TSV, and Hybrid Bonding Innovations
   - 공개 영문 초록 기반 한국어 요약: bonder recipe와 lithography scanner correction을 함께 최적화해 BSPDN 유사 공정에서 2.8 nm 미만 M+3σ post-bond overlay를 달성했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/a7404afc4bcea36ceb3a8c08f5f944bde2d67c6a)

14. **S33-06 — [Characterization of Solderless Connection by Laser Welding and Its Application on Power Module](https://doi.org/10.1109/ectc51846.2026.00237)**
   - 세션: Session 33 - Emerging Materials and Interconnect Technologies for Advanced Packaging
   - 공개 영문 초록 기반 한국어 요약: laser-welded solderless connection을 고전류·shear·thermal-cycle로 평가해 solder 대비 저항 약 50% 감소와 2.3배 shear strength를 보고했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/a43dd9df751e786e889ddde8d16c150f64215eba)

15. **S36-03 — [Interfacial Fracture Characterization Using Wedge Testing of Electroless Plated Films on Additively Manufactured Conductive Polymers](https://doi.org/10.1109/ectc51846.2026.00255)**
   - 세션: Session 36 - Flexible Electronics and Thin-Assembly Warpage
   - 공개 영문 초록 기반 한국어 요약: custom wedge/DCB 시험으로 FFF conductive polymer 위 electroless Cu 계면을 평가했으며, 실제 파괴가 Cu/printed interface가 아닌 polycarbonate/epoxy에서 일어날 만큼 접착이 강함을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/2c8c046ec87aeb6a447ad6ed3ad7b1064b0884e9)

16. **S37-03 — [In-Situ Observation and Modeling of Crack Velocity at Wafer-to-Wafer Bonding Interface](https://doi.org/10.1109/ectc51846.2026.00262)**
   - 세션: Session 37 - Interactive Presentations - Thermo-Mechanical Stress and Reliability Analysis for Materials in Future Packaging
   - 공개 영문 초록 기반 한국어 요약: Maszara blade test를 vision system으로 실시간 촬영해 bond energy가 비슷한 dielectric도 crack velocity가 10배 다를 수 있음을 보이고 analytical/cohesive model로 설명했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/4cbc2278a6598123d01ba2a20d649adbeb5ffb5f)

17. **S37-08 — [FEA-Integrated 3PB and BOR Testing for Fracture Strength Characterization of Ultrathin Dies: Effects of Thickness, Surface Conditions, and Anisotropy](https://doi.org/10.1109/ectc51846.2026.00267)**
   - 세션: Session 37 - Interactive Presentations - Thermo-Mechanical Stress and Reliability Analysis for Materials in Future Packaging
   - 공개 영문 초록 기반 한국어 요약: 3PB·ball-on-ring 시험과 FEA·SEM fractography를 결합해 ultrathin die의 large deformation·anisotropy를 반영한 fracture strength를 구하고 closed-form 오차가 최대 29.2%임을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/847341e55d1f0f1c3fe38c4c09497000aca10abb)

18. **S37-11 — [Thermal Characterization and Power Dissipation Enhancement of Hybrid-Bonded Chip Stack](https://doi.org/10.1109/ectc51846.2026.00270)**
   - 세션: Session 37 - Interactive Presentations - Thermo-Mechanical Stress and Reliability Analysis for Materials in Future Packaging
   - 공개 영문 초록 기반 한국어 요약: hybrid-bonded 3D stack의 uniform/hot-zone heating을 실험·simulation으로 검증하고 flat Si heat pipe가 hot-zone 냉각을 25% 이상 개선함을 보고했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/b2d31000570888068a18d72eb393241e472f8583)

19. **S37-20 — [Reliability Characteristics of Through Glass Vias With Polymer Liners](https://doi.org/10.1109/ectc51846.2026.00279)**
   - 세션: Session 37 - Interactive Presentations - Thermo-Mechanical Stress and Reliability Analysis for Materials in Future Packaging
   - 공개 영문 초록 기반 한국어 요약: 비파괴 thickness metrology, in-situ Raman, two-photon imaging으로 CVD polymer-lined TGV의 stress와 subsurface crack을 추적해 liner가 glass cracking을 줄임을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/845a77e523c0edffc57b08ee7b13698ece404c8a)

20. **S37-25 — [Assembly and Reliability Characterization of Glass-Cored Substrate Package for AI/HPC Applications](https://doi.org/10.1109/ectc51846.2026.00284)**
   - 세션: Session 37 - Interactive Presentations - Thermo-Mechanical Stress and Reliability Analysis for Materials in Future Packaging
   - 공개 영문 초록 기반 한국어 요약: 74×74 mm glass-core와 organic-core substrate의 조립 거동, package warpage, JEDEC mechanical reliability를 비교해 제조상 핵심 차이를 정리했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/d2871241b3f4853d33c71db0316acecbfe5c4b28)

21. **S38-30 — [High-Efficiency 2 by 1 Antipodal Vivaldi Array on Ultra-thin PTFE for sub-6 GHz 5G: Cricut-Based Rapid Prototyping and Characterization](https://doi.org/10.1109/ectc51846.2026.00317)**
   - 세션: Session 38 - Interactive Presentations - Photonics, mmWave Applications, and Emerging Technologies
   - 공개 영문 초록 기반 한국어 요약: consumer Cricut cutter와 Cu foil로 5 GHz Vivaldi 2×1 array를 1시간 이내 제작해 98~99% 치수정확도와 7.5 dBi measured gain을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/e4d7a1a076fc8f0f317bdc485a45c03bb48226fb)

22. **S38-32 — [BEM-Based Characterization of a D-Band On-Chip Patch Antenna Array](https://doi.org/10.1109/ectc51846.2026.00319)**
   - 세션: Session 38 - Interactive Presentations - Photonics, mmWave Applications, and Emerging Technologies
   - 공개 영문 초록 기반 한국어 요약: backscattering modulation으로 100 GHz 이상 D-band on-chip antenna를 비접촉 OTA 측정하고 BEM simulation과 교차검증해 FEM보다 큰 계산절감을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/1c671b3c7a5e57d9ea7921877d4b693dfe2948ee)

23. **S39-01 — [Trace-Element Effects in SAC Alloys: Mitigating HIP Defects in 5G/Automotive SoC SMT Assemblies](https://doi.org/10.1109/ectc51846.2026.00322)**
   - 세션: Session 39 - Interactive Presentations - Bonding Processes and Analysis in Next Generation Interconnects
   - 공개 영문 초록 기반 한국어 요약: 실시간 SMT scope와 AES·미세조직 분석으로 SAC의 trace P가 oxide는 줄이지만 Cu6Sn5를 늘려 HIP를 악화시키고 Ge가 더 균형적인 첨가제임을 밝혔다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/ea8bc8066ca5178df7f6f229cd21d4a3dc76e4d4)

24. **S39-15 — [Integration and Characterization of Two Connection Schemes for Backside Power Delivery Network](https://doi.org/10.1109/ectc51846.2026.00336)**
   - 세션: Session 39 - Interactive Presentations - Bonding Processes and Analysis in Next Generation Interconnects
   - 공개 영문 초록 기반 한국어 요약: 두 BSPDN 연결구조의 resistance·capacitance·heating rate를 측정해 250 nm 잔류 Si가 heating rate를 100에서 50 K/mW로 낮춤을 확인했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/21b9cd7f7f811d3516270a12fe54b88e308f236f)

25. **S39-23 — [Time and Environment Characterization of Biodegradable Materials for Transient RF Systems](https://doi.org/10.1109/ectc51846.2026.00344)**
   - 세션: Session 39 - Interactive Presentations - Bonding Processes and Analysis in Next Generation Interconnects
   - 공개 영문 초록 기반 한국어 요약: biodegradable dielectric·printable conductor의 시간·환경 의존 RF 특성을 resonant structure로 측정해 계획된 degradation을 RF 설계 변수로 연결한다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/b1247a6cccccb58274c62719c7c06e9a8aea1ab9)

26. **S39-24 — [Impact of Cu Density on Via-to-Via Hybrid Bonding: Morphological and Electrical Characterizations](https://doi.org/10.1109/ectc51846.2026.00345)**
   - 세션: Session 39 - Interactive Presentations - Bonding Processes and Analysis in Next Generation Interconnects
   - 공개 영문 초록 기반 한국어 요약: CMP erosion과 metal density 영향을 morphology·전기측정으로 비교해 localized Cu density 6%에서는 bonding이 가능하지만 25%에서는 실패함을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/5bcc8dd9ca9bf9fb47c71668cae41098fb224c94)

27. **S39-30 — [Comprehensive Characterization of Surface Activation for Chip-to-Wafer Hybrid Bonding in 3D Flash Memory](https://doi.org/10.1109/ectc51846.2026.00351)**
   - 세션: Session 39 - Interactive Presentations - Bonding Processes and Analysis in Next Generation Interconnects
   - 공개 영문 초록 기반 한국어 요약: contact angle, nanoscale roughness, shear strength로 wet/VUV/RIE/non-bias plasma의 SiO2 activation을 비교해 121°C C2W bonding용 전처리 조합을 최적화했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/6330157e2b291d6d5851b5a9afd188991314eb5e)

28. **S39-32 — [Interfacial Analysis of Hybrid Bonding Using Water Surface Tension-Driven Self-Assembly for HBM](https://doi.org/10.1109/ectc51846.2026.00353)**
   - 세션: Session 39 - Interactive Presentations - Bonding Processes and Analysis in Next Generation Interconnects
   - 공개 영문 초록 기반 한국어 요약: water surface-tension self-assembly와 conventional flip-chip의 void ratio를 SAM·SEM으로 비교해 물 사용이 bondability를 악화시키지 않고 void는 topography·particle 영향임을 보였다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/8cca8c8d9b96d0084193595beba61930dd8c131f)

29. **S40-30 — [Temperature-Dependent Electrical Characterization of New ABF-Type A Material up to 220 GHz](https://doi.org/10.1109/ectc51846.2026.00389)**
   - 세션: Session 40 - Interactive Presentations - Materials, Manufacturing, and Assembly Techniques in Advanced Packaging Solutions
   - 공개 영문 초록 기반 한국어 요약: microstrip ring resonator와 transmission line으로 ABF Type-A의 10~220 GHz Dk·Df·insertion loss를 80°C와 115°C에서 측정했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/6e5fc6e3840c1c0e7900431c716ead7dc8eff2ec)

30. **S41-26 — [Direct Glass-Copper Vias Integrated with Blind-Cavity Embedded Chips Using Nanoscale Liner](https://doi.org/10.1109/ectc51846.2026.00416)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: blind-cavity glass embedded chip과 Cu via를 제작하고 X-ray·micro-CT로 conformal fill을 비파괴 확인한 뒤 -50~150°C 100회 shock에서 delamination이 없음을 보고했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/c979dba3defef09019d8bc7e22eb83aa2c04946a)

31. **S41-31 — [Compact 6-GHz Microstrip Bandpass Filter with Folded-Arm Resonators and Dual Transmission Zeros: Design, Fabrication and Measurement](https://doi.org/10.1109/ectc51846.2026.00421)**
   - 세션: Session 41 - Student Interactive Presentations
   - 공개 영문 초록 기반 한국어 요약: folded-arm resonator와 cross coupling으로 6.4 GHz compact bandpass filter를 제작해 7.2% bandwidth, 2.7 dB insertion loss를 측정했다.
   - 초록 출처: [Semantic Scholar 초록 색인](https://www.semanticscholar.org/paper/96487627cccf34874bf20bb64084f37b392a5dc4)

## 제목 키워드 오탐으로 제외한 발표

아래 발표들은 최초 자동 검색에는 걸렸지만, 초록과 제목의 실제 의미를 검토한 뒤 semiconductor process metrology/inspection 목록에서는 제외했다.

- **2025-S14-04 — [Development of a Novel WoWoW Process for 1/1.3-inch 50 Megapixel Three-Wafer-Stacked CMOS Image Sensor With DNN Circuits](https://doi.org/10.1109/ectc51687.2025.00099)**
  - 제외 이유: CMOS image sensor의 제품/공정 개발이며 `image`가 inspection imaging을 뜻하지 않는다.
- **2025-S33-06 — [Dry Film Photo-Imageable Dielectric Enabling Glass Core Substrate TGV Filling and Build-Up](https://doi.org/10.1109/ectc51687.2025.00233)**
  - 제외 이유: `photo-imageable dielectric`은 재료명·패터닝 특성이지 검사 영상이 아니다.
- **2025-S36-06 — [Simulation of Mechanical Cu Pad Expansion Mechanism and Measures to Increase Expansion](https://doi.org/10.1109/ectc51687.2025.00254)**
  - 제외 이유: 제목의 `measures`는 개선책이라는 뜻이며 measurement가 아니다.
- **2025-S38-02 — [Bio-Packaging Development of a Wearable Fluidic Monitoring System for Improved Blood Glucose Management in Critically Ill Diabetic Patients](https://ectc.net/wp-content/uploads/2025/06/75-ECTCFinal-Web.pdf)**
  - 제외 이유: 중환자 혈당 모니터링용 wearable fluidic sensor로, 패키징 공정 MI가 아니다.
- **2025-S40-02 — [Lithography-Free Anisotropic Magnetoresistance Sensor-Based Rotational Speed Measurement System on PEEK With Integrated Electronics](https://doi.org/10.1109/ectc51687.2025.00339)**
  - 제외 이유: 회전속도 측정용 AMR sensor 응용으로, 패키징 공정 MI가 아니다.
- **2026-S38-29 — [Piezo-Magnetostrictive Transducer-Powered Wireless Implanted Sensors for Monitoring Hemodynamics](https://doi.org/10.1109/ectc51846.2026.00316)**
  - 제외 이유: 혈류역학 모니터링용 implant sensor 응용으로, 패키징 공정 MI가 아니다.

## 함께 제공되는 데이터

- `datasets/ectc-mi-paper-metadata.csv`: 128개 검토 대상(포함 122·제외 6)의 연도, 발표 ID, 분류, 제목, 세션, 전체 저자·소속, DOI, 초록 색인 URL, OA PDF 여부.
- `exports/ectc-2025-2026-mi-abstracts-ko.md`: 출처와 한국어 요약을 함께 적은 사람이 읽는 원본 문서.
- `datasets/ectc-mi-abstract-audit-shortlist.csv`: 두 해 전체 DOI 초록 감사에서 추가 검토 대상으로 잡힌 항목과 신호.
- `notes/2025-ectc-75-complete-program-index.md`, `notes/2026-ectc-76-complete-program-index.md`: 두 해 전체 프로그램 원문 색인.
