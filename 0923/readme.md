# 📚 웹 프로그래밍 & Git/GitHub 협업 정리 노트

본 저장소는 웹 프로그래밍(CSS3) 기초 학습 내용 및 Git/SourceTree를 활용한 버전 관리, GitHub 협업 프로세스와 타사 툴(Jira, Slack) 연동 가이드를 정리한 문서입니다.

---

## 📌 목차
1. [SourceTree (Git GUI 툴) 활용법](#1-sourcetree-git-gui-툴-활용법)
2. [Git / GitHub 협업 프로세스 및 외부 툴 연동](#2-git--github-협업-프로세스-및-외부-툴-연동)
3. [웹 프로그래밍: CSS3로 웹 페이지 꾸미기](#3-웹-프로그래밍-css3로-웹-페이지-꾸미기)

---

## 1. SourceTree (Git GUI 툴) 활용법

### 1.1 SourceTree란?
SourceTree는 복잡한 Git 명령어 대신 직관적인 그래픽 유저 인터페이스(GUI)를 제공하여 버전 관리를 쉽게 할 수 있도록 돕는 무료 도구입니다.

### 1.2 주요 특징 및 장점
* **직관적인 버전 관리**: 커밋(Commit) 이력, 브랜치(Branch) 병합 과정, 코드 변경 사항(Diff)을 한눈에 그래프로 확인 가능
* **명령어 대체**: 클릭만으로 Commit, Push, Pull, Merge, Rebase, Stash 등의 핵심 Git 작업 수행
* **주요 호스팅 서비스 연동**: GitHub, Bitbucket, GitLab 등과 용이하게 연결
* **무료 제공**: Windows 및 macOS 환경 모두 지원

### 1.3 설치 및 설정 순서
1. **Sourcetree 다운로드**: 공식 페이지에서 설치 파일 다운로드
2. **라이선스 동의 & 설치 파일 실행**
3. **계정 연동 설정**: 초기 설정 단계에서 '건너뛰기' 선택 가능 (필요 시 Bitbucket 연동)
4. **Mercurial 설정 해제**: Git 사용이 목적이므로 Mercurial 체크박스 해제
5. **사용자 정보 입력**: Git 커밋 시 표시될 Name 및 Email 설정
6. **SSH 키 설정**: 기존 생성 키가 없을 경우 '아니오' 선택 후 진행
7. **완료 및 실행**: 로컬 디렉토리를 열어 Git 상태 파악 및 시각적 모니터링 수행

---

## 2. Git / GitHub 협업 프로세스 및 외부 툴 연동

### 2.1 역할별 협업 프로세스

| 구분 | 역할 | 주요 작업 내용 |
| :--- | :--- | :--- |
| **팀장 (Maintainer)** | **01. Repository 생성** | 깃허브에 프로젝트 원본 저장소 생성 |
| | **02. Issue 할당** | 작업 할 일 목록 작성 및 담당 팀원 배정 |
| | **06. Code Review** | 팀원의 PR 코드를 검토하고 피드백 작성 |
| | **07. Merge** | 문제없는 코드를 원본 저장소에 최종 병합 |
| **팀원 (Developer)** | **03. Fork & Clone** | 원본 저장소를 내 계정으로 복사 후 로컬 PC로 다운로드 |
| | **04. Branch 생성** | 원본 코드 영향 방지를 위해 기능별 독립 작업 공간 생성 |
| | **05. Pull Request (PR)** | 작업 완료 후 깃허브에 올리고 원본 저장소에 병합 요청 |

---

### 2.2 지라(Jira) 연동
* **설치**: Jira 프로젝트 설정 > Apps에서 `GitHub for Jira` 검색 후 설치
* **계정 연동**: GitHub 계정 인증 및 협업할 레포지토리 연결
* **이슈 키 연동 방법**: 커밋 메시지 또는 PR 제목 앞에 Jira 이슈 번호 기재
  ```bash
  git commit -m "PROJ-123: 메인 페이지 HTML 레이아웃 작성"
  ```
  *(푸시 시 Jira 보드에서 해당 커밋/PR 상태가 자동으로 연동되어 표시됨)*

---

### 2.3 슬랙(Slack) 연동
* **설치**: Slack 앱 디렉토리에서 `GitHub` 앱 설치
* **채널 연동**: 알림을 수신할 Slack 채널에서 명령어 입력
  ```bash
  /github subscribe [조직명 또는 계정명]/[레포지토리이름]
  # 예시: /github subscribe MyOrg/project-repo
  ```
* **알림 세부 설정**: `/github settings` 명령어로 PR, 커밋, 리뷰 요청 등 세부 알림 켜기/끄기 설정 가능

---

## 3. 웹 프로그래밍: CSS3로 웹 페이지 꾸미기

### 3.1 CSS3 개요 및 기본 문법
* **CSS (Cascading Style Sheets)**: HTML 문서의 구조에 디자인과 스타일을 입혀주는 스타일 언어
* **기본 문법 구조**:
  ```css
  선택자 (Selector) {
      프로퍼티 (Property): 값 (Value);
  }
  ```
  * 예시: `p { color: blue; font-size: 15px; }`

---

### 3.2 CSS3 스타일 시트 적용 방법 3가지

#### 1) 인라인 스타일 (Inline Style)
HTML 태그 내부의 `style` 속성에 직접 스타일을 지정합니다.
```html
<p style="color: blue; font-size: 16px;">인라인 스타일 예시</p>
```

#### 2) 내부 스타일 시트 (Internal Style Sheet)
HTML 문서의 `<head>` 태그 안 `<style>` 태그 내에 작성합니다.
```html
<head>
  <style>
    body { background-color: mistyrose; }
    h3 { color: purple; }
  </style>
</head>
```

#### 3) 외부 스타일 시트 불러오기 (External Style Sheet)
별도의 `.css` 파일로 저장 후 HTML에서 불러옵니다.

* **`<link>` 태그 이용 (권장)**:
  ```html
  <link rel="stylesheet" type="text/css" href="mystyle.css">
  ```
* **`@import` 규칙 이용**:
  ```html
  <style>
    @import url("mystyle.css");
  </style>
  ```

---

### 3.3 CSS3 선택자(Selector) 대표 유형
* **태그 선택자**: 지정한 태그 전체에 스타일 적용 (`h3 { color: red; }`)
* **클래스 선택자 (`.`)**: HTML `class` 속성값으로 지정하며 중복 적용 가능 (`.warning { color: red; }`)
* **ID 선택자 (`#`)**: HTML `id` 속성값으로 지정하며 유일한 요소 지정 시 사용 (`#header { background: yellow; }`)
* **전체 선택자 (`*`)**: 웹 페이지 내 모든 태그에 스타일 적용 (`* { font-family: 'Noto Sans KR'; }`)

---

### 3.4 CSS3 핵심 규칙: 스타일 상속 (Inheritance)
* **상속 개념**: 부모 태그에 적용된 스타일 속성은 자식 태그로 자동 전달(상속)됩니다.
* **상속 코드 예시**:
  ```html
  <!-- 부모 p 태그에 지정된 초록색 스타일이 자식 em 태그에 상속됨 -->
  <p style="color: green;">
    부모 텍스트입니다. 
    <em>자식 텍스트도 부모의 초록색을 상속받습니다.</em>
  </p>
  ```
* **상속 재정의 (Overriding)**: 자식 태그에서 새로운 스타일을 정의하면 부모로부터 상속받은 스타일보다 우선 적용됩니다.
  ```html
  <p style="color: green;">
    부모 텍스트입니다. 
    <em style="color: red;">자식 태그에서 빨간색으로 재정의하였습니다.</em>
  </p>
  ```
