# 디테일한 교육관리 히어로 섹션 디자인 가이드

## 개요
"디테일한 교육관리" 페이지의 히어로 섹션 디자인 구조와 CSS 스타일을 정리한 문서입니다. Glassmorphism 효과와 그라데이션 배경을 활용한 모던한 디자인입니다.

## 레이아웃 구조

### `.recent-articles-hero`
메인 히어로 카드 컨테이너

```css
.recent-articles-hero {
    display: grid;
    grid-template-columns: 1.2fr 1fr;
    gap: 3rem;
    background: var(--bg-white);
    border-radius: 20px;
    padding: 2rem 3rem 3rem 0rem;
    margin-top: 0;
    margin-bottom: 3rem;
    min-height: 400px;
    align-items: center;
}
```

**레이아웃:**
- 2열 그리드 (1.2:1 비율)
- 왼쪽: 이미지 섹션 (1.2fr)
- 오른쪽: 콘텐츠 섹션 (1fr)
- 최소 높이: 400px

## 이미지 섹션

### `.hero-image-section`
이미지 컨테이너

```css
.hero-image-section {
    position: relative;
    height: 100%;
    min-height: 350px;
}
```

### `.hero-image-placeholder`
이미지 플레이스홀더 (그라데이션 배경)

```css
.hero-image-placeholder {
    width: 100%;
    height: 100%;
    border-radius: 16px;
    overflow: hidden;
    background: linear-gradient(135deg, var(--primary-blue), var(--primary-purple));
    position: relative;
}
```

**그라데이션 색상:**
- 시작: `var(--primary-blue)` (보통 #1E40AF 또는 #3B82F6)
- 끝: `var(--primary-purple)` (보통 #764BA2 또는 #667EEA)

**이미지 인라인 스타일:**
```html
<img src="..." style="width: 100%; height: 100%; object-fit: cover; border-radius: 12px;">
```

### `.hero-image-overlay`
이미지 오버레이 (선택적)

```css
.hero-image-overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: #000;
    padding: 1.5rem 2rem;
    display: flex;
    align-items: center;
    justify-content: center;
}
```

### `.hero-image-title`
이미지 내 제목 (선택적)

```css
.hero-image-title {
    font-size: 2.5rem;
    font-weight: 700;
    color: white;
    margin: 0;
    line-height: 1.2;
}
```

## 콘텐츠 섹션

### `.hero-content-section`
콘텐츠 영역

```css
.hero-content-section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 1rem;
}
```

### `.recent-articles-label`
라벨 (최근 게시물)

```css
.hero-content-section .recent-articles-label {
    font-size: 0.9rem;
    font-weight: 600;
    color: var(--text-gray);
    letter-spacing: 0.02em;
    text-transform: uppercase;
    margin-bottom: 0.5rem;
    display: block;
}
```

### `.hero-content-section .section-title`
섹션 제목

```css
.hero-content-section .section-title {
    margin-bottom: 1rem;
}

.section-title {
    font-size: 2rem;
    font-weight: 700;
    color: var(--text-dark);
    margin: 0;
}
```

### `.hero-description`
설명 텍스트

```css
.hero-description {
    font-size: 1.2rem;
    color: var(--text-gray);
    line-height: 1.6;
    margin: 0.5rem 0;
}
```

### `.hero-meta`
메타 정보 (날짜 등)

```css
.hero-meta {
    font-size: 0.95rem;
    color: var(--text-light);
    margin-top: 0.5rem;
}
```

## Glassmorphism 효과

### `.hero-glass-section`
Glassmorphism 히어로 섹션 (선택적 스타일)

```css
.hero-glass-section {
    position: relative;
    width: 100%;
    min-height: 600px;
    margin: 2rem 0 4rem 0;
    border-radius: 24px;
    overflow: hidden;
    isolation: isolate;
    opacity: 0;
    transform: translateY(30px);
    animation: fadeInUp 1s ease-out forwards;
}
```

### `.hero-background`
그라데이션 배경

```css
.hero-background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(180deg, 
        #020617 0%, 
        #0f172a 5%,
        #1e293b 10%,
        #1e3a8a 20%,
        #1e40af 30%,
        #1e3a8a 40%,
        #1e40af 50%,
        #2563eb 60%,
        #3b82f6 70%,
        #fbbf24 80%,
        #f59e0b 90%,
        #d97706 100%);
    background-image: 
        radial-gradient(ellipse at 20% 20%, rgba(30, 58, 138, 0.9) 0%, transparent 50%),
        radial-gradient(ellipse at 80% 40%, rgba(30, 64, 175, 0.8) 0%, transparent 50%),
        radial-gradient(ellipse at 50% 50%, rgba(37, 99, 235, 0.8) 0%, transparent 60%),
        /* ... 추가 radial-gradient들 ... */;
    z-index: 1;
    overflow: hidden;
}
```

**Glassmorphism 효과 적용:**
```css
backdrop-filter: blur(20px) saturate(180%);
-webkit-backdrop-filter: blur(20px) saturate(180%);
background: rgba(255, 255, 255, 0.1);
border: 1px solid rgba(255, 255, 255, 0.2);
```

## 애니메이션

### `@keyframes fadeInUp`
페이드인 업 애니메이션

```css
@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```

### `@keyframes cloudFloat`
구름 플로팅 애니메이션 (배경용)

```css
@keyframes cloudFloat {
    /* 구름 효과 애니메이션 */
}
```

## 칠판 카드 디자인 (이미지 기반)

이미지에서 보이는 칠판 카드는 HTML 구조로 구현할 수 있습니다:

```html
<div class="chalkboard-card">
    <div class="chalkboard-header">
        <span class="chalkboard-label">교육</span>
        <span class="chalkboard-label">학습</span>
    </div>
    <div class="chalkboard-content">
        <p class="chalkboard-question">원하는 방식으로 진행하려면...</p>
        <h3 class="chalkboard-main-text">진도율 조정해?</h3>
        <p class="chalkboard-footer">학습 진도, 더 정교하게 관리하자!</p>
    </div>
</div>
```

**칠판 카드 CSS (추정):**
```css
.chalkboard-card {
    background: linear-gradient(135deg, #2d5016 0%, #3a6b1f 100%);
    border: 8px solid #8b6914;
    border-radius: 8px;
    padding: 2rem;
    color: white;
    font-family: 'Chalk', cursive;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.3);
}

.chalkboard-label {
    background: #8b6914;
    color: white;
    padding: 0.25rem 0.75rem;
    border-radius: 4px;
    font-size: 0.75rem;
    font-weight: 600;
}

.chalkboard-question {
    font-size: 1rem;
    margin-bottom: 1rem;
}

.chalkboard-main-text {
    font-size: 2rem;
    font-weight: 700;
    margin: 1rem 0;
}

.chalkboard-footer {
    font-size: 0.9rem;
    margin-top: 1.5rem;
    padding-top: 1rem;
    border-top: 1px solid rgba(255, 255, 255, 0.2);
}
```

## 반응형 디자인

### 태블릿 (1024px 이하)
```css
@media (max-width: 1024px) {
    .recent-articles-hero {
        grid-template-columns: 1fr;
        gap: 2rem;
        padding: 2rem;
    }
    
    .hero-image-section {
        min-height: 300px;
    }
}
```

### 모바일 (768px 이하)
```css
@media (max-width: 768px) {
    .recent-articles-hero {
        grid-template-columns: 1fr;
        padding: 1.5rem;
        min-height: auto;
    }
    
    .hero-content-section .section-title {
        font-size: 1.5rem;
    }
    
    .hero-description {
        font-size: 1rem;
    }
}
```

## HTML 구조 예시

```html
<div class="recent-articles-hero">
    <!-- 왼쪽: 이미지 섹션 -->
    <div class="hero-image-section">
        <div class="hero-image-placeholder">
            <img src="../assets/thumbnails/다양한학습진도설정.png" 
                 alt="다양한 학습진도 설정" 
                 style="width: 100%; height: 100%; object-fit: cover; border-radius: 12px;">
        </div>
    </div>
    
    <!-- 오른쪽: 콘텐츠 섹션 -->
    <div class="hero-content-section">
        <span class="recent-articles-label">최근 게시물</span>
        <h2 class="section-title">다양한 학습진도 설정</h2>
        <p class="hero-description">순차·비순차 학습, 최소·인정 진도율</p>
        <p class="hero-meta">2025년 · LX2</p>
    </div>
</div>
```

## 주요 색상 팔레트

- **Primary Blue**: `#1E40AF` / `#3B82F6`
- **Primary Purple**: `#764BA2` / `#667EEA`
- **Gradient Start**: `var(--primary-blue)`
- **Gradient End**: `var(--primary-purple)`
- **Text Dark**: `var(--text-dark)`
- **Text Gray**: `var(--text-gray)`
- **Text Light**: `var(--text-light)`
- **Background White**: `var(--bg-white)`

## 타이포그래피

- **Section Title**: 2rem, 700 weight
- **Hero Description**: 1.2rem, normal weight
- **Hero Meta**: 0.95rem, normal weight
- **Label**: 0.9rem, 600 weight, uppercase

## 디자인 특징

1. **Glassmorphism 효과**: 반투명 배경 + 블러 효과
2. **그라데이션 배경**: 블루에서 퍼플로 자연스러운 전환
3. **2열 레이아웃**: 이미지와 텍스트의 균형잡힌 배치
4. **둥근 모서리**: 20px border-radius로 모던한 느낌
5. **애니메이션**: 페이드인 효과로 부드러운 등장

## 레이아웃 다이어그램

```
.recent-articles-hero (grid: 1.2fr 1fr)
├── .hero-image-section (1.2fr)
│   └── .hero-image-placeholder
│       └── <img> (그라데이션 배경 또는 이미지)
└── .hero-content-section (1fr)
    ├── .recent-articles-label
    ├── .section-title
    ├── .hero-description
    └── .hero-meta
```


