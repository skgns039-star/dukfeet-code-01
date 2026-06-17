# DUKFEET 상품 모델 영상 (dukfeet-code-01)

## 1. 프로젝트 목적
DUKFEET 핸드메이드 가죽 신발 상품페이지에 넣을 **16:9 상품 모델 영상**을 GitHub Pages로 공개 호스팅하고, 아임웹 코드 위젯에 한 번에 붙여넣을 HTML/CSS/JS를 제공합니다. 첫 화면에 DUKFEET 로고가 절제되게 등장한 뒤 영상으로 부드럽게 크로스페이드됩니다.

## 2~8. 계정 / 저장소 / URL
- GitHub 계정: **skgns039-star**
- 저장소명: **dukfeet-code-01**
- 저장소 URL: https://github.com/skgns039-star/dukfeet-code-01
- GitHub Pages 기본 주소: https://skgns039-star.github.io/dukfeet-code-01/
- 영상 URL: https://skgns039-star.github.io/dukfeet-code-01/videos/dukfeet-product-model-video.mp4?v=1
- 포스터 URL: https://skgns039-star.github.io/dukfeet-code-01/images/dukfeet-product-model-poster.png
- 아임웹 코드 파일 URL: https://skgns039-star.github.io/dukfeet-code-01/imweb/dukfeet-product-video-widget.html

## 9. 폴더 구조
```
dukfeet-code-01
├─ index.html                 # GitHub Pages 확인용 페이지(noindex)
├─ videos/dukfeet-product-model-video.mp4
├─ images/dukfeet-product-model-poster.png
├─ imweb/dukfeet-product-video-widget.html   # 아임웹 코드 위젯 붙여넣기용
├─ README.md
└─ .gitignore
```

## 10~13. 원본 보존 / 포스터 원본
- 원본 영상은 재인코딩·삭제·덮어쓰기 없이 그대로 보존했습니다. (FFmpeg 미사용)
- 원본 이미지도 리사이즈·재압축 없이 보존했습니다. (이미지 생성 AI 미사용)
- 포스터 원본 경로: `C:\01. 홈페이지 제작 샘플\01. 직원 폴더\나훈\code\public\images\dukfeet-rogo-hero.png`
- 실제 포스터 확장자: **.png** (image/png), 410×410px. `rogo` 철자는 사용자 지정대로 유지.
- 배포본은 위 원본을 복사해 `dukfeet-product-model-poster.png`로 사용합니다.

## 14~15. 아임웹 적용 / 새 섹션 추가
1. 아임웹 관리자 → 디자인 모드 → 상품 상세(또는 상세 공통) 페이지
2. 원하는 위치에 **새 섹션 → 코드 위젯** 추가
3. `imweb/dukfeet-product-video-widget.html` 전체를 복사해 붙여넣기 → 저장
4. 다른 섹션에도 동일 위젯을 추가할 수 있습니다(고유 클래스 `dukfeet-product-motion`로 충돌 방지, 스크립트는 위젯별로 자동 초기화).

## 16~18. SEO / ARIA / ALT 문구
- H2 제목(한국어): `DUKFEET 핸드메이드 가죽 신발 착용 영상`
- 설명(한국어): `모델의 움직임을 통해 DUKFEET 핸드메이드 가죽 신발의 실루엣과 착화 모습을 확인할 수 있습니다.`
- 영상 ARIA(aria-label): `DUKFEET 핸드메이드 가죽 신발의 착화 모습과 움직임을 보여주는 모델 영상`
- 이미지 ALT: `DUKFEET 핸드메이드 가죽 신발 브랜드 로고`
- 영문 제목: `DUKFEET Handmade Leather Shoes Model Video`
- 영문 설명: `View the silhouette, fit and movement of DUKFEET handmade leather shoes through this model video.`
- 영문 ALT: `DUKFEET handmade leather shoes brand logo`
- `<video>`에는 `alt` 미사용(대신 aria-label), 실제 `<img>`와 `<noscript> img`에만 ALT 적용. H1 미생성(상세페이지 구조에 맞춰 H2 사용).

## 19~22. 첫 화면 로고 애니메이션 (조절법)
- 동작: 화면 근접 → 로고 페이드인(+미세 확대 안정화) → 영상 `playing` 시 로고→영상 크로스페이드 → 페이드 완료 후 로고 visibility 제거.
- 로고 페이드인 시간: `--dukfeet-intro-enter-duration` (기본 800ms)
- 로고 확대 안정화: `--dukfeet-intro-settle-duration` (기본 1500ms)
- 로고 시작 배율: `--dukfeet-intro-start-scale` (기본 1.02 / 모바일 1.015)
- 영상 크로스페이드: `--dukfeet-video-reveal-duration` (기본 900ms)
- 회전/튕김/플래시/글리치 미사용. 영상 오류 시 로고 유지.

## 23~26. 검은 띠 크롭 / 피사체 위치
- PC 크롭값: `--dukfeet-video-crop-scale` 기본 **1.12**
  - 검은 띠가 남으면 1.15 또는 1.18로 올리기
  - 좌우가 많이 잘리면 1.08 또는 1.05로 낮추기
- 모바일 크롭값: 모바일 미디어쿼리의 `--dukfeet-video-crop-scale` 기본 **1.10** (동일 방식으로 조절)
- 피사체가 치우치면 `--dukfeet-video-position-x` / `--dukfeet-video-position-y` 조절
- CSS 크롭은 MP4 원본 해상도를 변경하지 않고, 검은 띠를 프레임 밖으로 밀어내는 방식입니다.

## 27~30. 영상/포스터 교체 · 캐시 갱신
- 영상 교체: 새 mp4를 `videos/dukfeet-product-model-video.mp4`로 교체 후 커밋·push
- 포스터 교체: 새 이미지를 `images/dukfeet-product-model-poster.png`로 교체(확장자 바뀌면 코드의 URL도 수정)
- 캐시 갱신: 코드의 영상 URL `?v=1` → `?v=2`로 올리기 (브라우저/Pages 캐시 무효화)

## 31~33. 문제 해결
- 영상이 안 나올 때: URL을 새 탭에서 열어 200·재생 확인 / 파일명 대소문자 / `?v=` 캐시 / 자동재생 정책(무음·playsinline 확인) / Pages 배포 완료 여부
- 이미지가 안 나올 때: 포스터 URL 200·Content-Type image/png 확인 / 경로·확장자 일치
- Pages 배포 확인: 저장소 Settings → Pages 상태, 기본 주소 200 응답 확인(배포 직후 수 분 지연 가능)

## 34~40. 주의사항
- HTML/CSS/JS는 **영상 원본 해상도를 높이지 않습니다.** 과도한 CSS 확대(크롭값↑)는 체감 화질을 낮출 수 있습니다.
- GitHub Pages는 전문 영상 CDN이 아닙니다. 파일·트래픽이 크게 늘면 별도 스토리지/CDN(R2, S3+CloudFront 등)을 검토하세요.
- 공개 URL에 `/public/`을 넣지 않습니다(레포 내부 폴더 구조와 무관한 Pages 경로 사용).
- Raw URL(raw.githubusercontent.com) 대신 GitHub **Pages** URL을 사용합니다(정확한 MIME·캐시·안정성).
- `prefers-reduced-motion: reduce` 환경에서는 전환/애니메이션을 제거하고 포스터를 안정적으로 표시합니다.
- 본 `index.html`은 리소스 확인용이며 `noindex`입니다(아임웹 상품페이지 SEO와 별개).
