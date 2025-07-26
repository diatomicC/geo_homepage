# 🌐 GEO Blog 

Generative Engine Optimization(GEO)을 주제로 한 SEO 최적화 블로그 및 외주 랜딩페이지 프로젝트입니다.  
Astro를 프론트엔드 프레임워크로 사용하며, Cloudflare Workers를 백엔드로 활용해 글 업로드를 처리합니다.  
블로그 콘텐츠는 `.md` 파일로 GitHub에 저장되고, push될 때마다 정적 사이트가 자동 빌드/배포됩니다.

---

## 프로젝트 구조

```

geo-blog/
├── apps/
│   ├── frontend/            # Astro 블로그 (정적 사이트)
│   └── backend/             # Cloudflare Workers API (글 업로드 처리)
├── shared/                  # 공통 유틸리티 (선택적)
├── .github/workflows/       # CI/CD 자동화
└── package.json             # workspace 설정

````

---

## 기술 스택

- **Frontend**: [Astro](https://astro.build) + Tailwind CSS
- **Markdown Blog**: content/blog/*.md
- **Backend**: [Cloudflare Workers](https://developers.cloudflare.com/workers/)
- **Hosting**: [Cloudflare Pages](https://pages.cloudflare.com)
- **CI/CD**: GitHub Actions + Cloudflare 자동 빌드
- **Repository**: Git 기반 콘텐츠 저장 (DB 없음)

---

## 로컬 개발 환경

### 1. 프로젝트 설치

```bash
git clone https://github.com/diatomicC/geo_homepage.git
cd geo_homepage
npm install
````

### 2. 프론트엔드 실행

```bash
cd apps/frontend
npm install
npm run dev
```

### 3. 백엔드 실행 (Cloudflare Worker)

```bash
cd apps/backend
npm install
wrangler dev
```

환경 변수는 `wrangler.toml` 또는 `wrangler secrets`로 설정:

* `GITHUB_TOKEN`
* `GITHUB_OWNER`
* `GITHUB_REPO`

---

## ✍글 작성 흐름 (자동 배포)

1. 사용자가 글 작성 폼에서 POST 요청 → Cloudflare Worker API
2. API가 `.md` 파일 생성 및 GitHub에 push
3. GitHub push 감지됨 → Cloudflare Pages가 Astro 정적 빌드
4. 블로그에 새로운 글 자동 반영

---

## Astro 관련 명령어

```bash
# Astro dev 서버 실행
npm run dev

# Astro 정적 사이트 빌드
npm run build
```

---

## Secrets & 설정

* Cloudflare Workers 환경 변수 설정: `wrangler.toml`
* GitHub 저장소 접근을 위한 Personal Access Token 필요
* 커밋 메시지는 Conventional Commits 사용 권장 (`feat:`, `fix:`, `chore:` 등)

---

## TODO (협업 관리용)

* [ ] 블로그 상세 페이지 디자인 개선
* [ ] OG 이미지 자동 생성 기능
* [ ] 작성자 인증 기능 (JWT or OAuth)
* [ ] 검색 기능 (Fuse.js 등)

---

## 참고 자료

* [Astro Docs](https://docs.astro.build)
* [Cloudflare Workers Docs](https://developers.cloudflare.com/workers/)
* [Markdown + SSG = SEO 최강 구조](https://jamstack.org)

---

## Maintainers

* [@juheehur](https://github.com/juheehur)
* [@rxg-24](https://github.com/rxg-24)

```
