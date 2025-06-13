# Yongrae Jo - GNSS/GPS 기술 블로그

GNSS/GPS 기술과 관련된 개발 경험과 지식을 공유하는 기술 블로그입니다.

## ◆ 소개

이 블로그는 [Hugo](https://gohugo.io/) 정적 사이트 생성기와 [Ananke](https://github.com/theNewDynamic/gohugo-theme-ananke) 테마를 사용하여 제작되었습니다.

### 주요 다루는 내용

- **🛰️ GNSS/GPS 기술** - 위성 항법 시스템의 이론과 실제 구현
- **📡 RTK/PPP** - 고정밀 측위 기술과 알고리즘
- **💻 C/C++ 개발** - 시스템 레벨 프로그래밍과 최적화
- **🔧 임베디드 시스템** - 실시간 GPS 수신기 개발
- **📊 신호 처리** - GNSS 신호 분석과 알고리즘

## ◆ 기술 스택

### 사이트
- **Hugo** v0.147.8 - 정적 사이트 생성기
- **Ananke Theme** - 반응형 블로그 테마
- **GitHub Pages** - 호스팅
- **GitHub Actions** - 자동 배포

### 개발 환경
- **언어**: C/C++, Python, MATLAB
- **도구**: Git/GitHub, Linux/Unix
- **라이브러리**: RTKLIB, 신호 처리

## ◆ 로컬 개발

### 요구사항
- Hugo v0.147.8 이상
- Git

### 설치 및 실행

```bash
# 저장소 클론
git clone --recursive https://github.com/yongrae-jo/yongrae-jo.github.io.git

# 디렉토리 이동
cd yongrae-jo.github.io

# 개발 서버 실행
hugo server --buildDrafts
```

사이트는 `http://localhost:1313`에서 확인할 수 있습니다.

### 새 포스트 작성

```bash
# 새 포스트 생성
hugo new posts/your-post-title.md

# 개발 서버에서 초안 포함 미리보기
hugo server --buildDrafts
```

## ◆ 배포

GitHub Actions를 통해 자동으로 배포됩니다.

1. `master` 브랜치에 푸시
2. GitHub Actions가 자동으로 사이트 빌드
3. GitHub Pages에 배포 완료

## ◆ 프로젝트 구조

```
├── .github/
│   └── workflows/
│       └── hugo.yml          # GitHub Actions 워크플로우
├── content/
│   ├── posts/               # 블로그 포스트
│   ├── about.md            # About 페이지
│   └── _index.md           # 홈페이지
├── themes/
│   └── ananke/             # 테마 (서브모듈)
├── static/                 # 정적 파일
├── hugo.toml              # Hugo 설정
└── README.md              # 프로젝트 설명
```

## ◆ 라이선스

이 블로그의 콘텐츠는 개인적인 견해이며, 지속적으로 학습하고 발전하는 과정을 기록하고 있습니다.

---

*GNSS 기술에 관심 있는 모든 분들과 지식을 공유하고자 합니다.* 