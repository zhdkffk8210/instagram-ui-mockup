# Instagram UI MockUp

Instagram 웹 피드 페이지를 HTML/CSS로 구현한 정적 목업 프로젝트입니다.

---

## HTML 구조 분석 및 설계

- `<header>` — 고정 상단 네비게이션 (로고, 검색, 아이콘)
- `<main>` — 피드 영역 (스토리 + 포스트) + 사이드 메뉴
- CSS 파일을 관심사별로 분리: `general.css` / `header.css` / `main.css` / `side.css`

## 시맨틱 태그를 이용한 마크업 구현

- `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>` 활용
- `<h1>`은 `sr-only` 클래스로 시각적 숨김 처리하여 스크린 리더 지원
- 아이콘 버튼에 `aria-label`, 모든 이미지에 `alt` 속성 명시

## CSS 레이아웃 구성 및 스타일링

- `:root`에 CSS 변수로 색상 토큰 관리 (`--text-dark`, `--border-color` 등)
- 전체 레이아웃 Flexbox 기반: 헤더(가로 배치), 피드(세로 배치), 스토리(가로 스크롤)
- 헤더/사이드 메뉴 `position: fixed`로 스크롤 시 고정
- 스토리 아바타는 SVG `<circle>` + CSS `stroke`로 원형 테두리 구현

## 반응형 미디어 쿼리 적용

- **기본 스타일이 모바일**, `min-width`로 점진 확장
- `620px` — 포스트/스토리에 `border` + `border-radius` 카드형 UI 전환
- `768px` — 헤더 검색바 표시
- `1024px` — 사이드 메뉴 표시, 배경색 변경

## 리소스(아이콘, 이미지 등) 적용

- `assets/icons/` — SVG 아이콘 17개 (로고, 네비게이션, 좋아요, 댓글, 공유 등)
- `assets/images/` — 프로필 이미지(`avatar.png`), 게시물 이미지(`picture.jpeg`)
- 프로필 이미지는 `border-radius: 50%`로 원형 클리핑
- Google Fonts `Roboto` (400/500/700) — `preconnect`로 로딩 최적화
