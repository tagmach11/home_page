# 뉴스룸 아티클 페이지 CSS 스타일 가이드

## 개요
뉴스룸에서 카드를 클릭했을 때 나오는 아티클 상세 페이지의 CSS 스타일을 정리한 문서입니다.

## 레이아웃 구조

### `.article-layout`
아티클 페이지의 메인 레이아웃 (콘텐츠 + 목차)

```css
.article-layout {
    display: grid;
    grid-template-columns: 1fr 300px;
    gap: 3rem;
    max-width: 1400px;
    margin: 0 auto;
}
```

**반응형:**
- 1200px 이하: `grid-template-columns: 1fr 250px; gap: 2rem;`
- 1024px 이하: `grid-template-columns: 1fr;` (목차가 아래로 이동)

## 아티클 상세 영역

### `.article-detail`
아티클 상세 콘텐츠 컨테이너

```css
.article-detail {
    padding: 2rem 0;
}
```

### `.article-header`
아티클 헤더 영역 (배지, 이미지, 제목, 메타 정보)

```css
.article-header {
    margin-bottom: 3rem;
    padding-bottom: 2rem;
    border-bottom: 1px solid #E5E7EB;
}
```

### `.article-badge`
아티클 배지 (카테고리 표시)

```css
.article-header .article-badge {
    position: static;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(135deg, #1E40AF 0%, #3B82F6 100%);
    color: white;
    padding: 0.35rem 0.85rem;
    border-radius: 20px;
    font-size: 0.75rem;
    font-weight: 700;
    margin-bottom: 1rem;
    letter-spacing: 0.5px;
    text-transform: uppercase;
    box-shadow: 0 2px 8px rgba(30, 64, 175, 0.3);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}
```

**배지 색상:**
- 기본: `linear-gradient(135deg, #1E40AF 0%, #3B82F6 100%)` (파란색)
- AI 기능: `#8b5cf6` (보라색)
- 인증: `#667eea` (남색)
- 수상: `#f59318` (주황색)

### `.article-detail-title`
아티클 제목

```css
.article-detail-title {
    font-size: 2.5rem;
    font-weight: 700;
    color: #1F2937;
    line-height: 1.3;
    margin-bottom: 0.75rem;
    margin-top: 0;
}
```

**반응형:**
- 768px 이하: `font-size: 1.75rem;`

### `.article-meta`
아티클 메타 정보 (날짜, 작성자)

```css
.article-meta {
    color: #9CA3AF;
    font-size: 0.95rem;
    margin-top: 0;
}
```

### `.article-image`
아티클 이미지 컨테이너

```css
.article-image {
    margin-bottom: 3rem;
}

.article-image img {
    display: block;
    max-width: 100%;
    height: auto;
}
```

**인라인 스타일 (HTML에서 사용):**
```html
<img src="..." style="max-width: 100%; height: auto; border-radius: 12px; box-shadow: 0 4px 20px rgba(0,0,0,0.1);">
```

## 섹션 스타일

### `.article-section`
아티클 섹션 컨테이너

```css
.article-section {
    margin-bottom: 3rem;
}
```

### `.article-section h2`
섹션 제목

```css
.article-section h2 {
    font-size: 1.75rem;
    font-weight: 700;
    color: var(--text-dark);
    margin-bottom: 1.5rem;
    padding-bottom: 0.5rem;
    border-bottom: 2px solid var(--border-color);
}
```

**반응형:**
- 768px 이하: `font-size: 1.4rem;`

### `.article-section h2 .section-number`
섹션 번호 (선택적)

```css
.article-section h2 .section-number {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 40px;
    height: 40px;
    background: linear-gradient(135deg, #1E40AF 0%, #3B82F6 100%);
    color: white;
    border-radius: 50%;
    text-align: center;
    line-height: 1;
    font-size: 1.1rem;
    font-weight: 700;
    margin-right: 0.75rem;
    vertical-align: middle;
    box-shadow: 0 2px 8px rgba(30, 64, 175, 0.3);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
    flex-shrink: 0;
}

.article-section h2:hover .section-number {
    transform: scale(1.05);
    box-shadow: 0 4px 12px rgba(30, 64, 175, 0.4);
}
```

### `.article-section p`
섹션 본문 텍스트

```css
.article-section p {
    font-size: 1.05rem;
    line-height: 1.8;
    color: var(--text-dark);
    margin-bottom: 1.5rem;
}
```

**인라인 스타일 (강조 텍스트):**
```html
<p style="font-size: 1.05rem; line-height: 1.8; color: #333; font-weight: 600; margin-bottom: 1.5rem;">
```

## 아티클 푸터

### `.article-footer`
아티클 푸터 영역

```css
.article-footer {
    margin-top: 4rem;
    padding-top: 2rem;
    border-top: 2px solid var(--border-color);
}
```

### `.back-button`
뒤로가기 버튼

```css
.back-button {
    display: inline-block;
    color: var(--dark-blue);
    font-weight: 600;
    text-decoration: none;
    padding: 0.75rem 1.5rem;
    border: 2px solid var(--dark-blue);
    border-radius: 8px;
    transition: all 0.3s;
}

.back-button:hover {
    background: var(--dark-blue);
    color: white;
    transform: translateX(-5px);
}
```

## 목차 (Table of Contents)

### `.table-of-contents`
목차 컨테이너 (오른쪽 고정)

```css
.table-of-contents {
    position: sticky;
    top: 120px;
    height: fit-content;
    background: transparent;
    border: none;
    border-radius: 0;
    padding: 0;
    box-shadow: none;
}
```

**반응형:**
- 1024px 이하: `position: relative; top: 0; margin-bottom: 3rem;`

### `.toc-header`
목차 헤더

```css
.toc-header h3 {
    font-size: 1rem;
    font-weight: 700;
    color: var(--text-dark);
    margin-bottom: 1rem;
    padding-bottom: 0.75rem;
    border-bottom: 1.5px solid var(--border-color);
}
```

### `.toc-nav`
목차 네비게이션

```css
.toc-nav {
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
}
```

### `.toc-link`
목차 링크

```css
.toc-link {
    display: block;
    padding: 0.625rem 0.75rem;
    color: var(--text-gray);
    text-decoration: none;
    font-size: 0.875rem;
    line-height: 1.6;
    border-radius: 8px;
    transition: all 0.15s ease;
}

.toc-link:hover {
    background: rgba(30, 58, 138, 0.05);
    color: var(--dark-blue);
}

.toc-link.active {
    background: rgba(30, 58, 138, 0.1);
    color: var(--dark-blue);
    font-weight: 600;
}
```

## 추가 컴포넌트

### `.summary-card`
요약 카드

```css
.summary-card {
    background: var(--bg-light);
    border-left: 4px solid var(--dark-blue);
    padding: 2rem;
    border-radius: 8px;
    margin-bottom: 3rem;
}

.summary-card h3 {
    font-size: 1.25rem;
    font-weight: 700;
    margin-bottom: 1.5rem;
    color: var(--text-dark);
}
```

### `.summary-grid`
요약 그리드

```css
.summary-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
}
```

**반응형:**
- 768px 이하: `grid-template-columns: 1fr;`

### `.problem-box`, `.solution-box`
문제/해결 박스

```css
.problem-box, .solution-box {
    background: var(--bg-light);
    padding: 1.5rem;
    border-radius: 8px;
    margin: 1.5rem 0;
}

.problem-box {
    border-left: 4px solid #EF4444; /* 빨간색 */
}

.solution-box {
    border-left: 4px solid #10B981; /* 초록색 */
}
```

### `.feature-list`, `.feature-item`
기능 리스트

```css
.feature-list {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
}

.feature-item {
    display: flex;
    gap: 1.5rem;
    background: var(--bg-light);
    padding: 1.5rem;
    border-radius: 8px;
}
```

**반응형:**
- 768px 이하: `flex-direction: column; text-align: center;`

### `.quote-box`
인용 박스

```css
.quote-box {
    background: linear-gradient(135deg, var(--gradient-start), var(--gradient-end));
    padding: 2.5rem;
    border-radius: 12px;
    color: white;
    margin: 3rem 0;
}

.quote-text {
    font-size: 1.15rem;
    font-style: italic;
    line-height: 1.8;
    margin: 0;
    text-align: center;
}
```

**반응형:**
- 768px 이하: `.quote-text { font-size: 1rem; }`

## 주요 색상 팔레트

- **Primary Text**: `#1F2937` / `var(--text-dark)`
- **Secondary Text**: `var(--text-gray)`
- **Meta Text**: `#9CA3AF`
- **Border**: `#E5E7EB` / `var(--border-color)`
- **Background Light**: `var(--bg-light)`
- **Background White**: `var(--bg-white)`
- **Primary Blue**: `#1E40AF` / `#3B82F6` / `var(--dark-blue)`
- **Gradient**: `linear-gradient(135deg, #1E40AF 0%, #3B82F6 100%)`
- **Shadow**: `rgba(30, 64, 175, 0.3)`

## 주요 타이포그래피

- **Article Title**: 2.5rem (모바일: 1.75rem), 700 weight
- **Section Title**: 1.75rem (모바일: 1.4rem), 700 weight
- **Body Text**: 1.05rem, line-height: 1.8
- **Meta Text**: 0.95rem
- **Badge**: 0.75rem, 700 weight, uppercase
- **TOC Link**: 0.875rem

## 레이아웃 구조 다이어그램

```
.article-layout
├── .article-detail (1fr)
│   ├── .article-header
│   │   ├── .article-badge
│   │   ├── .article-image
│   │   ├── .article-detail-title
│   │   └── .article-meta
│   ├── .article-section (반복)
│   │   ├── h2 (.section-number)
│   │   └── p
│   └── .article-footer
│       └── .back-button
└── .table-of-contents (300px)
    ├── .toc-header
    │   └── h3
    └── .toc-nav
        └── .toc-link (반복)
```

## 인라인 스타일 정리

### 이미지 스타일
```html
<img src="..." style="max-width: 100%; height: auto; border-radius: 12px; box-shadow: 0 4px 20px rgba(0,0,0,0.1);">
```

### 강조 텍스트 스타일
```html
<p style="font-size: 1.05rem; line-height: 1.8; color: #333; font-weight: 600; margin-bottom: 1.5rem;">
```

### 이미지 컨테이너 스타일
```html
<div style="margin: 2rem 0; text-align: center;">
```

## 반응형 브레이크포인트

- **1200px 이하**: 목차 너비 250px로 축소
- **1024px 이하**: 목차가 아래로 이동 (1열 레이아웃)
- **768px 이하**: 
  - 제목 크기 축소 (2.5rem → 1.75rem)
  - 섹션 제목 크기 축소 (1.75rem → 1.4rem)
  - 요약 그리드 1열로 변경
  - 기능 아이템 세로 배치


