# 업데이트 정보 CSS 스타일 가이드

## 개요
업데이트 정보 페이지(`dev-update.html`)에서 사용되는 CSS 스타일을 정리한 문서입니다.

## 주요 컨테이너

### `.update-main-container`
메인 레이아웃 컨테이너 (70% 콘텐츠 + 30% 네비게이션)

```css
.update-main-container {
    display: grid;
    grid-template-columns: 70% 30%;
    gap: 4rem;
    max-width: 1400px;
    margin: 0 auto;
    padding: 2rem 0;
}
```

### `.update-content`
업데이트 콘텐츠 영역

```css
.update-content {
    background: #FFFFFF;
}
```

## 버전 섹션

### `.version-section`
각 버전 정보를 담는 섹션

```css
.version-section {
    margin-bottom: 3rem;
    padding: 2rem;
    background: #FFFFFF;
    border-radius: 16px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.04);
    scroll-margin-top: 2rem;
}
```

### `.version-title`
버전 제목 (예: Version 2.5.0)

```css
.version-title {
    font-size: 1.75rem;
    font-weight: 700;
    color: #1A1A1A;
    margin: 0 0 0.5rem 0;
    letter-spacing: -0.02em;
}
```

### `.version-date`
버전 릴리즈 날짜

```css
.version-date {
    font-size: 0.875rem;
    color: #8B8B8B;
    margin-bottom: 2rem;
    font-weight: 400;
}
```

## 섹션 서브타이틀

### `.section-subtitle`
신규기능, 개선사항, 오류수정 등의 섹션 제목

```css
.section-subtitle {
    font-size: 1rem;
    font-weight: 600;
    color: #1A1A1A;
    margin: 2rem 0 1rem 0;
    display: flex;
    align-items: center;
    gap: 0.5rem;
}
```

### `.section-subtitle::before`
서브타이틀 앞의 그라데이션 바

```css
.section-subtitle::before {
    content: '';
    width: 4px;
    height: 16px;
    background: linear-gradient(135deg, #667EEA 0%, #764BA2 100%);
    border-radius: 2px;
}
```

## 변경사항 리스트

### `.change-list`
변경사항 목록 컨테이너

```css
.change-list {
    list-style: none;
    padding: 0;
    margin: 0 0 2rem 0;
}
```

### `.change-item`
개별 변경사항 아이템

```css
.change-item {
    padding: 1rem 1.25rem;
    margin-bottom: 0.5rem;
    background: #F8F9FA;
    border-radius: 12px;
    border-left: 3px solid transparent;
    font-size: 0.95rem;
    line-height: 1.6;
    color: #2D3748;
}
```

### `.change-description`
변경사항 설명 텍스트

```css
.change-description {
    color: #2D3748;
    margin: 0;
}
```

### `.feedback-link`
피드백 링크

```css
.feedback-link {
    color: #0067C5;
    text-decoration: none;
    font-size: 0.9rem;
}

.feedback-link:hover {
    text-decoration: underline;
}
```

## 스티키 네비게이션

### `.sticky-nav`
오른쪽 고정 네비게이션 영역

```css
.sticky-nav {
    position: sticky;
    top: 2rem;
    height: fit-content;
    max-height: calc(100vh - 4rem);
    overflow-y: hidden;
}
```

### `.nav-title`
네비게이션 제목

```css
.nav-title {
    font-size: 1rem;
    font-weight: 600;
    color: var(--text-dark);
    margin-bottom: 0.5rem;
}
```

### `.nav-menu`
네비게이션 메뉴 컨테이너

```css
.nav-menu {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 0rem;
    margin-bottom: 0;
}
```

### `.nav-menu-link`
네비게이션 링크

```css
.nav-menu-link {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    padding: 0.4rem 1rem;
    color: var(--text-dark);
    text-decoration: none;
    border-radius: 8px;
    transition: all 0.2s;
    font-weight: 500;
    font-size: 0.9rem;
    position: relative;
}

.nav-menu-link:hover {
    background: var(--bg-light);
    color: var(--dark-blue);
}

.nav-menu-link.active {
    background: rgba(30, 58, 138, 0.1);
    color: var(--dark-blue);
}
```

### `.nav-menu-default`
기본 표시되는 네비게이션 메뉴

```css
.nav-menu-default {
    display: flex;
    flex-direction: column;
    gap: 0rem;
}

.nav-menu-default.hide {
    display: none;
}
```

### `.nav-menu-more`
더보기 네비게이션 메뉴

```css
.nav-menu-more {
    display: none;
}

.nav-menu-more.show {
    display: block;
}
```

### `.nav-more-btn`
더보기 버튼

```css
.nav-more-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    padding: 0.5rem 1.25rem;
    color: var(--dark-blue);
    text-decoration: none;
    border-radius: 8px;
    transition: all 0.2s;
    font-weight: 500;
    font-size: 1rem;
    cursor: pointer;
    margin-top: 0.5rem;
    background: var(--bg-light);
}

.nav-more-btn:hover {
    background: rgba(30, 58, 138, 0.1);
}
```

## 주요 색상 팔레트

- **Primary Text**: `#1A1A1A`
- **Secondary Text**: `#2D3748`
- **Date Text**: `#8B8B8B`
- **Background Light**: `#F8F9FA`
- **Background White**: `#FFFFFF`
- **Link Blue**: `#0067C5`
- **Gradient Start**: `#667EEA`
- **Gradient End**: `#764BA2`
- **Active Background**: `rgba(30, 58, 138, 0.1)`
- **Shadow**: `rgba(0, 0, 0, 0.04)`

## 주요 타이포그래피

- **Version Title**: 1.75rem, 700 weight
- **Section Subtitle**: 1rem, 600 weight
- **Change Description**: 0.95rem, normal weight
- **Version Date**: 0.875rem, normal weight
- **Nav Link**: 0.9rem, 500 weight

## 레이아웃 구조

```
.update-main-container
├── .update-content (70%)
│   └── .version-section (반복)
│       ├── .version-title
│       ├── .version-date
│       └── .section-subtitle (반복)
│           └── .change-list
│               └── .change-item (반복)
│                   └── .change-description
└── .sticky-nav (30%)
    ├── .nav-title
    └── .nav-menu
        ├── .nav-menu-default
        │   └── .nav-menu-link (반복)
        ├── .nav-menu-more
        │   └── .nav-menu-link (반복)
        └── .nav-more-btn
```

