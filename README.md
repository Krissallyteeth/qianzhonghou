# qianzhonghou — 프로젝트 투자/원가 참조표

프로젝트 투자비용·원가과목을 정리한 정적 웹페이지 모음입니다. 저장소 하나에 **두 개의 독립 페이지**가 들어 있습니다.

| 페이지 | 내용 | 폴더 |
|--------|------|------|
| **投资划期** | 项目投资费用（预算或已发生）前－中－后 划期 | `index.html` (루트) |
| **成本科目** | 项目成本科目及释义 | `chengbenkemu/` |

---

## 1. 投资划期 페이지 (项目投资费用 前-中-后 划期)

투자비용을 **前期 / 中期 / 后期**로 분류한 참조표.

**링크**
- Cloudflare: https://qianzhonghou.pages.dev
- GitHub Pages: https://krissallyteeth.github.io/qianzhonghou/

**기간 정의**

| 기간 | 정의 |
|------|------|
| **前期** | 项目可行性论证及施工前勘察设计等所发生的投入 |
| **中期** | 项目完整建设期（施工开工至整体验收或中交）发生的项目投入 |
| **后期** | 从项目整体验收或中交后至正式生产（非生产性项目为正式投入使用）3~6个月发生的项目投入 |

**구성**: `建设类` / `非建设类` 두 탭의 투자분류 划期표.

---

## 2. 成本科目 페이지 (项目成本科目及释义)

원가/비용 과목(一级科目·二级科目)과 그 释义를 정리한 참조표. 엑셀 원본의 파란색(`#00B0F0`)·빨간색(`#FF0000`) 강조를 그대로 보존했습니다.

**링크**
- Cloudflare: https://chengbenkemu.pages.dev *(별도 프로젝트로 배포 필요 — 아래 참고)*
- GitHub Pages: https://krissallyteeth.github.io/qianzhonghou/chengbenkemu/

**구성**: `建设类项目` / `非建设类项目` 두 탭. 각 탭은 成本项目类(一级/二级科目) + 解释 표.

---

## 기술 스택

- 순수 HTML / CSS / JS — 외부 의존성 없음, 각 페이지 단일 `index.html`
- 오프라인에서 바로 열림 (파일 더블클릭 가능)
- `lang="zh-CN"`, 중문 UI, 시스템 폰트만 사용

## 배포

### GitHub Pages (자동)

`.github/workflows/pages.yml` 가 `main` 푸시 시 저장소 전체를 자동 배포합니다.
- 投资划期: https://krissallyteeth.github.io/qianzhonghou/
- 成本科目: https://krissallyteeth.github.io/qianzhonghou/chengbenkemu/

> 중국에서는 GitHub Pages가 차단될 수 있어 Cloudflare Pages를 권장합니다.

### Cloudflare Pages (수동 / 페이지별 별도 프로젝트)

각 페이지를 별도 Cloudflare 프로젝트로 배포해 독립 주소를 부여합니다.

```bash
# 投资划期 (루트)
npx wrangler pages deploy . --project-name qianzhonghou --branch main --commit-dirty=true

# 成本科目 (chengbenkemu 폴더)
npx wrangler pages project create chengbenkemu --production-branch main   # 최초 1회
npx wrangler pages deploy chengbenkemu --project-name chengbenkemu --branch main --commit-dirty=true
```

> 참고: 중국에서 GitHub `git pull`이 차단될 경우, 저장소 코드는 GitHub에 이미 반영돼 있으므로 파일만 받아 `wrangler`로 배포하면 됩니다. (Cloudflare API는 중국에서 접속 가능)

## 원본 파일

- `V2-项目投资费用（预算或已发生）前-中-后划期_20260520.xlsx`
- `项目成本科目及释义.xlsx`

## 파일 구조

```
.
├── index.html                  # 投资划期 페이지
├── chengbenkemu/
│   └── index.html              # 成本科目 페이지
├── README.md
└── .github/workflows/
    ├── pages.yml               # GitHub Pages 자동 배포
    └── cloudflare.yml          # Cloudflare 자동 배포 (Secret 등록 시 동작)
```
