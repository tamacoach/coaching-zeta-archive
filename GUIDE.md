# 🚀 동해시 AI 강연 아카이브 - 사용 가이드

## 📦 포함된 파일

```
donghe-ai-lecture/
├── index.html              # 메인 설정 파일
├── README.md               # 홈페이지
├── _sidebar.md             # 사이드바 메뉴
├── .nojekyll              # GitHub Pages 설정
├── lectures/               # 강연 기록
│   └── 2025-08-30-donghe-ai.md
├── archive/                # 아카이브
│   └── all-lectures.md
├── about/                  # 소개
│   ├── intro.md
│   └── contact.md
└── images/                 # 이미지 폴더 (사용자가 추가)
```

---

## 🏃 로컬에서 실행하기

### 방법 1: Python 서버

```bash
cd donghe-ai-lecture
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
docsify serve donghe-ai-lecture
```

---

## 🌐 GitHub Pages에 배포하기

### 1. GitHub 저장소 만들기

```bash
cd donghe-ai-lecture
git init
git add .
git commit -m "초기 커밋: 동해시 AI 강연 아카이브"
```

### 2. GitHub에 푸시

```bash
git remote add origin https://github.com/YOUR_USERNAME/donghe-ai-archive.git
git branch -M main
git push -u origin main
```

### 3. GitHub Pages 활성화

1. 저장소 Settings 탭
2. Pages 메뉴
3. Source: main 브랜치 선택
4. Save!

5분 후 `https://YOUR_USERNAME.github.io/donghe-ai-archive/` 에서 확인!

---

## ✏️ 새 강연 추가하기

### 1. 새 마크다운 파일 생성

`lectures/2025-XX-XX-new-lecture.md` 파일 생성

### 2. 내용 작성

기존 `2025-08-30-donghe-ai.md` 파일을 복사해서 수정하세요!

### 3. 사이드바 업데이트

`_sidebar.md` 파일에 새 링크 추가:

```markdown
- 📅 2025년
  - [08-30 동해시 AI 강연](/lectures/2025-08-30-donghe-ai)
  - [XX-XX 새 강연](/lectures/2025-XX-XX-new-lecture)  ← 추가
```

### 4. 홈페이지 업데이트

`README.md`의 "최근 강연" 섹션 업데이트

---

## 🖼️ 이미지 추가하기

### 1. 이미지 파일 업로드

`images/` 폴더에 이미지 파일 넣기

### 2. 마크다운에서 참조

```markdown
![설명](./images/photo.jpg)
```

또는 절대 경로:

```markdown
![설명](/images/photo.jpg)
```

### 3. 이미지 갤러리

```html
<div class="image-gallery">
  <img src="./images/photo1.jpg" alt="사진1">
  <img src="./images/photo2.jpg" alt="사진2">
  <img src="./images/photo3.jpg" alt="사진3">
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

### 로고 추가

1. `_media/logo.png` 파일 추가
2. `index.html`에서 자동으로 표시됨

### 테마 변경

`index.html`의 CSS 링크 변경:

```html
<!-- 다크 테마 -->
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/dark.css">
```

---

## 📝 마크다운 팁

### 표 만들기

```markdown
| 항목 | 내용 |
|------|------|
| 날짜 | 2025-08-30 |
| 장소 | 동해시 |
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
    <h3>숫자</h3>
    <p>설명</p>
  </div>
</div>
```

---

## 🔧 문제 해결

### Q: 이미지가 안 보여요
A: 이미지 경로를 확인하세요. `/images/` 또는 `./images/`

### Q: 사이드바가 안 나와요
A: `_sidebar.md` 파일이 있는지 확인하세요

### Q: GitHub Pages에서 404 에러
A: `.nojekyll` 파일이 있는지 확인하세요

### Q: 검색이 안 돼요
A: 브라우저 캐시를 지우고 다시 시도하세요

---

## 💡 다음 단계

### 1. 실제 이미지로 교체
현재 placeholder 이미지를 실제 사진으로 교체하세요

### 2. 커스텀 도메인 연결
`tuk.me` 같은 도메인 연결 가능

### 3. Google Analytics 추가
방문자 통계 추적

### 4. 댓글 기능 추가
Giscus 같은 댓글 시스템 추가 가능

---

## 📞 도움이 필요하신가요?

궁금한 점이 있으면 언제든 물어보세요! 😊
