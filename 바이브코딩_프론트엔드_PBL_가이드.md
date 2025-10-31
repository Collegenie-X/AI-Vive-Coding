# 바이브 코딩 프론트엔드 PBL 실전 가이드
## 백엔드 없이 포트폴리오 만들기

---

## 프로그램 개요

### 핵심 컨셉
**"서버 없이도 동작하는 완전한 웹 애플리케이션 만들기"**

일반 고등학생들이 복잡한 백엔드 서버 없이도 LocalStorage와 JSON 파일만으로 완전히 동작하는 웹 애플리케이션을 만들 수 있습니다. 이는 빠른 프로토타이핑과 실험에 최적화된 방식입니다.

### 기술 스택
- **프론트엔드**: HTML, CSS, JavaScript (Vanilla 또는 React)
- **데이터 저장**: LocalStorage, JSON 파일
- **AI 도구**: Cursor AI, ChatGPT (더미 데이터 생성)
- **배포**: Vercel, Netlify, GitHub Pages

### 학습 목표
1. 프론트엔드만으로 완전한 CRUD 애플리케이션을 만들 수 있다
2. LocalStorage를 활용한 데이터 관리 방법을 이해한다
3. JSON 파일로 초기 데이터를 구성하고 활용할 수 있다
4. Cursor를 활용한 바이브 코딩 방식을 체득한다
5. 빠른 프로토타이핑과 실험 정신을 기른다

---

## Cursor 사용 방법 완벽 가이드

### 1단계: Cursor 설치 및 설정

#### 설치 과정
```bash
# 1. Cursor 다운로드
https://cursor.sh 접속 → Download 클릭

# 2. 설치 완료 후 실행

# 3. 프로젝트 폴더 열기
File → Open Folder → 프로젝트 폴더 선택
```

#### 초기 설정
```
1. Settings (⌘ + ,) 열기
2. Cursor Settings 탭 선택
3. AI Model: GPT-4 선택 (무료 플랜은 제한적)
4. Language: Korean 설정 (선택사항)
```

---

### 2단계: Cursor 핵심 기능 익히기

#### 기능 1: AI Chat (⌘ + L)
**용도**: AI와 대화하며 코드 작성, 문제 해결, 아이디어 논의

**사용 예시**
```
학생: "LocalStorage를 사용해서 할 일 목록을 저장하고 
불러오는 함수를 만들어줘. 
추가, 삭제, 수정, 조회 기능이 필요해."

Cursor AI: [코드 생성]

학생: "이 코드에 날짜별로 정렬하는 기능도 추가해줘"

Cursor AI: [코드 수정]
```

#### 기능 2: AI Edit (⌘ + K)
**용도**: 선택한 코드를 AI가 수정하도록 요청

**사용 방법**
```
1. 수정하고 싶은 코드 블록 선택
2. ⌘ + K 누르기
3. 수정 요청 입력
   예: "이 함수를 async/await 방식으로 바꿔줘"
4. Accept (⌘ + Enter) 또는 Reject (Esc)
```

#### 기능 3: AI Composer (⌘ + I)
**용도**: 여러 파일을 동시에 생성하거나 수정

**사용 예시**
```
"할 일 관리 앱을 만들어줘.
파일 구조:
- index.html: 메인 페이지
- style.css: 스타일
- app.js: 로직
- data.json: 초기 데이터

기능:
- 할 일 추가/삭제/완료 표시
- LocalStorage에 저장
- 날짜별 필터링"
```

#### 기능 4: Inline AI (Tab)
**용도**: 코드 작성 중 자동 완성

**사용 방법**
```javascript
// 주석을 작성하면 AI가 코드를 제안
// 사용자 데이터를 LocalStorage에 저장하는 함수
[Tab 키를 누르면 AI가 코드 생성]
```

---

### 3단계: Cursor로 프로젝트 시작하기

#### 프로젝트 생성 워크플로우

**Step 1: 프로젝트 폴더 생성**
```bash
# 터미널에서
mkdir my-project
cd my-project
code . # 또는 Cursor로 폴더 열기
```

**Step 2: Cursor AI Chat으로 프로젝트 구조 생성**
```
프롬프트:
"다음 구조로 프로젝트를 만들어줘:

프로젝트명: 학생 스터디 플래너
기능:
1. 과목별 학습 계획 등록
2. 학습 시간 기록
3. 진행률 시각화 (차트)
4. 목표 달성 체크

파일 구조:
- index.html
- css/style.css
- js/app.js
- js/storage.js (LocalStorage 관리)
- data/subjects.json (과목 초기 데이터)
- data/plans.json (학습 계획 템플릿)

기술:
- Vanilla JavaScript
- Chart.js (차트)
- LocalStorage (데이터 저장)
- 반응형 디자인

모든 파일을 생성하고 기본 코드를 작성해줘."
```

**Step 3: 생성된 파일 확인 및 수정**
```
1. 생성된 파일들 확인
2. 각 파일 열어서 코드 리뷰
3. 필요한 부분 수정 요청
```

---

## PBL 프로젝트 템플릿

### 템플릿 1: 할 일 관리 앱 (입문)

#### 프로젝트 개요
- **난이도**: ⭐ (입문)
- **예상 시간**: 4-6시간
- **학습 목표**: LocalStorage CRUD 기본 익히기

#### 폴더 구조
```
todo-app/
├── index.html              # 메인 페이지
├── css/
│   └── style.css          # 스타일시트
├── js/
│   ├── app.js             # 메인 로직
│   ├── storage.js         # LocalStorage 관리
│   └── ui.js              # UI 업데이트
└── data/
    └── initial-todos.json # 초기 데이터 (선택)
```

#### Cursor 프롬프트 예시

**1. 프로젝트 초기화**
```
"할 일 관리 앱을 만들어줘.

기능:
1. 할 일 추가 (제목, 설명, 마감일)
2. 할 일 완료 체크
3. 할 일 삭제
4. 할 일 수정
5. 필터링 (전체/진행중/완료)
6. LocalStorage에 자동 저장

UI 요구사항:
- 상단: 입력 폼 (제목, 설명, 마감일, 추가 버튼)
- 중간: 필터 버튼 (전체/진행중/완료)
- 하단: 할 일 목록 (카드 형태)
- 각 카드: 체크박스, 제목, 설명, 마감일, 수정/삭제 버튼

디자인:
- 모던하고 깔끔한 UI
- 파스텔 톤 색상
- 반응형 (모바일 지원)

파일 구조:
- index.html
- css/style.css
- js/app.js
- js/storage.js
- js/ui.js

모든 파일을 생성하고 완전히 동작하는 코드를 작성해줘."
```

**2. 기능 추가 요청**
```
"할 일에 우선순위(높음/보통/낮음) 기능을 추가하고,
우선순위별로 색상을 다르게 표시해줘.
- 높음: 빨간색
- 보통: 노란색
- 낮음: 초록색"
```

**3. 데이터 내보내기/가져오기 추가**
```
"할 일 데이터를 JSON 파일로 내보내고 가져오는 기능을 추가해줘.
- 내보내기: 버튼 클릭 시 todos.json 파일 다운로드
- 가져오기: 파일 선택 시 데이터 불러오기"
```

#### storage.js 핵심 코드 예시
```javascript
// LocalStorage 관리 클래스
class StorageManager {
  constructor(key) {
    this.key = key; // 'todos' 같은 키 이름
  }

  // 데이터 저장
  save(data) {
    try {
      localStorage.setItem(this.key, JSON.stringify(data));
      return true;
    } catch (error) {
      console.error('저장 실패:', error);
      return false;
    }
  }

  // 데이터 불러오기
  load() {
    try {
      const data = localStorage.getItem(this.key);
      return data ? JSON.parse(data) : [];
    } catch (error) {
      console.error('불러오기 실패:', error);
      return [];
    }
  }

  // 데이터 삭제
  clear() {
    localStorage.removeItem(this.key);
  }

  // 항목 추가
  add(item) {
    const data = this.load();
    item.id = Date.now(); // 고유 ID 생성
    item.createdAt = new Date().toISOString();
    data.push(item);
    this.save(data);
    return item;
  }

  // 항목 수정
  update(id, updates) {
    const data = this.load();
    const index = data.findIndex(item => item.id === id);
    if (index !== -1) {
      data[index] = { ...data[index], ...updates };
      this.save(data);
      return data[index];
    }
    return null;
  }

  // 항목 삭제
  delete(id) {
    const data = this.load();
    const filtered = data.filter(item => item.id !== id);
    this.save(filtered);
    return filtered;
  }

  // 항목 검색
  find(id) {
    const data = this.load();
    return data.find(item => item.id === id);
  }

  // 조건부 검색
  filter(predicate) {
    const data = this.load();
    return data.filter(predicate);
  }
}

// 사용 예시
const todoStorage = new StorageManager('todos');

// 할 일 추가
todoStorage.add({
  title: '수학 숙제',
  description: '1-3장 문제 풀기',
  dueDate: '2025-11-05',
  priority: 'high',
  completed: false
});

// 할 일 목록 불러오기
const todos = todoStorage.load();

// 완료되지 않은 할 일만 필터링
const pending = todoStorage.filter(todo => !todo.completed);
```

---

### 템플릿 2: 학습 플래너 (중급)

#### 프로젝트 개요
- **난이도**: ⭐⭐ (중급)
- **예상 시간**: 8-10시간
- **학습 목표**: 복잡한 데이터 구조, 차트 시각화

#### 폴더 구조
```
study-planner/
├── index.html
├── css/
│   ├── style.css
│   └── components.css
├── js/
│   ├── app.js
│   ├── storage.js
│   ├── chart.js          # 차트 관리
│   ├── calendar.js       # 캘린더 기능
│   └── utils.js          # 유틸리티 함수
├── data/
│   ├── subjects.json     # 과목 목록
│   ├── templates.json    # 학습 계획 템플릿
│   └── sample-data.json  # 샘플 데이터
└── assets/
    └── icons/            # 아이콘 이미지
```

#### subjects.json 예시
```json
{
  "subjects": [
    {
      "id": "math",
      "name": "수학",
      "color": "#FF6B6B",
      "icon": "📐",
      "weeklyGoal": 10
    },
    {
      "id": "english",
      "name": "영어",
      "color": "#4ECDC4",
      "icon": "📚",
      "weeklyGoal": 8
    },
    {
      "id": "science",
      "name": "과학",
      "color": "#95E1D3",
      "icon": "🔬",
      "weeklyGoal": 7
    }
  ]
}
```

#### templates.json 예시
```json
{
  "templates": [
    {
      "id": "daily-routine",
      "name": "일일 학습 루틴",
      "tasks": [
        {
          "time": "06:00",
          "subject": "english",
          "activity": "단어 암기",
          "duration": 30
        },
        {
          "time": "19:00",
          "subject": "math",
          "activity": "문제 풀이",
          "duration": 60
        }
      ]
    },
    {
      "id": "exam-prep",
      "name": "시험 대비 플랜",
      "tasks": [
        {
          "daysBeforeExam": 7,
          "subject": "all",
          "activity": "전체 복습",
          "duration": 120
        }
      ]
    }
  ]
}
```

#### Cursor 프롬프트 예시

**1. 프로젝트 생성**
```
"학습 플래너 앱을 만들어줘.

데이터 구조:
1. subjects.json: 과목 정보 (이름, 색상, 아이콘, 주간 목표 시간)
2. LocalStorage: 학습 기록 (날짜, 과목, 시간, 내용)

주요 기능:
1. 대시보드
   - 오늘의 학습 시간 요약
   - 과목별 진행률 (원형 차트)
   - 주간 학습 시간 추이 (선 그래프)

2. 학습 기록 추가
   - 과목 선택 (subjects.json에서 불러오기)
   - 학습 시간 입력 (시작/종료 또는 총 시간)
   - 학습 내용 메모
   - 날짜 선택

3. 캘린더 뷰
   - 월별 캘린더
   - 날짜별 학습 시간 표시 (색상 강도로)
   - 날짜 클릭 시 상세 내역

4. 통계
   - 과목별 누적 시간
   - 일일/주간/월간 평균
   - 목표 달성률

5. 템플릿 기능
   - templates.json에서 템플릿 불러오기
   - 템플릿 적용 (일괄 학습 계획 생성)
   - 커스텀 템플릿 저장

기술 스택:
- Vanilla JavaScript
- Chart.js (차트)
- LocalStorage (학습 기록)
- JSON 파일 (과목, 템플릿)

UI 디자인:
- 사이드바: 메뉴 (대시보드, 기록 추가, 캘린더, 통계)
- 메인 영역: 선택된 메뉴 내용
- 반응형 디자인
- 다크모드 지원

모든 파일을 생성하고 완전히 동작하는 코드를 작성해줘."
```

**2. 차트 추가**
```
"Chart.js를 사용해서 다음 차트를 추가해줘:

1. 도넛 차트: 과목별 학습 시간 비율
   - 각 과목의 색상 사용
   - 중앙에 총 학습 시간 표시

2. 선 그래프: 최근 7일 학습 시간 추이
   - X축: 날짜
   - Y축: 학습 시간 (시간 단위)
   - 과목별 라인 (색상 구분)

3. 바 차트: 과목별 목표 대비 달성률
   - 목표 시간 vs 실제 시간
   - 100% 이상이면 초록색, 미만이면 빨간색

차트는 반응형으로 만들어줘."
```

#### chart.js 핵심 코드 예시
```javascript
// 차트 관리 클래스
class ChartManager {
  constructor(storageManager) {
    this.storage = storageManager;
  }

  // 과목별 학습 시간 도넛 차트
  createSubjectChart(canvasId, subjects) {
    const ctx = document.getElementById(canvasId).getContext('2d');
    const records = this.storage.load();
    
    // 과목별 시간 집계
    const subjectTimes = {};
    subjects.forEach(subject => {
      subjectTimes[subject.id] = 0;
    });
    
    records.forEach(record => {
      if (subjectTimes[record.subjectId] !== undefined) {
        subjectTimes[record.subjectId] += record.duration;
      }
    });
    
    // 차트 데이터 준비
    const data = {
      labels: subjects.map(s => s.name),
      datasets: [{
        data: subjects.map(s => subjectTimes[s.id]),
        backgroundColor: subjects.map(s => s.color),
        borderWidth: 2
      }]
    };
    
    // 차트 생성
    return new Chart(ctx, {
      type: 'doughnut',
      data: data,
      options: {
        responsive: true,
        plugins: {
          legend: {
            position: 'bottom'
          },
          title: {
            display: true,
            text: '과목별 학습 시간'
          }
        }
      }
    });
  }

  // 주간 학습 시간 추이 선 그래프
  createWeeklyTrendChart(canvasId, subjects) {
    const ctx = document.getElementById(canvasId).getContext('2d');
    const records = this.storage.load();
    
    // 최근 7일 날짜 생성
    const dates = [];
    for (let i = 6; i >= 0; i--) {
      const date = new Date();
      date.setDate(date.getDate() - i);
      dates.push(date.toISOString().split('T')[0]);
    }
    
    // 날짜별, 과목별 시간 집계
    const datasets = subjects.map(subject => {
      const data = dates.map(date => {
        const dayRecords = records.filter(r => 
          r.date === date && r.subjectId === subject.id
        );
        return dayRecords.reduce((sum, r) => sum + r.duration, 0) / 60; // 시간 단위
      });
      
      return {
        label: subject.name,
        data: data,
        borderColor: subject.color,
        backgroundColor: subject.color + '33', // 투명도 추가
        tension: 0.4
      };
    });
    
    return new Chart(ctx, {
      type: 'line',
      data: {
        labels: dates.map(d => {
          const date = new Date(d);
          return `${date.getMonth() + 1}/${date.getDate()}`;
        }),
        datasets: datasets
      },
      options: {
        responsive: true,
        plugins: {
          title: {
            display: true,
            text: '주간 학습 시간 추이'
          }
        },
        scales: {
          y: {
            beginAtZero: true,
            title: {
              display: true,
              text: '시간'
            }
          }
        }
      }
    });
  }
}

// 사용 예시
const chartManager = new ChartManager(studyStorage);

// subjects.json 불러오기
fetch('data/subjects.json')
  .then(response => response.json())
  .then(data => {
    chartManager.createSubjectChart('subjectChart', data.subjects);
    chartManager.createWeeklyTrendChart('trendChart', data.subjects);
  });
```

---

### 템플릿 3: 포트폴리오 웹사이트 (중급)

#### 프로젝트 개요
- **난이도**: ⭐⭐ (중급)
- **예상 시간**: 6-8시간
- **학습 목표**: JSON 데이터 기반 동적 콘텐츠 생성

#### 폴더 구조
```
portfolio/
├── index.html
├── css/
│   ├── style.css
│   ├── animations.css
│   └── responsive.css
├── js/
│   ├── app.js
│   ├── portfolio.js      # 포트폴리오 데이터 관리
│   ├── contact.js        # 연락 폼 (LocalStorage 저장)
│   └── theme.js          # 다크모드 토글
├── data/
│   ├── profile.json      # 프로필 정보
│   ├── projects.json     # 프로젝트 목록
│   ├── skills.json       # 스킬 목록
│   └── experiences.json  # 경험/활동
└── assets/
    ├── images/
    └── icons/
```

#### profile.json 예시
```json
{
  "name": "홍길동",
  "title": "고등학생 개발자",
  "bio": "문제를 해결하고 가치를 만드는 것을 좋아하는 고등학생입니다.",
  "avatar": "assets/images/profile.jpg",
  "contact": {
    "email": "hong@example.com",
    "github": "https://github.com/hong",
    "blog": "https://blog.hong.com"
  },
  "social": [
    {
      "platform": "GitHub",
      "url": "https://github.com/hong",
      "icon": "fab fa-github"
    },
    {
      "platform": "LinkedIn",
      "url": "https://linkedin.com/in/hong",
      "icon": "fab fa-linkedin"
    }
  ]
}
```

#### projects.json 예시
```json
{
  "projects": [
    {
      "id": "study-planner",
      "title": "학습 플래너",
      "description": "학생들을 위한 스마트 학습 관리 도구",
      "thumbnail": "assets/images/study-planner.png",
      "tags": ["JavaScript", "Chart.js", "LocalStorage"],
      "featured": true,
      "links": {
        "demo": "https://study-planner.vercel.app",
        "github": "https://github.com/hong/study-planner"
      },
      "details": {
        "problem": "학습 시간을 효과적으로 관리하기 어려움",
        "solution": "시각화와 목표 설정으로 학습 동기 부여",
        "features": [
          "과목별 학습 시간 기록",
          "진행률 시각화",
          "목표 설정 및 달성률 추적"
        ],
        "techStack": [
          "Vanilla JavaScript",
          "Chart.js",
          "LocalStorage API"
        ],
        "screenshots": [
          "assets/images/planner-1.png",
          "assets/images/planner-2.png"
        ]
      }
    }
  ]
}
```

#### skills.json 예시
```json
{
  "categories": [
    {
      "name": "프론트엔드",
      "skills": [
        {
          "name": "HTML/CSS",
          "level": 85,
          "icon": "fab fa-html5"
        },
        {
          "name": "JavaScript",
          "level": 75,
          "icon": "fab fa-js"
        },
        {
          "name": "React",
          "level": 60,
          "icon": "fab fa-react"
        }
      ]
    },
    {
      "name": "도구",
      "skills": [
        {
          "name": "Git",
          "level": 70,
          "icon": "fab fa-git-alt"
        },
        {
          "name": "Cursor AI",
          "level": 80,
          "icon": "fas fa-robot"
        }
      ]
    }
  ]
}
```

#### Cursor 프롬프트 예시

**1. 프로젝트 생성**
```
"포트폴리오 웹사이트를 만들어줘.

데이터 소스:
- profile.json: 프로필 정보
- projects.json: 프로젝트 목록
- skills.json: 스킬 목록
- experiences.json: 경험/활동

페이지 구성:
1. 홈 섹션
   - 프로필 사진, 이름, 타이틀
   - 간단한 자기소개
   - 소셜 링크

2. About 섹션
   - 상세 자기소개
   - 스킬 바 차트 (skills.json 기반)
   - 관심사

3. Projects 섹션
   - 프로젝트 카드 그리드 (projects.json 기반)
   - 필터링 (태그별)
   - 카드 클릭 시 모달로 상세 정보
   - 라이브 데모, GitHub 링크

4. Experience 섹션
   - 타임라인 형식
   - experiences.json 기반

5. Contact 섹션
   - 연락 폼 (이름, 이메일, 메시지)
   - 제출 시 LocalStorage에 저장
   - 제출 완료 알림

기능:
- 부드러운 스크롤 애니메이션
- 다크모드 토글 (LocalStorage에 설정 저장)
- 반응형 디자인
- 로딩 시 JSON 파일 자동 로드

기술:
- Vanilla JavaScript
- CSS Grid/Flexbox
- Intersection Observer (스크롤 애니메이션)
- LocalStorage (다크모드, 연락 메시지)

디자인:
- 모던하고 미니멀
- 부드러운 애니메이션
- 프로페셔널한 느낌

모든 파일을 생성하고 완전히 동작하는 코드를 작성해줘."
```

**2. 프로젝트 필터링 추가**
```
"Projects 섹션에 다음 기능을 추가해줘:

1. 태그 필터
   - 모든 프로젝트의 태그 추출
   - 태그 버튼 생성 (All, JavaScript, React 등)
   - 버튼 클릭 시 해당 태그 프로젝트만 표시
   - 애니메이션 효과

2. 검색 기능
   - 검색창 추가
   - 제목, 설명, 태그에서 검색
   - 실시간 필터링

3. 정렬 기능
   - 최신순, 오래된순, 이름순
   - 드롭다운 선택"
```

#### portfolio.js 핵심 코드 예시
```javascript
// 포트폴리오 데이터 관리 클래스
class PortfolioManager {
  constructor() {
    this.data = {
      profile: null,
      projects: null,
      skills: null,
      experiences: null
    };
  }

  // 모든 JSON 파일 로드
  async loadAll() {
    try {
      const [profile, projects, skills, experiences] = await Promise.all([
        fetch('data/profile.json').then(r => r.json()),
        fetch('data/projects.json').then(r => r.json()),
        fetch('data/skills.json').then(r => r.json()),
        fetch('data/experiences.json').then(r => r.json())
      ]);

      this.data = { profile, projects, skills, experiences };
      return this.data;
    } catch (error) {
      console.error('데이터 로드 실패:', error);
      return null;
    }
  }

  // 프로필 렌더링
  renderProfile() {
    const { name, title, bio, avatar, social } = this.data.profile;
    
    const profileHTML = `
      <div class="profile-container">
        <img src="${avatar}" alt="${name}" class="profile-avatar">
        <h1 class="profile-name">${name}</h1>
        <p class="profile-title">${title}</p>
        <p class="profile-bio">${bio}</p>
        <div class="social-links">
          ${social.map(s => `
            <a href="${s.url}" target="_blank" rel="noopener">
              <i class="${s.icon}"></i>
            </a>
          `).join('')}
        </div>
      </div>
    `;
    
    document.getElementById('profile-section').innerHTML = profileHTML;
  }

  // 프로젝트 렌더링
  renderProjects(filter = null) {
    let projects = this.data.projects.projects;
    
    // 필터 적용
    if (filter && filter !== 'all') {
      projects = projects.filter(p => p.tags.includes(filter));
    }
    
    const projectsHTML = projects.map(project => `
      <div class="project-card" data-id="${project.id}">
        <img src="${project.thumbnail}" alt="${project.title}">
        <div class="project-info">
          <h3>${project.title}</h3>
          <p>${project.description}</p>
          <div class="project-tags">
            ${project.tags.map(tag => `
              <span class="tag">${tag}</span>
            `).join('')}
          </div>
          <div class="project-links">
            ${project.links.demo ? `
              <a href="${project.links.demo}" target="_blank">
                <i class="fas fa-external-link-alt"></i> 데모
              </a>
            ` : ''}
            ${project.links.github ? `
              <a href="${project.links.github}" target="_blank">
                <i class="fab fa-github"></i> GitHub
              </a>
            ` : ''}
          </div>
        </div>
      </div>
    `).join('');
    
    document.getElementById('projects-grid').innerHTML = projectsHTML;
    
    // 카드 클릭 이벤트
    document.querySelectorAll('.project-card').forEach(card => {
      card.addEventListener('click', () => {
        const projectId = card.dataset.id;
        this.showProjectModal(projectId);
      });
    });
  }

  // 프로젝트 상세 모달
  showProjectModal(projectId) {
    const project = this.data.projects.projects.find(p => p.id === projectId);
    if (!project) return;
    
    const modalHTML = `
      <div class="modal-overlay" id="project-modal">
        <div class="modal-content">
          <button class="modal-close">&times;</button>
          <h2>${project.title}</h2>
          <p class="modal-description">${project.description}</p>
          
          <div class="modal-section">
            <h3>문제</h3>
            <p>${project.details.problem}</p>
          </div>
          
          <div class="modal-section">
            <h3>해결책</h3>
            <p>${project.details.solution}</p>
          </div>
          
          <div class="modal-section">
            <h3>주요 기능</h3>
            <ul>
              ${project.details.features.map(f => `<li>${f}</li>`).join('')}
            </ul>
          </div>
          
          <div class="modal-section">
            <h3>기술 스택</h3>
            <div class="tech-stack">
              ${project.details.techStack.map(t => `
                <span class="tech-badge">${t}</span>
              `).join('')}
            </div>
          </div>
          
          <div class="modal-section">
            <h3>스크린샷</h3>
            <div class="screenshots">
              ${project.details.screenshots.map(s => `
                <img src="${s}" alt="스크린샷">
              `).join('')}
            </div>
          </div>
        </div>
      </div>
    `;
    
    document.body.insertAdjacentHTML('beforeend', modalHTML);
    
    // 모달 닫기
    document.querySelector('.modal-close').addEventListener('click', () => {
      document.getElementById('project-modal').remove();
    });
    
    document.querySelector('.modal-overlay').addEventListener('click', (e) => {
      if (e.target.classList.contains('modal-overlay')) {
        document.getElementById('project-modal').remove();
      }
    });
  }

  // 스킬 렌더링
  renderSkills() {
    const skillsHTML = this.data.skills.categories.map(category => `
      <div class="skill-category">
        <h3>${category.name}</h3>
        <div class="skills-list">
          ${category.skills.map(skill => `
            <div class="skill-item">
              <div class="skill-header">
                <i class="${skill.icon}"></i>
                <span>${skill.name}</span>
                <span class="skill-level">${skill.level}%</span>
              </div>
              <div class="skill-bar">
                <div class="skill-progress" style="width: ${skill.level}%"></div>
              </div>
            </div>
          `).join('')}
        </div>
      </div>
    `).join('');
    
    document.getElementById('skills-section').innerHTML = skillsHTML;
  }

  // 태그 필터 버튼 생성
  createTagFilters() {
    const allTags = new Set();
    this.data.projects.projects.forEach(project => {
      project.tags.forEach(tag => allTags.add(tag));
    });
    
    const filtersHTML = `
      <button class="filter-btn active" data-filter="all">All</button>
      ${[...allTags].map(tag => `
        <button class="filter-btn" data-filter="${tag}">${tag}</button>
      `).join('')}
    `;
    
    document.getElementById('project-filters').innerHTML = filtersHTML;
    
    // 필터 버튼 이벤트
    document.querySelectorAll('.filter-btn').forEach(btn => {
      btn.addEventListener('click', () => {
        document.querySelectorAll('.filter-btn').forEach(b => 
          b.classList.remove('active')
        );
        btn.classList.add('active');
        
        const filter = btn.dataset.filter;
        this.renderProjects(filter === 'all' ? null : filter);
      });
    });
  }

  // 초기화
  async init() {
    await this.loadAll();
    this.renderProfile();
    this.createTagFilters();
    this.renderProjects();
    this.renderSkills();
  }
}

// 사용
const portfolio = new PortfolioManager();
portfolio.init();
```

---

### 템플릿 4: 가상 ChatGPT 챗봇 (고급)

#### 프로젝트 개요
- **난이도**: ⭐⭐⭐ (고급)
- **예상 시간**: 10-12시간
- **학습 목표**: 더미 데이터로 AI 챗봇 시뮬레이션

#### 핵심 아이디어
실제 ChatGPT API 없이 미리 정의된 응답 패턴으로 챗봇 시뮬레이션

#### 폴더 구조
```
chatbot-simulator/
├── index.html
├── css/
│   └── chat.css
├── js/
│   ├── app.js
│   ├── chatbot.js        # 챗봇 로직
│   ├── storage.js        # 대화 저장
│   └── patterns.js       # 응답 패턴 매칭
├── data/
│   ├── responses.json    # 미리 정의된 응답
│   ├── intents.json      # 의도 분류
│   └── contexts.json     # 문맥 정보
└── assets/
    └── avatars/
```

#### responses.json 예시
```json
{
  "greetings": [
    "안녕하세요! 무엇을 도와드릴까요?",
    "반갑습니다! 궁금한 것이 있으신가요?",
    "안녕하세요! 오늘 하루 어떠세요?"
  ],
  "coding_help": {
    "javascript": [
      "JavaScript는 웹 개발의 핵심 언어입니다. 어떤 부분이 궁금하신가요?",
      "JavaScript로 무엇을 만들고 싶으신가요? 도와드리겠습니다!"
    ],
    "html": [
      "HTML은 웹 페이지의 구조를 만드는 언어입니다. 구체적으로 어떤 태그가 궁금하신가요?"
    ]
  },
  "study_tips": [
    "효과적인 학습을 위해서는:\n1. 목표를 명확히 설정하세요\n2. 규칙적인 학습 시간을 가지세요\n3. 배운 내용을 정리하세요",
    "포모도로 기법을 추천드립니다. 25분 집중 + 5분 휴식을 반복하세요!"
  ],
  "fallback": [
    "죄송하지만 잘 이해하지 못했습니다. 다시 설명해 주시겠어요?",
    "흥미로운 질문이네요! 조금 더 구체적으로 말씀해 주시겠어요?",
    "그 부분은 제가 아직 잘 모르겠습니다. 다른 질문이 있으신가요?"
  ]
}
```

#### intents.json 예시
```json
{
  "intents": [
    {
      "tag": "greeting",
      "patterns": [
        "안녕",
        "안녕하세요",
        "hi",
        "hello",
        "반가워"
      ],
      "responses": "greetings"
    },
    {
      "tag": "coding_javascript",
      "patterns": [
        "자바스크립트",
        "javascript",
        "js",
        "코딩",
        "프로그래밍"
      ],
      "responses": "coding_help.javascript",
      "context": "coding"
    },
    {
      "tag": "study_help",
      "patterns": [
        "공부",
        "학습",
        "공부법",
        "어떻게 공부",
        "효과적인 학습"
      ],
      "responses": "study_tips"
    }
  ]
}
```

#### Cursor 프롬프트 예시

```
"가상 ChatGPT 챗봇 시뮬레이터를 만들어줘.

동작 방식:
1. 사용자가 메시지 입력
2. 입력된 메시지를 intents.json의 패턴과 매칭
3. 매칭된 의도(intent)에 해당하는 응답을 responses.json에서 가져오기
4. 랜덤하게 하나 선택해서 응답
5. 매칭되지 않으면 fallback 응답

고급 기능:
1. 키워드 매칭
   - 입력 메시지에서 키워드 추출
   - 여러 키워드가 있으면 가장 관련성 높은 의도 선택

2. 문맥 유지
   - 이전 대화 기억 (최근 5개)
   - 문맥에 따라 응답 조정
   - 예: "그것에 대해 더 알려줘" → 이전 주제 계속

3. 타이핑 효과
   - 응답이 한 글자씩 나타나는 애니메이션
   - 실제 ChatGPT처럼 자연스럽게

4. 대화 저장
   - LocalStorage에 대화 내역 저장
   - 새로고침해도 대화 유지
   - 대화 삭제 기능

5. 다양한 응답 타입
   - 텍스트
   - 코드 블록 (syntax highlighting)
   - 리스트
   - 링크

UI:
- ChatGPT 스타일 인터페이스
- 사용자 메시지: 오른쪽, 파란색
- 봇 메시지: 왼쪽, 회색
- 입력창 하단 고정
- 자동 스크롤
- 다크모드

파일 구조:
- index.html
- css/chat.css
- js/app.js
- js/chatbot.js
- js/storage.js
- js/patterns.js
- data/responses.json
- data/intents.json
- data/contexts.json

모든 파일을 생성하고 완전히 동작하는 코드를 작성해줘."
```

#### chatbot.js 핵심 코드 예시
```javascript
// 챗봇 엔진 클래스
class ChatbotEngine {
  constructor() {
    this.intents = null;
    this.responses = null;
    this.context = [];
    this.conversationHistory = [];
  }

  // 데이터 로드
  async init() {
    const [intents, responses] = await Promise.all([
      fetch('data/intents.json').then(r => r.json()),
      fetch('data/responses.json').then(r => r.json())
    ]);
    
    this.intents = intents.intents;
    this.responses = responses;
  }

  // 메시지 처리
  async processMessage(userMessage) {
    // 대화 기록에 추가
    this.conversationHistory.push({
      role: 'user',
      content: userMessage,
      timestamp: new Date().toISOString()
    });
    
    // 의도 파악
    const intent = this.detectIntent(userMessage);
    
    // 응답 생성
    const response = this.generateResponse(intent, userMessage);
    
    // 대화 기록에 추가
    this.conversationHistory.push({
      role: 'assistant',
      content: response,
      timestamp: new Date().toISOString()
    });
    
    return response;
  }

  // 의도 감지
  detectIntent(message) {
    const messageLower = message.toLowerCase();
    let bestMatch = null;
    let bestScore = 0;
    
    // 각 의도의 패턴과 매칭
    this.intents.forEach(intent => {
      let score = 0;
      
      intent.patterns.forEach(pattern => {
        if (messageLower.includes(pattern.toLowerCase())) {
          score += 1;
        }
      });
      
      if (score > bestScore) {
        bestScore = score;
        bestMatch = intent;
      }
    });
    
    return bestMatch;
  }

  // 응답 생성
  generateResponse(intent, userMessage) {
    if (!intent) {
      // 매칭 실패 시 fallback
      return this.getRandomResponse(this.responses.fallback);
    }
    
    // 응답 경로 파싱 (예: "coding_help.javascript")
    const responsePath = intent.responses.split('.');
    let responseArray = this.responses;
    
    responsePath.forEach(key => {
      responseArray = responseArray[key];
    });
    
    // 배열이 아니면 배열로 변환
    if (!Array.isArray(responseArray)) {
      responseArray = [responseArray];
    }
    
    // 랜덤 응답 선택
    let response = this.getRandomResponse(responseArray);
    
    // 개인화 (사용자 이름 포함 등)
    response = this.personalizeResponse(response, userMessage);
    
    return response;
  }

  // 랜덤 응답 선택
  getRandomResponse(responses) {
    return responses[Math.floor(Math.random() * responses.length)];
  }

  // 응답 개인화
  personalizeResponse(response, userMessage) {
    // 사용자 메시지에서 키워드 추출하여 응답에 반영
    // 예: "JavaScript 배우고 싶어" → "JavaScript 학습을 도와드리겠습니다!"
    
    return response;
  }

  // 대화 기록 가져오기
  getHistory() {
    return this.conversationHistory;
  }

  // 대화 기록 초기화
  clearHistory() {
    this.conversationHistory = [];
  }
}

// 챗봇 UI 클래스
class ChatbotUI {
  constructor(engine, storageManager) {
    this.engine = engine;
    this.storage = storageManager;
    this.chatContainer = document.getElementById('chat-messages');
    this.inputField = document.getElementById('user-input');
    this.sendButton = document.getElementById('send-button');
    
    this.setupEventListeners();
    this.loadHistory();
  }

  setupEventListeners() {
    // 전송 버튼 클릭
    this.sendButton.addEventListener('click', () => this.sendMessage());
    
    // Enter 키로 전송
    this.inputField.addEventListener('keypress', (e) => {
      if (e.key === 'Enter' && !e.shiftKey) {
        e.preventDefault();
        this.sendMessage();
      }
    });
  }

  async sendMessage() {
    const message = this.inputField.value.trim();
    if (!message) return;
    
    // 사용자 메시지 표시
    this.addMessage(message, 'user');
    this.inputField.value = '';
    
    // 타이핑 인디케이터 표시
    this.showTypingIndicator();
    
    // 봇 응답 생성 (약간의 지연 추가로 자연스럽게)
    setTimeout(async () => {
      const response = await this.engine.processMessage(message);
      this.hideTypingIndicator();
      
      // 봇 응답 표시 (타이핑 효과)
      await this.addMessageWithTyping(response, 'assistant');
      
      // 대화 저장
      this.saveHistory();
    }, 500 + Math.random() * 1000); // 0.5~1.5초 랜덤 지연
  }

  addMessage(content, role) {
    const messageDiv = document.createElement('div');
    messageDiv.className = `message ${role}-message`;
    
    const avatar = document.createElement('div');
    avatar.className = 'message-avatar';
    avatar.textContent = role === 'user' ? '👤' : '🤖';
    
    const contentDiv = document.createElement('div');
    contentDiv.className = 'message-content';
    
    // 코드 블록 처리
    if (content.includes('```')) {
      contentDiv.innerHTML = this.formatCodeBlocks(content);
    } else {
      contentDiv.textContent = content;
    }
    
    messageDiv.appendChild(avatar);
    messageDiv.appendChild(contentDiv);
    this.chatContainer.appendChild(messageDiv);
    
    // 스크롤 하단으로
    this.chatContainer.scrollTop = this.chatContainer.scrollHeight;
  }

  async addMessageWithTyping(content, role) {
    const messageDiv = document.createElement('div');
    messageDiv.className = `message ${role}-message`;
    
    const avatar = document.createElement('div');
    avatar.className = 'message-avatar';
    avatar.textContent = role === 'user' ? '👤' : '🤖';
    
    const contentDiv = document.createElement('div');
    contentDiv.className = 'message-content';
    
    messageDiv.appendChild(avatar);
    messageDiv.appendChild(contentDiv);
    this.chatContainer.appendChild(messageDiv);
    
    // 타이핑 효과
    let index = 0;
    const typingSpeed = 30; // ms per character
    
    return new Promise((resolve) => {
      const typeChar = () => {
        if (index < content.length) {
          contentDiv.textContent += content[index];
          index++;
          this.chatContainer.scrollTop = this.chatContainer.scrollHeight;
          setTimeout(typeChar, typingSpeed);
        } else {
          resolve();
        }
      };
      typeChar();
    });
  }

  showTypingIndicator() {
    const indicator = document.createElement('div');
    indicator.className = 'typing-indicator';
    indicator.id = 'typing-indicator';
    indicator.innerHTML = `
      <div class="message-avatar">🤖</div>
      <div class="typing-dots">
        <span></span>
        <span></span>
        <span></span>
      </div>
    `;
    this.chatContainer.appendChild(indicator);
    this.chatContainer.scrollTop = this.chatContainer.scrollHeight;
  }

  hideTypingIndicator() {
    const indicator = document.getElementById('typing-indicator');
    if (indicator) {
      indicator.remove();
    }
  }

  formatCodeBlocks(content) {
    // ```code``` 형식을 <pre><code>로 변환
    return content.replace(/```(\w+)?\n([\s\S]+?)```/g, (match, lang, code) => {
      return `<pre><code class="language-${lang || 'plaintext'}">${this.escapeHtml(code.trim())}</code></pre>`;
    });
  }

  escapeHtml(text) {
    const div = document.createElement('div');
    div.textContent = text;
    return div.innerHTML;
  }

  saveHistory() {
    const history = this.engine.getHistory();
    this.storage.save(history);
  }

  loadHistory() {
    const history = this.storage.load();
    if (history && history.length > 0) {
      history.forEach(msg => {
        this.addMessage(msg.content, msg.role);
      });
      this.engine.conversationHistory = history;
    } else {
      // 환영 메시지
      this.addMessage('안녕하세요! 무엇을 도와드릴까요?', 'assistant');
    }
  }

  clearChat() {
    this.chatContainer.innerHTML = '';
    this.engine.clearHistory();
    this.storage.clear();
    this.addMessage('대화가 초기화되었습니다. 새로운 대화를 시작하세요!', 'assistant');
  }
}

// 초기화
(async () => {
  const engine = new ChatbotEngine();
  await engine.init();
  
  const storage = new StorageManager('chatbot-history');
  const ui = new ChatbotUI(engine, storage);
  
  // 대화 초기화 버튼
  document.getElementById('clear-chat').addEventListener('click', () => {
    if (confirm('대화를 초기화하시겠습니까?')) {
      ui.clearChat();
    }
  });
})();
```

---

## PBL 프로젝트 진행 가이드

### 1주차: 기획 및 설계

#### Day 1-2: 아이디어 및 요구사항 정의
**활동**
1. 브레인스토밍: 만들고 싶은 것 나열
2. 문제 정의: 누구의 어떤 문제를 해결하는가?
3. 사용자 스토리 작성
   ```
   "~로서, ~를 하고 싶다, 왜냐하면 ~"
   
   예: "고등학생으로서, 학습 시간을 기록하고 싶다, 
   왜냐하면 어느 과목에 시간을 많이 쓰는지 알고 싶기 때문이다"
   ```

**Cursor 활용**
```
"다음 아이디어를 구체화해줘:

아이디어: [학생이 작성]
타겟 사용자: [학생이 작성]
해결하려는 문제: [학생이 작성]

다음을 제안해줘:
1. 핵심 기능 5가지
2. 필요한 데이터 구조
3. 화면 구성
4. 기술 스택
5. 예상 어려움과 해결 방법"
```

#### Day 3-4: 데이터 구조 및 화면 설계
**활동**
1. JSON 데이터 구조 설계
2. 와이어프레임 스케치
3. 사용자 플로우 정의

**Cursor 활용**
```
"다음 기능을 위한 JSON 데이터 구조를 설계해줘:

기능: [기능 설명]
필요한 정보: [정보 나열]

다음을 포함해줘:
1. 데이터 스키마 (JSON 형식)
2. 샘플 데이터 3개
3. LocalStorage 저장/불러오기 함수
4. CRUD 함수 (추가, 조회, 수정, 삭제)"
```

#### Day 5: 프로젝트 구조 생성
**활동**
1. 폴더 구조 생성
2. 기본 파일 생성 (HTML, CSS, JS)
3. JSON 파일 작성

**Cursor 활용**
```
"다음 구조로 프로젝트를 생성해줘:

[폴더 구조 붙여넣기]

각 파일에 기본 코드와 주석을 작성해줘.
HTML은 시맨틱 태그를 사용하고,
CSS는 변수와 플렉스박스를 활용하고,
JavaScript는 클래스 기반으로 작성해줘."
```

---

### 2주차: 개발

#### Day 6-8: 핵심 기능 구현
**활동**
1. LocalStorage 관리 모듈 구현
2. 데이터 CRUD 기능 구현
3. UI 렌더링 함수 작성

**Cursor 활용 패턴**
```
# 기능별로 단계적 구현

Step 1: 데이터 관리
"LocalStorage를 사용해서 [데이터 타입] 데이터를 
관리하는 클래스를 만들어줘.
메서드: save, load, add, update, delete, find"

Step 2: UI 렌더링
"[데이터]를 받아서 HTML 카드로 렌더링하는 함수를 만들어줘.
각 카드는 [요소들] 포함"

Step 3: 이벤트 처리
"[버튼]을 클릭하면 [동작]하도록 이벤트 리스너를 추가해줘"

Step 4: 통합
"위의 모든 기능을 통합해서 동작하도록 만들어줘"
```

#### Day 9-10: 추가 기능 및 UI 개선
**활동**
1. 검색/필터링 기능
2. 정렬 기능
3. 애니메이션 추가
4. 반응형 디자인

**Cursor 활용**
```
"다음 기능을 추가해줘:

1. 실시간 검색
   - 입력창에 타이핑하면 즉시 필터링
   - 제목, 설명, 태그에서 검색

2. 정렬 기능
   - 최신순, 오래된순, 이름순
   - 드롭다운으로 선택

3. 부드러운 애니메이션
   - 항목 추가 시 페이드인
   - 항목 삭제 시 슬라이드아웃
   - CSS transition 사용"
```

---

### 3주차: 완성 및 배포

#### Day 11-12: 테스트 및 버그 수정
**활동**
1. 전체 기능 테스트
2. 엣지 케이스 처리
3. 에러 처리 추가

**테스트 체크리스트**
```
기능 테스트:
□ 모든 CRUD 동작 확인
□ 데이터 저장/불러오기 확인
□ 필터/검색 동작 확인
□ 정렬 동작 확인

UI/UX 테스트:
□ 모바일 반응형 확인
□ 버튼 호버 효과 확인
□ 로딩 상태 표시 확인
□ 에러 메시지 표시 확인

데이터 테스트:
□ 빈 데이터 처리
□ 잘못된 입력 처리
□ LocalStorage 용량 초과 처리
□ 데이터 손실 방지 확인
```

**Cursor 활용**
```
"다음 에러를 처리하는 코드를 추가해줘:

1. LocalStorage 용량 초과
   - try-catch로 감싸기
   - 에러 발생 시 사용자에게 알림
   - 오래된 데이터 삭제 제안

2. 잘못된 입력
   - 유효성 검사 함수
   - 입력 전 검증
   - 에러 메시지 표시

3. 데이터 로드 실패
   - 기본값으로 초기화
   - 사용자에게 알림"
```

#### Day 13-14: 최적화 및 문서화
**활동**
1. 코드 리팩토링
2. 주석 추가 (한글)
3. README 작성

**Cursor 활용**
```
"이 코드를 리팩토링해줘:

[코드 붙여넣기]

다음을 개선해줘:
1. 중복 코드 제거
2. 함수 분리 (한 함수당 하나의 역할)
3. 변수명 명확하게
4. 한글 주석 추가
5. 에러 처리 강화"
```

**README 템플릿**
```markdown
# 프로젝트명

## 프로젝트 소개
한 문장으로 설명

## 주요 기능
- 기능 1
- 기능 2
- 기능 3

## 기술 스택
- HTML/CSS/JavaScript
- LocalStorage
- Chart.js (해당 시)

## 설치 및 실행
1. 저장소 클론
2. index.html 열기

## 사용 방법
1. 단계 1
2. 단계 2

## 데이터 구조
```json
{
  "example": "data"
}
```

## 스크린샷
![스크린샷](assets/screenshot.png)

## 배운 점
- 배운 점 1
- 배운 점 2

## 개선 계획
- 추가하고 싶은 기능
```

#### Day 15: 배포 및 발표
**활동**
1. GitHub Pages 또는 Vercel 배포
2. 발표 자료 준비
3. 프로젝트 발표

**배포 방법**

**GitHub Pages**
```bash
# 1. GitHub 저장소 생성
# 2. 코드 푸시
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin [저장소 URL]
git push -u origin main

# 3. Settings → Pages → Source: main branch → Save
# 4. 배포 URL 확인: https://[username].github.io/[repo-name]
```

**Vercel**
```bash
# 1. Vercel 계정 생성
# 2. 프로젝트 폴더에서
npm i -g vercel
vercel login
vercel

# 3. 질문에 답변
# 4. 배포 URL 확인
```

---

## 자주 발생하는 문제 해결

### 문제 1: LocalStorage 데이터가 사라짐
**원인**: 브라우저 캐시 삭제, 시크릿 모드

**해결책**
```javascript
// 데이터 백업 기능 추가
class StorageManager {
  // 데이터 내보내기
  export() {
    const data = this.load();
    const json = JSON.stringify(data, null, 2);
    const blob = new Blob([json], { type: 'application/json' });
    const url = URL.createObjectURL(blob);
    
    const a = document.createElement('a');
    a.href = url;
    a.download = `${this.key}-backup-${Date.now()}.json`;
    a.click();
    
    URL.revokeObjectURL(url);
  }
  
  // 데이터 가져오기
  import(file) {
    return new Promise((resolve, reject) => {
      const reader = new FileReader();
      
      reader.onload = (e) => {
        try {
          const data = JSON.parse(e.target.result);
          this.save(data);
          resolve(data);
        } catch (error) {
          reject(error);
        }
      };
      
      reader.onerror = reject;
      reader.readAsText(file);
    });
  }
}
```

### 문제 2: JSON 파일 로드 실패 (CORS 에러)
**원인**: 로컬 파일 시스템에서 fetch 사용

**해결책 1: Live Server 사용**
```
VS Code 확장 프로그램 "Live Server" 설치
→ HTML 파일에서 우클릭 → "Open with Live Server"
```

**해결책 2: JSON 데이터를 JS 파일로 변환**
```javascript
// data/subjects.js
export const subjects = [
  {
    id: "math",
    name: "수학",
    color: "#FF6B6B"
  }
];

// app.js
import { subjects } from './data/subjects.js';
```

### 문제 3: 데이터가 너무 많아서 LocalStorage 용량 초과
**원인**: LocalStorage는 5-10MB 제한

**해결책**
```javascript
class StorageManager {
  save(data) {
    try {
      // 용량 체크
      const json = JSON.stringify(data);
      const size = new Blob([json]).size;
      const maxSize = 5 * 1024 * 1024; // 5MB
      
      if (size > maxSize) {
        // 오래된 데이터 삭제
        const sorted = data.sort((a, b) => 
          new Date(b.createdAt) - new Date(a.createdAt)
        );
        const trimmed = sorted.slice(0, Math.floor(sorted.length * 0.8));
        
        localStorage.setItem(this.key, JSON.stringify(trimmed));
        
        alert('저장 공간이 부족하여 오래된 데이터 20%를 삭제했습니다.');
        return false;
      }
      
      localStorage.setItem(this.key, json);
      return true;
    } catch (error) {
      if (error.name === 'QuotaExceededError') {
        alert('저장 공간이 부족합니다. 데이터를 백업하고 일부 삭제해주세요.');
      }
      return false;
    }
  }
}
```

### 문제 4: 모바일에서 레이아웃 깨짐
**해결책**
```css
/* 반응형 기본 설정 */
* {
  box-sizing: border-box;
}

/* 모바일 우선 */
.container {
  width: 100%;
  padding: 1rem;
}

.grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

/* 태블릿 */
@media (min-width: 768px) {
  .grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* 데스크톱 */
@media (min-width: 1024px) {
  .container {
    max-width: 1200px;
    margin: 0 auto;
  }
  
  .grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

---

## Cursor 고급 활용 팁

### 팁 1: 컨텍스트 제공하기
```
"이 프로젝트는 고등학생을 위한 학습 플래너야.
현재 LocalStorage로 학습 기록을 저장하고 있어.

[기존 코드]

이 코드에 다음 기능을 추가해줘:
- 주간 목표 설정
- 목표 달성률 계산
- 달성 시 축하 애니메이션"
```

### 팁 2: 단계적 요청
```
# 한 번에 모든 것을 요청하지 말고 단계적으로

Step 1: "먼저 데이터 구조만 설계해줘"
Step 2: "이 데이터 구조로 저장/불러오기 함수 만들어줘"
Step 3: "이제 UI 렌더링 함수 만들어줘"
Step 4: "모든 것을 통합해줘"
```

### 팁 3: 예시 제공
```
"다음과 같은 형식으로 카드를 만들어줘:

[예시 HTML 또는 스크린샷 설명]

- 왼쪽: 아이콘
- 중앙: 제목과 설명
- 오른쪽: 버튼 2개 (수정, 삭제)
- 호버 시 그림자 효과"
```

### 팁 4: 에러 해결
```
"다음 에러가 발생해:

[에러 메시지 복사]

관련 코드:
[코드 붙여넣기]

원인을 찾고 수정해줘"
```

### 팁 5: 코드 리뷰 요청
```
"이 코드를 리뷰해줘:

[코드]

다음 관점에서 피드백해줘:
1. 가독성
2. 성능
3. 에러 처리
4. 베스트 프랙티스
5. 개선 방안"
```

---

## 학생 성과물 예시

### 예시 1: 습관 트래커
**기능**
- 습관 목록 관리
- 일일 체크
- 연속 달성 일수 표시
- 달성률 통계

**데이터 구조**
```json
{
  "habits": [
    {
      "id": 1,
      "name": "아침 운동",
      "category": "건강",
      "goal": "매일",
      "streak": 7,
      "records": [
        {
          "date": "2025-10-31",
          "completed": true,
          "note": "30분 조깅"
        }
      ]
    }
  ]
}
```

### 예시 2: 독서 기록장
**기능**
- 읽은 책 목록
- 독서 진행률
- 메모 및 인용구
- 월별 독서량 차트

**데이터 구조**
```json
{
  "books": [
    {
      "id": 1,
      "title": "어린 왕자",
      "author": "생텍쥐페리",
      "totalPages": 120,
      "currentPage": 50,
      "status": "reading",
      "startDate": "2025-10-01",
      "notes": [
        {
          "page": 25,
          "content": "중요한 것은 눈에 보이지 않아",
          "type": "quote"
        }
      ]
    }
  ]
}
```

### 예시 3: 가계부
**기능**
- 수입/지출 기록
- 카테고리별 분류
- 월별 통계
- 예산 설정 및 알림

**데이터 구조**
```json
{
  "transactions": [
    {
      "id": 1,
      "type": "expense",
      "amount": 5000,
      "category": "식비",
      "description": "점심",
      "date": "2025-10-31"
    }
  ],
  "budget": {
    "monthly": 100000,
    "categories": {
      "식비": 50000,
      "교통": 20000
    }
  }
}
```

---

## 평가 기준

### 기능 완성도 (40점)
- 계획한 핵심 기능 모두 동작 (20점)
- 데이터 CRUD 정상 작동 (10점)
- 에러 처리 및 예외 상황 대응 (10점)

### 코드 품질 (30점)
- 코드 가독성 (주석, 변수명) (10점)
- 모듈화 및 재사용성 (10점)
- 효율성 및 최적화 (10점)

### UI/UX (20점)
- 디자인 완성도 (10점)
- 사용성 및 직관성 (5점)
- 반응형 디자인 (5점)

### 창의성 및 문제해결 (10점)
- 독창적인 아이디어 (5점)
- 문제 해결 과정 (5점)

---

## 마무리

이 가이드를 통해 학생들은:

1. **실전 경험**: 백엔드 없이도 완전한 웹 애플리케이션 제작
2. **빠른 프로토타이핑**: Cursor로 아이디어를 즉시 구현
3. **데이터 관리**: LocalStorage와 JSON 활용법 체득
4. **문제 해결**: 실제 개발 과정의 어려움 극복
5. **포트폴리오**: 배포 가능한 결과물 확보

**핵심 메시지**
> "서버가 없어도, 복잡한 백엔드 지식이 없어도,
> 여러분의 아이디어를 실현할 수 있습니다.
> Cursor와 함께라면 더 빠르고 쉽게!"

**다음 단계**
- 실제 백엔드 연동 (Firebase, Supabase)
- 사용자 인증 추가
- 실시간 동기화
- PWA (Progressive Web App) 변환
- 외부 API 연동

---

**버전**: 1.0  
**최종 수정**: 2025-10-31  
**대상**: 일반 고등학생  
**난이도**: 입문~중급

