# 개인 소개 웹사이트

Hugo와 GitHub Pages로 만든 개인 소개 사이트입니다.

- 사이트: https://vaeexng.github.io/MyWebPage/
- 저장소: https://github.com/vaeexng/MyWebPage

## 사용한 도구와 버전

- Hugo 0.143.0 extended (GitHub Actions 워크플로에 버전을 지정했습니다)
- Python 3 (수업에서 제공한 `prepare_github_pages.py`로 배포 설정을 만들었습니다)
- Git, VS Code

## 내 컴퓨터에서 빌드하고 확인하기

1. Hugo extended 0.143.0 이상을 설치합니다. 맥은 `brew install hugo`를 쓰고, `hugo version`으로 확인합니다.
2. 저장소를 내려받습니다.
   ```
   git clone https://github.com/vaeexng/MyWebPage.git
   cd MyWebPage
   ```
3. 필요한 의존성을 설치하고 빌드합니다. 결과는 `public/` 폴더에 생깁니다.
   ```
   python3 .github/pages_build.py --dependencies
   SITE_BASE_URL=http://localhost:8000/ python3 .github/pages_build.py --build
   ```
4. 만들어진 사이트를 열어 확인합니다.
   ```
   python3 -m http.server 8000 -d public
   ```
   브라우저에서 http://localhost:8000/ 을 엽니다.

## 내용을 수정하고 배포하기

| 고칠 내용 | 파일 |
|---|---|
| 이름, 소개, 기술, 학습 이력, 프로젝트, 연락처, 링크 | `site/hugo.yaml` |
| 이미지 | `site/static/images/` |
| 배포 설정 | `.github/` (수업 스크립트가 만든 파일이라 직접 고치지 않습니다) |

1. 파일을 수정하고 저장합니다.
2. 변경을 커밋하고 `main` 브랜치에 push합니다.
   ```
   git add .
   git commit -m "변경 내용을 설명하는 메시지"
   git push
   ```
3. 저장소의 **Actions** 탭에서 `Deploy Hugo to GitHub Pages` 실행이 초록 체크가 되는지 확인합니다.
4. 공개 사이트를 새로고침(⇧+⌘+R)해서 변경이 반영됐는지 확인합니다.

GitHub 저장소의 Settings → Pages → Source는 **GitHub Actions**로 설정되어 있습니다.

## 출처와 이용 조건

| 자료 | 구분 | 출처 | 조건 |
|---|---|---|---|
| Hugo Profile 테마 | 외부 | https://github.com/gurusabarish/hugo-profile | MIT License, 원본 `LICENSE` 파일 유지 |
| 배포 설정 스크립트 | 외부(수업 제공) | 수업에서 제공한 `prepare_github_pages.py` | 수업 자료 |
| 소개 글, 프로젝트 설명 | 직접 작성 | 본인 (문장 다듬기에 AI의 도움을 받았습니다) | - |
| 영화 사이트 화면 이미지 | 직접 제작 | 직접 만든 사이트(movie-lab)를 캡처한 이미지 | - |
| 프로필 이미지 등 일부 이미지 | 외부 | 테마에 포함된 예시 이미지 | 직접 만든 이미지로 교체 예정 |