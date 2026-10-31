# ChatGPT 대화로 개발한 업무 보조도구 — 공개용 가상 포털

이 프로젝트는 실제 업무 도구의 **화면 구성과 주요 상호작용을 가상 데이터로 재현한 안전한 공개 데모**입니다. 실제 업무 시스템, 인허가 기관, 비공개 저장소, 개인 식별정보와 연결되지 않습니다.

## 기능

- `#/applications` 가상의 신청 상세 사이트 및 그 위에 나타나는 검토 패널. 신청 건을 선택하면 주소·지번·첨부 판정이 바뀝니다.
- 지도 오버레이: 신청 필지를 허용 구역 위에 강조 (실제 지도 아님)
- 근거문서: 해당 지번 강조 검색 (가상 문서)
- 보완 문구 다중 선택 및 로컬 복사
- `#/manager` 대시보드·구역 편집·예외 검수·데이터 관리
- `#/territory` 구역정보 관리
- `#/renewal` 대량 신청 현황 대조·전일 변동·예외 검수·가상 CSV 보고서 다운로드
- `#/issuance` 서류 발급 입력보조 시연 (실제 발급 없음)
- `#/story` 제작 경위, AI 활용 방식 및 공개 범위 안내

## 브라우저 실행

`index.html` 파일을 열면 됩니다. 별도 서버, 로그인, 설치, API 키가 필요 없습니다. 공개 사이트에서 실제 업무를 처리하는 기능은 없습니다.

## GitHub Pages 신규 배포

### GitHub 웹 UI로 게시

1. 새 **공개** 저장소 `ai-workflow-public-demo`를 만듭니다.
2. 이 패키지의 `index.html`, `assets/`, `.github/`, `.nojekyll`, `README.md`, `PRIVACY.md` 파일을 저장소 루트에 업로드합니다.
3. Settings → Pages → Build and deployment → Source를 **GitHub Actions**로 설정합니다.
4. Actions에서 `Publish public demo to GitHub Pages` 워크플로가 완료되면 사이트가 게시됩니다.
5. 예상 주소: `https://goyoung2.github.io/ai-workflow-public-demo/` (저장소 소유자와 이름을 바꾼 경우 다르게 표시됩니다).

### Windows에서 GitHub CLI로 게시

Git 및 GitHub CLI(`gh`)가 설치되어 있고 `gh auth login`을 완료한 PC에서 `DEPLOY_GITHUB_PAGES.ps1`을 실행합니다. 새 저장소를 만들고, 파일을 업로드하며, Pages 설정을 시도합니다. 기존 비공개 업무 저장소는 전혀 건드리지 않습니다.

## 파일 구성

- `index.html`, `assets/app.css`, `assets/app.js`: 실제 웹사이트
- `.github/workflows/deploy-pages.yml`: Pages 자동 배포 설정
- `DEPLOY_GITHUB_PAGES.ps1`: 인증된 Windows PC에서 1회 배포 자동화
- `PRIVACY.md`: 공개 안전 경계
- `screenshots/`: 개발 중 가상 데이터로 촬영한 화면

이 데모는 독립 구현물이며 실제 업무 도구의 원본 소스코드 또는 실제 운영 화면의 녹화본이 아닙니다.
