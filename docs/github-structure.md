# 📁 .github/ 폴더 설명서

이 문서는 `.github/` 폴더의 역할과 이곳에 어떤 파일을 넣어야하는지 설명하는 가이드입니다.

---

## ✅ 폴더 구조 개요

```
.github/
├── workflows/
│   └── deploy.yml            # GitHub Actions 자동 배포 설정
├── ISSUE_TEMPLATE/
│   └── bug_report.md         # 버그 리포트용 이슈 템플릿 (선택)
├── PULL_REQUEST_TEMPLATE.md  # PR 올릴 때 자동으로 뜨는 템플릿 (선택)
├── CONTRIBUTING.md           # 협업 기여 가이드 (선택)
```

---

## 📌 필수 파일 설명

### 1. `.github/workflows/deploy.yml`

- GitHub Actions 워크플로우 설정 파일
- 우리가 GitHub에 푸시할 때 **Cloudflare Pages로 자동 배포**되도록 함
- 작성자: 개발자 (자동화 담당)

> 이 파일 없으면 push해도 사이트가 자동으로 업데이트되지 않음

---

## ✍️ 선택적으로 추가하면 좋은 파일

### 2. `PULL_REQUEST_TEMPLATE.md`

- PR 올릴 때 자동으로 뜨는 템플릿
- 리뷰하기 쉽게 변경 내용을 요약할 수 있도록 안내함

```md
## 요약
변경한 내용 요약:

## 관련 이슈
- closes #

## 스크린샷 (UI 변경 시)
(선택 사항)
```

### 3. `ISSUE_TEMPLATE/bug_report.md`

- 버그 제보를 위한 템플릿
- 반복되는 형식을 통일시켜 이슈를 관리하기 쉽게 만듦

```yaml
name: 버그 리포트
description: 에러나 문제 상황을 보고합니다
title: "[BUG] "
labels: ["bug"]
body:
  - type: textarea
    id: description
    attributes:
      label: 문제 설명
      placeholder: 어떤 문제가 발생했는지 적어주세요
```

### 4. `CONTRIBUTING.md`

- 이 저장소에서 협업할 때 지켜야 할 규칙 정리
- 커밋 컨벤션, 브랜치 전략, PR 방법 등

```md
# 🤝 CONTRIBUTING

- 커밋은 Conventional Commit 사용
- main 브랜치에 직접 푸시하지 말고, PR로 병합
- PR 제목은 간결하게, 내용은 변경 사항 설명 필수
```

---

## 💡 언제 만들까?

| 파일명 | 만들 시점 |
|--------|-------------|
| `deploy.yml` | Cloudflare Pages 자동화 시 바로 필요 |
| `PULL_REQUEST_TEMPLATE.md` | PR을 서로 리뷰하기 시작할 때 |
| `CONTRIBUTING.md` | 팀 규모가 늘어나거나 규칙이 생기기 시작할 때 |
| `ISSUE_TEMPLATE/*` | 오픈소스 또는 외부 제보를 받을 때 유용 |

---

## 🔐 보안 관련 파일

- `SECURITY.md`: 보안 이슈 제보 가이드 (공개 프로젝트일 경우만 필요)
- `FUNDING.yml`: GitHub에서 ‘스폰서하기’ 버튼을 활성화할 때 사용

---

## 📌 정리

- `.github/workflows/` = 자동화 (GitHub Actions)
- `.github/PULL_REQUEST_TEMPLATE.md` = 협업 일관성 유지
- `.github/ISSUE_TEMPLATE/` = 이슈 관리 구조화
- `.github/CONTRIBUTING.md` = 협업 규칙 가이드

---

이 폴더는 GitHub가 **자동으로 인식하는 특수 경로**이므로 정해진 규칙에 맞게 작성하면 플랫폼의 다양한 기능을 활용할 수 있습니다.
