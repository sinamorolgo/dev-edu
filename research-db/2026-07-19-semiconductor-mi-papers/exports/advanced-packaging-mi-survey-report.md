# 어드밴스드 패키징에서 중요한 Metrology & Inspection(MI)

## 서베이 논문·산업 로드맵·ECTC 문헌 기반 조사 리포트

| 항목 | 내용 |
|---|---|
| 조사 기준일 | 2026-07-19 |
| MI의 의미 | Metrology & Inspection(계측 및 검사) |
| 대상 | 2.5D/3D 패키징, chiplet/interposer, TSV/TGV, fan-out, HBM, wafer-to-wafer·die-to-wafer hybrid bonding |
| 핵심 질문 | 어떤 측정 대상과 결함이 중요한가? 어떤 방법으로 측정하는가? 현재 기술 공백은 무엇인가? |
| 근거 | peer-reviewed review, 공식 roadmap·NIST 보고서, 업계 설문 preprint, ECTC 2023–2026 로컬 문헌 DB |

> **한 줄 결론:** 관련 서베이 논문은 분명히 있다. 다만 전 공정을 포괄해 MI를 보편적인 중요도 순으로 평가한 단일 systematic review는 찾지 못했다. 여러 review와 산업 roadmap의 교집합은 **① hybrid-bonding 표면·정렬·계면, ② buried defect의 비파괴 3D 검사, ③ warpage·coplanarity·thermomechanical 상태**를 최우선군으로 지목한다.

---

## 1. 핵심 요약

### 1.1 무엇이 가장 중요한가

중요도는 장비명이 아니라 먼저 **측정해야 할 대상(measurand)과 잡아야 할 결함(defect)**으로 정의하는 편이 정확하다. 문헌과 roadmap을 교차하면 다음과 같이 정리된다.

| 우선군 | 반드시 관리할 MI | 대표 위험 | 종합 판단 |
|---|---|---|---|
| 최우선 | **Hybrid-bonding 표면·정렬·계면 건전성**: roughness, nanotopography, Cu recess/dishing, particle·residue·oxide, overlay, die shift·tilt, void·gap, bond strength, contact resistance | 미접합, 불완전 Cu 접촉, 계면 void, misalignment, 초기 수율 손실 | HBM·fine-pitch 3D integration의 가장 직접적인 병목 |
| 최우선 | **Buried defect의 비파괴 3D 검사와 위치 특정**: void, delamination, crack, missing/open joint, TSV fill defect, buried RDL defect | 완성된 stack 내부 결함을 표면 AOI로 볼 수 없음 | 산업 설문과 MAPT가 공통으로 가장 큰 capability gap으로 지목 |
| 최우선 | **Global/local geometry와 thermomechanics**: bow/warp, TTV, flatness, coplanarity, die tilt, stress/strain, CTE, temperature-dependent deformation | bond 불량, die shift, solder fatigue, delamination, assembly 불가 | wafer·panel 대형화와 이종재료 적층에서 전 공정에 영향을 줌 |
| 높음 | **TSV/TGV·RDL·µ-bump 형상과 건전성**: CD, depth, taper, sidewall, liner/seed, fill seam·void, protrusion, RDL L/S·thickness·overlay, bump height·volume·coplanarity | open/short, RC 증가, EM, 불균일 접합 | 고밀도 interconnect의 직접 CTQ(critical-to-quality) |
| 높음 | **재료·표면 화학과 공정 상태**: organic contamination, residue, oxide, composition, cure, Tg, modulus, viscoelasticity, moisture, adhesion | 구조 검사 전에 이미 잠재 결함을 만드는 원인 변수 | 구조 영상만으로는 예측하기 어려운 yield·reliability precursor |
| 높음 | **Electrical/KGD 및 thermal validation**: continuity, contact resistance, leakage, TDR/S-parameter, hotspot, interface thermal resistance | 물리 결함의 기능 영향 불명, 고가 good die 동반 폐기 | physical MI와 실제 기능·신뢰성을 연결하는 확인 축 |
| 횡단 조건 | **HVM 적합성**: non-destructive, inline/in-situ, full-area coverage, throughput, uncertainty, traceability, multimodal fusion, AI | 연구실에서 보이지만 fab에서는 못 쓰는 측정 | 별도 측정 항목이 아니라 모든 MI의 채택 조건 |

이 표의 순서는 공식적인 universal ranking이 아니다. 최신 [MAPT Roadmap 2.0](https://srcmapt.org/chapter10/), [IRDS 2024 Metrology](https://irds.ieee.org/images/files/pdf/2024/2024IRDS_MET.pdf), NIST 보고서와 공정별 review에서 **반복되는 정도, 수율·신뢰성 영향, 현존 capability gap**을 기준으로 종합한 판단이다.

### 1.2 가장 직접적인 자료

빠르게 읽을 자료를 고르면 다음 다섯 개가 핵심이다.

1. [MAPT Roadmap 2.0, Chapter 10 — Manufacturing and Process Development Metrology](https://srcmapt.org/chapter10/): 무엇을 측정해야 하는지와 중장기 resolution 목표까지 가장 직접적으로 제시한다.
2. [Process Metrology and Validation for 3D Advanced Packaging: A Comprehensive Review](https://doi.org/10.14775/ksmpe.2026.25.1.124) (Paik et al., 2026): 3D advanced packaging MI를 전기·NDT·warpage·reliability까지 넓게 묶은 최신 종합 review다.
3. [Volumetric nondestructive metrology for 3D semiconductor packaging: A review](https://doi.org/10.1016/j.measurement.2023.114065) (Su et al., 2024): X-ray, SAM, THz를 중심으로 buried/volumetric inspection을 가장 깊게 다룬다.
4. [HBM 하이브리드 본딩을 위한 계측 및 검사 최신 기술 동향](https://doi.org/10.6117/kmeps.2025.32.4.001) (주승환 외, 2025): HBM hybrid bonding에 가장 직접적인 한국어 review다.
5. [A review on warpage measurement metrologies for advanced electronic packaging](https://doi.org/10.1016/j.microrel.2024.115456) (Sun & Zhang, 2024): warpage 측정법을 독립적으로 비교한다.

---

## 2. 범위와 용어

### 2.1 Metrology와 Inspection의 차이

- **Metrology**는 길이, 높이, 거칠기, overlay, warpage, stress, 저항처럼 연속적인 물리량을 수치와 불확도로 측정한다.
- **Inspection**은 particle, void, crack, delamination, open/short처럼 결함의 존재·위치·크기·종류를 검출하고 분류한다.
- **Validation/test**는 측정된 구조가 전기적·열적 기능과 신뢰성 요구를 만족하는지 확인한다.
- **Failure isolation/analysis**는 고장이 난 위치를 찾고 물리적 원인을 확정한다. 생산 MI와 목적은 다르지만 buried 3D 구조에서는 같은 영상·전기·열 기술을 공유하므로 인접 범위로 포함했다.

### 2.2 왜 front-end MI와 다른가

어드밴스드 패키징은 크기가 서로 다른 wafer, die, interposer, substrate와 polymer·metal·Si·glass를 적층한다. 따라서 다음 문제가 동시에 생긴다.

- 표면에서 보이지 않는 계면과 interconnect가 늘어난다.
- nm급 local topography와 수백 mm scale의 wafer/panel warpage를 함께 봐야 한다.
- 같은 결함도 재료 조합과 깊이에 따라 광학·초음파·X-ray contrast가 달라진다.
- die를 적층할수록 Known Good Die(KGD)와 partial-assembly test의 경제적 가치가 커진다.
- 최종 수율뿐 아니라 throughput, sampling coverage, handling, recipe robustness가 측정 기술 채택을 좌우한다.

### 2.3 주요 약어

| 약어 | 뜻 |
|---|---|
| CTQ | Critical to Quality; 수율·품질을 좌우해 반드시 관리해야 할 특성 |
| HVM | High-Volume Manufacturing; 양산 |
| NDI/NDT | Non-Destructive Inspection/Testing; 비파괴 검사 |
| AOI | Automated Optical Inspection; 자동 광학 검사 |
| SAM/CSAM | Scanning Acoustic Microscopy; 주사 음향 현미경 |
| RDL | Redistribution Layer; 재배선층 |
| TSV/TGV | Through-Silicon/Through-Glass Via |
| TTV | Total Thickness Variation; 총 두께 편차 |
| KGD | Known Good Die; 적층 전 양품으로 확인된 die |
| POD | Probability of Detection; 정해진 결함을 검출할 확률 |
| GR&R | Gage Repeatability and Reproducibility; 측정 반복성·재현성 평가 |
| EM | Electromigration; 전류에 의한 금속 원자 이동과 열화 |

---

## 3. 조사 방법과 해석 원칙

### 3.1 사용한 근거 계층

| 근거 | 용도 | 해석 시 주의점 |
|---|---|---|
| 공식 roadmap·정부/표준화 보고서 | 산업 전체의 unmet need와 향후 목표 파악 | 전망치이며 특정 제품의 관리 규격은 아님 |
| Peer-reviewed review/perspective | 기술 원리, 적용 대상, 장단점, 연구 공백 파악 | 대개 NDT·TSV·warpage처럼 범위가 분절됨 |
| 응답자 기반 업계 설문 | 중요도와 현장 pain point를 수치로 확인 | 2026년 자료는 preprint이고 FA 중심 |
| ECTC 2023–2026 로컬 DB 247편 | 최근 연구의 실제 분포와 반복 주제 확인 | MI 후보를 선별한 corpus이므로 전체 학회 대비 점유율로 해석할 수 없음 |

### 3.2 우선순위 산정 원칙

본 리포트의 우선순위는 다음 네 기준의 정성적 합성이다.

1. MAPT·IRDS·NIST 문서에서 반복적으로 명시되는가.
2. 여러 독립 review에서 같은 gap이 확인되는가.
3. 결함이 yield, assembly feasibility, field reliability에 직접 영향을 주는가.
4. 현재 방법이 resolution·penetration·coverage·throughput을 동시에 만족하지 못하는가.

따라서 “X-ray가 1위” 같은 장비 순위가 아니라, **검출해야 할 위험을 먼저 정하고 서로 보완하는 측정법을 배치하는 방식**으로 결론을 냈다.

---

## 4. 관련 서베이·리뷰 문헌 지도

### 4.1 종합 및 비파괴 검사

| 문헌 | 유형·범위 | 핵심 내용 | 이 리포트에서의 역할 |
|---|---|---|---|
| [Paik et al., 2026](https://doi.org/10.14775/ksmpe.2026.25.1.124) | Peer-reviewed comprehensive review; 3D packaging | µ-bump, hybrid bonding, interposer, S-parameter/TDR, X-ray tomography, SAM, thermography, THz, warpage·stress·reliability를 통합 | 가장 넓은 최신 학술 출발점 |
| [Su et al., 2024](https://doi.org/10.1016/j.measurement.2023.114065) | Peer-reviewed review; volumetric NDT | X-ray microscopy, SAM, THz와 3D fault isolation, ML/AI | buried defect priority의 핵심 근거 |
| [Chen et al., 2024](https://doi.org/10.1115/1.4064361) | Peer-reviewed review; packaging NDT | optical, X-ray, active IR, SAM, AFM, laser/vibration, SQUID, impedance 계열 비교 | modality 범위를 넓히는 보조 근거 |
| [Aryan et al., 2018](https://doi.org/10.3390/s18071981) | Open-access peer-reviewed overview; IC package NDT | X-ray, SAM, IR thermography, magnetic current imaging, SAW, ultrafast laser의 장단점 | 오래됐지만 원리와 비교표가 좋은 기초 review |
| [Meshki Zadeh et al., 2025](https://doi.org/10.3390/s25247499) | Open-access peer-reviewed review; SAM | multi-die, TSV, hybrid bonding의 delamination·underfill void·Cu-Cu crack과 SAM/ML | SAM의 강점과 해상도–깊이 trade-off 근거 |
| [Su et al., 2020](https://doi.org/10.1016/j.microrel.2020.113657) | Peer-reviewed review; flip-chip solder joint NDT | crack, void, missing ball과 optical, X-ray, IR, SAM, laser ultrasound | µ-bump/solder joint 검사 기초 |

### 4.2 공정·측정 대상별 review

| 문헌 | 유형·범위 | 핵심 내용 | 주의점 |
|---|---|---|---|
| [주승환 외, 2025](https://doi.org/10.6117/kmeps.2025.32.4.001) | Peer-reviewed 한국어 동향 review; HBM hybrid bonding | 장비 alignment, post-bond overlay, 고속·고해상도 topography, 고밀도 sampling, 실시간 결함 분석, subsurface void | Review의 장비 성능 수치는 각 원 논문까지 추적해 사용해야 함 |
| [Kottur et al., 2026](https://doi.org/10.31399/asm.edfa.2026-2.p012) | EDFA technical review; hybrid bonding | CMP planarity, submicron misalignment, interfacial void, warpage와 SAM·X-ray CT·optical/IR·SEM/FIB 비교 | 전통적인 research journal review보다는 기술 review 성격 |
| [Lu et al., 2025](https://doi.org/10.1115/1.4069965) | Peer-reviewed review; TSV | TSV geometry·fill·liner 관련 optical, X-ray, SEM, AFM, diffraction, TSOM | TSV/TGV 상세 taxonomy 근거 |
| [Sun & Zhang, 2024](https://doi.org/10.1016/j.microrel.2024.115456) | Peer-reviewed review; warpage | moiré, DIC, laser scanning, optical interferometry, contact 방식 비교 | 온도별 full-field warpage 중요성의 핵심 근거 |
| [Tao et al., 2025](https://doi.org/10.1109/TCPMT.2025.3603484) | Peer-reviewed perspective; packaging soft materials | cure kinetics, Tg, chemorheology, moisture, residual stress, CTE, adhesion, reference material·표준화 | 구조 영상 중심 taxonomy가 빠뜨리기 쉬운 재료 MI 보완 |
| [Zhou et al., 2024](https://doi.org/10.1016/j.microrel.2024.115372) | Peer-reviewed hybrid-bonding process review | warpage, planarity, cleanliness, alignment, oxide morphology, Cu dishing, surface activation | MI 전용 review는 아니지만 공정 CTQ를 연결해 줌 |

### 4.3 “중요도”에 가장 가까운 응답자 설문

[Kottur et al., *Failure Analysis in Transition*](https://arxiv.org/abs/2606.22149)은 2026년 6월 공개된 약 100명 규모의 업계 설문 preprint다. 생산 inline MI 전체가 아니라 failure analysis(FA) 관점이라는 한계가 있지만, 현재 찾은 자료 중 현장 우선순위를 수치로 묻는 데 가장 가깝다.

| 설문 결과 | 값 | 의미 |
|---|---:|---|
| Package & heterogeneous-integration FA 중요도 | 7.92/10 | 조사한 FA domain 중 가장 높음 |
| 가장 어려운 emerging architecture: hybrid bonding | 54% | interface void/gap/misalignment가 대표 pain point |
| Destructive보다 NDI 개선이 더 필요 | 72% | buried structure를 보존한 채 보는 capability가 우선 |
| 미래 accelerator: high-resolution NDI | 8.18/10 | buried structure용 고해상도 영상이 1위 |
| AI/ML defect detection·classification | 7.27/10 | 영상 획득뿐 아니라 해석 자동화도 병목 |
| 표준화 지지 | 83% | multimodal data와 비교 가능한 기준 필요 |

이 수치는 **peer review 전 preprint의 자기보고식 설문 결과**이고 본문에 정확한 응답자 수가 제시되지 않았으므로 보편적인 산업 통계로 일반화하면 안 된다. 다만 MAPT·IRDS와 방향이 일치한다는 점에서 보조 근거로 사용할 수 있다.

---

## 5. 공식 로드맵이 말하는 중요 MI

### 5.1 MAPT Roadmap 2.0

[MAPT Roadmap 2.0 Chapter 10](https://srcmapt.org/chapter10/)은 현재 가장 직접적인 전체 taxonomy다.

- Hybrid/fusion bonding의 핵심 metric으로 **surface roughness, Cu recess depth, bond energy, overlay, bond-interface void**를 명시한다.
- Advanced packaging thermomechanics에 **adhesion, fracture toughness, CTE, wafer bow, modulus, Tg, viscosity, fatigue, humidity, thermal conductivity, viscoelasticity**를 포함한다.
- TSV와 wafer/die stack에서 **고속·고coverage의 비파괴 buried defect 검사**가 필요하다고 본다.
- W2W/C2W alignment는 `<50 nm`, void 검출은 `<1 µm` 수준의 목표를 제시한다.
- buried void/delamination/crack 검출 목표는 중장기적으로 `<500 nm`, 장기적으로 `<250 nm`까지 내려간다.
- 단일 장비가 아니라 **hybrid metrology, process sensor/e-test data fusion, ML/AI, virtual metrology**를 요구한다.

페이지가 고정된 인용이 필요하면 [MAPT Roadmap 2023 PDF](https://srcmapt.org/wp-content/uploads/2024/03/SRC-MAPT-Roadmap-2023-v4.pdf)의 Chapter 10, 특히 문서 p.185–193과 Table 10.2를 함께 사용한다. 다만 최신판 자체는 2025년에 공개된 웹 기반 Roadmap 2.0이다.

### 5.2 IRDS 2024 Metrology

[IRDS 2024 Metrology](https://irds.ieee.org/images/files/pdf/2024/2024IRDS_MET.pdf) §5.12는 advanced packaging MI를 다음처럼 구체적으로 열거한다.

- Substrate: topography/warpage, linewidth/spacing/pitch, film thickness, die-attach coplanarity, interlevel via diameter
- Hybrid bonding: planarity, roughness/nanotopography, alignment·tilt·placement, interface defect/particle, organic contamination, bump defect, edge/void, adhesion energy
- Thermal: multilayer stack와 interface thermal characterization, cooling·heat-load validation, uncertainty model
- Test: fine-pitch probing, KGD test/binning, package electrical test

IRDS는 chiplet이 이종재료, 복잡한 thermal signature, 서로 다른 power, 더 촘촘한 placement와 더 많은 interface를 만든다는 점을 MI 난도의 근본 원인으로 본다.

### 5.3 NIST와 ECTC 산업 보고서

- [NIST, *Metrology Gaps in the Semiconductor Ecosystem*](https://www.nist.gov/system/files/documents/2023/06/05/CHIPS_Metrology-Gaps-in-the-Semi-Ecosystem_0.pdf)은 2년 이상의 stakeholder engagement와 market research를 바탕으로 interface·subsurface interconnect·internal 3D structure의 warpage, void, stress, adhesion, reliability를 더 높은 throughput과 resolution으로 측정해야 한다고 정리한다.
- [NIST IR 8577](https://nvlpubs.nist.gov/nistpubs/ir/2025/NIST.IR.8577.pdf)은 micro/nano scale multilayer package에서 defect와 alignment를 볼 도구, thermal characterization, standard method·data exchange가 부족하다고 재확인한다.
- [2024 ECTC Special Session Report: *Advancing Metrology for Next-Generation Microelectronics*](https://tsapps.nist.gov/publication/get_pdf.cfm?pub_id=958598)는 NIST, Intel, TSMC, ASE, KLA의 관점을 묶는다. 공통 요구는 sub-micron NDI, high-speed surface topology, in-situ/inline process health, 3D X-ray·IR, electrical/thermal/stress/material correlation, AI classification, standardization과 HVM 적합성이다.
- [iNEMI Packaging & Heterogeneous Integration Roadmap](https://roadmap.inemi.org/inemi-roadmap/packaging-heterogeneous-integration)은 reliability/metrology 항목에서 MAPT의 advanced-packaging metrology table을 직접 참조한다.

IEEE Heterogeneous Integration Roadmap(HIR)은 metrology를 cross-cutting 영역으로 인식하지만, 공개 최신판에는 독립적인 상세 MI chapter가 충분히 갖춰져 있지 않다. 그러므로 현재 priority 근거로는 MAPT·IRDS·NIST가 더 직접적이다.

---

## 6. 공정 단계별 MI 매트릭스

| 공정 단계 | 핵심 측정 대상 | 대표 결함·위험 | 1차 screen | 보완·확인 |
|---|---|---|---|---|
| Incoming wafer/substrate/carrier | thickness, TTV, bow/warp, flatness, edge, particle, material property | handling 불량, 뒤틀림, edge crack, substrate yield 손실 | optical AOI, interferometry/laser, wafer-shape measurement | material analysis, X-ray/ultrasound |
| RDL/UBM 형성 | L/S, CD, thickness, overlay, via opening, residue | open/short, necking, bridge, incomplete via, residue | AOI, CD-SEM/OCD, confocal/WLI, film metrology, e-test | SEM/FIB, XRF·spectroscopy |
| TSV/TGV 형성·fill·reveal | top/bottom CD, depth, taper, scallop, sidewall, liner/seed, fill seam/void, Cu protrusion, stress | fill void, barrier/seed 불연속, leakage, RC 증가, keep-out-zone stress | optical/confocal/scatterometry, X-ray, AFM/WLI, electrical test | FIB-SEM/TEM, Raman/XRD stress |
| µ-bump 형성 | height, diameter, pitch, volume, coplanarity, UBM, missing/bridge | non-wet, open/short, solder void/crack, 접합 압력 불균일 | 3D optical, AOI, X-ray, e-test | SAM, cross-section/SEM |
| Hybrid bonding 전 | global/local planarity, roughness/nanotopography, Cu recess/protrusion, particle/residue/oxide, surface activation, alignment mark | 접촉 면적 부족, void nucleation, Cu 미접촉, misalignment | optical particle inspection, AFM/SPM, WLI/CSI, profilometry, optical/IR alignment | XPS/AES/ToF-SIMS/FTIR, contact angle, local SEM |
| Bonding 중·직후 | overlay, X/Y/θ, die shift/tilt, bond wave/contact area, gap | die placement error, trapped particle, incomplete bond | optical/IR/SWIR alignment, moiré/shape measurement | e-test, process sensor data |
| Post-bond stack | interface void/gap/delamination, incomplete Cu contact, crack, buried overlay, bond energy | latent open, 약한 접합, field failure | SAM + X-ray CT/XRM/laminography + IR을 재료·깊이에 맞게 조합 | daisy chain/Kelvin/TDR, shear/crack/4-point bend, FIB-SEM/TEM |
| Mold·cure·reflow·anneal | temperature-dependent warpage, stress/strain, cure, Tg, CTE, moisture, adhesion | die shift, package crack, delamination, solder fatigue | chamber moiré/DIC/interferometry, DSC/DMA/TMA/rheology, thermography | fracture/adhesion test, spectroscopy, reliability stress |
| Final test·FA | continuity, resistance/leakage, SI/PI, thermal hotspot/path, 정확한 fault location | KGD 손실, open/short, hotspot, EM·reliability failure | wafer/package e-test, BIST, TDR/EOTPR, S-parameter, IR/LIT | emission/SQUID, X-ray/SAM, selective destructive analysis |

### 6.1 패키지 구조별 강조점

| 구조 | 특히 우선할 MI |
|---|---|
| HBM·hybrid bonding | pre-bond surface chemistry/topography, Cu recess, overlay·tilt, post-bond nanovoid, contact resistance, KGD |
| 2.5D interposer·chiplet | RDL/TSV integrity, die placement·coplanarity, µ-bump joint, KGD, electrical/thermal path |
| FOWLP/FOPLP | die shift/rotation, mold-flow·cure, panel warpage, RDL overlay/open/short, edge·delamination |
| TSV-based 3D stack | high-AR TSV profile·liner·fill, Cu protrusion, TSV-induced stress, buried joint, thermal hotspot |
| Glass substrate/TGV | TGV geometry·crack, panel shape/warpage, glass defect, RDL, transparent-material inspection recipe |

---

## 7. 측정 기술 비교: 한 장비로는 충분하지 않다

| 기술 | 강한 대상 | 대표 한계 | 적합한 역할 |
|---|---|---|---|
| 2D optical AOI | surface particle, RDL pattern, edge, missing/bridge | buried interface를 볼 수 없음; 재료·반사율 영향 | 고속 전수 screen |
| 3D optical, confocal, WLI/CSI, interferometry | height, coplanarity, roughness/topography, warpage, bump·RDL geometry | steep/high-AR 구조와 투명·혼합재료 recipe가 어려움 | inline geometry control |
| AFM/SPM | nm-scale roughness, Cu recess/dishing, local nanotopography | 느리고 작은 면적만 측정 | hybrid-bond surface 정밀 reference·sampling |
| X-ray 2D/CT/XRM/laminography | metal interconnect, µ-bump, TSV fill, 3D buried defect | resolution–FOV–penetration–throughput trade-off, reconstruction artifact | volumetric NDI와 구조 위치 특정 |
| SAM/CSAM | interface delamination, void, underfill, crack | immersion 필요, lateral resolution·재료 stack 제약, 금속 사이 결함 한계 | 넓은 계면의 depth-selective NDI |
| IR/SWIR·transmission IR | through-Si alignment, bond interface, die placement | Cu·고농도 Si·불투명층의 투과와 깊이 해상도 한계 | alignment와 빠른 post-bond screen |
| Active IR/LIT/thermography | hotspot, crack/void의 열 응답, full-field functional anomaly | 깊이·결함 종류의 역문제가 모호할 수 있음 | 빠른 fault isolation과 thermal validation |
| THz/microwave | dielectric/organic 계면, 일부 buried feature | lateral resolution과 HVM 성숙도 | X-ray/SAM이 약한 재료의 보완 |
| Electrical: Kelvin/daisy chain/TDR/EOTPR/S-parameter | open/short, contact resistance, fault distance, interconnect performance | 물리 형상과 정확한 3D 원인을 단독으로 확정하기 어려움 | 기능 확인과 physical MI 상관 |
| XPS/AES/ToF-SIMS/FTIR/Raman | oxide, residue, contamination, chemistry, stress/material state | 대개 local/offline; 진공·sample prep 또는 해석 필요 | 결함 원인과 process precursor 규명 |
| SEM/FIB/TEM | nm-scale morphology와 계면 root cause | local, 느림, destructive/sample-prep artifact | 최종 ground truth와 FA |

핵심은 **screen–localize–confirm**의 계층형 조합이다.

1. Optical/shape/e-test로 빠르게 전수 또는 고coverage screen을 한다.
2. X-ray·SAM·IR·thermography 중 결함과 재료에 맞는 방법으로 buried 위치를 좁힌다.
3. 필요한 소수만 FIB/SEM/TEM·단면·접합강도 시험으로 원인을 확정한다.

이 구조가 필요한 이유는 최신 hybrid-bonding review들이 공통으로 지적하듯 **nanoscale resolution, full-field coverage, subsurface visibility, HVM throughput을 동시에 만족하는 단일 기술이 없기 때문**이다.

---

## 8. 최소 MI 스택 제안

특정 장비 vendor와 무관하게 advanced-packaging 개발·양산 라인에 필요한 최소 기능을 정리하면 다음과 같다.

1. **고속 surface inspection**: particle, residue proxy, RDL/edge/bump defect를 잡는 optical AOI
2. **3D geometry·shape metrology**: thickness/TTV, wafer·panel warpage, die tilt, bump coplanarity, RDL/TSV 형상
3. **Hybrid-bond nano-surface metrology**: roughness, nanotopography, Cu recess/dishing, local planarity
4. **Alignment/overlay metrology**: pre-bond placement와 post-bond buried overlay를 모두 확인
5. **Multimodal buried NDI**: X-ray 계열을 중심으로 SAM·IR·THz/thermal 중 필요한 조합
6. **Thermomechanical/material metrology**: 온도별 warpage·stress, cure/Tg/CTE, moisture, adhesion
7. **Electrical/thermal validation**: KGD, continuity/contact resistance, TDR/S-parameter, hotspot·thermal interface
8. **Selective destructive reference**: 비파괴 검사 성능을 교정하고 false positive/negative를 확인할 cross-section·FIB/SEM/TEM
9. **Data/standard layer**: lot·wafer·die 좌표 traceability, multimodal registration, measurement uncertainty, reference artifact, defect taxonomy, AI model monitoring

장비 사양을 비교할 때는 nominal resolution만 보면 부족하다. 최소한 **검출확률(POD), false-call rate, field of view, penetration depth, sampling coverage, measurement time, GR&R/uncertainty, 취급 가능한 warp, 자동화와 좌표 정합성**을 함께 평가해야 한다.

---

## 9. ECTC 2023–2026 로컬 문헌 DB가 보여주는 흐름

이 조사와 별도로 구축된 ECTC corpus에는 MI 핵심 및 인접 특성평가·고장분석 논문이 총 **247편** 포함되어 있다.

| 연도 | 포함 논문 | 핵심 MI | 인접 특성평가·FA |
|---:|---:|---:|---:|
| 2023 | 60 | 27 | 33 |
| 2024 | 65 | 29 | 36 |
| 2025 | 61 | 22 | 39 |
| 2026 | 61 | 30 | 31 |
| **합계** | **247** | **108** | **139** |

제목·세션·한국어 초록 요약을 이용해 후보를 만든 뒤 논문별 hit를 수동 재검토한 multi-label 집계는 다음과 같다. 한 논문이 여러 축에 동시에 들어갈 수 있다.

| 연구 축 | 합계 | 2023 | 2024 | 2025 | 2026 |
|---|---:|---:|---:|---:|---:|
| 소재·표면·계면·미세조직/물성 | 104 | 20 | 26 | 32 | 26 |
| 신뢰성·가속시험·열화·PHM | 68 | 14 | 18 | 17 | 19 |
| 전기·RF·광 interconnect 성능 계측 | 60 | 17 | 15 | 15 | 13 |
| 양산형 계측·자동화: inline, high-speed, wafer-scale, real-time, 표준화 | 57 | 10 | 15 | 14 | 18 |
| Hybrid/direct bonding 계측: 표면, overlay, 계면, bond strength | 56 | 12 | 10 | 14 | 20 |
| AI/ML·digital twin·measurement-model coupling | 54 | 10 | 12 | 17 | 15 |
| 내부결함 NDT·inspection·fault isolation/FA | 50 | 10 | 10 | 10 | 20 |
| Warpage·stress·deformation·CTE/shrinkage | 49 | 10 | 11 | 17 | 11 |
| Thermal/temperature metrology | 26 | 8 | 8 | 4 | 6 |

247편 중 245편이 위 아홉 축 중 하나 이상에 포함되었다. Physical packaging MI와 거리가 있는 hardware-security 인접 논문 2편은 이 taxonomy에서 제외했다. `optical interferometry`를 광 interconnect 성능으로 잘못 세거나 `current stress`를 기계응력으로 잘못 세는 식의 단순 keyword 오탐도 수동으로 제거했다.

절대 건수는 넓게 정의한 소재·계면 특성평가가 가장 많다. 최근 방향을 보여 주는 신호로는 **hybrid/direct bonding이 2026년 20편, 내부결함 NDT·FA가 20편으로 각각 이전 연도의 최고치보다 크게 늘었고**, HVM형 계측·자동화도 2023년 10편에서 2026년 18편으로 증가한 점이 눈에 띈다. 이는 roadmap에서 확인한 hybrid interface, buried NDI, inline/high-throughput 요구와 방향이 같다.

다만 이 247편은 애초에 MI 관련 후보를 선별해 만든 **overlapping thematic corpus**다. 연도별 conference program의 발표 수 차이도 정규화하지 않았다. 따라서 주제별 논문 수를 시장 중요도나 ECTC 전체 연구 비중으로 곧바로 해석해서는 안 된다. 정확한 논문별 근거는 같은 폴더의 다음 자료에서 확인할 수 있다.

- [`ectc-2023-2024-mi-abstracts-ko.md`](./ectc-2023-2024-mi-abstracts-ko.md)
- [`ectc-2025-2026-mi-abstracts-ko.md`](./ectc-2025-2026-mi-abstracts-ko.md)
- [`ectc-2023-2024-mi-papers.csv`](./ectc-2023-2024-mi-papers.csv)
- [`ectc-2025-2026-mi-papers.csv`](./ectc-2025-2026-mi-papers.csv)

---

## 10. 공통 기술 공백

1. **Resolution–FOV–penetration–throughput trade-off**
   nm급, full-area, deeply buried, non-destructive, inline을 한 번에 만족하는 도구가 없다.

2. **Buried nano-void와 interface chemistry**
   void의 형상뿐 아니라 contamination·oxide·adhesion과 실제 electrical reliability를 연결하기 어렵다.

3. **In-situ/dynamic 측정 부족**
   bonding pressure·anneal·reflow·humidity 상태에서 변하는 warpage, stress, cure, 계면 형성을 양산 속도로 보기 어렵다.

4. **High-AR TSV/TGV와 opaque stack**
   bottom CD, liner/seed conformality, Cu fill void를 non-destructive inline으로 동시에 확인하기 어렵다.

5. **Fine-pitch probing과 KGD access**
   pitch가 줄고 stack이 닫힐수록 전기적 접근이 어려워진다.

6. **Physical–electrical–reliability correlation 부족**
   영상 defect 크기가 실제 resistance, thermal path, fatigue life에 미치는 영향을 제품별로 다시 학습해야 한다.

7. **표준·reference artifact·데이터 호환성 부족**
   서로 다른 장비의 좌표, defect class, uncertainty, 3D volume과 e-test 결과를 일관되게 비교하기 어렵다.

8. **Ground truth 자체의 artifact**
   destructive cross-section과 FIB sample prep가 원래 없던 crack·smear·delamination을 만들 수 있다.

---

## 11. 실무 적용 권고

### 11.1 MI 기획 순서

1. 패키지 구조별 CTQ와 failure mechanism을 먼저 정의한다.
2. 각 CTQ에 대해 **예방 precursor → inline screen → post-bond NDI → functional validation → destructive confirmation**의 연결을 만든다.
3. resolution보다 제품 수준의 POD, false call, coverage, cycle time과 measurement uncertainty를 합격 기준으로 둔다.
4. 온도·습도·공정 load 상태의 warpage/stress를 room-temperature 결과와 분리해 관리한다.
5. wafer–die–package 좌표를 이어 주는 데이터 모델을 먼저 정하고, AI는 충분한 ground truth와 drift monitoring이 있을 때 적용한다.
6. reference sample과 round-robin을 통해 장비·site 간 재현성을 검증한다.

### 11.2 연구 과제로 우선 검토할 질문

- `<1 µm` buried void를 실제 product stack에서 어느 throughput과 POD로 찾을 수 있는가?
- pre-bond particle·organic residue·Cu oxide·recess가 post-bond void와 contact resistance에 각각 얼마나 기여하는가?
- global wafer shape와 local pad nanotopography를 같은 좌표계에서 어떻게 연결할 것인가?
- temperature-dependent warpage와 die shift를 공정 중 실시간으로 측정할 수 있는가?
- X-ray, SAM, IR, e-test 결과를 한 defect 좌표와 confidence로 융합할 수 있는가?
- destructive ground truth 없이 AI false negative를 어떻게 추정하고 관리할 것인가?

---

## 12. 최종 판단

“어드밴스드 패키징에서 어떤 MI가 중요한가”에 대한 가장 안전한 답은 다음과 같다.

1. **Hybrid bonding을 한다면 표면 상태, Cu/dielectric 높이차, alignment/overlay, interface void와 bond integrity가 1차 CTQ다.**
2. **모든 2.5D/3D 구조에는 buried defect를 비파괴로 찾고 3D 위치를 특정하는 능력이 공통 병목이다.**
3. **Warpage·coplanarity·stress를 온도와 공정 단계에 따라 측정하지 않으면 local interconnect MI만으로 수율을 설명할 수 없다.**
4. **TSV/TGV·RDL·µ-bump의 형상 측정은 여전히 기본이며 electrical/KGD·thermal validation과 연결해야 한다.**
5. **최종 해법은 단일 최고 장비가 아니라 surface/shape, X-ray, acoustic, IR/thermal, electrical, selective destructive 분석을 데이터로 묶은 hybrid metrology다.**

따라서 새 MI 프로그램이나 장비 평가를 시작한다면, 우선순위는 **(a) hybrid-bond interface, (b) high-resolution volumetric NDI, (c) temperature-dependent warpage/thermomechanics**의 세 축으로 잡고, 대상 제품에 따라 TSV/RDL/bump·materials·electrical/thermal 모듈을 붙이는 구성이 가장 문헌 근거가 강하다.

---

## 참고문헌 및 공식 자료

### 핵심 review·perspective

1. S.-J. Paik, K.-S. Moon, Y. Lee, and S. J. Hong, “Process Metrology and Validation for 3D Advanced Packaging: A Comprehensive Review,” *Journal of the Korean Society of Manufacturing Process Engineers*, 25(1), 124–136, 2026. [DOI](https://doi.org/10.14775/ksmpe.2026.25.1.124)
2. Y. Su et al., “Volumetric nondestructive metrology for 3D semiconductor packaging: A review,” *Measurement*, 225, 114065, 2024. [DOI](https://doi.org/10.1016/j.measurement.2023.114065)
3. 주승환 외, “HBM 하이브리드 본딩을 위한 계측 및 검사 최신 기술 동향,” *마이크로전자 및 패키징학회지*, 32(4), 1–23, 2025. [DOI](https://doi.org/10.6117/kmeps.2025.32.4.001)
4. H. R. Kottur et al., “Inspection and Metrology Challenges in Hybrid Bonding,” *EDFA Technical Articles*, 28(2), 12–24, 2026. [DOI](https://doi.org/10.31399/asm.edfa.2026-2.p012)
5. K. Lu et al., “A Review of Through-Silicon Via Inspection and Metrology Technology for Advanced Semiconductor Packaging,” *Journal of Manufacturing Science and Engineering*, 147(12), 121005, 2025. [DOI](https://doi.org/10.1115/1.4069965)
6. G. Sun and S. Zhang, “A review on warpage measurement metrologies for advanced electronic packaging,” *Microelectronics Reliability*, 160, 115456, 2024. [DOI](https://doi.org/10.1016/j.microrel.2024.115456)
7. R. Tao et al., “Material Needs and Measurement Challenges for Advanced Semiconductor Packaging: Understanding the Soft Side of Science,” *IEEE Transactions on Components, Packaging and Manufacturing Technology*, 2025. [NIST record](https://www.nist.gov/publications/material-needs-and-measurement-challenges-advanced-semiconductor-packaging) · [DOI](https://doi.org/10.1109/TCPMT.2025.3603484)
8. P. Aryan, S. Sampath, and H. Sohn, “An Overview of Non-Destructive Testing Methods for Integrated Circuit Packaging Inspection,” *Sensors*, 18(7), 1981, 2018. [Open access](https://www.mdpi.com/1424-8220/18/7/1981) · [DOI](https://doi.org/10.3390/s18071981)
9. P. Meshki Zadeh, S. Brand, and E. Dehghan-Niri, “Recent Progress in Structural Integrity Evaluation of Microelectronic Packaging Using Scanning Acoustic Microscopy (SAM): A Review,” *Sensors*, 25(24), 7499, 2025. [Open access](https://www.mdpi.com/1424-8220/25/24/7499)
10. Y. Chen et al., “Research Status and Progress on Non-Destructive Testing Methods for Defect Inspection of Micro-Electronic Packaging,” *Journal of Electronic Packaging*, 146(3), 030801, 2024. [DOI](https://doi.org/10.1115/1.4064361)
11. L. Su, X. Yu, K. Li, and M. Pecht, “Defect inspection of flip chip solder joints based on non-destructive methods: A review,” *Microelectronics Reliability*, 110, 113657, 2020. [Publisher](https://www.sciencedirect.com/science/article/pii/S0026271419308522) · [DOI](https://doi.org/10.1016/j.microrel.2020.113657)
12. A. Zhou et al., “Research progress of hybrid bonding technology for three-dimensional integration,” *Microelectronics Reliability*, 155, 115372, 2024. [DOI](https://doi.org/10.1016/j.microrel.2024.115372)

### Roadmap·정부·산업 자료

13. SRC, [MAPT Roadmap 2.0, Chapter 10: Manufacturing and Process Development Metrology](https://srcmapt.org/chapter10/), 2025.
14. SRC, [Microelectronics and Advanced Packaging Technologies Roadmap 2023, v4](https://srcmapt.org/wp-content/uploads/2024/03/SRC-MAPT-Roadmap-2023-v4.pdf), Chapter 10.
15. IEEE, [International Roadmap for Devices and Systems 2024 — Metrology](https://irds.ieee.org/images/files/pdf/2024/2024IRDS_MET.pdf), §5.12 Advanced Packaging.
16. NIST, [Metrology Gaps in the Semiconductor Ecosystem](https://www.nist.gov/system/files/documents/2023/06/05/CHIPS_Metrology-Gaps-in-the-Semi-Ecosystem_0.pdf), 2023.
17. NIST, [NIST IR 8577: Semiconductors and Microelectronics Standards Working Group Annual Report for 2024](https://nvlpubs.nist.gov/nistpubs/ir/2025/NIST.IR.8577.pdf), 2025.
18. R. Tao, B. Chan, and J. Vardaman, [2024 ECTC Special Session Report: *Advancing Metrology for Next-Generation Microelectronics*](https://tsapps.nist.gov/publication/get_pdf.cfm?pub_id=958598), 2024.
19. iNEMI, [Packaging & Heterogeneous Integration Roadmap](https://roadmap.inemi.org/inemi-roadmap/packaging-heterogeneous-integration).
20. H. R. Kottur et al., “Failure Analysis in Transition: An Industry Survey of Challenges, Priorities, and Standardization Needs in Advanced Packaging and Heterogeneous Integration,” arXiv preprint, 2026. [arXiv](https://arxiv.org/abs/2606.22149)

### 표준·공정 보조자료

21. SEMI, [SEMI 3D4 — Guide for Metrology for Measuring Thickness, TTV, Bow, Warp, Sori, and Flatness of Bonded Wafer Stacks](https://store-us.semi.org/products/3d00400-semi-3d4-guide-for-metrology-for-measuring-thickness-total-thickness-variation-ttv-bow-warp-sori-and-flatness-of-bonded-wafer-stacks).
22. SEMI, [SEMI 3D6 — Guide for CMP and Micro-Bump Processes for Frontside TSV Integration](https://store-us.semi.org/products/3d00600-semi-3d6-guide-for-cmp-and-micro-bump-processes-for-frontside-through-silicon-via-tsv-integration).
23. SEMI, [SEMI 3D13 — Guide for Measuring Voids in Bonded Wafer Stacks](https://store-us.semi.org/products/3d01300-semi-3d13-guide-for-measuring-voids-in-bonded-wafer-stacks).
24. imec, [Wafer-to-wafer hybrid bonding: pushing the boundaries to 400 nm interconnect pitch](https://www.imec-int.com/en/articles/wafer-wafer-hybrid-bonding-pushing-boundaries-400nm-interconnect-pitch).

---

## 조사 한계

- 검색 기준일 이후 발표되거나 paywall 뒤에만 있는 자료는 반영되지 않을 수 있다.
- “중요도”에 대한 universal score가 없어, 본 리포트의 우선군은 독립 문헌과 roadmap의 합의점을 종합한 결과다.
- 제품 architecture, pitch, 재료, 개발/양산 단계에 따라 실제 CTQ와 허용 규격은 달라진다.
- ECTC corpus는 MI 관련 연구를 의도적으로 선별했으므로 bibliometric 전체 모집단이 아니다.
- 2026 업계 설문은 유용하지만 아직 peer-reviewed 논문이 아니며 FA 응답을 중심으로 한다.
