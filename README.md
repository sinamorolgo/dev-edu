# 개발 이해 가이드

비개발자에게 개발 흐름과 Git 협업을 설명하기 위한 정적 웹 페이지입니다.

## 포함 페이지

- `index.html`: 공유용 홈
- `dev-explained.html`: 개발 전체 흐름 설명
- `git-branch-pr-guide.html`: Git 브랜치, commit, push, PR 설명

## GitHub Pages로 공유하기

1. 이 폴더를 GitHub 저장소에 push합니다.
2. GitHub 저장소에서 `Settings` → `Pages`로 이동합니다.
3. `Build and deployment`에서 `Deploy from a branch`를 선택합니다.
4. Branch를 `main`, folder를 `/root`로 선택하고 저장합니다.
5. 잠시 후 아래 형태의 링크가 생깁니다.

```text
https://계정명.github.io/저장소명/
```

## 다른 배포 선택지

Vercel이나 Netlify에 저장소를 연결해도 그대로 배포됩니다. 빌드 명령은 필요 없습니다.
