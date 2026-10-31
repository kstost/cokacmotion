# aimotion 데모 목록

데모 125편. 원칙: 표현 기법과 기술적 내용만 참고한다. 데모의 9:16(1080×1920) 형식·길이·구도·배치·자막·문구·색은 가져가지 않고, 작업 중인 영상과 그 스킬의 형식을 따른다.

편마다 폴더는 `demos/<id>/`이다: NOTES.md(데모 장면, 기법과 원리와 `main.js:줄`, 결정성 전략, 한계), 소스, `out/poster.jpg`(절정 한 장), `out/sheet.jpg`(1초마다 한 장).
모든 데모가 부르는 공통 코드는 `demos/_lib/`에 있다.

## 웹 그래픽 기법 (01–17)

SVG 필터, 셰이더, GPU 시뮬레이션, three.js — 웹 그래픽의 기본기

- **01-svg-ink 먹 한 방울** — SVG 필터 · feTurbulence + feDisplacementMap
  - 데모 장면: 한지(섬유결이 비치는 아이보리 종이, 아래쪽은 찢긴 가장자리 너머 검은 펠트) 위로 먹 한 방울이 카메라 쪽에서 떨어진다.
  - 배울 점: 먹 레이어 하나 = 필터 두 단계 · setup — 번진 먹을 굽는다 · 젖은 먹 · frame — 싼 필터 하나 · 농담(水墨) · 먹방울과 튐
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **02-css-popup 펼쳐지는 종이 마을** — CSS 3D 변형 · perspective + preserve-3d
  - 데모 장면: 어두운 호두나무 책상 위에서 금박 테두리와 「종이 마을 · 펼쳐 보세요」 글씨가 찍힌 천 장정 팝업북이 어둠 속에서 떠오른다(0–0.45 s).
  - 배울 점: 카메라 = perspective + 회전된 world · 접힘선에 놓인 transform-origin = 경첩 · 카드 = 인쇄된 종이 · 카드의 인쇄는 setup 이후 절대 바뀌지 않는다 · 면마다의 조명 · 빛나는 것들
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, style.css, index.html, out/poster.jpg, out/sheet.jpg

- **03-coral-growth 자라는 산호** — Canvas 2D 절차적 생성 · Space Colonization
  - 데모 장면: 햇빛이 비스듬히 내려오는 얕은 바다. 수면 아래에서 본 물결 무늬가 화면 위쪽에서 일렁이고, 모래 바닥에는 커스틱(물결이 모은 빛) 그물이 천천히 흐른다.
  - 배울 점: Space colonization · 크라운 모양 · 구워 두고 t로 읽기 · 파이프 모델 두께 · 그리기 · 살아 있는 느낌
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **04-sketch-diagram 손으로 그린 설명** — rough.js + perfect-freehand · 손그림 렌더링
  - 데모 장면: 스탠드 빛이 비치는 스케치북 한 장(종이 결, 옅은 점 격자, 아래는 책상).
  - 배울 점: 획(stroke)이 단위다 · 하나의 펜 시간표 · 수채 번짐 · 프레임 렌더
  - 라이브러리: rough.js, perfect-freehand
  - 영상: rough.js, perfect-freehand: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **05-fbm-nebula 흐르는 성운** — WebGL2 프래그먼트 셰이더 · 도메인 워핑 fBm
  - 데모 장면: 검은 별밭 가운데에서 보라·청록·주황 가스가 바깥으로 번지며 피어나고(0–3.6초), 가스가 천천히 휘감기며 흐르는 동안 카메라가 다가간다.
  - 배울 점: fBm · 도메인 워핑 · 부드러운 발광층 · 색 · 별 · 점화
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **06-aurora-raymarch 오로라, 빛의 커튼** — WebGL2 볼류메트릭 레이마칭
  - 데모 장면: 북쪽을 바라보는 호숫가의 밤(9초). 검은 화면에서 별과 산, 가문비나무 실루엣이 떠오르고, 왼쪽 지평선 너머에서 시작한 초록 커튼이 오른쪽 위 하늘 꼭대기까지 대각선으로 걸쳐 있다.
  - 배울 점: 커튼 = 수평면 위의 리본 + 수직 면 · 패스 0 — 거리장 굽기 · 패스 1 — 볼륨 레이마칭 · 구간별 해석 적분 · 립시츠 검사 · 고도별 발광
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **07-sdf-planet 고리를 두른 행성** — SDF 레이마칭 · 셰이더 하나로 만든 3D
  - 데모 장면: 고리 평면 바로 아래(−2.6°)에서 거의 옆으로 본 행성으로 시작한다. 햇빛을 받은 고리가 가는 빛줄로 행성 앞을 가로지르고, 그 고리의 그림자가 북반구에 굵은 띠로 드리운다.
  - 배울 점: SDF 장면과 구 추적(sphere tracing) · 고리 = 평면 + 1D 광학 깊이 프로파일 · 고리의 빛 = 얇은 판의 단일 산란 · 그림자 두 방향 · 행성 표면 · 카메라와 태양의 연출
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **08-caustics 수영장 바닥의 빛** — WebGL2 셰이더 · 굴절 코스틱
  - 데모 장면: 맑은 날 수영장을 비스듬히 내려다본다(카메라가 천천히 내려앉는다). 어둠에서 떠오른 화면에 햇빛이 차오르며 12.5 cm 타일 바닥 위로 빛의 그물(코스틱)이 춤추기 시작하고, 진한 파란 레인 라인과 끝의 T자, 타일 줄눈이 물결에 따라 일렁여 보인다.
  - 배울 점: 해석적 수면 · 패스 1 — 코스틱 스플랫 · 잎 그림자 · 패스 2 — 장면 · 패스 3 — 마무리
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **09-gpu-galaxy 20만 개의 별** — WebGL2 포인트 스프라이트 · 버텍스 셰이더 궤도
  - 데모 장면: 어둠 속에서 나선은하가 떠오른다. 세로 화면에 맞춰 장축을 비스듬히 세운 사진 같은 정면 구도: 금빛 중심부, 푸른 바깥 팔, 오목한 안쪽 가장자리를 따라 가는 갈색 먼지띠, 팔을 따라 박힌 분홍 HII 매듭이 보인다(0–2 s).
  - 배울 점: 별 21만 개 = 점 스프라이트 한 번의 drawArrays(POINTS) · 플럭스 보존 스프라이트 · 먼지와 HII · 풀린 별빛(diffuse) · 카메라 · HDR 파이프라인
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **10-curl-flow 보이지 않는 바람** — GPU 파티클 · 컬 노이즈 + 핑퐁 텍스처
  - 데모 장면: 깊은 남색 어둠에서 시작한다. 0–2.2 s에 빛나는 연기선이 아래에서부터 차오르며 보이지 않던 상승기류가 드러난다.
  - 배울 점: 상태 = 텍스처 두 장 · 이류(fragment shader, main.js:66) · 보이지 않는 구 · 흔적 · 연기 와이어(dye) · 색과 깊이
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 영상: CPU 검증 프레임당 5.8s — 그대로 옮기면 MP4 내보내기가 매우 느리다. 해상도를 낮추거나 미리 굽는다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **11-reaction-diffusion 스스로 그리는 무늬** — GPGPU 반응-확산 · Gray–Scott
  - 데모 장면: 어두운 청록 바닥 위, 0초에 씨앗 하나가 희미하게 빛난다. 카메라는 2.3배로 다가가 있고, 씨앗이 호박색 구슬로 부풀었다가 스스로 둘로 갈라지며(유사분열) 고리 모양 군락을 이룬다.
  - 배울 점: 상태 = RGBA32F 텍스처 하나 · Gray–Scott 한 스텝 · 공간·시간에 따라 변하는 feed/kill · 씨앗 · 표면 렌더 · 최종 셰이더
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 영상: CPU 검증 프레임당 10.2s — 그대로 옮기면 MP4 내보내기가 매우 느리다. 해상도를 낮추거나 미리 굽는다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **12-stable-fluids 물속에 퍼지는 잉크** — GPU 유체 시뮬레이션 · Stable Fluids
  - 데모 장면: 수면에서 비스듬히 내려오는 빛줄기가 깊은 남청색 물속을 비추고, 맨 위에는 커스틱이 일렁이며 부유 입자가 떠다닌다.
  - 배울 점: 격자 · 서브스텝 순서 · 야코비 압력 30회 · 잉크 이류: MacCormack · 노즐 스크립트 · 빛
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 영상: CPU 검증 프레임당 3.2s — 그대로 옮기면 MP4 내보내기가 매우 느리다. 해상도를 낮추거나 미리 굽는다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **13-glass-jellyfish 유리 해파리** — three.js 물리 기반 재질 · 투과 + 블룸 후처리
  - 데모 장면: 완전한 어둠에서 시작해 수면 쪽 빛줄기(god rays)와 함께 유리 같은 해파리가 화면 아래쪽에서 떠오른다.
  - 배울 점: 유리 갓 = 닫힌 두께 껍질 + MeshPhysicalMaterial · 투과(refraction) 버퍼 활용 · 안에서 켜지는 빛 · 촉수·구완 = 시간 지연(follow-the-leader) 닫힌 식 · 배경 · 플랑크톤
  - 라이브러리: three.js
  - 영상: three.js — 영상 스킬이 three.js를 넣는 방법을 따른다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **14-instanced-coral 피어나는 산호초** — three.js 인스턴싱 · 수천 개의 폴립
  - 데모 장면: 검정에서 밝아지며 낮은 시점의 산호초가 보인다. 폴립이 모두 움츠러든 산호 머리(장미·보라·민트 빛 돔 6개)와 주황 가지산호, 물결무늬 모래 위에서 일렁이는 커스틱 빛, 위쪽에서 들어오는 은빛 물고기 떼.
  - 배울 점: 폴립 = 파라미터만 가진 인스턴스 지오메트리 · 배치 = 피보나치 점 + 법선 정렬 · 개화 파동 = 인스턴스마다 숫자 하나 · 보이지 않는 폴립은 아예 만들지 않음 · 모래와 커스틱 · 물고기 떼
  - 라이브러리: three.js
  - 영상: three.js — 영상 스킬이 three.js를 넣는 방법을 따른다
  - 영상: CPU 검증 프레임당 1.2s — 그대로 옮기면 MP4 내보내기가 매우 느리다. 해상도를 낮추거나 미리 굽는다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **15-geo-globe 지구 위를 나는 길** — d3-geo · 실제 해안선 + 정사영
  - 데모 장면: 0–2.6 s 등장 — 어두운 지구가 빠르게 돌며 들어온다. 그동안 태양이 서쪽에서 들어와(새벽) 유럽·아프리카·인도가 밝아지고, 동아시아는 밤으로 남아 도시 불빛이 켜져 있다.
  - 배울 점: d3-geo 파이프라인 하나 · 육지 (main.js:386–399) · 낮과 밤의 경계 (main.js:401–419) · 빛 (main.js:421–461) · 도시 불빛 (main.js:131–205, 463–510) · 항로 (main.js:207–221, 538–630)
  - 라이브러리: d3, world-atlas
  - 영상: d3: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 영상: 실제 지도 데이터(world-atlas) — 영상에서는 직접 그린 양식화된 지도로 바꾼다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **16-rapier-marbles 쏟아지는 구슬** — Rapier2D (WebAssembly) 물리 · 미리 굽기
  - 데모 장면: 0–0.7 s 등장 — 어두운 데서 호두나무 틀, 참나무 판, 황동 깔때기와 핀 삼각형, 유리 반사가 드러난다.
  - 배울 점: 물리는 실제 단위로 (sim.js) · 2D에 없는 물리: 뒷판 마찰 (sim.js:113–124) · 기하 (sim.js:15–56) · 미리 굽기 (sim.js:62–145, main.js:37–38) · 그리기 (main.js)
  - 라이브러리: Rapier2D
  - 영상: Rapier2D: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, sim.js, index.html, out/poster.jpg, out/sheet.jpg

- **17-hangul-particles 글자가 된 별** — WebGL2 포인트 스프라이트 · 텍스트 샘플링
  - 데모 장면: 어둠 속에서 은청색 나선은하가 떠오른다. 팔이 둘이고, 안쪽이 바깥보다 빨리 도는 차등 회전을 한다. 1.2 s부터 별들이 안쪽부터 차례로 은하를 떠나 소용돌이치며 모인다.
  - 배울 점: 텍스트 샘플링 · 대응 짓기 · 위치 = t의 닫힌 함수 · 소프트 원형 스프라이트 · 닫힌 형태의 셔터 → 빛 꼬리 · HDR 블룸
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

## 아날로그 표현 (18–27)

수채화·유화·판화·리소·필름·목탄 — 재료의 질감을 코드로

- **18-watercolor 번지는 수채화** — WebGL2 GPGPU · 물과 안료 시뮬레이션 (Curtis 1997 방식)
  - 데모 장면: 어두운 화판 위에 황목(cold-press) 수채화지가 마스킹 테이프로 붙어 있다. 종이는 둥근 돌기와 섬유가 보이는 높이장이다.
  - 배울 점: 종이 · 얕은 물 층 · 접촉선 고정 · 물 갱신 + 안료 + 모세관 + 붓 · 블룸·백런 · 그림
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **19-impasto 두껍게 바른 유화** — WebGL2 · 붓질 기반 렌더링 + 높이맵 조명
  - 데모 장면: 번트 시에나로 초벌한 리넨 캔버스가 갤러리 조명 아래 놓여 있다. 씨실과 날실이 엇갈리는 결이 보인다. 화면은 소용돌이 근처에 살짝 다가가 있다가 3.6초까지 물러난다.
  - 배울 점: 절차적 장면 · 곡선 붓질 생성 · 한 번의 인스턴스 드로 · 획 정점 셰이더 · 획 조각 셰이더 · 누적(MRT)
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **20-woodcut 목판화 한 장** — 절차적 판각 + WebGL2 잉크 인쇄 셰이더
  - 데모 장면: 어두운 작업대에 벚나무 판목 하나가 놓여 있다. 판목에는 밑그림(한시타)이 붙어 있고, 카메라는 큰 파도의 물마루에 바짝 다가가 있다.
  - 배울 점: 모양 마스크 · 정확한 거리 변환 · 톤 = 선 굵기 · 외곽선, 거품, 손톱 · 깊이 · 판각 순서
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, design.js, shader.js, index.html, out/poster.jpg

- **21-risograph 리소그래프 두 도** — WebGL2 · 별색 망점 분판 + 판 어긋남 + 곱하기 겹쳐 찍기
  - 데모 장면: 리소그래프의 배지 트레이를 위에서 내려다본다. 화면 위쪽은 기계 몸체이고, 그 창으로 형광 분홍 드럼이 보인다.
  - 배울 점: 분판 · AM 망점 · 고르지 않은 잉크막 · 겹쳐 찍기 · 판 어긋남 · 세트오프(롤러 자국)
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, sep.js, shader.js, index.html, out/poster.jpg

- **22-super8 여름날의 8mm 필름** — WebGL2 후처리 · 영사기 게이트 흔들림·깜빡임·먼지·할레이션
  - 데모 장면: 어두운 방에서 영사기 램프가 켜진다(필라멘트가 주황에서 흰색으로 데워짐). 처음 0.5초는 긁히고 누렇게 바랜 투명 리더가 지나가고, 스플라이스가 게이트를 넘어가며 화면이 한 번 툭 튄다.
  - 배울 점: 장면: 선형 복사휘도 HDR · 할레이션 피라미드 · 필름과 영사기 · 노출 · 리버설 특성곡선 · 그레인 = 염료 구름
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, film.js, scene.js, index.html, out/poster.jpg

- **23-vhs 1997년 비디오테이프** — WebGL2 후처리 · YIQ 색 번짐·트래킹 노이즈·브라운관
  - 데모 장면: 화면 가득 다가선 브라운관 TV다. 위아래로 휜 유리 가장자리와 검은 플라스틱 베젤이 보이고, 아래 베젤에는 스피커 슬롯과 초록 전원 LED가 있다.
  - 배울 점: 캠코더 · 녹화 · 재생 · 빛 피라미드 · CRT · 주사선 240줄
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, scene.js, vhs.js, index.html, out/poster.jpg

- **24-paper-stopmotion 종이 인형 극장** — Canvas 2D · 12fps 스톱모션 + 손으로 오린 종이
  - 데모 장면: 남색 판지 무대 위의 밤바다, 9.5초. 처음에는 조명이 꺼져 있다가 0.8초 동안 켜진다. 오린 파도 네 줄(뒤일수록 흐린 청회색, 앞일수록 짙은 남색, 앞쪽 세 줄은 마루마다 크림색 거품 조각을 덧붙임)이 손으로 앞뒤로 밀리며 출렁이고, 붉은 돛배가 파도 사이에서 까딱이며 오른쪽으로 간다.
  - 배울 점: 종이를 오리는 과정 · 잘린 단면의 흰 심 · 종이 결 · 그림자는 높이에서 · 다면 무대(multiplane) · 스톱모션 시간
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **25-charcoal 목탄 스케치** — WebGL2 · 종이 결에 걸리는 목탄 + 문지름·지우개
  - 데모 장면: 제도판에 붙은 앵그르지 한 장(가로 줄무늬 결이 보이는 크림색 종이, 왼쪽 위에서 비스듬히 비추는 조명), 10초.
  - 배울 점: 종이 이(tooth) 높이장 · 목탄 침착 · 옆으로 눕힌 막대 · 찰필·티슈 문지름 · 떡지우개 · 표시
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **26-engraving 동판에 새긴 달** — WebGL2 셰이더 · 명암을 선의 굵기로 (판화 해칭)
  - 데모 장면: 등불 아래 호두나무 작업대에 광택 나는 동판이 놓여 있다(0–0.6초 밝아짐). 판 위로 창빛 반사가 천천히 흐른다.
  - 배울 점: 달은 그림이 아니라 "어둡기 D"를 계산하는 함수 · 테의 그림자 · 판화가의 말로 옮기기: 선 가족 세 개 · 선 하나의 모양 · 안티에일리어싱 = 정확한 박스 필터 · 하늘·테두리·글자
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, shader.js, index.html, out/poster.jpg

- **27-marbling 물 위의 마블링** — 수학적 마블링 · 잉크 방울과 빗질의 닫힌식 변형 (Jaffer·Lu)
  - 데모 장면: 우윳빛 사이즈(수조 물) 위로 창빛이 비친다. 맨 아래에는 수조의 호두나무 테두리(자막 자리).
  - 배울 점: 잉크 막 = 다각형, 동작 = 평면의 닫힌식 사상 · 적응 세분 · 움직이는 송곳 · 체크포인트 · 그리기 · 종이
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, ops.js, index.html, out/poster.jpg

## 웹 플랫폼 기술 (28–32)

WebGPU, Web Audio, 가변 폰트, 역기구학, 데이터 전환

- **28-webgpu-particles 백만 개의 입자** — WebGPU 컴퓨트 셰이더 · 입자 100만 개 중력 시뮬레이션
  - 데모 장면: 별이 깔린 어둠 속에서 원반은하 두 개가 화면 위아래에 떠오른다(0–0.9 s). 위쪽 은하는 궤도면에 거의 누워 있고 아래쪽 은하는 58° 기울어져 있다.
  - 배울 점: 입자 1,048,576개 · 은하 핵의 궤도는 JS에서 적분 · 스텝마다 쓰는 값은 setup에서 미리 한 번에 쓴다 · 동적 오프셋 uniform · 입자 스텝 = 비디오 1프레임당 3회의 drift–kick–drift · 입자–메시(PM) 자기중력
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: WebGPU — 영상 내보내기(헤드리스)에는 쓰지 않는다. 원리만 참고
  - 파일: NOTES.md, main.js, camera.js, model.js, index.html, out/poster.jpg

- **29-audio-sync 소리가 그리는 빛** — Web Audio · OfflineAudioContext 합성 + FFT 분석 동기화
  - 데모 장면: 9.6초짜리 짧은 곡(D장조 5음 음계)에 맞춰 밤하늘 같은 어둠 한가운데에서 빛의 꽃이 핀다.
  - 배울 점: 합성(synth.js, OfflineAudioContext 48 kHz 스테레오) · 컨볼루션 리버브 · 분석(analysis.js, 순수 JS, 우리가 짠 FFT) · 밴드 레벨 · 온셋 · 온셋마다 새로 생긴 음높이
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 영상: 소리 — 소리를 쓸지는 영상 스킬의 규칙을 따른다. 소리에 그림을 맞추는 방식을 참고한다
  - 파일: NOTES.md, main.js, analysis.js, score.js, synth.js, index.html, out/poster.jpg

- **30-kinetic-type 움직이는 글자** — 가변 폰트 · font-variation-settings 굵기 축 + 글자 단위 모션
  - 데모 장면: 깊은 남색 화면에서 내레이션 "작은 소리가 / 큰 울림이 된다"가 음절 단위로 말해지듯 움직인다.
  - 배울 점: 가변 폰트 · 우리가 직접 하는 조판 · 음절의 모습 = 신호들의 합 · 메아리 · 드러냄표 · 아래 캔버스
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **31-ik-character 손을 뻗는 아이** — 2D 뼈대 · FABRIK 역기구학 + 스키닝
  - 데모 장면: 어둠 속에서 뼈대(뼈 34개)와 삼각형 메시 선이 먼저 걷는다. 배경(해 질 녘 하늘, 산, 언덕)이 밝아진다.
  - 배울 점: 뼈대와 스키닝 (rig.js, main.js:376–510) · 종이 조각 메시 (rig.js:213–290) · 걷기와 발 IK (main.js:44–120, 186–210) · FABRIK + 관절 제한 (rig.js:79–109, main.js:211–242) · 시선과 표정 (main.js:247–263) · 2차 운동 (rig.js:129–187, main.js:655–669)
  - 라이브러리: d3
  - 영상: d3: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, rig.js, index.html, out/poster.jpg

- **32-dataviz-motion 숫자가 움직일 때** — d3 · 데이터 전환 애니메이션 (막대 순위 → 산키 → 지도)
  - 데모 장면: 설명형(익스플레이너) 데이터 영상이다. 아시아 8개 컨테이너 항만의 물동량을 세 가지 그림으로 보여 준다. 세 장면 내내 같은 물체 8개가 같은 색을 유지한 채 모양만 바꾼다.
  - 배울 점: 데이터와 곡선 (layout.js) · 막대 순위 경주 · 부드러운 순위 · 축 재조정 · 숫자 · 연도 주행 거리계
  - 라이브러리: d3, world-atlas
  - 영상: d3: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 영상: 실제 지도 데이터(world-atlas) — 영상에서는 직접 그린 양식화된 지도로 바꾼다
  - 파일: NOTES.md, main.js, layout.js, index.html, out/poster.jpg

## 자연 현상 · 광학 · 수학 (33–41)

바다·구름·침식·천·군집, 빛의 간섭과 분산, 프랙털 딥 줌

- **33-ocean 노을 진 바다** — WebGL2 · FFT 해양 파도 (Tessendorf) + 대기 산란
  - 데모 장면: 수면 3.6 m 높이에서 해를 마주 본다. 시작할 때 해는 수평선 위 2.2°에 있고, 바다는 잔물결에 낮은 너울이 겹친 잔잔한 상태다.
  - 배울 점: 스펙트럼 · 시간 발전 · 유도 스펙트럼 · 역FFT · 캐스케이드 · 풀기
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **34-clouds 빛이 지나는 구름** — WebGL2 볼류메트릭 레이마칭 · 다중 산란 근사 + 빛내림
  - 데모 장면: 150 m 언덕에서 계곡 너머 해(고도 25°)를 올려다본다. 화면 위쪽에는 높이 5 km에 가까운 적란운 직전의 큰 적운(congestus)이 서 있고, 둘레에 작은 적운들이 흩어져 있다.
  - 배울 점: 노이즈 굽기 · 밀도 · 날씨 맵 · 구름 레이마칭 · 자기 그림자 · Beer–Lambert와 다중 산란 옥타브
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **35-erosion 빗물이 깎은 산** — GPGPU 수력 침식 · 파이프 모델 + 퇴적
  - 데모 장면: 0–1 s 등장 — 검은 화면에서 아침 햇빛을 받은 산괴가 드러난다. 능선이 날카로운 산이고, 위쪽에는 눈이 있고 아래쪽 완만한 비탈에는 숲이 있다.
  - 배울 점: 상태: 512×512 격자, RGBA32F 텍스처 세 장 · 지형 생성 · 반복 1회 = 전체 격자 패스 3개 · FLUX · WATER · MOVE
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, terrain.js, index.html, out/poster.jpg

- **36-cloth 바람에 날리는 비단** — XPBD 천 시뮬레이션 · 위치 기반 동역학 미리 굽기
  - 데모 장면: 0–1.5 s 등장 — 어두운 스튜디오다. 진홍 비단 한 폭(1.0×1.5 m)이 두 개의 황동 핀에 가는 줄로 매달려 있다.
  - 배울 점: 시뮬레이션 (sim.js, setup에서 한 번) · 입자와 시간 간격 · 제약 · Long-range attachment · 공기력 · 바람
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, sim.js, index.html, out/poster.jpg

- **37-fracture 깨지는 유리** — 보로노이 파괴 + Rapier2D 물리 미리 굽기
  - 데모 장면: 어두운 방에서 화면이 밝아진다. 나무 창틀 너머로 초점이 나간 밤의 도시(창문 불빛과 가로등이 보케로 번진 모습)가 보인다.
  - 배울 점: 충돌점 중심 보로노이 (fracture.js) · 유한한 균열 속도 (fracture.js:153–219, main.js:291) · 시간 재매핑 (main.js:42) · 조각의 운명과 Rapier2D 굽기 (sim.js) · 유리 렌더링 (WebGL2, main.js:214–460, 796–)
  - 라이브러리: d3, Rapier2D
  - 영상: d3, Rapier2D: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, fracture.js, sim.js, index.html, out/poster.jpg

- **38-murmuration 찌르레기 군무** — 보이드 알고리즘 · 수천 마리 군집 미리 굽기
  - 데모 장면: 0–2.3 s 등장 — 해가 막 진 뒤의 하늘이다. 왼쪽 지평선은 주황으로 타고, 위로 갈수록 라벤더를 지나 짙은 남색이 된다.
  - 배울 점: 시뮬레이션 (sim.js, setup에서 굽기) · 위상적 이웃 · 힘 · 정보를 가진 소수 · 매 · 경보 파동
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, sim.js, index.html, out/poster.jpg

- **39-thin-film 비눗방울 무지개** — 스펙트럼 박막 간섭 · 두께장 흐름
  - 데모 장면: 어두운 정원(흐린 보케 불빛) 아래쪽에서 갓 불어 낸 비눗방울이 떠오르며 출렁인다(0–2.7초). 막이 아직 두꺼워서 (≈1.5 µm) 거의 투명한 은빛에 분홍·초록이 옅게 비치고, 꼭대기에만 작은 무지개 고리가 있다.
  - 배울 점: 스펙트럼 박막 반사율 · CIE 1931 → sRGB를 가중치로 접기 · 두께장 h(s, t) · 방울 모양과 두 벽 · 터짐
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **40-prism 빛을 나누는 프리즘** — 스펙트럼 광선 추적 · 파장별 굴절 (분산)
  - 데모 장면: 어두운 방, 바닥은 옅은 돌(스크린 역할), 뒤는 어두운 벽. 공기에는 먼지가 떠다닌다. 0.3초부터 위쪽 틈(슬릿)으로 들어온 흰 빛의 띠가 일정한 속도로 내려와(빛의 앞머리가 진행) 1초쯤 유리 프리즘(SF11 고밀도 플린트, 꼭지각 55°, 꼭짓점이 오른쪽)에 닿는다.
  - 배울 점: 파장별 굴절률 — Sellmeier · 스펙트럼 광선 추적 · 두 번째 프리즘 · 광선 → 빛 띠 텍스처 · 방 렌더링 = 단일 산란 · 색 변환
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **41-deep-zoom 끝없는 맨델브로트** — 섭동 이론 딥 줌 · 고정밀 기준 궤도 + GPU 델타
  - 데모 장면: 똑바로 선(가시가 위, 심장형이 아래) 맨델브로트 집합 전체로 시작해 0.3초 머문 뒤 가속하여, 시호스 밸리로 초당 약 2.1자릿수(×130)의 일정한 속도로 파고든다.
  - 배울 점: 고정밀 기준점 — BigInt 고정소수점 · 미니브로트의 크기와 방향 · 섭동 반복 (GPU, float32) · 글리치 방지 — Zhuoran 재기준(rebasing) · BLA(쌍선형 근사)로 반복 건너뛰기 · 내부 판정
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

## 아날로그 표현 2 (42–50)

붓글씨·암실·폴라로이드·스테인드글라스·활판·자수·네온

- **42-calligraphy 붓으로 쓴 한 글자** — 붓 물리 모델 · 먹 머금음·필압·비백 + 화선지 번짐
  - 데모 장면: 검은 모포 위에 화선지 한 장이 깔려 있다. 가장자리는 손으로 뜬 종이처럼 들쭉날쭉하고 섬유가 삐져나와 있다.
  - 배울 점: 획 스켈레톤 · 눌린 붓털의 발자국 · 96가닥의 털 · 먹 머금음 · 캡슐 굽기 · 닥 섬유
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, brush.js, index.html, out/poster.jpg

- **43-darkroom 암실에서 떠오르는 사진** — WebGL2 · 현상 반응 (잠상 → 은 입자) + 안전등
  - 데모 장면: 붉은 안전등만 켜진 암실을 위에서 내려다본다. 스테인리스 싱크 위에 현상액·정지액·정착액 트레이 세 개가 나란히 놓여 있다.
  - 배울 점: 골목 장면 · 젖은 자갈 · 네거티브와 인화지 곡선 · 브로마이드 드래그 · 현상 시계 · 젖은 시각
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **44-polaroid 폴라로이드가 떠오르기까지** — WebGL2 · 즉석 필름 시약 확산 + 색 현상 단계
  - 데모 장면: 여름 바닷가의 밝은 빛 속에서, 민트색 즉석카메라가 초점이 흐린 바다·하늘·모래를 배경으로 화면 위쪽을 채운다.
  - 배울 점: 여름 장면 · 같은 함수를 두 번 굽는다 · 퍼짐 시각 · 시약 두께 · 불투명제 · 세 염료층의 속도
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **45-stained-glass 빛이 머무는 유리창** — WebGL2 · 색유리 투과광 + 납선 + 바닥에 맺힌 빛
  - 데모 장면: 어두운 석조 예배당의 끝벽에 지름 6.8m의 장미창이 있다. 카메라는 창 아래 바닥 가까이에 서서 창을 올려다보다가 천천히 물러나며 바닥 쪽으로 고개를 숙인다.
  - 배울 점: 돌 창살과 영역 · 유리 조각 = 보로노이 셀 ∩ 영역 · 납 띠(came) · 돌 · 그리자이유(유리 위에 구운 갈색 안료) · 텍스처 2장
  - 라이브러리: d3
  - 영상: d3: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, design.js, gl.js, shaders.js, index.html, out/poster.jpg

- **46-letterpress 꾹 눌러 찍은 활판** — 높이맵 활자 + 잉크 압착 셰이더 · 활판 인쇄
  - 데모 장면: 작은 클램셸(조개형) 활판 인쇄기를 위에서 내려다본다. 화면 위쪽 절반은 판(chase)에 짜 넣은 납 활자, 아래쪽 절반은 경첩으로 이어진 압반(platen)이다.
  - 배울 점: 활자 = 몸통 + 수염 + 면 · 수염(beard) · 판 짜기 · 텍스처 · 면 섬유 · 먼지 자국(hickey)
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, forme.js, gl.js, shader.js, index.html, out/poster.jpg

- **47-embroidery 한 땀 한 땀 수놓은 꽃** — 절차적 자수 · 땀 경로 + 실 광택 셰이더
  - 데모 장면: 자작나무 수틀(위쪽에 놋쇠 나사 조임쇠)에 팽팽히 끼운 천연 리넨, 수틀 밖 천은 방사형 주름으로 처져 있고 아래쪽 천 위에 잘라 둔 분홍·초록·금색 실 토막이 놓여 있다.
  - 배울 점: 땀 생성 (stitches.js) · 작업 순서와 속도 · 그리기 3패스 · 바늘과 작업 실
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, shaders.js, stitches.js, index.html, out/poster.jpg

- **48-scratch-art 긁어서 드러나는 무지개** — WebGL2 · 스크래치 페이퍼 (긁기 마스크 + 왁스 부스러기)
  - 데모 장면: 짙은 호두나무 탁자 위의 스크래치 보드(검은 왁스 코팅, 아래에 무지개 인쇄 카드). 왼쪽 위 등불에 왁스가 은은히 빛난다.
  - 배울 점: 획 설계 · 손의 시계 τ · 긁기 마스크 · 보드 합성 · 부스러기 · 붓 타격 시각
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, art.js, shaders.js, index.html, out/poster.jpg

- **49-zoetrope 돌아가는 조이트로프** — 회전 원통 + 틈새 스트로보 · 실제 원리로 만든 움직임
  - 데모 장면: 어두운 방, 왼쪽 위 텅스텐 등불 아래 참나무 탁자 위의 조이트로프: 깎은 호두나무 받침과 놋쇠 축, 호두나무 몸통, 검은 옻칠 띠에 금선과 마름모 장식, 위아래 놋쇠 테, 열두 개의 세로 틈새.
  - 배울 점: 움직임은 그림을 바꿔서가 아니라 기하에서 나온다 · 장면 = 해석적 광선 추적 · 등빛과 그림자 · 셔터 적분 · 왜 2.5회/초에 말이 달리나 · 종이 띠
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, shader.js, strip.js, index.html, out/poster.jpg

- **50-neon 밤거리의 네온사인** — WebGL2 · 유리관 기체 방전 발광 + 벽 반사광
  - 데모 장면: 비 내린 밤, 붉은 벽돌 벽에 커피집 네온사인이 걸려 있다. 카메라는 젖은 보도 바로 위 낮은 곳(0.36m)에서 벽을 올려다본다.
  - 배울 점: 한 줄 관 중심선 · 기체·코팅 · 선광원 반사광 · 벽 지도 · 바닥 지도 · 벽돌
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, gl.js, shaders.js, sign.js, index.html, out/poster.jpg

## 모션 타이포그래피 (51–66)

글자를 거리장·타일·종이·물리·불·빛으로 움직이기

- **51-topo-type 등고선 글자** — 부호 거리장 · 등치선 · 거리장 보간 모핑
  - 데모 장면: 어두운 탁자 위에 인쇄된 지형도 한 장이 놓여 있다. 종이에는 테두리 선(가는 선 + 굵은 선 + 그 사이 흑백 눈금 막대)과 격자 십자 표시가 찍혀 있다.
  - 배울 점: 글자 → 거리장 · 거리장 보간 모핑 · 등심선(바다) · 땅 · 손으로 측량한 선 · 인쇄
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, shader.js, index.html, out/poster.jpg

- **52-parametric-hangul 코드로 짠 한글** — 파라메트릭 글꼴 · 한글 모아쓰기 규칙 · 획 골격 오프셋
  - 데모 장면: 크림색 종이 위에서 바우하우스·스위스 팔레트(크림, 먹, 주홍)로 진행한다. 화면의 모든 글자는 폰트 파일 없이 코드(`face.js`)가 매 프레임 획 골격에서 만든 외곽선이다.
  - 배울 점: 낱자 = 획 골격 · 모아쓰기 · 외곽선 = 골격 오프셋 · 대비 = 타원 펜 · 모서리 · 획 끝
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, face.js, index.html, out/poster.jpg

- **53-swiss-grid 격자 위의 리듬** — 가변 폰트 폭 맞춤(wdth·wght·opsz·GRAD) · 모듈 그리드 조판
  - 데모 장면: 120 bpm(한 박 0.5 s). 국제 타이포그래피 양식(스위스 스타일)의 움직이는 포스터다. 오프화이트 바탕에 검정, 빨강 하나만 쓴다.
  - 배울 점: 폭 표 굽기 · 잉크 기준 맞춤 · 표 뒤집기 · 안무 · 그리드와 리듬 장치 · 한글
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **54-title-sequence 오려 낸 제목** — 컷아웃 그래픽 · 가위 자국 윤곽 · 2프레임 홀드(12fps) · 매치 컷
  - 데모 장면: 가상의 1959년 영화 「아홉 번째 계단」(THE NINTH STEP)의 오프닝 타이틀이다. 10초 동안 다섯 숏이 재즈처럼 끊어지며 이어진다.
  - 배울 점: 글자를 종이로 (trace.js) · 가위질 (paper.js:65 scissor) · 포즈 = 손으로 다시 놓기 · 종이의 질감과 두께 · 매치 컷 · 리듬
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, paper.js, trace.js, index.html, out/poster.jpg

- **55-truchet-type 타일로 짠 글자** — 다중 스케일 트루셰 타일 · 모서리 점유 기반 타일 선택
  - 데모 장면: 따뜻한 종이 위에 크기가 다른 정사각 타일(120·60·30·15px)이 화면 전체에 깔려 있다. 타일마다 반지름 s/2의 사분원 실이 대각 두 모서리를 감싼다(스미스 트루셰 타일).
  - 배울 점: 타일 어휘: 호로 하는 마칭 스퀘어(5비트) · 모서리 점유 → 쿼드트리 · 실(스미스 타일)과 90° 회전 · 도는 동안 바뀌는 잉크 · 물결 일정 · 렌더링 (WebGL2, 인스턴스 한 버퍼)
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, shaders.js, index.html, out/poster.jpg

- **56-ribbon-text 글자의 강** — SDF 글리프 아틀라스 · 회전 최소화 프레임 위 글자 배치 · 인스턴싱 · 피사계 심도
  - 데모 장면: 짙은 남색 어둠 속을 금빛 글자의 강 여덟 줄기가 3D 곡선을 따라 흐른다. 강마다 시 한 줄을 되풀이해 싣고 있다.
  - 배울 점: 배회 모양 · 합류 모양 · 곡선 · 회전 최소화 프레임 · 자세 · 빛
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, gl.js, river.js, shaders.js, index.html, out/poster.jpg

- **57-quilling-type 종이 띠로 세운 글자** — 글리프 윤곽 → 세운 종이 띠 · 말림이 풀리는 띠 · 부드러운 그림자
  - 데모 장면: 낮고 가까운 시점. 빛을 마주 보는 역광이고, 피사계 심도가 얕아 앞뒤 종이가 흐리다. "온"의 ㅗ 왼쪽 끝 모서리에 테라코타색 띠 뭉치(아르키메데스 코일)가 톡 튀어나온다.
  - 배울 점: 윤곽 → 띠 경로 · 띠 메시와 풀리는 코일 · 채움 무늬 · 빛과 그림자
  - 라이브러리: three.js, opentype.js
  - 영상: opentype.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 영상: three.js — 영상 스킬이 three.js를 넣는 방법을 따른다
  - 파일: NOTES.md, main.js, quill.js, index.html, out/poster.jpg

- **58-pixel-sort 정렬된 소란** — GPU 픽셀 정렬(비토닉 정렬망) · 밝기 구간 분할 정렬 · 색수차
  - 데모 장면: 해 질 녘 포스터 한 장이 9.6초 동안 녹았다가 되돌아온다. 배경은 남색에서 보라·자홍·산호·호박색으로 내려가는 하늘이고, 수평선에 반쯤 걸린 해와 부서진 반사광이 깔린 바다가 있다.
  - 배울 점: 포스터 (BASE, shaders.js:151) · 구간 시작점 (분할 정렬 트릭) · 키 (shaders.js:192) · 부등식 점검 · 비토닉 정렬망 (main.js:247–255) · 합성 (COMP, shaders.js:249)
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, shaders.js, index.html, out/poster.jpg

- **59-glyph-mosaic 글자로 빚은 등대** — 9단 굵기 글리프 SDF 아틀라스 · 휘도→굵기 하프톤 · 레이마칭 장면
  - 데모 장면: 화면 전체가 36열 × 64행(한 칸 30 px)의 한글 격자다. 짧은 시 한 편이 왼쪽 위에서부터 읽는 순서대로 이어 쓰여 있고, 단어 사이는 가운뎃점 `·`이다.
  - 배울 점: 구분점 · SDF 구 추적 · 바다 · 하늘 · 회전하는 빔 · 번쩍임
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, gl.js, shaders.js, index.html, out/poster.jpg

- **60-jelly-type 말랑한 글자** — XPBD 연체(거리·면적 제약) · 글리프 외곽선 삼각분할 · 충돌
  - 데모 장면: 연보라 배경지 위에 창문 모양의 햇빛이 비스듬히 걸린 파스텔 스튜디오가 크림색에서 서서히 밝아진다. 화면 위에서 산딸기색 젤리 글자 말(Pretendard Black 600 px, 약 490×540)이 떨어진다.
  - 배울 점: 메시: 외곽선 → 연체 (mesh.js) · 외곽선 · 윤곽 방향 · 내부 점 · 삼각형 분류 · 고체
  - 라이브러리: d3, opentype.js
  - 영상: d3, opentype.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, mesh.js, scene.js, sim.js, index.html, out/poster.jpg

- **61-shadow-type 그림자로 읽는 글자** — 두 글자 돌출의 교집합(투영 조형) · 다중 광원 그림자
  - 데모 장면: 어두운 갤러리. 공중에 뜬 흰 석고 조형이 기울어진 축으로 천천히 구른다. 오른쪽 뒤에서 호박색 투광기가 조리개를 열 듯 네모난 빛을 벽에 연다(0.1–1.3 s).
  - 배울 점: 조형 = 두 돌출의 정확한 교집합 · 충실도 (보고) · 왜 벽 둘이 아니라 벽과 탁자인가 · 빛 · 연무와 먼지 · 이야기 곡선
  - 라이브러리: three.js, opentype.js
  - 영상: opentype.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 영상: three.js — 영상 스킬이 three.js를 넣는 방법을 따른다
  - 파일: NOTES.md, main.js, solid.js, index.html, out/poster.jpg

- **62-fogged-glass 김 서린 창** — 김 밀도장 · 물방울 입자(병합·흘러내림) · 굴절 법선 맵 · 보케
  - 데모 장면: 밤에 방 안에서 창밖을 본다. 유리 너머 도시의 불빛은 초점 밖이라 칠각 조리개 모양의 보케 원반으로 맺힌다.
  - 배울 점: 글씨 → 획 (strokes.js, setup) · 래스터화 · 이진화와 세선화 · 그래프 추적 · 조립 · 다듬기
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, drops.js, gl.js, shaders.js, strokes.js, index.html, out/poster.jpg

- **63-burning-type 타고 남은 글자** — 도착 시간장(16방향 다익스트라) · 불꽃 전선 셰이딩(흑체 색) · 불씨 입자
  - 데모 장면: 어둠 속에서 크림색 종이 한 장이 화면 가득 떠오른다. 비스듬한 섬유결과 얼룩이 보인다. 종이에는 "기억은 / 타지 / 않는다"(나눔명조 ExtraBold 300 px)가 불에 타지 않는 무언가로 쓰여 있어, 아주 희미한 결로만 보인다.
  - 배울 점: 도착 시간장 T(x) (field.js, setup에서 약 0.35 s) · 격자와 탐색 · 속도장 · 국소 앞선 속도 · 업로드 · 글자 (main.js:382)
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, field.js, index.html, out/poster.jpg

- **64-caustic-type 빛으로 쓴 글자** — 역설계 커스틱(최적 수송·포아송 반복) · 광자 메시 래스터화 · 분산
  - 데모 장면: 어두운 방의 엷은 트래버틴 바닥(줄눈이 있는 큰 석판, 결 무늬, 작은 기공)에 높은 창으로 든 햇빛이 1 : 1.5 직사각형으로 떨어진다.
  - 배울 점: 역설계 — 원하는 밝기 → 렌즈 · 목표 밝기 · 관례 (Ferraro) · 반복 · 포아송 풀이기 · node 단위 점검
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, design.js, index.html, out/poster.jpg

- **65-physarum-type 점균이 쓴 글자** — Physarum 에이전트(감지·회전·이동·침착) · 확산·감쇠 · 먹이장
  - 데모 장면: 암시야 현미경 아래의 짙은 청흑색 시야다. 처음에는 초점이 흐렸다가 맞는다. 아홉 개의 귀리 조각이 테두리만 밝게 빛난다.
  - 배울 점: Jones (2010) Physarum 모형, GPU(WebGL2) · 한 스텝 · 감지·회전·이동 · Jones의 배제 · 침착 · 확산·감쇠
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **66-rain-poem 빗속의 시** — GPU 2D 파동 방정식 · 굴절 · 프레넬 반사 · 수면 커스틱
  - 데모 장면: 해 질 녘, 돌로 된 얕은 수반을 바로 위에서 내려다본다. 바닥 화강암에는 시 한 편이 세로쓰기로 (오른쪽 열부터) 새겨져 있고, 홈에는 닳은 금박이 남아 있다.
  - 배울 점: 수면: 감쇠 2D 파동 방정식 (GPU, shaders.js:35) · 라플라시안 · CFL 조건 · 감쇠 · 빗방울 · 기울기·곡률 (shaders.js:62)
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, gl.js, scene.js, shaders.js, index.html, out/poster.jpg

## GSAP (67–72)

SplitText, MorphSVG, Flip, MotionPath — PixiJS·three.js와 함께

- **67-gsap-splittext 글자가 입장하는 법** — GSAP SplitText · ScrambleText · CustomEase — 라인 마스크 · 글자 스태거 · 스크램블
  - 데모 장면: 밝은 에디토리얼이다. 따뜻한 종이색(#f3eee4) 바탕에 먹색 글자를 쓰고, 강조색은 주홍(#e2401c) 하나만 쓴다.
  - 배울 점: SplitText, 분할은 모두 setup에서 · CustomEase · ScrambleTextPlugin · 흩어졌다 다시 모이기 · 줄긋기·박자·마침표
  - 라이브러리: GSAP
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **68-gsap-morphsvg 모양의 여행** — GSAP MorphSVG · DrawSVG · MotionPath
  - 데모 장면: 크림색 종이 위에 그린 미드센추리 플랫 일러스트다. 화면 위쪽 가운데에 햇살 무늬(sunburst)를 두른 해가 있고, 아래로 점묘 무늬가 들어간 언덕 세 겹과 막대사탕 모양 나무가 이어진다.
  - 배울 점: 도형 저작 규칙 · MorphSVGPlugin 설정 · 날갯짓도 모핑 · MotionPathPlugin · DrawSVGPlugin · 색 변화
  - 라이브러리: GSAP
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **69-gsap-flip 다시 놓이는 것들** — GSAP Flip · FLIP 레이아웃 전환 · CSS 그리드/플렉스
  - 데모 장면: 미술관 도록처럼 차분한 화면이다. - 바탕은 옅은 회백(#efece6)이다. - 카드(3:4)는 위쪽 62%가 그 절기의 색면이고, 색면 안에 작은 SVG 모티프와 번호가 있다.
  - 배울 점: 진짜 CSS 레이아웃 다섯 개 · Flip.getState로 상태를 기록한다 · Flip.fit(getVars)로 변환을 계산한다 · 중첩 공유 요소 모핑 · 스태거 전환 · 덱 자체의 움직임
  - 라이브러리: GSAP
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **70-gsap-motionpath 종이비행기 편지** — GSAP MotionPath(캔버스 객체) · CustomWiggle · Physics2D
  - 데모 장면: 맑은 봄날 오후다. 하늘은 위에서 아래로 파스텔 하늘색 → 복숭앗빛 → 크림색으로 내려온다. 왼쪽 위에 연노랑 해와 무리가 있고, 납작한 구름 다섯 개가 천천히 흐른다.
  - 배울 점: 업계 패턴: 일반 객체를 트윈하고 캔버스는 직접 그린다 · MotionPathPlugin · 경로 만들기 · 트윈 · 곡률 뱅크 · 이음매 없는 반복
  - 라이브러리: GSAP
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **71-gsap-pixi 물결 넘김 포스터** — PixiJS 8 · DisplacementFilter · GSAP PixiPlugin
  - 데모 장면: 패션 잡지 「WAVE」 7호의 포스터 네 장이 액체처럼 넘어간다. 색은 토마토 레드, 울트라마린, 애시드 옐로, 크림, 잉크 다섯 가지다.
  - 배울 점: PixiJS 8 · 앱 · 그리기 경로 · RGB 분리 = 색 채널 사본 세 장 · 액체 전환 = 마스크 + 변위 · SplitText(Pixi 8 내장)
  - 라이브러리: GSAP, PixiJS
  - 영상: PixiJS: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, art.js, kit.js, pixi-global.js, posters.js, index.html, out/poster.jpg

- **72-gsap-three 카메라 안무** — GSAP 타임라인 × three.js · 카메라 경로 · 장면 연출
  - 데모 장면: 파스텔 하늘 배경 위에 둥근 받침대에 얹힌 장난감 섬 마을이 떠 있다. 받침대는 복숭아색 쟁반에 크림색 테두리가 둘려 있고 그 안에 청록 바다가 있다.
  - 배울 점: GSAP 3.15: 장면 전체를 움직이는 타임라인 하나 · 카메라 리그 · MotionPathPlugin · 배 · 철길 · 곡선 매개변수
  - 라이브러리: three.js, GSAP
  - 영상: three.js — 영상 스킬이 three.js를 넣는 방법을 따른다
  - 파일: NOTES.md, main.js, diorama.js, index.html, out/poster.jpg

## 유명 라이브러리 (73–82)

anime.js, Motion, Lottie, p5.js, Paper.js, Zdog, matter-js, mo.js, Babylon.js, Tone.js

- **73-anime-stagger 점들의 합창** — anime.js 4 · 그리드 스태거 · SVG 드로잉/모프
  - 데모 장면: 96 BPM(한 박 625 ms, 16박 = 4마디). 바우하우스 악보 포스터가 살아 움직인다. 크림색 종이에 검정·빨강·코발트·노랑만 쓴다.
  - 배울 점: 타임라인 하나 · 그리드 스태거 · 층으로 쌓는 점 · 이징 · 숫자 래스터 · 망점 구
  - 라이브러리: anime.js
  - 영상: anime.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **74-motion-spring 알림이 내려앉을 때** — Motion(motion.dev) · 스프링 물리 · 수동 시계 seek
  - 데모 장면: 부드러운 파스텔 그라디언트 위에 CSS로 그린 일반 휴대폰이 있다(흑연색 테두리, 펀치홀 카메라, 측면 버튼, 상표 없음).
  - 배울 점: Motion의 animate와 스프링 · 수동 시계 · 값 하나에 animate 하나, 움직임마다 래퍼 하나 · 스프링을 가진 동작들 · 관찰창 곡선
  - 라이브러리: Motion
  - 영상: Motion: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg

- **75-lottie-code 코드로 쓴 로티** — lottie-web · 트림 패스 · 리피터 · 매트 · 셰이프 모프 (JSON을 코드로 작성)
  - 데모 장면: 크림색 바탕(#FFF4DE), 아래에는 남색 언덕 두 겹, 위에는 「오늘의 날씨 / 서울 · 하루의 하늘」과 기온이 있다.
  - 배울 점: 키프레임과 이징 · 트림 패스 · 리피터 · 셰이프 모프 · 트랙 매트 · 마스크
  - 라이브러리: lottie-web
  - 영상: lottie-web: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, lottie-kit.js, weather.js, style.css, index.html, out/poster.jpg

- **76-p5-tree 바람 부는 나무** — p5.js · 재귀 가지치기 · noise 바람 · 인스턴스 모드
  - 데모 장면: 결이 있는 종이에 그린 봄 일러스트다. 위는 옅은 하늘색에서 복숭앗빛으로 번지는 하늘이고, 수채 얼룩 같은 구름이 천천히 오른쪽으로 흐른다.
  - 배울 점: p5.js 2 인스턴스 모드를 무대 캔버스에 붙이기 (main.js:405) · 재귀 가지치기 (tree.js:72, 그리기 main.js:180) · 우산형 수관 · 맞춤 · 그리기 · 자람
  - 라이브러리: p5.js
  - 영상: p5.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, art.js, tree.js, index.html, out/poster.jpg

- **77-paper-boolean 오리고 붙인 풍경** — Paper.js · 불리언 연산(unite/subtract/intersect) · 경로 스무딩
  - 데모 장면: 장난감 종이 극장(toy theatre)이다. - 극장 틀: 남색 판지 프로시니엄이 화면을 감싼다. 위가 둥근 무대 입구에 겨자색 금박 테를 둘렀다.
  - 배울 점: Paper.js를 t로 몰기 (main.js:598) · 불리언으로 지은 조각들 (setup, 정적) · unite · 마을 실루엣 · intersect · exclude
  - 라이브러리: Paper.js
  - 영상: Paper.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, cut.js, index.html, out/poster.jpg

- **78-zdog-planet 작은 행성** — Zdog · 평면 의사 3D 일러스트 · 팔레트 낮/밤 전환
  - 데모 장면: 부드러운 하늘 그라데이션(하늘색 → 크림) 위에 떠 있는 작은 초록 행성이다.
  - 배울 점: Zdog 장면 그래프 · 그리는 순서 (z 정렬) · 조명 흉내 (Zdog에는 빛이 없다) · 팔레트 낮/노을/밤 · 튀어나오기 · 해와 달
  - 라이브러리: Zdog
  - 영상: Zdog: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, models.js, palette.js, index.html, out/poster.jpg

- **79-matter-galton 갈톤 보드** — matter-js 강체 물리 · 고정 dt 굽기 · 이항분포 → 정규분포
  - 데모 장면: 밝은 종이 바탕(점 격자) 위에 그린 인포그래픽형 갈톤 보드다.
  - 배울 점: 물리 (matter-js 0.20, sim.js) · 2D 갈톤 보드의 문제와 보정 · 조율 결과 · 잠자기 · 사전 굽기 (pre-roll) · 그리기 (Canvas 2D, main.js)
  - 라이브러리: matter-js
  - 영상: matter-js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, sim.js, index.html, out/poster.jpg

- **80-mojs-burst 축하의 순간** — mo.js · Burst · Shape · ShapeSwirl · Html · Timeline.setProgress
  - 데모 장면: 따뜻한 흰 바탕(#FFF6EA)의 앱 화면에서 시작한다. 위에 「오늘은 특별한 날 / 하트를 눌러 확인해 보세요」, 아래에 자두색 탭 바가 있다.
  - 배울 점: 단 하나의 mojs.Timeline · Shape + then 체인 · 커스텀 도형 · Burst · ShapeSwirl · 속성별 이징·곡선
  - 라이브러리: mo.js
  - 영상: mo.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, seek.js, style.css, index.html, out/poster.jpg

- **81-babylon-greenhouse 아침의 온실** — Babylon.js · PBR 유리 · 그림자 생성기(PCF) · GlowLayer · 부피광 산란
  - 데모 장면: 해 뜰 무렵 정원의 나무 탁자 위에 빅토리아풍 작은 유리 온실(워디언 케이스)이 놓여 있다. 크림색 주물 틀에 박공지붕, 용마루 장식(크레스팅)과 양 끝 피니얼이 있다.
  - 배울 점: 렌더 루프 없이 t로 그리기 (main.js:214, main.js:294) · 빛 · 태양 · 채움광 · IBL · 하늘
  - 라이브러리: Babylon.js
  - 영상: Babylon.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, world.js, index.html, out/poster.jpg

- **82-tone-shapes 소리가 그린 도형** — Tone.js(오프라인 합성) · 악보 기반 모션 · GSAP 타임라인 · SVG
  - 데모 장면: 크림색 종이 위에 칸딘스키·바우하우스풍 구성이 음악과 함께 한 겹씩 쌓인다. 빨강·파랑·노랑과 검은 선을 쓴다.
  - 배울 점: 악보 하나, 감각 둘 (score.js) · 소리: Tone.Offline (synth.js:17) · 잔향 · 마무리 · 재생 · 그림: 일시정지된 GSAP 타임라인 하나 (main.js:139)
  - 라이브러리: Tone.js, GSAP
  - 영상: Tone.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 영상: 소리 — 소리를 쓸지는 영상 스킬의 규칙을 따른다. 소리에 그림을 맞추는 방식을 참고한다
  - 파일: NOTES.md, main.js, score.js, synth.js, index.html, out/poster.jpg

## 웹 네이티브 애니메이션 (83–85)

CSS @keyframes, SVG SMIL, 스크롤 기반 애니메이션

- **83-css-keyframes CSS로만 그린 일출** — CSS @keyframes · @property · conic/radial-gradient · clip-path · mix-blend-mode
  - 데모 장면: 산이 겹겹이 선 호숫가의 해돋이를 밝은 그라디언트 일러스트로 그린다. 캔버스·셰이더·이미지 파일이 없고, 모든 픽셀은 CSS(그라디언트, clip-path 다각형, 블렌드 모드, 필터, offset-path)다.
  - 배울 점: 등록된 커스텀 속성(@property)과 하나의 색 대본 · clip-path 다각형 보간 (ridges.js) · 블렌드·필터 · 새: offset-path (style.css:274) · 호수: 장면을 복제한 반사 (main.js:111, style.css:237)
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, ridges.js, style.css, index.html, out/poster.jpg

- **84-svg-smil 태엽 장치** — SVG SMIL(animateTransform · animateMotion · animate) · setCurrentTime
  - 데모 장면: 크림색 종이에 갈색 잉크로 새긴 동판화 도판이다. 놋쇠·강철·주홍은 손으로 칠한 듯한 옅은 채색이다. 위쪽 「그림 1」은 태엽으로 도는 천체 운행기(오러리), 아래쪽 「그림 2」는 그것을 움직이는 동력 장치다.
  - 배울 점: 맞물림이 맞는 인벌류트 톱니 (gears.js) · 바퀴열 전체가 같이 째깍인다: accumulate="sum" (movement.js:65) · 진자와 닻: keyTimes/keySplines (movement.js:167) · 태엽: d 모핑과 stroke-dashoffset (movement.js:98) · 오러리: animateMotion + keyPoints, rotate="auto" (orrery.js) · 숫자가 켜진다: <animate> on fill/opacity/r (main.js:71–main.js:87)
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, gears.js, movement.js, orrery.js, style.css, index.html, out/poster.jpg

- **85-scroll-timeline 스크롤로 읽는 이야기** — CSS 스크롤 기반 애니메이션(scroll() · view()) · 스크롤 위치 제어
  - 데모 장면: 밝은 잡지풍 롱리드 「한 잔의 커피가 오기까지」를 보이지 않는 독자가 읽어 내려간다. 무대 위쪽 1080×1600은 기사가 담긴 스크롤 컨테이너다.
  - 배울 점: 스크롤 컨테이너와 시계 (main.js) · scroll() — 진행 막대와 표지 시차 · view() — 문단 · 이름 있는 view timeline — 섹션 그림과 숫자 · 고정(sticky) 요소 · timeline-scope — 컨테이너 밖에서 읽기
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 스크롤 기반 — 영상에는 스크롤이 없다. 원리만 참고
  - 파일: NOTES.md, main.js, style.css, index.html, out/poster.jpg

## 영상 표현력 (86–95)

표정 리그, 임팩트, 장면 전환, 멀티플레인 카메라, 닫힌식 물리 — 짧은 영상의 연출 장치

- **86-face-rig 에… 에… 에취!** — 얼굴 리그 · 표정 채널 + 연기 곡선
  - 데모 장면: 평면 스티커 일러스트다. 둥근 도형을 쓰고, 잉크 외곽선은 6.5px, 스티커 그림자는 번짐 없이 아래로 11px 떨어진다.
  - 배울 점: 채널 24개 · 포즈 · 같은 리그, 다른 인물 · 눈 · 눈썹 · 코
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, rig.js, index.html, out/poster.jpg, out/sheet.jpg

- **87-sensor-vision 밤 숲의 한 사람** — 센서 시점 · 스칼라장 + 거짓 색 + 스캔 전환
  - 데모 장면: 밤 #070b18 바탕이다. 강조색은 지금 켜진 채널의 색 하나만 쓴다: 달빛 #bcd0ff, 열 #ff9a4a, 소리 #7fe7ff, 고정 #ffcf5a.
  - 배울 점: 같은 장소, 세 가지 표현 · 스칼라장 = t의 순수 함수 · 열 · 연기 기둥 = 이류(advection)된 노이즈 · 소리 · 거짓 색(컬러맵 LUT)
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **88-loupe-lens 날개의 파랑** — 돋보기 렌즈 · 굴절 왜곡 + 숨은 층 + 아이리스 전환
  - 데모 장면: 호두나무 책상, 크림색 표본 카드, 연필과 자, 파란 나비(검은 테두리에 흰 점, 날개맥)가 나오는 평면 벡터 일러스트다.
  - 배울 점: 세 개의 숨은 층(setup에서 굽는다) · 능선의 자리는 모든 레벨에서 같다 · 굴절 = 픽셀마다 반지름을 다시 매기는 일 · 큰 렌즈 = 평평한 안쪽 + 굴절하는 테 띠 · 아이리스 · 렌즈의 몸
  - 라이브러리: GSAP
  - 파일: NOTES.md, main.js, art.js, index.html, out/poster.jpg, out/sheet.jpg

- **89-impact-kit 세 번 찍는 도장** — 임팩트 키트 · 한 박자를 세게 만드는 겹침
  - 데모 장면: 어두운 남색 펠트 깔판 위에 한지 서식 「한 박자 연습장」이 놓여 있다. 서식에는 결재란처럼 생긴 세 칸(작게 · 중간 · 크게)과 칸마다 「(인)」 자리가 인쇄되어 있다.
  - 배울 점: 박자 하나 = (t − t_hit)의 닫힌 식 묶음 · 겹침의 순서와 예산 · 채널 분리: 한 요소에 세 움직임이 섞이지 않고 더해진다 · 자국 굽기 · 도장 그리기 · 배경 굽기
  - 라이브러리: GSAP
  - 파일: NOTES.md, main.js, art.js, kit.js, index.html, out/poster.jpg, out/sheet.jpg

- **90-measure-hud 구름 위의 아침** — 재는 연출 · 오도미터 + 계기 바늘 + 줄자
  - 데모 장면: 평면 일러스트다. 색 온도로 이야기가 흐른다. 밤(남색) → 구름 속 새벽(라일락·장밋빛) → 해돋이(하늘색·금빛).
  - 배울 점: 값 하나에서 모든 계기로 · 오도미터 자리 올림 · 바퀴별 모션 블러 · 드럼 느낌과 고정폭 숫자 · 글린트 · 바늘: 스프링 + 떨림 + 잔상
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **91-gait-cycle 눈 위의 박자** — 닫힌식 보행 주기 · 발 고정 · 발자국 박자
  - 데모 장면: 깊이 층(뒤 → 앞): 하늘 그라데이션과 구름, 해와 빛무리, 먼 언덕 두 겹, 전나무 두 줄, 눈밭(바람 자국과 눈 입자), 따뜻한 햇빛 덧칠과 반짝임, 발자국, 토끼와 닭(긴 아침 그림자), 앞쪽 눈 둔덕과 마른 풀, 빛줄기, 세 겹으로 내리는 눈(가까운 눈송이는 흐림), 박자 띠, 글자.
  - 배울 점: 하나의 경로 → 공통 박자 격자 · 발 고정(planted feet) · 토끼: 포물선 비행 + 찌그러짐·늘어남 · 닭: 번갈아 걷기 + 기우뚱 + 머리 고정 · 발자국 = 눈 위의 움푹한 자국 · 박자 띠와 재생 빛줄기
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **92-type-acting 고백하던 날** — 뜻을 연기하는 글자 · 채널 기반 글자 효과
  - 데모 장면: 오후 햇빛이 드는 책상 위에 편지지 한 장이 놓여 있다. 창틀 그림자가 십자로 비스듬히 떨어지고, 그 안에서 나뭇잎 그림자가 흔들린다.
  - 배울 점: 단위(unit)와 쉬는 자리 · text · outline · shard · 채널 · 효과
  - 라이브러리: opentype.js
  - 영상: opentype.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, fx.js, index.html, out/poster.jpg, out/sheet.jpg

- **93-transition-kit 종이배의 하루** — 장면 전환 키트 · 와이프·아이리스·휩 팬·매치 컷
  - 데모 장면: 모든 전환은 같은 문법을 따른다. 1. 히어로 글자가 먼저 빠진다. 0.28초 `power2.in`으로, 들어올 때(0.72초 `expo.out`)보다 빠르다.
  - 배울 점: 구조 · 장면 그리기 · 카메라 · 종이배 · 휩 팬 · 스캔 띠
  - 라이브러리: GSAP
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **94-multiplane 이슬 너머 먼 불빛** — 멀티플레인 카메라 · 평면 일러스트의 깊이
  - 데모 장면: 해 뜨기 직전의 대숲이다. 대나무 줄기 사이로 먼 언덕 위의 작은 한옥 한 채가 보이고, 그 집 창 하나에만 불이 켜져 있다.
  - 배울 점: 기준 카메라로 그린 카드 · 카메라 · 카드 굽기와 흐림 피라미드 · 피사계 심도 · 랙 포커스 · 대기 원근
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **95-closed-form-physics 다 같이, 멈춰** — 닫힌식 물리 · 시뮬레이션 없이 튕기고 흔들리기
  - 데모 장면: 팔레트: 크림 벽(#FAE6CA), 나무 식탁(#D89C60), 잉크(#2B211B), 강조색 토마토(#E9483B) 하나.
  - 배울 점: 동전 — 오일러 원반의 유한 시간 정지 · 콩 — 포물선 조각 + 기하급수 바운드 + 정확히 R에 서는 구르기 · 역으로 겨누기 · 숟가락·푸딩·꼬투리 — 선형 진동자의 중첩 · 감쇠율 σ를 푼다 · 같은 함수를 다른 시각에서 부르기 — 스트로보와 나선
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, layout.js, phys.js, index.html, out/poster.jpg, out/sheet.jpg

## 타이포그래피 모션그래픽 (96–115)

말하는 자막, 플랩 전광판, 한글 조합, 만화 의성어, 금속 타이틀 — 글자가 주인공인 장면

- **96-kinetic-camera 오늘은 그냥, 한 번** — 키네틱 타이포그래피 · 글자 지도 위를 나는 카메라
  - 데모 장면: 독백은 "매일 아침 / 생각만 했다 / 오늘은 / 그냥 / 한 번 / 해 보기로 / 했다."이다. 글꼴은 Pretendard Variable 하나에 굵기 두 단계(300, 900)만 쓴다.
  - 배울 점: 글자 지도 조판 · 회전한 문구는 가운데에 둔다 · 카메라 = 닮음 변환, 이동 = 닮음군의 측지선 · 이동 곡선 s(t) · 이어짐 · 벽이 보이지 않게
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **97-karaoke-captions 양말 도둑** — 말하는 자막 · 단어 단위 타이밍 + 하이라이트 필 + 강조 팝
  - 데모 장면: 밤의 방을 평면 스티커 일러스트로 그렸다(잉크 외곽선 5–6px, 둥근 도형). 남색 벽과 달빛 창, 빨랫줄의 양말 세 켤레가 보인다.
  - 배울 점: 말 타이밍 표 · 줄바꿈은 setup에서 한 번 잰다 · 알약(FLIP) · 단어 색 상태 · 강조 팝 · 밑줄 스우시
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **98-split-flap 집으로 가는 막차** — 플랩 전광판 · 반쪽 판이 넘어가는 기계식 글자
  - 데모 장면: 어두운 역 벽에 금속 테두리의 안내판이 걸려 있고, 그 위에 따뜻한 막대 조명이 매달려 있다. 안내판은 머리판(`출발` · `밤 열차 안내` · `지금 23:57` 플랩 시계)과 7줄 × 11칸(열차 2칸, 시각 4칸, 행선지 4칸, 타는 곳 1칸)으로 되어 있다.
  - 배울 점: 드럼과 플랩 순서 · 넘김 일정 = t의 순수 함수 · 넘김 한 번 그리기 · 글자판은 setup에서 한 번 굽는다 · 조명은 곱하기 한 번 · 유리와 전조등
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **99-knockout-zoom 여름으로 난 창** — 녹아웃 글자 · 카운터를 통과하는 줌
  - 배울 점: 핀홀 카메라 하나 · 지수 줌 · 녹아웃(글자 = 창) · 절단면(벽 두께) · 펀치와 카운터 · 풍경
  - 라이브러리: opentype.js
  - 영상: opentype.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **100-echo-type 지금** — 에코와 늘임 · 시간 지연 반복 + 늘어나는 글자
  - 데모 장면: 인쇄된 포스터다. 잉크는 세 가지(종이색 #ece4d3, 먹 #17140f, 주홍 #ec3b1b)만 쓴다. 악장마다 세 잉크의 역할(바탕·앞장·에코)이 바뀌고, 6단 그리드를 따라가는 와이프로 넘어간다.
  - 배울 점: 시간 지연 에코 · 세 가지 지연 · 위아래 거울 줄 · 늘여도 고른 외곽선 · 번갈아 칠하기와 잉크 역할 바꾸기 · 그리드 와이프
  - 라이브러리: opentype.js
  - 영상: opentype.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **101-marker-annotate 여백에 남긴 비법** — 형광펜과 손 주석 · 손으로 긋는 강조의 문법
  - 데모 장면: 호두나무 책상에 접힌 자국이 있는 레시피 한 장(「주말 부엌 노트 No. 12 · 토마토 달걀볶음」)이 놓여 있다.
  - 배울 점: 표시 = 폴리라인 + 필압 + 손의 시간 · 속도는 손을 따른다 · 필압 윤곽 · 그리기 · 형광펜 · 모양 만들기
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **102-iso-blocks 쌓으면, 꿈** — 아이소메트릭 복셀 글자 · 블록 조립과 재조립
  - 데모 장면: 미감은 파스텔 장난감 스튜디오다. - 배경: 위는 하늘색, 아래는 라일락 바닥으로 넘어가는 그라디언트. 왼쪽 위에 소프트박스 빛이 있고, 지평선 근처에 초점이 나간 장난감 실루엣과 필름 그레인을 깔았다.
  - 배울 점: 글자 → 격자 · 획을 따라가는 순서 · 닫힌 식 착지 · 같은 블록으로 다시 짓기 · 정사영 카메라와 깊이 정렬 · 그리기
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **103-word-swap 오늘의 빈칸** — 단어 교체 키트 · 한 자리에서 바뀌는 낱말
  - 데모 장면: 미감은 밤의 포스터다. 남보라 밤하늘에 크림색 글자를 쓰고, 강조색은 호박색(#ffbe55) 하나만 쓴다. - 배경: 별, 초승달, 해가 뜰 자리에서 퍼지는 빛살과 얇은 동심원, 먼 언덕의 작은 집 불빛, 가까운 언덕, 떠다니는 먼지, 필름 그레인.
  - 배울 점: 시간표와 구조 · 이징은 GSAP에서 가져온다 · 폭 맞춤 = FLIP · 슬라이스 · 프리즘 · 폭 맞춤 교체
  - 라이브러리: GSAP
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **104-type-tunnel 오늘이라는 터널** — 글자 터널 · 3D 공간을 지나가는 글자
  - 데모 장면: 미감은 '밤의 종이 등불'이다. 원고지 칸이 희미하게 그어진 짙은 남색 원통 안에서, 글자는 등불처럼 빛난다.
  - 배울 점: 원통 좌표 하나로 모든 것을 놓는다 · 벽 글자는 축에서 보면 똑바로 읽힌다 · 세 종류의 글자 · 글자 아틀라스와 합성 · 속도 곡선 = 이야기 · 카메라
  - 라이브러리: three.js
  - 영상: three.js — 영상 스킬이 three.js를 넣는 방법을 따른다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **105-comic-sfx 택배 왔다** — 만화 의성어 레터링 · 소리를 그리는 글자
  - 데모 장면: 어두운 책상 위에 바랜 크림색 원고지가 놓여 있다. 원고지에는 하늘색 밑그림 칸, 재단선, 머리글 「07 택배 왔다」가 인쇄되어 있다.
  - 배울 점: 글자 가공(setup, sfx.js:124 prepGlyph) · 배치(매 프레임, t의 닫힌 식) · 겹겹이 그리기(sfx.js:253 drawLetter) · 소리에 딸린 표시 · 인쇄 흉내 · 칸 연출
  - 라이브러리: opentype.js
  - 영상: opentype.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, art.js, sfx.js, index.html, out/poster.jpg, out/sheet.jpg

- **106-ime-compose 보내기 전에** — 조합되는 한글 · 입력기 조합 + 쓰고 지우는 문장
  - 데모 장면: 미감은 밤 방 안의 휴대폰이다. 남보라 방, 커튼 사이 창밖의 흐린 도시 불빛(보케)과 달, 이불과 베개가 있고, 화면 빛이 방을 비춘다.
  - 배울 점: 입력은 키 목록 하나뿐이다 · 두벌식 오토마타 · 매 프레임 처음부터 다시 친다 · 입력기 표시 · 지운 말의 두 가지 운명 · 자판
  - 라이브러리: GSAP
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **107-unroll-text 돌고 돌아 제자리** — 경로 위 조판 · 호 길이로 맞춘 경로 모핑
  - 데모 장면: 미감은 '크림색 종이 위 포스터'다. 바탕은 바랜 크림색 종이(결, 섬유, 배지 중심의 옅은 동심원)이고, 먹색 글자에 강조색은 주홍 하나만 쓴다.
  - 배울 점: 테이프(setup, main.js:40 buildTape) · 경로 = 회전 함수 θ(u)(main.js:64 makeShapes) · 모핑: 같은 u에서 접선을 섞고, 헤드에서부터 적분(main.js:286 buildPath) · 글자 배치(main.js:370 이후) · 흐름 F(t)(main.js:268-281) · 달팽이(main.js:175 drawSnail, 배치 main.js:469)
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **108-liquid-fill 가득 찬 아침** — 차오르는 글자 · 글자를 그릇으로 쓰는 액체
  - 데모 장면: 깊이는 다섯 겹이다. 가장 뒤에는 흐린 선반 소품(원두 병·컵·화분)과 펜던트 조명이 있다(구울 때 blur 6px·3px).
  - 배울 점: 글자 → 그릇 · 수위의 성격은 모양에서 나온다 · 수면 = 닫힌 식의 출렁임 · 기울어도 수평 · 물줄기 = 탄도 · 기포·물보라
  - 라이브러리: opentype.js
  - 영상: opentype.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **109-paper-unfold 접힌 쪽지** — 펼쳐지는 종이 글자 · 접힘선 따라 열리는 타이포그래피
  - 데모 장면: 미감은 오후 햇살이 드는 교실 책상이다. - 배경: 꿀색 합판 책상(긴 나뭇결, 연필 낙서), 지우개와 지우개 가루, 노란 연필, 펼친 공책 귀퉁이.
  - 배울 점: 종이 = 경첩 사슬 · 같은 접힘선으로 다른 모양 · 원근 카메라와 텍스처 조각 · 그리는 순서 · 종이답게 보이는 것들 · 문구와 박자
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **110-sticker-peel 나중에 말고 지금** — 다이컷 스티커 · 말려 올라가는 떼기
  - 데모 장면: 짙은 호두나무 책상이다. 왼위에서 스탠드 불빛이 들어온다. 헤어라인 가공 알루미늄 노트북 뚜껑이 놓여 있고(브랜드 없음), 오른위에는 반쯤 쓴 스티커 대지가, 왼아래에는 연필이 걸쳐 있다.
  - 배울 점: 다이컷 칼선 굽기(setup, sticker.js:141 bakeSticker) · 철썩 붙기(main.js:76 slapPose, main.js:97 drawFlat, main.js:113 surfaceFx) · 말려 올라가는 떼기(sticker.js:243-286, main.js:278 peelState, main.js:453 drawPeel) · 홀로그램 「지금」(main.js:420 drawNow) · 장면(scene.js)
  - 라이브러리: opentype.js
  - 영상: opentype.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, designs.js, scene.js, sticker.js, index.html, out/poster.jpg, out/sheet.jpg

- **111-chrome-sting 오늘의 발견** — 방송 타이틀 스팅 · 금속 입체 글자 + 반사 + 빛 쓸기
  - 데모 장면: 미감은 '방송 그래픽'이다. 남색이 도는 검은 스튜디오에 위에서 희미한 빛기둥이 내려오고, 바닥은 검게 윤이 난다.
  - 배울 점: 윤곽 → Shape → ExtrudeGeometry · 법선 고치기 · 조명 = 그린 스튜디오 · 빛 띠 · 반사 바닥 · 카메라
  - 라이브러리: three.js, opentype.js
  - 영상: opentype.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 영상: three.js — 영상 스킬이 three.js를 넣는 방법을 따른다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **112-projection-map 이 골목도 무대였다** — 프로젝션 매핑 타이포그래피 · 건물 면의 호모그래피와 아나모픽
  - 데모 장면: 카메라는 처음부터 끝까지 움직이지 않는다. 관객은 골목 계단에 서 있어서 눈높이가 3 m이고, 수평을 본다.
  - 배울 점: 고정 카메라와 벽마다 호모그래피 하나 · 글자는 벡터로 사영한다 · 내용의 좌표계 네 가지 · 처마 띠: 앞면은 어긋나고 아래는 그늘 · 창: 유리는 빛을 지우고, 블라인드·셔터·문은 안쪽 평면에서 받는다 · 빛 층: 벽 색에 더하고, 질감을 다시 곱한다
  - 라이브러리: opentype.js
  - 영상: opentype.js: 영상 스킬에 없는 라이브러리라면 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **113-puffy-type 빵빵하게** — 거리장 부풀림 셰이딩 · 높이장 법선 · 광택과 접촉 그림자
  - 데모 장면: 미감은 캔디 파스텔 스튜디오다. - 배경: 라일락에서 복숭아빛으로 넘어가는 호리존트 벽이다. 벽이 바닥으로 휘는 자리(y ≈ 1370)가 빛을 받아 밝다.
  - 배울 점: 모양 → 거리장 아틀라스 · 열기 · 닫기 · 높이 = 거리의 함수 · 부풀림 R(t) · 찌르기: 높이장에 더한 패임
  - 라이브러리: 없음 (브라우저 기능만)
  - 영상: 손으로 쓴 WebGL2 셰이더 — 영상 스킬의 WebGL 층(three.js 등) 위에서 다시 쓴다
  - 파일: NOTES.md, main.js, shader.js, index.html, out/poster.jpg, out/sheet.jpg

- **114-beat-type 하나 둘 셋 넷** — 박자에 맞춘 글자 · 마디·박·엇박으로 짜는 타이포 레이아웃
  - 데모 장면: 고대비 포스터다. 종이(#efe6d3), 먹(#15130f), 주홍(#e2402a) 세 색만 쓰고, 마디마다 바탕이 뒤집힌다.
  - 배울 점: 악보 표 하나가 전부를 정한다 · 타격 → 타이포 반응 · 예비 동작과 안착을 박으로 잰다 · 다섯 구성 · 한글 조판 · 소리
  - 라이브러리: GSAP
  - 영상: 소리 — 소리를 쓸지는 영상 스킬의 규칙을 따른다. 소리에 그림을 맞추는 방식을 참고한다
  - 파일: NOTES.md, main.js, score.js, synth.js, index.html, out/poster.jpg, out/sheet.jpg

- **115-marquee-tape 취급주의, 오늘의 주인공** — 흐르는 글자 띠 · 무한 마키 테이프
  - 데모 장면: 미감은 밝은 종이 공작 포스터다. 라일락 종이 벽(결 무늬, 아래로 갈수록 짙어짐) 앞에 크라프트 상자가 떠 있다.
  - 배울 점: 끝없는 흐름 = 오프셋 mod 주기 · 띠 = 중심선 위 N개 표본, 표본마다 자기 틀 · 벨트 레일 · 접선 감기 · 겹침 순서가 늘 같다 · 비틀림
  - 라이브러리: three.js
  - 영상: three.js — 영상 스킬이 three.js를 넣는 방법을 따른다
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

## 모션그래픽 디자인 (116–125)

로고 리빌, 메타볼, 아이소메트릭 설명, 앱 소개, 방송 그래픽, 지도 경로 — 모션 디자인의 단골 장면

- **116-logo-reveal 동틀녘 러닝 클럽** — 로고 리빌 · 도형이 모여 심벌과 워드마크로
  - 데모 장면: 새벽 남색 바탕(#13173d → #1c2156 → #2b2461)에 크림(#fff1dc), 해 주황(#ff6a3d), 금빛(#ffb63e)을 쓴다.
  - 배울 점: 하나의 움직임 아이디어 = 한 바퀴 · 트랙 경로 · 꼬리 = 점이 지나온 길 · 도형이 서로를 가린다 · 락업의 정렬은 측정해서 맞춘다 · 높이
  - 라이브러리: GSAP
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **117-gooey-blobs 몽글몽글** — 메타볼 블롭 · 붙고 갈라지고 글자를 감싸는 액체
  - 데모 장면: 미감은 굵은 평면 팔레트와 그레인이다. 장면 A는 크림 종이(#f4ecdd)에 먹색 글자를 쓰고, 액체는 해바라기(#ffc21e)·토마토(#ff5433)를 쓴다.
  - 배울 점: 장의 기울기 · 조각마다 색 · 글자 커버리지를 더하고 빼야 · 커널 · 색 섞기 · 글자를 장에 넣기
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, goo.js, index.html, out/poster.jpg, out/sheet.jpg

- **118-dot-matrix 점 하나로 여는 무대** — 점 격자 모션 · 점의 크기와 색으로 그리는 도형과 글자
  - 데모 장면: 미감은 무대 LED 월의 방송 그래픽이다. 짙은 코발트 패널 위에 꺼진 LED(옅은 푸른 점)가 늘 깔려 있다.
  - 배울 점: 점 하나 = 장들의 합성 · 거리장 → 점 크기 · 점 → 선 → 면은 한 모양 · 아이콘 · 글자 거리장 · 전선(와이프)과 점마다의 스프링
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **119-iso-explainer 편지 한 통이 집에 닿기까지** — 아이소메트릭 설명 장면 · 흐름이 보이는 작은 세계
  - 데모 장면: 미감은 밝은 파스텔 인포그래픽(아이소메트릭 설명 일러스트)이다. - 하늘: 옅은 물빛에서 크림색으로 넘어가는 그라디언트다.
  - 배울 점: 투영과 카메라 · 한 빛에서 나온 세 톤 · 호 길이 고리와 일정한 간격 · 위상은 주인공의 일정표에서 역산한다 · 깊이 정렬: 분리축 의존 그래프 + 위상 정렬 · 부드러운 그림자
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **120-perfect-loop 끝에서 처음으로** — 완벽한 루프 · 끝과 처음이 이어지는 기하 패턴
  - 데모 장면: 포스터는 위에서 아래로 다음 순서로 짜여 있다. - 머리줄: `NO.120 LOOP STUDY`, `L = 9.60 S · 30 FPS` - 큰 제목 두 줄: 끝에서 / 처음으로.
  - 배울 점: 모든 장치는 L/k 주기다 · 90° 물결 = 한 칸 이동 · 줌 루프(드로스테) · 넘겨주는 움직임(릴레이) · 글자도 돈다 · 임팩트 예산
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **121-mesh-gradient 숨 고르는 아침** — 흐르는 그라데이션 메시 · 필름 그레인 · 유리 카드
  - 데모 장면: 위계: 제목 280px / 카드 큰 숫자 132px / 카드 제목·알약 38–46px / 라벨 20–34px.
  - 배울 점: 그라데이션 메시 · 움직이는 제어점 = 역변위 · 새벽 → 아침 전선 · 글자 = 메시를 보는 창 · 크림 ↔ 먹색은 실제 명도로 정한다 · 유리 카드
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, field.js, index.html, out/poster.jpg, out/sheet.jpg

- **122-app-promo 목마르기 전에** — 앱 소개 모션 · 폰 목업 + 화면 전환 + 탭 + 기능 콜아웃
  - 데모 장면: 미감은 밝은 플랫 일러스트 앱 광고다. 바탕은 세이지 종이색이고, 가장자리에 흐린 몬스테라 잎 두 겹과 떠다니는 물방울 보케, 필름 그레인을 깔았다.
  - 배울 점: 이야기 시계 한 곳 · 기기 = CSS 3D 리그 · 3D 투영으로 지시선 찾기 · 화면 전환은 UI의 논리를 따른다 · 터치 표시 · 세는 숫자
  - 라이브러리: GSAP
  - 파일: NOTES.md, main.js, style.css, index.html, out/poster.jpg, out/sheet.jpg

- **123-lower-thirds 모퉁이 라이브** — 방송 그래픽 패키지 · 로어서드 · 티커 · 버그 · 스팅어
  - 데모 장면: 샷 A는 눈 오는 밤 골목의 붕어빵 노점에서 사장님을 찍은 인터뷰 미디엄 숏이다. 줄무늬 차양과 전구가 있고, 뒤로는 초점이 나간 골목(창, 네온, 보케)이 보인다.
  - 배울 점: 디자인 시스템 · 시그니처 동작 "앞서는 라임, 따라오는 바" · 글자를 재서 바를 만든다 · 티커와 숫자 · 층과 슬롯 · 장면
  - 라이브러리: GSAP
  - 파일: NOTES.md, main.js, scene.js, style.css, index.html, out/poster.jpg, out/sheet.jpg

- **124-shape-mascot 네모, 무게를 싣다** — 도형 마스코트 · 애니메이션 원칙과 스미어 프레임
  - 데모 장면: 미감은 '애니메이터의 연필 테스트'다. 짙은 책상 위에 작화지 석 장이 겹쳐 있다. 맨 위 장은 아래에서 올라오는 라이트 테이블 빛으로 가운데가 밝다.
  - 배울 점: 몸의 궤적: 구간 목록 · 찌그러짐·늘어남(부피 보존) · 예비 동작 · 글자는 스프링 받침 · 스미어 프레임과 멀티플 · 따라가는 움직임: 닫힌식 스프링 더듬이
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg

- **125-route-map 바람섬 사흘 걷기** — 지도 경로 모션 · 가상의 섬 위의 여정
  - 데모 장면: 미감은 설명 영상용 일러스트 지도다. 청록 바다, 크림·세이지색 단계 채색의 땅, 먹선, 그리고 강조색 주홍(#E2472B) 하나를 쓴다.
  - 배울 점: 섬 만들기 · 해안선과 등고선 추적 · 바다의 메아리 고리 · 땅의 깊이 · 지형 힌트 · 길과 호 길이
  - 라이브러리: 없음 (브라우저 기능만)
  - 파일: NOTES.md, main.js, index.html, out/poster.jpg, out/sheet.jpg
