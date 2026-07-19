# 조사 로그

## 2026-07-19

- 반도체 MI 논문 조사 DB 폴더 생성
- 조사 자료를 논문 원문, 노트, 출처, 그림, 데이터, 산출물로 구분
- ECTC 공식 사이트와 2025·2026 공식 프로그램 자료 확인 시작
- `2025-ectc-75-final-program.pdf` 보관: 75회 ECTC의 52쪽짜리 행사 프로그램 북이며 논문 전체 본문을 담은 프로시딩은 아님
- `2026-ectc-76-call-for-papers.pdf` 보관: 76회 ECTC 논문 모집 및 기술 분야 안내
- `2025-ectc-75-complete-program-index.md` 생성: Session 1-41, 구두 252건과 인터랙티브 139건 등 총 391건의 제목·저자·소속·세션 메타데이터 수록
- `2026-ectc-76-final-program-v2.pdf`와 사용자 제공 추출 텍스트 보관
- `2026-ectc-76-complete-program-index.md` 생성: Session 1-41, 구두 252건과 인터랙티브 171건 등 총 423건의 제목·저자·소속·세션 메타데이터 수록
- 두 연도 모두 OCR을 사용하지 않고 PDF 내장 텍스트를 추출했으며, 세션 연속성·발표 수·제목·저자/소속 존재 여부를 검증함
- `MI`를 Metrology & Inspection으로 정의하고, 공식 태그 부재를 보완하기 위해 핵심 MI와 인접 특성평가·고장분석의 2단계 분류 기준을 수립
- 공식 프로그램의 814개 기술 발표 제목을 1차 검색한 뒤 Crossref conference container의 2025년 379개·2026년 416개 DOI 레코드와 대조
- Semantic Scholar 공개 초록을 이용해 두 해 DOI 레코드 전체를 감사하여 제목만으로 빠진 overlay, moiré alignment, anomaly detection, in-situ monitoring 논문을 추가 검토
- 제목의 `image`, `photo-imageable`, `measures`, 의료 모니터링 등이 만든 명백한 오탐 6편을 제외
- 최종 포함: 2025년 61편(핵심 22, 인접 39), 2026년 61편(핵심 30, 인접 31), 총 122편
- ECTC 논문 자체의 공개 초록 확인: 120/122편. Semantic Scholar 119편과 OpenAlex 1편에서 확인했다. 2025 S06-03은 동일 제목 후속 저널판을 ECTC 초록과 구분해 참고로만 사용했으며, 2026 S41-03은 프로그램 외 공개 초록 미확보
- `ectc-2025-2026-mi-paper-review.md`에 122편의 제목, DOI/초록 출처, 한국어 핵심 요약을 수록하고 CSV export를 생성
- 사람이 바로 읽을 수 있도록 `exports/ectc-2025-2026-mi-abstracts-ko.md`를 별도 생성하고 122편의 제목·세션·저자/소속·DOI·초록 출처·한국어 재서술 초록을 수록
- 한국어 문장은 공식 초록이나 공식 번역이 아니라, 공개 영문 초록에 근거해 Codex가 작성한 요약임을 문서에 명시하고 JSON 요약 산출물을 제거
- `2023-ectc-73-final-program.pdf`와 `2024-ectc-74-final-program.pdf` 공식 원본 보관
- `2023-ectc-73-complete-program-index.md` 생성: Session 1-41, 구두 252건과 인터랙티브 134건 등 고유 발표 386건 수록
- 2023 원본 PDF p.11의 S06-05 동일 중복 인쇄는 색인에서 한 건으로 정규화하고 출처 오류를 문서에 명시함
- `2024-ectc-74-complete-program-index.md` 생성: Session 1-41, 구두 252건과 인터랙티브 139건 등 총 391건 수록
- 2023·2024 모두 OCR 없이 PDF 내장 텍스트와 좌표를 사용했으며, 주요 다단 페이지 렌더링·세션 번호·발표 번호·제목·저자/소속·역색인 링크를 검증함
- 2023 공식 프로그램 386건과 2024 공식 프로그램 391건, 총 777건을 Crossref의 각 IEEE ECTC conference container와 대조함
- 두 해 모두 367건씩 총 734건의 프로그램 발표를 DOI에 연결하고, Semantic Scholar에서 733건의 공개 초록을 확보해 전체 초록 누락 감사를 수행함
- 제목 신호뿐 아니라 공개 초록의 AFM·DIC·CSAM·AOI·XRM·PAS·failure analysis·in-situ monitoring 신호까지 재검토함
- 의료 모니터링 센서, CMOS image sensor 제품 공정, lithography의 `image/exposure`처럼 MI 용어와 겹치는 대표 오탐을 제외함
- 최종 포함: 2023년 60편(핵심 27, 인접 33), 2024년 65편(핵심 29, 인접 36), 총 125편
- ECTC DOI 기반 공개 초록 확인: 119/125편. 2023 S41-21은 동일 연구진의 후속 SPIE 공개 초록으로 보완했고, 나머지 5편은 제목 기준 설명임을 명시함
- `notes/ectc-2023-2024-mi-paper-review.md`, `exports/ectc-2023-2024-mi-abstracts-ko.md`, `exports/ectc-2023-2024-mi-papers.csv`에 최종 결과를 정리함
