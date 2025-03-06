# CSS 정리

사람: 김소연
생성 일시: 2025년 3월 6일 오후 1:02

## 1. float

 - 레이아웃을 구성할 때 block 레벨 요소를 가로 정렬하기 위해 사용된다.

 ❗ float 선언된 요소와 선언되지 않은 요소간 margin이 사라지는 문제가 발생할 수 있다. 

 → float이 선언되지 않은 요소에 `overflow : hidde` 을 추가한다.

 ❗ float 선언된 요소를 포함하는 부모 요소의 높이가 반영 되지 않을 때

→ float이 선언된 부모 요소에 `overflow : hidden`을  추가한다.

→ float이 선언된 부모 요소에 :`:after {display:block; content: ‘’; clear:both;}` 를 적는다.

## 2. 마진 상쇄

 - 여러 블록 요소의 상하 마진이 겹칠 때 가장 큰 크기로 합쳐지는 현상

 ❗ 해결법

→ 블록 요소의 상단 또는 하단에 padding이나 border값으로 벽을 만들어 주는 방식

→ 블록에 `position : absolute`  또는 `float  :left/right` 상태

→ 블록에 `display:flex` 또는 `display:grid` 일 때의 내부 영역

## 3. 상속 우선순위 (=cascading)

 - CSS가 충돌 될 때 적용되는 우선순위를 말한다.

❗ 중요도

```jsx
1. head 요소 내의 style 요소
2. head 요소 내의 style 요소 내의 @import 문
3. <link> 로 연결된 CSS 파일
4. <link> 로 연결된 CSS 파일 내의 @import 문
5. 브라우저 디폴트 스타일시트
```

❗ 명시도

<aside>
💡

`!important` > 인라인 스타일 > 아이디 선택자 > 클래스/어트리뷰트/가상 선택자 > 태그 선택자 > 전체 선택자 > 상위 요소에 의해 상속된 속성

</aside>

## 4. Interactive UI 를 위한 속성들

### 🤔transition

 - CSS 프로퍼티 값이 변화할 때, 변화가 일정 시간에 걸쳐 일어나도록 하는 것

 → shorthand : `transition: property duration function delay`

### 🤔animation

 - CSS 스타일을 부드럽게 변화시키는 것 ([공식문서 보러가기](https://developer.mozilla.org/ko/docs/Web/CSS/animation)) 

 - 애니메이션을 나타내는 CSS와 애니메이션 시퀀스를 나타내는 키프레임(`@keyframes`)을 사용한다.

 → `@keyframes` : [공식문서 보러가기](https://developer.mozilla.org/ko/docs/Web/CSS/@keyframes)

### 🤔 transform

 - 이동(translate), 회전(rotate), 확대축소(scale), 비틀기(skew) 효과를 줄 수 있다.

 - 2D transform

| transform function | 설명 | 단위 |
| --- | --- | --- |
| translate(x,y) | 요소의 위치를 X축으로 x만큼, Y축으로 y만큼 이동시킨다. | px, %, em 등 |
| translateX(n) | 요소의 위치를 X축으로 x만큼 이동시킨다. | px, %, em 등 |
| translateY(n) | 요소의 위치를 Y축으로 y만큼 이동시킨다. | px, %, em 등 |
| scale(x,y) | 요소의 크기를 X축으로 x배, Y축으로 y배 확대 또는 축소 시킨다. | 0과 양수 |
| scaleX(n) | 요소의 크기를 X축으로 x배 확대 또는 축소 시킨다. | 0과 양수 |
| scaleY(n) | 요소의 크기를 Y축으로 y배 확대 또는 축소 시킨다. | 0과 양수 |
| skew(x-angle,y-angle) | 요소를 X축으로 x 각도만큼, Y축으로 y 각도만큼 기울인다. | +/- 각도(deg) |
| skewX(x-angle) | 요소를 X축으로 x 각도만큼 기울인다. | +/- 각도(deg) |
| skewY(y-angle) | 요소를 Y축으로 y 각도만큼 기울인다. | +/- 각도(deg) |
| rotate(angle) | 요소를 angle만큼 회전시킨다. | +/- 각도(deg) |

 ⭐ transform-origin : 요소의 기본 기준점을 설정할 때 사용 (기본값은 정중앙인 50%,50%)

- 3D transform

| transform function | 설명 | 단위 |
| --- | --- | --- |
| translate3d(x,y,z) | 요소의 위치를 X축으로 x만큼, Y축으로 y만큼 Z축으로 z만큼 이동시킨다. | px, %, em 등 |
| translateX(n) | 요소의 위치를 X축으로 x만큼 이동시킨다. | px, %, em 등 |
| translateY(n) | 요소의 위치를 Y축으로 y만큼 이동시킨다. | px, %, em 등 |
| translateZ(n) | 요소의 위치를 Z축으로 z만큼 이동시킨다. | px, %, em 등 |
| scale3d(x,y) | 요소의 크기를 X축으로 x배, Y축으로 y배, Z축으로 z배 확대 또는 축소 시킨다. | 0과 양수 |
| scaleX(n) | 요소의 크기를 X축으로 x배 확대 또는 축소 시킨다. | 0과 양수 |
| scaleY(n) | 요소의 크기를 Y축으로 y배 확대 또는 축소 시킨다. | 0과 양수 |
| scaleZ(n) | 요소의 크기를 Z축으로 z배 확대 또는 축소 시킨다. | 0과 양수 |
| rotate3d(x,y,z) | 요소를 X축으로 x각도, Y축으로 y각도, Z축으로 z각도 회전시킨다. | +/- 각도(deg) |
| rotateX(x) | 요소를 X축으로 x각도 회전시킨다. | +/- 각도(deg) |
| rotateY(y) | 요소를 Y축으로 y각도 회전시킨다. | +/- 각도(deg) |
| rotateZ(z) | 요소를 Z축으로 z각도 회전시킨다. | +/- 각도(deg) |