# 项目投资费用（预算或已发生）前－中－后划期

项目投资費用를 **前期 / 中期 / 后期**로 분류한 참조표 웹페이지.

**온라인 주소:** https://qianzhonghou.pages.dev

---

## 기간 정의

| 기간 | 정의 |
|------|------|
| **前期** | 项目达到收档要求所发生的项目投入费用 |
| **中期** | 项目完整建设期（施工开工至整体验收或中交）期间 |
| **后期** | 从项目整体验收或中交后至正式生产（非生产性项目为正式投入使用）3~6个月 |

## 페이지 구성

- **建设类** 탭 — 建设项目总投资（固定资产投资 / 铺底流动资金）费用 划期표
- **非建设类** 탭 — 非建设类项目总投资 费用 划期표

## 원본 파일

`V2-项目投资费用（预算或已发生）前-中-后划期_20260520.xlsx`

## 기술 스택

- 순수 HTML / CSS / JS — 외부 의존성 없음, 단일 파일(`index.html`)
- 오프라인에서 바로 열림 (파일 더블클릭 가능)

## 배포

### Cloudflare Pages (현재 운영 중)

```bash
npx wrangler pages deploy . --project-name qianzhonghou --branch main --commit-dirty=true
```

### GitHub Pages

https://krissallyteeth.github.io/qianzhonghou/

> 중국에서는 GitHub Pages가 차단될 수 있어 Cloudflare Pages를 권장합니다.
