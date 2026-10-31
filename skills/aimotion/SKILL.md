---
name: aimotion
description: 웹 그래픽 표현 기법 참고서 aimotion — 기법 하나당 데모 하나, 데모 125편의 구현 노트와 소스와 그림이 이 스킬 안에 모두 들어 있다. 장면에 맞는 기법을 찾아 원리와 소스를 읽고 지금 만드는 영상에 옮긴다. Use when building or improving a motion-graphics or video scene that needs richer visual expression — ink, watercolor, paper, print or film looks; shaders (fBm, raymarching, caustics, SDF); particles; fluid, cloth or physics simulation; kinetic or expressive typography, captions, title stings, lower thirds, logo reveals, scene transitions, isometric explainers, mascots, route maps; GSAP, three.js, Canvas 2D, SVG or CSS animation techniques — or when asked for 표현력 향상, 그래픽 업그레이드, 더 멋진 효과, 연출·기법 참고. Takes only the techniques and the technical content, never the demos' 9:16 format.
---

# aimotion — 표현 기법을 찾아 영상에 옮기기

aimotion은 웹 기술로 그래픽 영상을 표현하는 방법을 기법 하나당 짧은 데모 하나로 구현한 모음이다.
이 스킬 폴더에 데모 125편이 모두 들어 있다. 편마다 구현 노트(NOTES.md: 데모 장면, 기법과 원리와 `main.js:줄`, 결정성 전략, 한계), 소스, 그림이 있다.
네트워크 없이 이 폴더의 파일만 읽으면 된다.

## 무엇을 가져가나

- **가져간다: 표현 기법과 기술적 내용.** 어떤 효과를 어떤 원리로 만드는지(알고리즘, 셰이더, 합성과 빛, 질감, 움직임과 이징),
  무거운 일을 미리 굽고 t로 읽는 방법, 시뮬레이션을 되감는 방법, 성능 요령.
- **가져가지 않는다: 데모의 형식과 장면.** 데모는 모두 세로 9:16(1080×1920), 8–10초, 화면 아래 자막이라는 같은 틀로 만들었다.
  이 틀은 데모를 나란히 보여 주려고 정한 것일 뿐이다. 비율·크기·구도·배치·길이·이야기 구성·문구·색은 가져가지 않는다.
  형식(비율, 무대 크기, 안전 영역, 자막, 길이)은 작업 중인 영상과 그 스킬을 따른다.
- 코드 안의 1080·1920 같은 좌표와 크기는 데모 무대의 값이다. 옮길 때 영상 무대의 너비·높이에 맞춰 다시 계산한다.
  세로를 전제로 짠 배치는 영상의 비율에 맞게 다시 짠다.

## 쓰는 법

이 스킬 폴더를 `A`라 한다. 찾기 스크립트는 `S=A/scripts/aimotion.mjs`다(Node 18 이상, 의존성 없음).

1. **찾기**: `node $S search 잉크 번짐`, `node $S search particles 글자` — 제목·기법·배울 점·라이브러리·분류에서 찾아 순위대로 보여 준다.
   전체는 `node $S list`, 또는 `A/INDEX.md`(분류별 목록, 편마다 데모 장면·배울 점·라이브러리·영상 주의).
2. **보기**: `A/demos/<id>/out/poster.jpg`(절정 한 장)와 `out/sheet.jpg`(1초마다 한 장)를 이미지로 연다. 기법이 어떻게 보이는지 확인하는 용도다.
3. **원리**: `A/demos/<id>/NOTES.md`(`node $S show <id> --notes`) — "기법과 원리"가 핵심 아이디어와 그것이 있는 `main.js:줄`을 가리킨다.
4. **소스**: `A/demos/<id>/`의 파일을 그대로 읽는다(`node $S show <id> --code`는 소스 파일을 차례로 이어 보여 준다).
   데모가 부르는 공통 코드는 `A/demos/_lib/`(`node $S common`)에 있다: `stage.js`(시계·seek·`rand`·`track`·`ease`·`replay`)와 `type.js`(글꼴·거리장·윤곽).
5. **옮기기**: 아래 "영상에 옮길 때"를 따른다.

`<id>`는 데모 폴더 이름(`03-coral-growth`)이다. 스크립트에는 번호(`3`, `103`)만 써도 된다.
노트를 먼저 읽고 필요한 소스 부분만 본다. 한 편의 소스는 수만 자일 수 있다.

## 영상에 옮길 때

- **영상은 aimotion의 파일을 불러오지 않는다.** 원리를 이해한 뒤 영상 프로젝트의 코드로 다시 쓴다.
- **영상 스킬의 규칙이 먼저다.** 라이브러리·글꼴·소리·데이터·네트워크는 작업 중인 영상 스킬(또는 프로젝트)의 규칙을 따른다.
  그 규칙에 없는 라이브러리를 쓴 데모는 원리만 가져와 Canvas 2D·SVG·WebGL로 직접 쓴다. 물리는 미리 구운 결과를 t로 읽는다.
  실제 지도 데이터를 쓴 데모는 직접 그린 양식화된 지도로 바꾼다.
- **시계 대응**:
  - 데모의 `setup()` 굽기 → 영상에서 프레임 전에 한 번
  - `frame(t)` → 영상의 프레임 함수
  - `rand(seed)` → 영상의 시드 난수
  - `track`/`ease` 키프레임 → 영상 타임라인의 트윈
- **결정성**: 그림은 t의 순수 함수로 그린다. `Math.random`·`Date`·타이머·CSS transition은 쓰지 않는다.
  상태가 쌓이는 시뮬레이션은 고정 dt로 진행하고 체크포인트에서 다시 계산하거나(`demos/_lib/stage.js` `replay`), 미리 구워 둔다.
  옮긴 뒤에는 같은 t를 다른 순서로 찾아가도 같은 그림이 나오는지 확인한다.
- **무게**: 영상을 프레임 단위로 렌더하면(헤드리스 브라우저 등) 프레임마다 전부 다시 그린다.
  목록에 "CPU 검증 프레임당"이 1초를 넘는다고 적힌 기법은 해상도를 낮추거나 미리 굽는다.
- **셰이더·캔버스 함정**:
  - 음수 밑의 `pow`는 실제 GPU에서 NaN이 된다. 제곱은 `x * x`로 쓰고, 밑은 `max(x, 0.0)`으로 막는다.
  - NaN 한 픽셀이 블룸·블러를 타고 번지면 깜빡임이 된다.
  - 해시 격자 위의 요소는 주변 3×3칸을 합산한다.
  - 서브패스가 수천 개인 큰 경로에 `closePath`를 반복하지 않는다.
  - 프레임마다 2D 컨텍스트 상태(`lineCap`, `setLineDash`, `globalAlpha`, `globalCompositeOperation`, `filter`, 변환)를 기본값으로 되돌린다.