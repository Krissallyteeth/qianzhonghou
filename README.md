# qianzhonghou

项目投资费用（预算或已发生）划期 — 프로젝트 투자비용(예산/실집행) 기간 구분 웹페이지.

탭 기반 UI로 투자비용을 기간(划期)별로 분류·정리하는 단일 페이지 웹앱입니다.

## 특징

- **단독 HTML 파일** (`index.html`) — CSS/JS 모두 인라인, 외부 CDN·웹폰트·의존성 **0개**
- **오프라인 동작** — 인터넷 없이 브라우저로 바로 열림 (中国可离线使用)
- 시스템 폰트만 사용 (微软雅黑 / SimSun)
- `lang="zh-CN"`, 중문 UI

## 사용 방법

### 로컬 (가장 확실, 어디서나)
`index.html`을 다운로드해서 브라우저로 더블클릭하면 끝. 서버·계정·네트워크 불필요.
중국 환경에서도 100% 동작합니다.

### 온라인 링크

| 방법 | 주소 | 비고 |
|---|---|---|
| GitHub Pages (자동 배포) | https://krissallyteeth.github.io/qianzhonghou/ | 해외 정상, **중국에서는 차단/불안정** |
| 즉시 미리보기 (htmlpreview) | https://htmlpreview.github.io/?https://github.com/Krissallyteeth/qianzhonghou/blob/main/index.html | GitHub 의존, 중국 불안정 |
| Cloudflare Pages (권장) | 직접 배포 필요 (아래 참고) | 무료·전 세계, 备案 불필요 |

## 배포

### GitHub Pages (자동, 설정 완료됨)
`.github/workflows/pages.yml` 워크플로우가 `main` 브랜치 푸시 시 자동으로 GitHub Pages에 배포합니다.
별도 설정 불필요 (`enablement: true`로 Pages 자동 활성화).

### Cloudflare Pages (글로벌 접속 권장)
중국 포함 전 세계 접속을 위한 무료 옵션. 빌드 불필요한 정적 페이지라 설정이 간단합니다.

1. https://dash.cloudflare.com 가입 (무료)
2. **Workers & Pages → Create application → Pages → Connect to Git**
3. 저장소 `Krissallyteeth/qianzhonghou` 선택
4. 빌드 설정:
   - Production branch: `main`
   - Framework preset: **None**
   - Build command: **(비움)**
   - Build output directory: `/`
5. **Save and Deploy** → `https://qianzhonghou.pages.dev` 발급

## 중국 접속 고려사항

- GitHub Pages / Netlify / Vercel 은 중국에서 차단되거나 매우 느립니다.
- 무료 중 글로벌 최선은 **Cloudflare Pages** (github.io보다 훨씬 나음, 완벽 보장은 아님).
- 중국 접속이 핵심이면: **Gitee Pages(码云)** 미러 추가 (实名认证 필요) 또는 备案한 도메인 + 阿里云/腾讯云(유료).
- 단발성 공유라면 **HTML 파일 직접 전달**(위챗/이메일)이 가장 확실합니다.

## 다른 컴퓨터에서 이어서 작업

모든 작업물이 저장소에 있으므로 어디서든 클론해 이어서 작업할 수 있습니다.

```bash
git clone https://github.com/Krissallyteeth/qianzhonghou.git
cd qianzhonghou
```

## 파일 구조

```
.
├── index.html                 # 단독 웹페이지 (전체 앱)
├── README.md
└── .github/workflows/pages.yml # GitHub Pages 자동 배포
```
