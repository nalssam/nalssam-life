# 날쌤의 쓸모 있는 기록
GitHub Pages용 반응형 개인 저널. 의존성 없는 Python 정적 생성 + JavaScript 검색/카테고리/브라우저 저장 + 네이티브 공유.

## 실행
`python build.py` → dist/. 로컬 미리보기 `SITE_URL=http://localhost:8000 python build.py && python -m http.server 8000 -d dist`

## 발행
GitHub Settings → Pages → Source: GitHub Actions. main 커밋 후 Publish journal 실행. 주소 https://nalssam.github.io/nalssam-life/
GitHub 소유자 인증과 저장소 권한을 발행 백엔드로 사용합니다. 사이트 자체 로그인/CMS/비공개 초안 DB는 아직 연결하지 않았습니다. 방문자에게 쓰기 권한을 주지 않고 공개 회원가입은 없습니다. 소유자 외 collaborator를 추가하지 마세요.

## 글 추가
content/posts.json 배열에 기존 글 형식을 복사해 추가. slug는 영문 숫자 하이픈, category는 9개 분류 중 선택, body는 문단 문자열 배열. HTML은 이스케이프됩니다. main 커밋 즉시 자동 발행되므로 검토 후 커밋. 공개 저장소의 초안도 공개됩니다. 개인정보/학생 기록/키/토큰을 넣지 마세요.
사진은 얼굴 모자이크를 완료한 이미지에 한해 사용. 현재 버전은 인물 사진 없이 CSS 그래픽만 사용합니다. 운영시간·가격·경험을 지어내지 않습니다.

## 검색 노출
서버 렌더된 글별 HTML, canonical, description, Open Graph, BlogPosting JSON-LD, sitemap.xml, robots.txt, RSS 포함. 구조화 데이터는 실제 공개 본문과 일치합니다. 검색 순위/노출 보장은 하지 않습니다. 배포 후 Google Search Console / 네이버 서치어드바이저 소유 확인과 sitemap 제출은 별도로 필요합니다. 확인 토큰을 받은 후 추가 가능합니다.

## 검증
python build.py / node --check assets/app.js. 홈페이지·모든 링크·모바일·저장 재진입·빈 검색을 확인하세요. 운영 URL 변경 시 SITE_URL과 워크플로 env 수정.
