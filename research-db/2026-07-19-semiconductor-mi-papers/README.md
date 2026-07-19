# 반도체 MI 논문 조사 DB

- 조사 기준일: 2026-07-19
- 주제: 2.xD·HBM 첨단 패키징의 Metrology & Inspection
- 공개 범위: 최종 서베이, 우선순위표, ECTC 공개 초록 감사와 선별 논문 메타데이터

## 공개 산출물

- `exports/advanced-packaging-mi-survey-report.md`: review·roadmap·ECTC 근거를 묶은 전체 문헌 서베이
- `exports/advanced-packaging-inspection-priority-matrix.csv`: 단위공정별 P0/P0*/P1/P2 우선순위표
- `notes/advanced-packaging-inspection-survey-synthesis.md`: 페이지의 판단 기준, 아키텍처별 control plan과 근거 한계
- `notes/ectc-2023-2024-mi-paper-review.md`, `notes/ectc-2025-2026-mi-paper-review.md`: 연도별 포함 기준과 대표 근거
- `exports/ectc-2023-2024-mi-abstracts-ko.md`, `exports/ectc-2025-2026-mi-abstracts-ko.md`: 공개 초록 기반 한국어 재서술
- `exports/ectc-2023-2024-mi-papers.csv`, `exports/ectc-2025-2026-mi-papers.csv`: 선별 247건의 메타데이터와 요약
- 저장소 루트의 `advanced-packaging-inspection-guide.html`: 모바일 교육자료와 객관식 퀴즈
- `research-log.md`: 검색 범위와 조사 이력

## 원문과 로컬 캐시

공식 프로그램 PDF와 텍스트 추출본은 용량·재배포 범위와 행사 안내 정보 때문에 로컬 조사 캐시로만 보관한다. 공개 저장소에는 재서술한 초록 감사·분석 결과만 넣고, 원문은 각 노트에 연결한 ECTC·DOI 공식 URL에서 다시 확인한다.

## ECTC 2023·2024 MI 전수 조사 결과

- 최종 포함: **125편**
  - 2023: 핵심 MI 27편 + 인접 특성평가·고장분석 33편 = 60편
  - 2024: 핵심 MI 29편 + 인접 특성평가·고장분석 36편 = 65편
- ECTC DOI 기반 공개 초록 확인: **119/125편**
  - 2023 S41-21은 같은 연구진의 후속 SPIE 공개 초록으로 보완
  - 나머지 5편은 공개 초록을 찾지 못해 제목 기준 설명으로 명시
- 공식 프로그램 전체 777건과 Crossref DOI 734건을 연결하고, 공개 초록 733건을 감사해 제목 필터 밖의 후보까지 재검토

주요 산출물:

- `notes/ectc-2023-2024-mi-paper-review.md`: 분류 기준, 125편 제목, DOI/초록 링크, 한국어 핵심 요약, 대표 오탐
- `exports/ectc-2023-2024-mi-abstracts-ko.md`: 사람이 읽기 위한 125편 전용 초록 모음. 제목, 세션, 저자·소속, DOI, 초록 출처, 한국어 재서술 초록 수록
- `exports/ectc-2023-2024-mi-papers.csv`: 포함 125편의 전체 메타데이터와 한국어 요약

## ECTC 2025·2026 MI 전수 조사 결과

- 최종 포함: **122편**
  - 2025: 핵심 MI 22편 + 인접 특성평가·고장분석 39편 = 61편
  - 2026: 핵심 MI 30편 + 인접 특성평가·고장분석 31편 = 61편
- ECTC 논문 자체의 공개 초록 확인: **120/122편**
  - 2025 S06-03은 ECTC DOI·초록이 없어 동일 제목·저자의 후속 저널판을 별도 참고로만 사용
  - 2025 S41-05는 OpenAlex 초록 색인으로 보완
  - 2026 S41-03은 공식 프로그램의 제목·저자만 확인되고 DOI·공개 초록은 미확보
- 제목 키워드 오탐으로 제외: 6편

주요 산출물:

- `notes/ectc-2025-2026-mi-paper-review.md`: 분류 기준, 전수 제목, DOI/초록 링크, 논문별 한국어 초록 요약
- `exports/ectc-2025-2026-mi-abstracts-ko.md`: 사람이 읽기 위한 122편 전용 초록 모음. 제목, 세션, 저자·소속, DOI, 초록 출처, 한국어 재서술 초록 수록
- `exports/ectc-2025-2026-mi-papers.csv`: 포함 122편의 세션·전체 저자/소속·DOI·초록 출처·한국어 요약

## 2.xD·HBM 검사·계측 서베이 산출물

- `exports/advanced-packaging-mi-survey-report.md`: review·roadmap·ECTC 근거를 확장해 정리한 전체 문헌 서베이
- `notes/advanced-packaging-inspection-survey-synthesis.md`: 범위, 근거 한계, 우선순위 rubric, 아키텍처별 control plan과 문헌 검토 기록
- `exports/advanced-packaging-inspection-priority-matrix.csv`: 단위공정 검사·계측 중요도와 근거를 정리한 표
- 저장소 루트의 `advanced-packaging-inspection-guide.html`: 모바일 교육자료와 객관식 퀴즈
