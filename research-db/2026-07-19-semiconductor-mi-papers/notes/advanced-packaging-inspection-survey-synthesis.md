# 2.xD·HBM 첨단 패키징 검사·계측 서베이 종합 노트

> 조사 기준일: 2026-07-19
> 결과 페이지: `advanced-packaging-inspection-guide.html`
> 목적: ECTC 2023–2026의 반복 신호를 2.xD·HBM 단위공정 control plan으로 번역

## 1. 가장 중요한 결론

“X-ray로 범프가 잘 붙었는가”는 중요한 질문이지만 한 번에 답할 수 있는 질문은 아니다. “잘 붙었다”에는 최소 네 가지 서로 다른 판정이 들어 있다.

1. **기하:** x-y-θ 정렬, pad overlap, bump 높이, coplanarity
2. **구조:** missing/non-wet bump, bridge, void, crack, delamination
3. **전기:** continuity, open/short, Kelvin contact resistance, leakage
4. **수명:** bond strength, residual stress, thermal path, EM·열사이클 안정성

따라서 핵심은 장비 순위를 고정하는 것이 아니라 `KGD → pre-bond surface/geometry → overlay → buried interface → electrical → warpage/encapsulation → thermal/reliability`의 결함 탈출 게이트를 만드는 것이다.

## 2. 근거 범위와 한계

- ECTC 2023–2026 공식 프로그램: 386 + 391 + 391 + 423 = **1,591건**
- 자체 MI 포함 기준: **247건**
  - 2023: core 27 + adjacent 33 = 60
  - 2024: core 29 + adjacent 36 = 65
  - 2025: core 22 + adjacent 39 = 61
  - 2026: core 30 + adjacent 31 = 61
- 분류는 ECTC의 공식 MI 태그가 아니라 주 기여와 활용 역할에 대한 자체 판단이다.
- 로컬 `sources/`의 PDF는 학회 프로그램이며 개별 논문 원문이 아니다.
- 개별 논문 내용은 IEEE DOI 서지와 Semantic Scholar/OpenAlex 공개 초록 중심으로 확인했다. 숫자형 성능은 해당 시험차량의 결과로만 읽는다.
- 2026 proceedings DOI는 확인됐지만 최신 결과라 장기 재현성·성숙한 인용 검증이 부족하다.

## 3. 우선순위 판정 기준

### 등급

- **P0:** 아키텍처와 무관하게 수율·출하 판정을 지키는 필수 gate
- **P0\*:** 해당 구조를 사용하면 P0가 되는 조건부 필수 gate
- **P1:** 높은 sampling, 공정 램프, qualification에 중요한 항목
- **P2:** excursion, FA, 물리모델과 수명 예측의 심층 분석

### 판단 축

1. 고장 심각도와 시스템 영향
2. 다음 공정에서 결함이 숨을 가능성
3. 발생 가능성과 공정창 민감도
4. 이미 투입된 die·공정 가치
5. 계측 결과가 만드는 공정 피드백의 속도와 직접성
6. 제조 적용 coverage, takt time, MSA 능력

페이지의 순위는 보편 규격이 아니다. 실제 sampling과 spec은 product FMEA, occurrence, 장비 검출한계, Gage R&R, false escape/reject 비용과 공정능력으로 다시 정한다.

## 4. 아키텍처별 P0 이동

### Microbump + TCB/reflow/MR-MUF HBM

1. KGD·TSV/daisy-chain test
2. bump height/coplanarity/oxide
3. placement와 reflow/TCB 접합
4. X-ray/CT + SAM + electrical
5. MUF/NCF void·cure·warpage

### Bumpless hybrid-bond HBM

1. particle·유기/산화 잔사
2. surface roughness·Cu recess/protrusion·CMP map
3. die 전체 overlay·distortion
4. SAM/IR/nano-X-ray + Kelvin
5. bond strength·thermal stress·reliability

### 2.xD interposer·bridge

1. KGD와 interposer e-test
2. fine RDL CD/overlay/via/open-short
3. TSV/TGV fill·resistance·stress
4. logic/HBM microbump 접합
5. 대면적 warpage와 TIM/hotspot

## 5. X-ray의 정확한 역할

### 강점

- 고원자번호 금속과 solder의 매몰 형상
- missing/shifted bump, bridge, gross non-wet, solder extrusion
- solder/Cu fill의 큰 void·seam
- CT/XRM에서 층별 3D 위치, 부피와 defect segmentation

### 사각지대

- 2D 투영의 다층 중첩과 depth 부재
- CT/XRM의 FOV–해상도–시편 크기–scan time trade-off
- nm급 dielectric gap, 유기 오염, 매우 얇은 non-bond
- void가 없어도 생기는 high-resistance Cu contact

### 권장 correlation

`overlay/3D AOI → 2D X-ray screening → 위험 lot CT/XRM → SAM/IR interface → daisy/Kelvin electrical → LIT/TDR/FIB root cause`

## 6. 2023–2026 흐름

- **2023:** warpage·pad recess·overlay와 HBM 3D 결함을 정량화하는 scalable metrology가 선명해졌다.
- **2024:** high-throughput topography, embedded sensor, 3D XRM continual learning처럼 inline·in-situ 방향이 강화됐다.
- **2025:** HBM bump/XRM AI, physics-informed SAM, TSV stress·thermal, RDL correlative FA가 하나의 수율학습 흐름으로 연결됐다.
- **2026:** time-resolved/nano/computational X-ray, 100% overlay, wafer-scale sub-nm surface와 in-situ cure/warpage sensing이 전면에 나왔다.

## 7. 외부 핵심 문헌

1. [SRC MAPT Roadmap 2023](https://srcmapt.org/wp-content/uploads/2024/03/SRC-MAPT-Roadmap-2023-v4.pdf)
2. [NIST IRDS 2023 Metrology](https://www.nist.gov/publications/international-roadmap-devices-and-systemstm-2023-edition-metrology)
3. [IEEE HIR 2024 Test Technology](https://eps.ieee.org/wp-content/uploads/2025/11/HIR_2024_ch17_Test_Technology.pdf)
4. [iNEMI Packaging & Heterogeneous Integration Roadmap](https://roadmap.inemi.org/inemi-roadmap/packaging-heterogeneous-integration)
5. [HBM 하이브리드 본딩을 위한 계측 및 검사 최신 기술 동향](https://doi.org/10.6117/kmeps.2025.32.4.001), 2025
6. [Volumetric nondestructive metrology for 3D semiconductor packaging: A review](https://doi.org/10.1016/j.measurement.2023.114065), 2024
7. [A review on warpage measurement metrologies for advanced electronic packaging](https://doi.org/10.1016/j.microrel.2024.115456), 2024
8. [An Overview of Non-Destructive Testing Methods for IC Packaging Inspection](https://doi.org/10.3390/s18071981), 2018
9. [Defect inspection of flip chip solder joints based on non-destructive methods: A review](https://doi.org/10.1016/j.microrel.2020.113657), 2020
10. [State-of-the-art of Cu-Cu Hybrid Bonding](https://doi.org/10.1109/TCPMT.2024.3367985), 2024

## 8. 학습자용 영문 글 검토

최상단 추천:

1. [imec — Wafer-to-wafer hybrid bonding: pushing boundaries to 400 nm](https://www.imec-int.com/en/articles/wafer-wafer-hybrid-bonding-pushing-boundaries-400nm-interconnect-pitch)
2. [Semiconductor Engineering — Inspection, Metrology Issues in Advanced Packages](https://semiengineering.com/inspection-metrology-issues-in-advanced-packages/)

추가 검토:

3. [Metrology Under Pressure: Detecting Defects in Fine-Pitch Hybrid Bonding](https://semiengineering.com/metrology-under-pressure-detecting-defects-in-fine-pitch-hybrid-bonding/)
4. [How Advanced Packaging Is Reshaping Inspection](https://semiengineering.com/how-advanced-packaging-is-reshaping-inspection/)
5. [imec — Chiplets, Part I](https://www.imec-int.com/en/articles/chiplets-piecing-together-next-generation-chips-part-i)
6. [Excillum — Are X-ray methods up to the task?](https://www.excillum.com/metrology-for-hybrid-bonds-microbumps-and-tsvs-in-advanced-packaging-are-x-ray-methods-up-to-the-task/)
7. [Onto Innovation — Addressing metrology challenges](https://ontoinnovation.com/resources/addressing-the-challenges-of-metrology-for-advanced-packaging/)
8. [Onto Innovation — Enabling in-line process control for hybrid bonding](https://ontoinnovation.com/resources/enabling-in-line-process-control-for-hybrid-bonding-applications/)
9. [SPTS/KLA — Wafer inspection and metrology](https://www.spts.com/products/packaging-manufacturing/wafer-inspection-and-metrology-for-advanced-packaging)
10. [Rigaku — Semiconductor packaging applications](https://rigaku.com/products/semiconductor-metrology/application-notes/packaging)
11. [Nova — Precision metrology for hybrid bonding](https://www.novami.com/blog/precision-metrology-for-hybrid-bonding-novas-engineering-driven-approach-to-advanced-packaging/)
12. [imec — 2 µm pitch die-to-wafer hybrid bonding](https://www.imec-int.com/en/press/imec-demonstrates-die-wafer-hybrid-bonding-cu-interconnect-pad-pitch-2mm)

장비업체 글은 결함·처리량 문제를 이해하는 데만 사용하고 독립적인 성능 근거로 사용하지 않았다.

## 9. 학습자용 한글 글 검토

최상단 추천:

1. [SK하이닉스 — 어드밴스드 패키징을 견인하는 인터커넥션 기술](https://news.skhynix.co.kr/interconnection-for-advanced-packaging/)
2. [삼성전자 — 첨단 패키징과 시스템 수준 반도체 혁신](https://semiconductor.samsung.com/kr/news-events/tech-blog/advanced-packaging-and-the-shift-to-system-level-semiconductor-innovation/)

추가 검토:

3. [SK하이닉스 — 차세대 반도체 패키징](https://news.skhynix.co.kr/next-generation-semiconductor/)
4. [SK하이닉스 Future Talents — TSV와 MR-MUF](https://news.skhynix.co.kr/future-talents-class-ep1/)
5. [삼성전자 — AVP, 무어의 법칙을 넘어](https://semiconductor.samsung.com/kr/news-events/tech-blog/samsung-advanced-package-technology-avp-moving-semiconductors-beyond-moores-law/)
6. [삼성전자 — ASPS 2024 첨단 패키징](https://semiconductor.samsung.com/kr/news-events/tech-blog/asps-2024-samsung-unveils-cutting-edge-packaging-technology-to-accelerate-the-post-moore-era/)
7. [삼성 파운드리 — Advanced Heterogeneous Integration](https://semiconductor.samsung.com/kr/foundry/advanced-package/advanced-heterogeneous-integration/)
8. [삼성 파운드리 — Advanced Package](https://semiconductor.samsung.com/kr/foundry/advanced-package/)
9. [삼성전자 — TSV 용어사전](https://semiconductor.samsung.com/kr/support/tools-resources/dictionary/semiconductor-glossary-tsv/)
10. [KISTEP 기술동향브리프 — 반도체 후공정](https://www.kistep.re.kr/boardDownload.es?bid=0031&list_no=34995&seq=12576)
11. [Shimadzu Korea — microfocus X-ray CT](https://www.shimadzu.co.kr/products/non-destructive-testing/microfocus-x-ray-inspection-system/xslicer-smx-6000/index.html)
12. [전자신문 — hybrid-bond X-ray 검사 장비 기사](https://www.etnews.com/20250718000029?m=1)

기업 글과 산업 기사는 구조·용어·현장 관심사를 이해하는 보조 자료이며, 공정 capability의 독립 증거가 아니다.

## 10. 페이지에 사용한 대표 ECTC DOI

### 2023

- [Fine Pitch Die-to-Wafer Hybrid Bonding](https://doi.org/10.1109/ECTC51909.2023.00023)
- [3D Defect Detection and Metrology of HBMs](https://doi.org/10.1109/ECTC51909.2023.00161)
- [Critical Dimension Scatterometry for Hybrid Bonding Pad Recess](https://doi.org/10.1109/ECTC51909.2023.00240)
- [Advanced Overlay Metrology for CIS Bonding](https://doi.org/10.1109/ECTC51909.2023.00278)

### 2024

- [DCB Technique for W2W Bond Energy](https://doi.org/10.1109/ECTC51529.2024.00062)
- [High-Throughput Nanoscale Topography by Optical Interferometry](https://doi.org/10.1109/ECTC51529.2024.00157)
- [Micro Defect in Bump Interface for 2.5DIC](https://doi.org/10.1109/ECTC51529.2024.00301)
- [Buried Package Segmentation in 3D XRM](https://doi.org/10.1109/ECTC51529.2024.00314)

### 2025

- [2 µm Pitch D2W Hybrid Bonding](https://doi.org/10.1109/ECTC51687.2025.00054)
- [HBM Bump Visual Inspection with AI](https://doi.org/10.1109/ECTC51687.2025.00161)
- [Are Voids Restricted to Cu-Cu Interface?](https://doi.org/10.1109/ECTC51687.2025.00222)
- [Fine-Line RDL Correlative Fault Isolation](https://doi.org/10.1109/ECTC51687.2025.00337)
- [Physics-Informed SAM Enhancement](https://doi.org/10.1109/ECTC51687.2025.00368)

### 2026

- [Wafer-Level Sub-nm Surface Roughness by RHEED](https://doi.org/10.1109/ECTC51846.2026.00141)
- [Time-Resolved 3D X-ray of EM Void Evolution](https://doi.org/10.1109/ECTC51846.2026.00160)
- [D2W Distortion Correction and Grid Measurement](https://doi.org/10.1109/ECTC51846.2026.00219)
- [Photon-Counting Nano-CT for Hybrid Copper Bonding](https://doi.org/10.1109/ECTC51846.2026.00239)
- [Computational 3D X-ray Imaging of HBM](https://doi.org/10.1109/ECTC51846.2026.00242)
- [High-Throughput CMP Topography by Fizeau Interferometry](https://doi.org/10.1109/ECTC51846.2026.00352)
- [High-Speed 100% Bond Overlay](https://doi.org/10.1109/ECTC51846.2026.00354)

## 11. 관련 로컬 산출물

- `exports/advanced-packaging-inspection-priority-matrix.csv`
- `exports/ectc-2023-2024-mi-abstracts-ko.md`
- `exports/ectc-2025-2026-mi-abstracts-ko.md`
- `exports/ectc-2023-2024-mi-papers.csv`
- `exports/ectc-2025-2026-mi-papers.csv`
- `notes/ectc-2023-2024-mi-paper-review.md`
- `notes/ectc-2025-2026-mi-paper-review.md`
