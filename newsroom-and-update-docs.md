# 뉴스룸 및 업데이트 정보 HTML/CSS 문서

## 목차
1. [뉴스룸 (newsroom.html)](#뉴스룸-newsroomhtml)
2. [업데이트 정보 (dev-update.html)](#업데이트-정보-dev-updatehtml)

---

## 뉴스룸 (newsroom.html)

### HTML 구조

#### 메인 레이아웃
```html
<!-- Newsroom Layout -->
<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; margin-top: 2rem;">
    
    <!-- Left: Main Featured Article -->
    <article style="background: white; border-radius: 16px; overflow: hidden; box-shadow: 0 4px 20px rgba(0,0,0,0.1); border: 1px solid rgba(0,0,0,0.05); height: fit-content;">
        <a href="article-sw-competition.html" style="text-decoration: none; color: inherit; display: block;">
            <div style="position: relative; cursor: pointer; transition: transform 0.2s; overflow: hidden;">
                <img src="../assets/articles/sw대상.png" alt="신SW상품대상" style="width: 100%; height: 100%; object-fit: cover; display: block;">
            </div>
            <div style="padding: 2rem; background: rgba(240, 147, 251, 0.02); border-top: 1px solid rgba(240, 147, 251, 0.1);">
                <h2 style="font-size: 1.5rem; font-weight: 700; line-height: 1.4; color: #1a1a1a; margin: 0 0 1rem 0;">신SW상품대상<br/>멀티미디어&서비스SW 부문 수상</h2>
                <div style="display: flex; align-items: center; gap: 1rem; margin-bottom: 1.5rem;">
                    <div>
                        <div style="font-size: 0.9rem; color: #666;">2025년 6월</div>
                    </div>
                </div>
                
                <p style="font-size: 1rem; line-height: 1.8; color: #333;">
                    과학기술정보통신부 주최, 전자신문 주관 '2025년 6월 신SW상품대상' 멀티미디어&서비스SW 부문 수상. AI 기반 맞춤형 학습관리시스템으로 교육 프로세스 일원화를 실현했습니다.
                </p>
                
                <div style="margin-top: 1.5rem; padding-top: 1.5rem; border-top: 1px solid #e0e0e0; text-align: center; color: #999;">
                    자세히 보기 →
                </div>
            </div>
        </a>
    </article>

    <!-- Right: 4 Cards Grid -->
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; grid-auto-rows: 1fr;">
        <!-- Card items -->
    </div>
</div>
```

#### 카드 아이템 스타일
```html
<article style="background: white; border-radius: 10px; overflow: hidden; box-shadow: 0 2px 8px rgba(0,0,0,0.1); transition: all 0.2s; cursor: pointer; border: 1px solid rgba(0,0,0,0.05); display: flex; flex-direction: column;">
    <a href="article-ai-counseling.html" style="text-decoration: none; color: inherit; display: flex; flex-direction: column; height: 100%;">
        <div style="position: relative; height: 180px; overflow: hidden;">
            <img src="../assets/articles/뉴스룸학생상담.png" alt="AI 다국어 학생 상담" style="width: 100%; height: 100%; object-fit: cover; display: block;">
        </div>
        <div style="padding: 0.875rem; flex: 1; display: flex; flex-direction: column; justify-content: space-between;">
            <div>
                <span style="color: #8b5cf6; font-weight: 600; font-size: 0.7rem; letter-spacing: 0.05em;">AI 기능</span>
                <h4 style="font-size: 0.875rem; font-weight: 600; margin: 0.5rem 0 0 0; color: #1a1a1a; line-height: 1.4;">AI 다국어 학생 상담 기능</h4>
            </div>
            <p style="font-size: 0.7rem; color: #666; margin: 0;">2025년 8월 14일</p>
        </div>
    </a>
</article>
```

#### CTA 섹션
```html
<!-- Development Update Link Section -->
<div style="margin-top: 4rem; text-align: center; padding: 3rem; background: #EFF1FF; border-radius: 16px;">
    <p style="font-size: 1.3rem; font-weight: 700; margin-bottom: 1rem; color: #5850EE;">LX2를 무료로 체험해보세요.</p>
    <h2 style="font-size: 2.2rem; color: black; margin-bottom: 2rem;">써보면서 이해하는 게 가장 빠릅니다</h2>
    <a href="https://www.lx2.kr/common/greeting.do" target="_blank" style="display: inline-block; background: #594CEE; color: white; padding: 1rem 2rem; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 1.1rem; transition: all 0.3s;" onmouseover="this.style.transform='translateY(-2px)'; this.style.boxShadow='0 4px 12px rgba(0,0,0,0.2)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='none'">
        LX2 바로 체험하기
    </a>
</div>
```

### 주요 스타일 속성

#### 메인 피처드 아티클
- `background: white`
- `border-radius: 16px`
- `box-shadow: 0 4px 20px rgba(0,0,0,0.1)`
- `border: 1px solid rgba(0,0,0,0.05)`
- 내부 패딩: `padding: 2rem`
- 배경색: `rgba(240, 147, 251, 0.02)`

#### 그리드 카드
- `border-radius: 10px`
- `box-shadow: 0 2px 8px rgba(0,0,0,0.1)`
- 이미지 높이: `180px`
- 패딩: `0.875rem`
- 배지 색상:
  - AI 기능: `#8b5cf6`
  - 인증: `#667eea`
  - 수상: `#f59318`

---

## 업데이트 정보 (dev-update.html)

### CSS 스타일

```css
.update-main-container {
    display: grid;
    grid-template-columns: 70% 30%;
    gap: 4rem;
    max-width: 1400px;
    margin: 0 auto;
    padding: 2rem 0;
}

.update-content {
    background: #FFFFFF;
}

.version-section {
    margin-bottom: 3rem;
    padding: 2rem;
    background: #FFFFFF;
    border-radius: 16px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.04);
    scroll-margin-top: 2rem;
}

.version-title {
    font-size: 1.75rem;
    font-weight: 700;
    color: #1A1A1A;
    margin: 0 0 0.5rem 0;
    letter-spacing: -0.02em;
}

.version-date {
    font-size: 0.875rem;
    color: #8B8B8B;
    margin-bottom: 2rem;
    font-weight: 400;
}

.section-subtitle {
    font-size: 1rem;
    font-weight: 600;
    color: #1A1A1A;
    margin: 2rem 0 1rem 0;
    display: flex;
    align-items: center;
    gap: 0.5rem;
}

.section-subtitle::before {
    content: '';
    width: 4px;
    height: 16px;
    background: linear-gradient(135deg, #667EEA 0%, #764BA2 100%);
    border-radius: 2px;
}

.change-list {
    list-style: none;
    padding: 0;
    margin: 0 0 2rem 0;
}

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

.change-description {
    color: #2D3748;
    margin: 0;
}

.feedback-link {
    color: #0067C5;
    text-decoration: none;
    font-size: 0.9rem;
}

.feedback-link:hover {
    text-decoration: underline;
}

.sticky-nav {
    position: sticky;
    top: 2rem;
    height: fit-content;
    max-height: calc(100vh - 4rem);
    overflow-y: hidden;
}

.nav-title {
    font-size: 1rem;
    font-weight: 600;
    color: var(--text-dark);
    margin-bottom: 0.5rem;
}

.nav-menu {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 0rem;
    margin-bottom: 0;
}

.nav-menu-item {
    margin: 0;
    padding: 0;
}

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

.nav-menu-default {
    display: flex;
    flex-direction: column;
    gap: 0rem;
}

.nav-menu-default.hide {
    display: none;
}

.nav-menu-more {
    display: none;
}

.nav-menu-more.show {
    display: block;
}

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

### HTML 구조

#### 탭 네비게이션
```html
<!-- Tab Navigation -->
<div class="update-tabs" style="display: flex; gap: 0.5rem; margin-bottom: 2rem; border-bottom: 2px solid #E5E7EB;">
    <button class="update-tab active" data-tab="updates" onclick="switchTab('updates')" style="background: none; border: none; padding: 1rem 1.5rem; font-size: 1rem; font-weight: 600; color: #1E3A8A; cursor: pointer; border-bottom: 3px solid #1E3A8A; margin-bottom: -2px; transition: all 0.3s;">
        주요 업데이트
    </button>
    <button class="update-tab" data-tab="versions" onclick="switchTab('versions')" style="background: none; border: none; padding: 1rem 1.5rem; font-size: 1rem; font-weight: 600; color: #6B7280; cursor: pointer; border-bottom: 3px solid transparent; margin-bottom: -2px; transition: all 0.3s;">
        업데이트 이력
    </button>
</div>
```

#### 업데이트 카드
```html
<a href="../news/article-classroom-renewal.html" style="text-decoration: none; display: block;">
    <article style="background: white; border-radius: 20px; overflow: hidden; box-shadow: 0 2px 8px rgba(0,0,0,0.08); transition: all 0.3s; cursor: pointer; display: flex; height: 200px;">
        <!-- Left Text Section -->
        <div style="flex: 1; padding: 2rem; display: flex; flex-direction: column; justify-content: center;">
            <div style="display: flex; gap: 0.5rem; flex-wrap: wrap; margin-bottom: 1rem;">
                <div style="display: inline-block; background: #1E3A8A15; color: #1E3A8A; padding: 0.25rem 0.75rem; border-radius: 12px; font-size: 0.75rem; font-weight: 600;">UI/UX</div>
                <div style="display: inline-block; background: #1E3A8A15; color: #1E3A8A; padding: 0.25rem 0.75rem; border-radius: 12px; font-size: 0.75rem; font-weight: 600;">디자인</div>
                <div style="display: inline-block; background: #1E3A8A15; color: #1E3A8A; padding: 0.25rem 0.75rem; border-radius: 12px; font-size: 0.75rem; font-weight: 600;">학습환경</div>
            </div>
            <h3 style="font-size: 1.5rem; font-weight: 700; margin: 0 0 0.75rem 0; color: #1a1a1a; line-height: 1.3;">강의실 UI/UX 업그레이드</h3>
            <p style="font-size: 0.9rem; color: #666; margin: 0; line-height: 1.6; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden;">AI 학습지원 · 다크모드 · 보드형 UI</p>
        </div>
        <!-- Right Image Section -->
        <div style="flex: 0 0 40%; display: flex; align-items: center; justify-content: center; position: relative; overflow: hidden; background: #f8f9fa;">
            <img src="../assets/articles/강의실UI_UX전면개편.png" alt="강의실 UI/UX 전면 개편" style="width: 100%; height: 100%; object-fit: cover;">
        </div>
    </article>
</a>
```

#### 버전 섹션
```html
<section id="version-2.5.0" class="version-section">
    <h2 class="version-title">Version 2.5.0</h2>
    <div class="version-date">2025년 11월 7일 릴리즈</div>
    
    <h3 class="section-subtitle">신규기능</h3>
    <ul class="change-list">
        <li class="change-item">
            <p class="change-description">GLightbox 기반 홍보영상 팝업 기능 정식 적용</p>
        </li>
    </ul>
    
    <h3 class="section-subtitle">개선사항</h3>
    <ul class="change-list">
        <li class="change-item">
            <p class="change-description">통합검색 UI 최종 시안 검수 및 적용</p>
        </li>
    </ul>
    
    <h3 class="section-subtitle">오류수정</h3>
    <ul class="change-list">
        <li class="change-item">
            <p class="change-description">검색 키워드 누락 문제 수정</p>
        </li>
    </ul>
</section>
```

#### 스티키 네비게이션
```html
<aside class="sticky-nav">
    <h2 class="nav-title">목차</h2>
    <nav class="nav-menu">
        <div class="nav-menu-default" id="nav-menu-default">
            <a href="#version-2.5.0" class="nav-menu-link active" onclick="scrollToVersion(event, 'version-2.5.0'); return false;">Version 2.5.0</a>
            <!-- More links -->
        </div>
        
        <div class="nav-menu-more" id="nav-menu-more">
            <!-- More version links -->
        </div>
        
        <div class="nav-more-btn" onclick="toggleNavMore()">
            더보기
        </div>
    </nav>
</aside>
```

### JavaScript 기능

#### 탭 전환
```javascript
function switchTab(tabName) {
    // Hide all tab contents
    document.querySelectorAll('.tab-content').forEach(content => {
        content.style.display = 'none';
    });
    
    // Remove active class from all tabs
    document.querySelectorAll('.update-tab').forEach(tab => {
        tab.classList.remove('active');
        tab.style.color = '#6B7280';
        tab.style.borderBottomColor = 'transparent';
    });
    
    // Show selected tab content
    document.getElementById(tabName + '-tab').style.display = 'block';
    
    // Add active class to selected tab
    const activeTab = document.querySelector(`[data-tab="${tabName}"]`);
    activeTab.classList.add('active');
    activeTab.style.color = '#1E3A8A';
    activeTab.style.borderBottomColor = '#1E3A8A';
}
```

#### 네비게이션 더보기 토글
```javascript
function toggleNavMore() {
    const defaultMenu = document.getElementById('nav-menu-default');
    const moreMenu = document.getElementById('nav-menu-more');
    const moreBtn = document.querySelector('.nav-more-btn');
    if (moreMenu && moreBtn && defaultMenu) {
        if (moreMenu.classList.contains('show')) {
            moreMenu.classList.remove('show');
            defaultMenu.classList.remove('hide');
            moreBtn.textContent = '더보기';
        } else {
            moreMenu.classList.add('show');
            defaultMenu.classList.add('hide');
            moreBtn.textContent = '접기';
        }
    }
}
```

#### 스크롤 이동
```javascript
function scrollToVersion(event, versionId) {
    event.preventDefault();
    const element = document.getElementById(versionId);
    if (element) {
        element.scrollIntoView({ behavior: 'smooth', block: 'start' });
        
        // Update active link
        document.querySelectorAll('.nav-menu-link').forEach(link => {
            link.classList.remove('active');
        });
        event.target.classList.add('active');
    }
}
```

### 주요 색상 팔레트

#### 업데이트 정보
- Primary Blue: `#1E3A8A`
- Light Blue Background: `#1E3A8A15` (15% opacity)
- Text Dark: `#1A1A1A`
- Text Gray: `#8B8B8B`
- Background Light: `#F8F9FA`
- Border: `#E5E7EB`

#### 뉴스룸
- CTA Background: `#EFF1FF`
- CTA Text: `#5850EE`
- Button: `#594CEE`
- Badge Colors:
  - AI 기능: `#8b5cf6`
  - 인증: `#667eea`
  - 수상: `#f59318`

### 레이아웃 구조

#### 뉴스룸
- 2열 그리드 레이아웃 (1:1 비율)
- 왼쪽: 메인 피처드 아티클 (큰 카드)
- 오른쪽: 2x2 그리드 (4개 작은 카드)

#### 업데이트 정보
- 탭 구조: 주요 업데이트 / 업데이트 이력
- 업데이트 탭: 단일 컬럼 카드 리스트
- 이력 탭: 70% 콘텐츠 + 30% 스티키 네비게이션

---

## 참고사항

- 뉴스룸은 주로 인라인 스타일을 사용
- 업데이트 정보는 `<style>` 태그 내부에 CSS 정의
- 반응형 디자인 고려 필요 (현재 고정 레이아웃)
- JavaScript는 기본적인 탭 전환 및 스크롤 기능 제공


