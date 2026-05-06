# Showreel 업로드 가이드

> 포트폴리오 히어로 쇼릴 영상을 게시하는 3가지 방법. 자동 감지 우선순위: **mp4 → Vimeo → YouTube**.

---

## 방법 1 · 로컬 mp4 파일 (1순위 · 가장 간단)

```bash
# 쇼릴 영상 파일을 assets 디렉토리에 복사
cp ~/Movies/Showreel-2026-Final.mp4 \
   /Users/jaeyongchoi/Desktop/main/projects/personal/choi/assets/showreel.mp4

# 포스터(썸네일) 이미지도 함께 (선택사항이지만 권장)
cp ~/Pictures/showreel-poster.jpg \
   /Users/jaeyongchoi/Desktop/main/projects/personal/choi/assets/showreel-poster.jpg
```

**권장 인코딩**:
- 코덱: H.264 (mp4)
- 해상도: 1920×1080 (16:9)
- 비트레이트: 8~12 Mbps
- 길이: 60~180초 (2분 48초가 표준)
- 파일 크기: <100MB (배포 시 Vercel 무료 티어 100MB 제한)

**ffmpeg 한 줄 변환** (참고):
```bash
ffmpeg -i input.mov -vcodec libx264 -crf 23 -preset slow -acodec aac -b:a 192k \
       -movflags +faststart assets/showreel.mp4
```
> `-movflags +faststart` = 웹 스트리밍 최적화 (메타데이터 앞으로)

---

## 방법 2 · Vimeo 임베드 (DP 표준 · 2순위 권장)

비공개·비밀번호 보호·커스텀 플레이어 가능. DP 업계 표준.

1. Vimeo에 영상 업로드 → URL 확인 (예: `https://vimeo.com/123456789`)
2. 숫자 ID만 추출 (`123456789`)
3. `index.html` 수정:

```html
<div class="showreel__hero"
     data-mp4=""              <!-- 비워두면 mp4 건너뜀 -->
     data-vimeo="123456789"   <!-- ← Vimeo ID -->
     data-youtube="">
```

비밀번호 보호 영상도 가능 (Vimeo 설정에서 도메인 화이트리스트).

---

## 방법 3 · YouTube 임베드 (3순위 · 무료 호스팅)

```html
<div class="showreel__hero"
     data-mp4=""
     data-vimeo=""
     data-youtube="dQw4w9WgXcQ">  <!-- YouTube watch?v= 뒤 ID -->
```

---

## 자동 감지 동작

페이지 로드 시 JS가 순서대로 확인:
1. `data-mp4` 경로에 HEAD 요청 → 200 OK면 mp4 모드
2. `data-vimeo` 값 있으면 Vimeo 모드
3. `data-youtube` 값 있으면 YouTube 모드
4. 셋 다 없으면 placeholder 유지 + 캡션 "Showreel — 업로드 대기"

클릭 시 해당 플레이어가 히어로 영역에 임베드되어 자동 재생.

---

## 포스터 이미지 (선택·강력 권장)

mp4·placeholder 모드일 때 배경 이미지로 표시.

- 권장 해상도: 1920×1080
- 포맷: JPG 품질 85% 또는 WebP
- 파일명: `assets/showreel-poster.jpg`
- 자동 감지 (HEAD 요청)

ffmpeg로 영상에서 한 프레임 추출:
```bash
ffmpeg -i assets/showreel.mp4 -ss 00:00:08 -vframes 1 -q:v 2 assets/showreel-poster.jpg
```

---

## 검증

```bash
cd /Users/jaeyongchoi/Desktop/main/projects/personal/choi
python3 -m http.server 8765
# 브라우저: http://localhost:8765/#showreel
```

캡션이 "**▶ Showreel 2026 · Click to Play**" 로 표시되면 자동 감지 성공.
