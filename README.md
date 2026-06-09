# MAISON GONY · QR Landing

QR 접속용 한/영/중 단일 브랜드 안내 페이지. GitHub Pages 정적 배포.

- **주소**: https://qr.maisongony.com
- **디자인**: maisongony.com 톤(미니멀 · 크림/어스톤 · 산세리프) 기반
- **기능**: 한국어/English/中文 전환(브라우저 언어 자동 감지 + 선택 저장), Google Analytics

## 파일 구성

```
index.html      메인 페이지 (HTML · CSS · JS 한 파일)
CNAME           커스텀 도메인 (qr.maisongony.com)
.nojekyll       GitHub Pages가 Jekyll로 처리하지 않도록
404.html        잘못된 경로 접근 시 안내
assets/         이미지(og-card.png 등) — assets/README.md 참고
```

## 내용 수정 방법

`index.html` 상단 `<script>` 안의 **`CONFIG`** 블록만 고치면 됩니다.

- `GA_ID` — Google Analytics 4 측정 ID (`G-XXXXXXXXXX`). 발급 전엔 그대로 두면 추적 비활성.
- `links.shop / instagram / journal / map` — 버튼 링크. `''` 로 비우면 버튼 자동 숨김.
- `visit.address / hours / phone` — 방문 안내. `''` 로 비우면 해당 줄 자동 숨김.

번역 문구는 같은 파일의 **`I18N`** 블록(ko/en/zh)에서 수정합니다.

## 로컬 미리보기

브라우저로 `index.html` 을 열거나, 폴더에서:

```powershell
python -m http.server 8000   # http://localhost:8000
```

## 배포 (GitHub Pages)

1. `main` 브랜치에 커밋 & 푸시
2. GitHub → **Settings → Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** / **/(root)**
3. **Custom domain** 에 `qr.maisongony.com` 입력 → 저장
4. DNS에 CNAME 레코드 추가 — 이름 `qr`, 대상 `artlapin.github.io`
5. 인증서 발급 후 **Enforce HTTPS** 체크

> DNS 전파에 최대 24시간 걸릴 수 있습니다.
