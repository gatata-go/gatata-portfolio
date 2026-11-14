# GATATA — Pages CMS 버전

## 포함된 파일
- `index.html`: 방문자 전용 공개 갤러리. 수정 버튼과 localStorage 편집 기능 제거.
- `.pages.yml`: Pages CMS 설정 (작품 / 프로필 / 메인 배너 / 카테고리).
- `data/site.json`: 작가 정보, 배너, 카테고리.
- `data/artworks.json`: 작품 목록 (각 작품의 `id`는 고유해야 함).
- `media/`: Pages CMS에서 업로드한 이미지.

## GitHub Pages + Pages CMS 연결
1. GitHub에서 새 **공개 저장소**를 만듭니다. (예: `gatata-portfolio`)
2. ZIP을 압축 해제하고 **폴더 안의 파일들** (`index.html`, `.pages.yml`, `data`, `media`)을 저장소 **최상위**에 업로드합니다. `.pages.yml`은 숨김 파일이므로 빠지지 않았는지 확인합니다.
3. GitHub 저장소 → Settings → Pages → Build and deployment → Deploy from a branch → `main` / `/(root)` → Save.
4. Pages 배포가 끝나면 `https://<사용자명>.github.io/<저장소명>/`에서 사이트를 확인합니다.
5. https://app.pagescms.org 에서 GitHub로 로그인하고 해당 저장소 접근을 허용합니다.
6. Pages CMS의 `작품 관리`에서 작품 목록을 수정하거나 항목을 추가합니다. 이미지는 CMS 이미지 선택기에서 업로드합니다.
7. `작가 프로필 · 메인 배너 · 카테고리`에서 소개, 배너, 카테고리를 수정합니다.
8. 저장하면 GitHub에 커밋됩니다. GitHub Pages 재배포가 완료되면 공개 사이트에 반영됩니다.

## 주의사항
- 이 버전은 **Pages CMS에서만 콘텐츠를 수정**합니다. 공개 사이트에는 편집 기능이나 로그인 화면이 없습니다.
- 관리자 로그인은 **Pages CMS의 GitHub 인증**을 사용합니다. 공개 사이트의 `/admin` 페이지를 만들지 않습니다.
- 공개 GitHub 저장소의 데이터/이미지는 모두 공개됩니다. 비밀번호, 비밀 키, 미공개 작품은 올리지 마세요.
- Pages CMS에 저장소 편집 권한을 허용한 GitHub 사용자만 수정할 수 있도록 GitHub 저장소 권한을 관리하세요. GitHub 2단계 인증을 권장합니다.
- `index.html`을 컴퓨터에서 **더블클릭해 file:// 로 열면** 브라우저가 JSON fetch를 차단할 수 있습니다. GitHub Pages에 올려 확인하거나 로컬 서버(`python -m http.server 8000`)를 사용하세요.
- 기존 HTML의 localStorage에만 저장된 개인 작품/프로필은 자동 이전되지 않습니다. Pages CMS에서 다시 등록해야 합니다.
- 작품 이미지가 큰 경우 GitHub 저장소 용량이 늘어납니다. 웹용으로 압축한 JPG/WEBP 권장.
- CMS에 저장한 새 작품의 `id`는 반드시 고유한 값을 입력하세요.
- `media` 이미지 경로는 GitHub Pages의 프로젝트 하위 경로에서도 동작하도록 상대 경로로 설정했습니다.
