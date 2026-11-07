# 다이빙솔루션 홈페이지

현재 디자인의 정적 웹사이트 배포 묶음입니다. 메인 1개, 교육 8개, 강사 9개 페이지를 포함합니다.

## GitHub 업로드

1. 기존 GitHub 계정을 그대로 사용합니다.
2. 홈페이지 전용 새 저장소 `divingsolution-home`을 생성합니다. 기존 투어 저장소 Maratha, Okinawa 및 캘린더 저장소는 덮어쓰지 않습니다.
3. 이 ZIP을 먼저 압축 해제합니다. `index.html`, `style.css`, `vercel.json`, `assets/`, `courses/`, `instructors/` 등 폴더 안의 파일과 하위 폴더를 저장소 최상위에 올립니다. ZIP 자체를 올리지 않습니다.
4. GitHub 웹 화면에서 Add file → Upload files로 업로드하고 Commit changes를 누릅니다. 큰 파일은 Git 클라이언트를 사용합니다.

저장소 최상위에 index.html이 있어야 합니다. divingsolution-github-upload 폴더를 한 겹 더 넣지 마세요.

## Vercel 연결

1. Vercel에서 Add New → Project → 위 GitHub 저장소를 Import합니다.
2. Framework Preset: Other.
3. Root Directory: 저장소 최상위(기본값).
4. 별도 설치·빌드 명령은 필요 없습니다. vercel.json의 outputDirectory는 현재 폴더(.)입니다.
5. Deploy 후 발급된 주소에서 메인, 교육·강사 상세페이지, 프로필 사진과 캘린더를 확인합니다.
6. GitHub와 연결된 배포 브랜치에 파일 변경을 반영하면 Vercel이 새로 배포합니다.

서비스 용도에 맞는 Vercel 요금제를 확인하세요. 이 묶음은 결제나 요금제 변경을 수행하지 않습니다.

## 기존 도메인 연결

Vercel 기본 주소에서 정상 동작을 확인한 다음 프로젝트 Settings → Domains에 divingsolution.kr와 www.divingsolution.kr를 추가합니다. 대표 주소와 리디렉션 방향을 정하고, Vercel 화면에 실제 표시된 DNS 값을 아임웹 도메인 관리에 적용합니다. IP나 CNAME 값을 임의로 쓰지 않습니다. 도메인 갱신은 기존 등록처에서 계속 관리합니다.

현재 묶음을 만든 것만으로 온라인 배포나 도메인 변경이 이뤄지지는 않습니다.

## 파일 구성

- index.html: 메인, 교육 목록, 강사 선택, 기존 캘린더 연동
- style.css / script.js: 공용 스타일과 보조 스크립트
- courses/: 교육 상세 8개 및 상담 스크립트
- instructors/: 강사 상세 9개와 멘토형 스타일
- assets/: 공식 가로·세로 로고, 현재 사용 중인 김종성 강사 사진
- vercel.json: Vercel 정적 배포 설정

## 운영 시 참고

- 캘린더는 기존 Supabase 프로젝트와 외부 JavaScript 라이브러리를 사용합니다. 기존 데이터 접근 정책과 서비스가 유지되어야 일정을 불러옵니다. 공개 클라이언트 설정이 포함되며 관리자용 서비스 키는 추가하지 않습니다.
- 상담 내용 복사는 방문자 기기에서만 수행합니다. 실제 상담 내용은 방문자가 카카오톡으로 직접 보냅니다.
- 교육비·운영 일정·취소 규정은 확정 자료에 따라 보완합니다. 게시 전 실제 교육 내용과 강사 정보를 최종 확인하세요.
- 기존 투어 링크는 해당 지역의 별도 사이트로 이동합니다.

공식 배포 안내: https://vercel.com/docs/deployments
빌드 설정 안내: https://vercel.com/docs/builds/configure-a-build
