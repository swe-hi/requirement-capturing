# Git Convention

## 제출 문서 종류

1. **요구사항 목록 (Functional Requirements List)**
- 모든 기능을 요구사항 형식으로 정리한 문서
- 파일명: `requirements-list.md`
2. **유스케이스 다이어그램 (Use Case Diagrams)**
- UML 도구로 작성된 다이어그램
- 파일명: `use-case-diagrams-[기능명].mdj`
- Git에서 통합이 어려우므로, 각 기능별로 파일 구성 후 메인브랜치에서 통합
3. **유스케이스 설명 (Use Case Descriptions)**
- 각 유스케이스에 대한 step-by-step 설명
- 파일명: `use-case-descriptions.md`

## 기능별 브랜치 구조

### 메인 브랜치

- `main`: 최종 제출 브랜치
- `develop`: 작업 브랜치

### 기능별 브랜치 (개인 작업용)

**회원 관리**

- `member-management/requirements`: 회원 관리 요구사항
- `member-management/diagrams`: 회원 관리 유스케이스 다이어그램
- `member-management/descriptions`: 회원 관리 유스케이스 설명

**대여소 및 자전거 관리**

- `station-bike/requirements`: 대여소/자전거 관리 요구사항
- `station-bike/diagrams`: 대여소/자전거 관리 유스케이스 다이어그램
- `station-bike/descriptions`: 대여소/자전거 관리 유스케이스 설명

**대여 정보 관리**

- `rental-info/requirements`: 대여 정보 관리 요구사항
- `rental-info/diagrams`: 대여 정보 관리 유스케이스 다이어그램
- `rental-info/descriptions`: 대여 정보 관리 유스케이스 설명

**결제 및 통계**

- `payment-stats/requirements`: 결제 및 통계 요구사항
- `payment-stats/diagrams`: 결제 및 통계 유스케이스 다이어그램
- `payment-stats/descriptions`: 결제 및 통계 유스케이스 설명

## 작업 흐름

1. 각자 자신의 기능별 브랜치에서 작업합니다.
2. 개인 작업이 완료되면 문서 작업용 브랜치로 PR을 생성합니다.
3. 문서 작업용 브랜치에서 통합 및 검토 후 `dev` 브랜치로 PR을 생성합니다.
4. 최종 검토 후 `dev`에서 `main`으로 병합하여 최종 제출 버전을 만듭니다.

## Git 명령어 예시

```bash
# 초기 설정
git clone [repository-url]
git checkout -b dev
git push origin dev

# 기능별 브랜치 생성 
git checkout dev
git branch member-management/requirements
git checkout member-management/requirements

# 작업 후
git add .
git commit -m "requirements: 회원 관리 요구사항 작성"
git push -u origin member-management/requirements
```

### Commit message 예시

- requirements: 요구사항 목록 관련 작업
- use-case-diagram: 유스케이스 다이어그램 관련 작업
- use-case-description: 유스케이스 설명 관련 작업
- docs: 일반 문서 관련 작업
- fix: 오류 수정 작업
- chore: 기타 작업

```bash
# 요구사항 작성
git commit -m "requirements: 회원 가입 기능 추가"
git commit -m "requirements: 회원 탈퇴 기능 추가"
git commit -m "requirements: 로그인/로그아웃 기능 추가"

# 유스케이스 다이어그램
git commit -m "use-case-diagram: 회원 가입 다이어그램 추가"
git commit -m "use-case-diagram: 회원 탈퇴 다이어그램 추가"
git commit -m "use-case-diagram: 로그인/로그아웃 다이어그램 추가"

# 유스케이스 설명
git commit -m "use-case-description: 회원 가입 step-by-step 설명 추가"
git commit -m "use-case-description: 회원 탈퇴 step-by-step 설명 추가"
git commit -m "use-case-description: 로그인/로그아웃 step-by-step 설명 추가"
```