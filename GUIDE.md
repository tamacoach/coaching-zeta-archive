# 🚀 코칭제타 행사 아카이브 - 사용 가이드

## 📦 포함된 파일

```
coachingjetta_work_space/
├── index.html              # 메인 설정 파일
├── README.md               # 홈페이지
├── _sidebar.md             # 사이드바 메뉴
├── .nojekyll              # GitHub Pages 설정
├── _media/                 # 프로필 이미지
│   ├── profile.jpg
│   └── favicon.ico
├── lectures/               # 행사 기록
│   └── 2025-12-13-reset2026.md
├── archive/                # 아카이브
│   └── all-lectures.md
├── about/                  # 소개
│   ├── intro.md
│   └── contact.md
└── images/                 # 이미지 폴더 (행사 사진, PDF 자료 등)
```

---

## 🏃 로컬에서 실행하기

### 방법 1: Python 서버

```bash
cd coachingjetta_work_space
python -m http.server 3000
```

브라우저에서 `http://localhost:3000` 접속

### 방법 2: VS Code Live Server

1. VS Code에서 폴더 열기
2. "Live Server" 확장 설치
3. `index.html` 우클릭 → "Open with Live Server"

### 방법 3: Docsify CLI

```bash
npm i docsify-cli -g
docsify serve coachingjetta_work_space
```

---

## 🌐 GitHub Pages에 배포하기

### 1. GitHub 저장소 만들기

```bash
cd coachingjetta_work_space
git init
git add .
git commit -m "초기 커밋: 코칭제타 행사 아카이브"
```

### 2. GitHub에 푸시

```bash
git remote add origin https://github.com/YOUR_USERNAME/coaching-zeta-archive.git
git branch -M master
git push -u origin master
```

### 3. GitHub Pages 활성화

1. 저장소 Settings 탭
2. Pages 메뉴
3. Source: master 브랜치 선택
4. Save!

5분 후 `https://YOUR_USERNAME.github.io/coaching-zeta-archive/` 에서 확인!

---

## ✏️ 새 행사 추가하기

### 1. 새 마크다운 파일 생성

`lectures/2025-XX-XX-new-event.md` 파일 생성

### 2. 내용 작성

기존 `2025-12-13-reset2026.md` 파일을 복사해서 수정하세요!

### 3. 사이드바 업데이트

`_sidebar.md` 파일에 새 링크 추가:

```markdown
- 📅 2025년
  - [12-13 Re:set 2026](/lectures/2025-12-13-reset2026)
  - [XX-XX 새 행사](/lectures/2025-XX-XX-new-event)  ← 추가
```

### 4. 아카이브 업데이트

`archive/all-lectures.md`에 새 행사 추가

### 5. 홈페이지 업데이트

`README.md`의 "최근 행사" 섹션 업데이트

---

## 🖼️ 이미지 및 파일 추가하기

### 1. 파일 업로드

`images/` 폴더에 이미지 또는 PDF 파일 넣기

### 2. 마크다운에서 참조 (**중요: Docsify 경로 규칙**)

Docsify는 SPA 방식이므로 **루트 기준 경로**를 사용해야 합니다:

```markdown
<!-- ✅ 올바른 방법 (루트 기준) -->
![설명](images/photo.jpg)

<!-- ❌ 잘못된 방법 (상대 경로) -->
![설명](../images/photo.jpg)
```

### 3. PDF 임베드하기

```html
<div class="pdf-container">
<iframe src="images/document.pdf" width="100%" height="600px" style="border: 1px solid #ddd; border-radius: 8px;" class="pdf-iframe"></iframe>
</div>

<div class="pdf-download-link">
📥 <a href="images/document.pdf" target="_blank" download>자료 다운로드</a>
</div>
```

### 4. 이미지 갤러리

```html
<div class="image-gallery">
  <img src="images/photo1.jpg" alt="사진1">
  <img src="images/photo2.jpg" alt="사진2">
  <img src="images/photo3.jpg" alt="사진3">
</div>
```

---

## 🎨 커스터마이징

### 색상 변경

`index.html`의 `:root` 부분 수정:

```css
:root {
  --theme-color: #4A90E2;  /* 원하는 색상으로 변경 */
}
```

### 프로필 이미지 변경

1. `_media/` 폴더에 원하는 이미지 추가
2. `index.html`에서 이미지 경로 수정
   - 현재: `_media/profile.jpg`

### 테마 변경

`index.html`의 CSS 링크 변경:

```html
<!-- Vue 테마 (기본) -->
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css">

<!-- 다크 테마 -->
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/dark.css">

<!-- Buble 테마 -->
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/buble.css">
```

---

## 📝 마크다운 팁

### 표 만들기

```markdown
| 항목 | 내용 |
|------|------|
| 날짜 | 2025-12-13 |
| 장소 | 서울 도곡타워팰리스 |
```

### 접기/펼치기

```markdown
<details>
<summary>제목</summary>

내용...

</details>
```

### 정보 박스

```html
<div class="info-box">
<h4>제목</h4>

내용...

</div>
```

### 통계 카드

```html
<div class="stats-grid">
  <div class="stat-card">
    <h3>22명</h3>
    <p>총 신청자</p>
  </div>
  <div class="stat-card">
    <h3>20명</h3>
    <p>실제 참석</p>
  </div>
</div>
```

### YouTube 임베드

```html
<iframe width="100%" height="450" src="https://www.youtube.com/embed/VIDEO_ID" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen style="border-radius: 8px; margin: 20px 0;"></iframe>
```

---

## 🔧 문제 해결

### Q: PDF가 404 에러로 안 보여요
A: 경로를 확인하세요. Docsify는 루트 기준 경로(`images/file.pdf`)를 사용해야 합니다. 상대 경로(`../images/file.pdf`)는 작동하지 않습니다.

### Q: 이미지가 로컬에서는 보이는데 GitHub Pages에서 안 보여요
A: 이미지 경로를 루트 기준으로 수정하세요 (`images/photo.jpg`)

### Q: 사이드바가 안 나와요
A: `_sidebar.md` 파일이 있는지 확인하세요

### Q: GitHub Pages에서 404 에러
A: `.nojekyll` 파일이 있는지 확인하세요

### Q: 검색이 안 돼요
A: 브라우저 캐시를 지우고 다시 시도하세요

### Q: 한글 파일명이 문제가 될까요?
A: GitHub Pages는 한글 파일명을 지원하지만, URL 인코딩 문제를 피하려면 영문 파일명 사용을 권장합니다.

---

## 💡 다음 단계

### 1. 실제 이미지로 교체
현재 placeholder 이미지를 실제 사진으로 교체하세요

### 2. 커스텀 도메인 연결
원하는 도메인을 GitHub Pages에 연결 가능

### 3. Google Analytics 추가
방문자 통계 추적

### 4. 댓글 기능 추가
Giscus 같은 댓글 시스템 추가 가능

### 5. 정기 행사 아카이빙
분기별 또는 월별로 행사를 체계적으로 정리

---

## 📞 도움이 필요하신가요?

궁금한 점이 있으면 언제든 물어보세요! 😊

## 🎯 Re:set 2026 프로젝트 팁

- 행사 자료(PDF)는 모두 `images/` 폴더에 저장
- 사진 파일명은 의미 있는 영문명 사용 (예: `speaker-kwon.jpg`)
- 각 섹션을 `<details>` 태그로 감싸서 페이지 로딩 최적화
- 모바일에서는 PDF iframe이 자동으로 숨겨지고 다운로드 버튼으로 대체됨
