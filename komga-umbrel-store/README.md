# Yucheol Apps — 개인용 Umbrel 커뮤니티 앱 스토어

Umbrel 공식 스토어에 없는 앱을 정식 앱처럼 설치하기 위한 개인 스토어입니다.

## 구성

- `umbrel-app-store.yml` — 스토어 정보 (id: yucheol)
- `yucheol-komga/` — Komga 앱 패키지
  - `umbrel-app.yml` — 앱 매니페스트 (버전 1.29.2, 포트 25600)
  - `docker-compose.yml` — 컨테이너 정의

앱 id 규칙: 스토어 id + 앱 이름 (예: `yucheol-komga`). 폴더 이름과 매니페스트의 id가 반드시 같아야 합니다.

## 등록 방법

1. 이 폴더의 내용 그대로를 GitHub repo로 만들어 올립니다 (구조 유지).
2. Umbrel 앱스토어 우측 상단 ⋯ 메뉴 → Community App Stores → repo 주소(`.git`으로 끝나는 주소)를 붙여넣고 추가합니다.
3. 스토어 목록에 Komga가 뜨면 일반 앱처럼 설치합니다.
4. 설치 후 Komga 앱 설정에서 라이브러리 폴더 접근을 허용합니다. Synology 공유 안의 만화 폴더를 선택하면 Komga 안에서 `/data`로 보입니다 (읽기 전용).
5. Komga 웹 화면(umbrel.local:25600)에서 첫 계정을 만들고, 라이브러리를 추가할 때 `/data` 아래 폴더를 지정합니다.

## 메모

- Komga의 DB·설정은 Umbrel 로컬 앱 저장소(`/config`)에 보관됩니다. 네트워크 공유에는 두지 않습니다 (Komga 공식 문서의 요구사항).
- 라이브러리는 읽기 전용 마운트라 원본 파일이 수정되지 않습니다.
- 새 앱을 추가할 때는 폴더를 하나 더 만들고 같은 규칙으로 파일을 넣으면 됩니다.
