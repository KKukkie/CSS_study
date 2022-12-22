# CSS study

```
CSS : Cascading Style Sheet
```

## 선택자

```
1) 태그 선택자 : DOM 객체 바로 사용 (ex. div)
2) ID 선택자 : DOM 객체 앞에 [#] 명시 (ex. #title)
3) Class 선택자 : DOM 객체 앞에 [#] 명시 (ex. .title)
4) 다중 선택자 : 1,2,3 번 선택자를 혼용하여 사용할 수 있다. 중간에 공백이 없어야 한다. (ex. .title#headline)
5) 자손 선택자 : 어떤 DOM 객체의 하위 객체를 명시하여 선택한다. (ex. div h1 / .box1 .title)
```

## Box

```
- em : 스타일 지정 요소의 font-size 속성 값에 비례하여 값을 결정한다.
> em은 같은 엘리먼트에서 지정된 font-size를 기준으로 px로 바뀌어 화면에 표시된다. 같은 엘리먼트에 설정된 폰트 크기 값이 없을 경우, 상위 요소의 폰트 사이즈가 기준이 된다. em은 같은 엘리먼트는 어디서라도 그 기준이 바뀔 수 있기 때문에 복잡한 css를 가질 경우 변환될 크기를 예측하기 어렵다는 단점이 있다.
(부모 요소의 글꼴 크기)

- pixel (px) : 화면을 구성하는 가장 기본이 되는 단위
> 모니터에 따라 상대적인 크기를 가진다. 반응형 웹에는 적절하지 않다.

- rem : 최상위 html 요소의 font-size 속성 값에 비례하여 값을 결정한다.
> 대개는 HTML tag에서 지정된 font-size가 기준이 된다. 만약 별도의 font-size를 설정하지 않은 경우에는 각 브라우저에서 기본적으로 설정된 값을 상속 받는다.
(루트 요소의 글꼴 크기)

- % (퍼센트) : 부모 요소의 해당 속성 값에 비례하여 지정한 비율의 값을 사용한다.
> 박스의 길이를 화면 크기에 맞춰야할 때 사용한다.


1) width : 가로

2) height : 세로

3) background-color : 배경화면 색

4) padding : top, right, bottom, left 순서로 내용(content)과 테두리(border) 사이의 간격의 크기를 지정한다.
> padding: [top] [right] [bottom] [left];
> padding: 20px 20px 20px 20px;
- padding-top
- padding-right
- padding-bottom
- padding-left

5) border : 경계선
> border : [선 굵기] [선 종류] [선 색깔];
> border : 1px solid blud;
- 선 종류는 검색해볼 것

6) box-sizing : 내용과 테두리 중 어느 것을 기준으로 box 의 크기를 제어할지 선택한다.
- content-box : Content 영역을 기준으로 box 의 size 를 적용
- border-box : Border 영역을 기준으로 box 의 size 를 적용 > 이 설정을 적용해야 알 수 없이 밀리는 레이아웃 이슈를 사전에 막을 수 있다.
* {
    box-sizing: border-box;
}
```

## Font

```
- 폰트 크기 > font-size: 28px;
- 폰트 스타일 > font-style: italic;
- 폰트 꾸미기 (밑줄, 중간선 등) > text-decoration: underline;
- 글자 굵기 조절 > font-weight: 600;
```

## Inline & Block

```
1) 블록 요소 : div > 자동으로 다음 줄로 넘어간다.
> 전후 줄바꿈이 들어가 다른 엘리먼트들을 다른 줄로 밀어내고 혼자 한 줄을 차지
- div, p, ul, dl, p, h~, ...

2) 인라인 요소 : 자동으로 다음 줄로 넘어가지 않는다.
> 전후 줄바꿈 없이 한 줄에 다른 엘리먼트들과 나란히 배치
- a, span, img, strong, em, input, button, textarea, select, ...

3) inline-block 요소 : 전후 줄바꿈 없이 한 줄에 다른 엘리먼트들과 나란히 배치되지만, width와 height 속성 지정 및 margin과 padding 속성의 상하 간격 지정이 가능
> 내부적으로는 block 엘리먼트의 규칙을 따르면서 외부적으로 inline 엘리먼트의 규칙을 따르게 되는 것
- button, input, select, ...

```

## Float + clear

```
- 원래 웹페이지에서 이미지를 어떻게 띄워서 텍스트와 함께 배치할 것인가에 대한 속성

1) inherit: 부모 요소에서 상속
2) left: 왼쪽에 부유하는 블록 박스를 생성. 페이지 내용은 박스 오른쪽에 위치하며 위에서 아래로 흐름.
3) right: 오른쪽에 부유하는 블록 박스를 생성. 페이지 내용은 박스 왼쪽에 위치하며 위에서 아래로 흐름. 이후 요소에 clear 속성이 있으면 페이지 흐름이 달라짐. none 이 아니라면 display 속성은 무시된다.
5) none : 요소를 부유시키지 않음

- clear : 설정된 float 속성을 취소시킨다.

1) clear:none > clear 를 설정하지 않은 것과 같다. 아무 의미 없다.
2) clear:left > 왼쪽을 취소
3) clear:right > 오른쪽을 취소
4) clear:both > 오른쪽 왼쪽을 취소
```

## Flex

```
1) display: flex > flex 레이아웃 속성으로 설정

2) flex-direction : 중심축 설정
- row : 요소들을 열(가로)을 기준으로 배치, 기본값
    - row-reverse : 가로로 배치하지만 요소들을 거꾸로 배치
- column : 요소들을 행(세로)을 기준으로 배치
    - column-reverse : 세로로 배치하지만 요소들을 거꾸로 배치

3) justify-content : 중심축 방향 정렬
- flex-start : 컨테이너의 시작점을 기준으로 정렬, 기본값
- flex-end : 컨테이너의 끝부분을 기준으로 정렬
- center : 컨테이너의 가운데 지점을 기준으로 정렬
- space-between : 컨테이너의 내부 요소들이 같은 간격을 기준으로 정렬 > 시작점과 끝부분에 여백이 없다.
- space-around : 컨테이너의 내부 요소들이 동일한 패딩 간격을 가지며 정렬 > 시작점과 끝부분에 여백이 생긴다. (요소들 간의 간격과 끝부분 사이의 간격이 다르다.)
- space-evenly : 컨테이너의 내부 요소들이 경계선과 모든 요소들 간의 간격이 동일하게 정렬 > 시작점과 끝부분에 여백이 있다. (요소들 간의 간격과 끝부분 사이의 간격이 동일하다.)

4) align-items : 중심축 반대 방향 정렬
가로가 중심축이면 세로 방향, 세로가 중심축이면 가로 방향 적용

- stretch : 중심축 반대 방향으로 컨테이너 양끝점까지 늘린다. 기본값
- flex-start : 컨테이너에서 중심축 반대 방향의 시작점을 기준으로 정렬한다.
- flex-end : 컨테이너에서 중심축 반대 방향의 끝부분을 기준으로 정렬한다.
- center : 컨테이너에서 중심축 반대 방향의 중심을 기준으로 정렬한다.

! flex-item 이 한 줄일 때 우선 적용된다.
> 두 줄 이상일 때에는 align-content 라는 다른 속성을 써주어야 한다.

! flex-direction 이 바뀌면 중심축의 방향이 바뀐다.
> 중심축의 방향이 바뀌면, [justify-content] 와 [align-item] 의 정렬 방향도 함께 바뀐다.

5) 가상 클래스 선택자 : 가상 클래스 선택자는 특정 요소의 상태를 미리 추정해서 가상의 클래스로 스타일을 적용할 수 있는 선택자
- :first-child : 형제 요소 중 첫 번째 요소를 선택하는 가상 클래스

- :first-of-type : 형제 요소 중 첫 번째 요소를 선택하는 가상 클래스
> first-child 와는 다르게 first-of-type 이라는 가상 클래스가 적용된 선택자에 해당 되는 요소만 카운트한다.

- :active : 활성화된 요소를 선택하는 가상 클래스
> 활성화된 요소 : 버튼 등을 클릭해서 요소의 동작이 활성화되어 있는 상태

- focus : focus 를 받고 있는 입력 창 등의 요소를 선택하는 가상 클래스 선택자
> focus 를 받고 있는 요소 : Tab 키 등을 이용해서 입력창의 커서가 활성화되어 있는 상태

- visited : 사용자가 방문한 적 있는 링크를 선택하는 가상 클래스 선택자
> 방문한적 있는 링크 : 링크를 눌러서 해당 경로를 방문한 기록이 브라우저상에 남아 있는 링크 (기본 컬러 : 보라색)

6) 가상 요소 선택자 : 실제로 html 요소를 수정하지 않고 css 만으로 가상 요소를 추가해 선택할 수 있다.
- content 에 반드시 값이 있어야 한다. (빈문자열이라도 (""))

- before : 선택한 요소 이전에 추가
- after : 선택한 요소 이후에 추가

7) 형제 요소 선택자

A ~ B {
    property : value
}

- A 와 같은 부모를 가지고 있은 형제 요소들 중 B 를 선택한다.

8) flex-wrap : flex-item 이 여러개일 때, item 들의 줄바꿈을 허용 여부를 결정한다.
- nowrap : 줄바꿈을 허용하지 않는다. 기본값
- wrap : 자연스럽게 줄바꿈이 발생한다.

9) aligh-content : 여러 줄이 된 Flex-item 의 중심 반대 축 정렬을 어떻게 할 지 결정한다.
- stretch : 쭉 늘어남. 기본값
- flex-start : 시작점을 기준으로 정렬함.
- flex-end : 끝부분을 기준으로 정렬함.
- center : 중앙을 기준으로 정렬함.
- space-between, space-around, space-evenly : 3번 justify-content 와 설명 동일

10) flex-flow : flex-direction 과 flex-wrap 을 합쳐놓은 단축 속성
[flex-direction: row;] + [flex-wrap: wrap;] = [flex-flow: row wrap;]

11) flex-item 속성들
- order : item 의 순서를 지정
- flex-basis : item 의 기본 사이즈를 지정
- flex-shrink
- flex-grow

```

## 상속

```
1) 상속되는 속성
- color, font-family, font-size 등

2) 상속되지 않는 속성
- padding, margin, border 등

3) 여러 개의 상속 속성이 겹쳤을 때, cascading 룰이 우선순위를 결정한다.
```

## 구글 폰트 적용

```
1) https://fonts.google.com 접속

2) 맨 오른쪽 [Use on the web] 탭에서 [@import] 부분을 복사한다.
<style> @import url('https://fonts.googleapis.com/css2?family=Song+Myung&display=swap'); </style>

3) html 헤더에 붙여 넣는다.

4) css 에서 적용한다.
div {
  font-family: "Song Myung", serif;
}
```

## Cascading

```
[수많은 스타일 요소 중 어떤 스타일을 브라우저에 그릴지 결정해주는 CSS 우선순위 적용 원리]

1) 중요도
- CSS 가 선언된 위치에 따라 우선순위가 결정된다.
    > 사용자나 개발자가 따로 설정하지 않았는데도 설정되는 기본 스타일

- 브라우저 스타일 시트 : 브라우저 개발자가 만든 기본 스타일 시트

- 사용자 스타일 시트 : 웹페이지 사용자가 직접 설정하는 스타일 시트
    > 사용자 폰트 지정
    > 고대비 모드 사용

- 개발자 스타일 시트 : 웹개발자가 직접 만든 스타일 시트
    > 개발자 시트 안에서도 우선순위를 가진다.
    [ <link> 로 연결한 css 파일 ] < [ <style> 요소 안에 있는 CSS ] < [ 인라인 스타일 CSS ]

- 적용 우선순위 : 브라우저 < 사용자 < 개발자


2) 구체성 (명시도)
- 선택할 대상을 구체적으로 특정할수록 명시도가 높아진다.
    > 명시도가 높아지면 우선순위도 함께 높아진다.

[부모에게 상속받은 속성] < [전체 선택자] < [태그 선택자] < [클래스 선택자 & 가상 선택자] < [ID 선택자]
                          *      <     div    <        .                <     #

- 강제로 명시도 끌어올리기 : [ !important ]
* {
    color: red!important;
}


3) 선언 순서
- 나중에 선언한 스타일이 우선 적용된다.
#text-id {
    color: violet
}

#text-id {
    color:teal
}

> teal 색깔이 적용된다.

```

## Background

```

background : [color] [image] [repeat] [positoin/size] [attachment]

> background : red url("../star.png") no-repeat center/cover fixed

```

## 상대 단위 - vw / vh

```
[요소의 규격을 viewport 의 너비값과 높이값에 비례하여 결정합니다.]

- viewport : 브라우저 안에서 실제로 화면이 그려지는 영역


```

## position

```
[HTML 요소가 배치되는 방식을 결정하는 속성]

(x, y, z 축)

- top / left / bottom / right : 해당 방향 기준으로 요소의 좌표값을 변경한다.

- position: static
    > 요소를 문서상 원래 있어야 하는 위치에 배치한다.
    > 기본값
    > top/left/bottom/right 적용 불가

- position: relative
    > 원래 있던 자리를 기준으로 요소의 위치를 조정할 수 있다.
    > top/left/bottom/right 적용 가능

- position: absolute
    > viewport 의 절대 좌표를 기준으로 요소의 위치를 조정할 수 있다.
    > top/left/bottom/right 적용 가능

- position: fixed
    > 스크롤과 무관하게 viewport 를 기준으로 요소의 위치를 설정할 수 있다.
    > viewport 가 기준

- position: sticky
    > 요소의 원래 위치에 있다가 스크롤이 내려가면 지정한 좌표에 고정된다.
    > static 과 fixed 를 혼합해서 사용하는 것과 같음
    > 부모 요소의 좌표가 기준

- [z-index]
    > 여러개의 요소가 겹쳐져 있을 때, 무엇이 앞으로 나올지 결정하는 속성
    > 값이 클수록 앞에 위치한다.

```

## Transition

```
[CSS 스타일 변화 시점을 부드럽고 자연스럽게 처리할 수 있게 해주는 기능이다.]

- trasition-property
    > 어떠한 속성(property) 에 transition 을 적용할 것인지 지정한다.
    > transition-property: color, transform

- transition-duration
    > transition 에 걸리는 시간을 지정한다.
    > transition-duration : 0.2s

- transition-timing-function
    > transtion 의 속도 패턴을 지정한다.
    > transition-duration: ease-in-out
        > linear : 일정한 속도로 변화한다.
        > ease : 시작할 때는 빨라지다 점차 느려진다.
        > ease-in : 천천히 시작하다가 점차 빠르게 끝난다.
        > ease-out : 빠르게 시작하다가 점차 천천히 끝난다.
        > ease-in-out : 천천히 시작하다가 정상 속도가 됐다가 빠르게 끝난다.

- transition-delay
    > transition 요청을 받은 후, 실제로 실행되기까지 기다려야하는 시간의 양을 지정한다.
    > transition-delay: 2s

- 단축 속성
    transition: [property] [duration] [timing-function] [delay]
    > transition: color 0.4s ease-in-out 1s

```

## Transform

```
[요소에 이동, 회전, 확대/축소, 비틀기 등의 변형 효과를 줄 수 있다.]
[변환 함수를 중첩 적용 시키는 것이 가능한 속성이다.]

(* deg : 각도)


- translate(x, y)
    > 요소의 좌표를 움직일 수 있다.
    > X축으로 x만큼, Y축으로 y만큼 이동시킨다.
    > transform: translate(20px, 25%)
    > translateX(n), translateY(n)

- scale(x, y)
    > X축으로 x만큼, Y축으로 y만큼, 요소를 축소 혹은 확대한다.
    > transform: scale(0.75, 1.1)
    > scaleX(n), scaleY(n)

- skew(x, y)
    > X축으로 x만큼, Y축으로 y만큼, 요소를 기울인다.
    > transform: skew(15deg, 10deg)
    > skewX(n), skew(n)

- rotate(n)
    > 요소를 n만큼 회전시킨다.
    > transform: rotate(45deg)

- 중첩 적용
    > 요소를 y축 방향으로 0.75 축소 + x축 방향으로 20도 기울이려면?
        => transform: scaleY(0.75) skewX(20deg)

```

## Animation

```
[여러 이미지를 연결해서 자연스럽게 움직이는 것처럼 보이게 만드는 기법]

> transition 을 이용해서 애니매이션을 만들었다.
> animation 속성과 keyframe 을 활용해서도 만들 수 있다.

- transition : 특정한 이벤트를 기점으로 작동한다. (hover 등)

- animation : 시작하기 위한 이벤트가 필요 없다. 시작, 정지, 반복까지 제어할 수 있다.
    > @keyframes 로 애니메이션을 정의하고, 정의한 애니메이션을 불러와서 제어해주어야 한다.
    > 또 @keyframes 로 다시 제어하는 로직을 만들어야 한다.
    > 매우 귀찮다...
    > transition 으로는 만들 수 없는 애니메이션을 이 속성으로 만들면 된다.

- keyframes (@keyframes)
    > CSS 애니메이션의 시작, 중간, 끝 등의 중간 상태를 정의한다.

@keyframes moveRight { // moveRight : 애니메이션 이름
    from { // 시작 시점 정의
        left: 0;
    }
    to { // 종료 시점 정의
        left: 200px;
    }
}

@keyframes moveRight { // moveRight : 애니메이션 이름
    0% { // 시작 시점 정의
        left: 0;
    }
    50% { // 중간 시점 정의
        left: 200px;
    }
    100% { // 종료 시점 정의
        top: 200px;
        left: 200px;
    }
}

- animation-name
    > 어떠한 keyframes 를 요소에 적용할 것인지 지정한다.
    > animation-name: moveRight

- animation-duration
    > 애니메이션을 한 번 재생하는데 걸리는 시간을 설정한다.
    > animation-duration: 2s

- animation-direction
    > 애니메이션 재생 방향을 정의한다. (정방향/역방향)
    > animation-direction: alternate
        > normal (기본값) : 정방향 재생
        > reverse : 역방향 재생
        > alternate : 정방향 재생, 반복 시 정방향/역방향을 번갈아 재생
        > alternate-reverse : 역방향 재생, 반복 시 역방향/정방향을 번갈아 재생

- animation-iteration-count
    > 애니메이션 재생 횟수를 정의한다.
    > animation-iteration-count: infinte
        > infinite : 무한
        > n : n번 재생

- animation-timing-function
    > 애니메이션 재생 패턴을 정의한다.
    > transition-timing-function 과 유사하다.

- animation-delay
    > 애니메이션 시작을 얼마나 지연할 지 설정한다.
    > animation-delay: 2s

- 단축 설정
    animation: [name] [duration] [timing-function] [delay] [iteration-count] [direction]
    > animation: moveRight 0.4s linear 1s infinite alternate


```

## Grid

```

- Flex 의 대체 레이아웃이 아니다.
- 큰 규모의 레이아웃 구성에 적합
- 레이아웃 구조가 확실하게 잡혀있는 경우, 효율적으로 반응형 디자이인 구현할 수 있다.
- 단, 그리드는 상대적을 최신 기술이기 때문에 모든 브라우저에서 지원하지 않는다.

- fr
    > fraction (분수) 의 약자
    > grid-template 에서 사용할 수 있는 비율 단위
        > grid-template-columns: 1fr 2fr 200px
        > grid-template-columns: 1fr 2fr 1fr 1fr

- repeat(a, b)
    > grid-template 에서 사용할 수 있는 반복 함수 b 규격의 grid-template 을 a 개 생성한다.
    > grid-template-columns: repeat(4, 1fr) == grid-template-columns = 1fr 1fr 1fr 1fr
    > grid-template-columns: 3fr repeat(2, 1fr 200px) == grid-template-columns = 3fr 1fr 200px 1fr 200px

```

## 미디어 쿼리

```

[viewport 의 너비에 따라 웹사이트의 스타일 시트를 수정할 수 있다.]
> viewport 너비 이외에도 단말기의 종류, 해상도 등을 기준으로 설정할 수 있다.

@media [조건문] {}

@media screen and (max-width: 500px) {
    // 스크린의 viewport 너비가 500px 이하일 경우
    // 적용시킬 스타일 시트
}

```

## BreakPoint

```

[반응형 웹사이트 작업의 기준이 되는 중단점을 말한다.]
> PC / 태블릿 / 모바일의 기준이 되는 규격 분기

[중단점] (> 절대적인 규격은 없다. 임시로 나눈 것 뿐이다.)
- Mobile : 0 ~ 767px
- Tablet : 768px ~ 1023px
- PC : 1024px ~ 1439px
- PC Large : 1440px ~


```

## 반응형 웹에서 자주 사용하는 속성 정리

```

- max-width & max-height : 해당 요소의 최대 너비 or 최대 높이를 설정합니다.
    > max-width: 1240px;

- min-width & min-height : 해당 요소의 최소 너비 or 최소 높이를 설정합니다.
    > min-width: 420px;

- max : 소괄호 안에 입력된 값 중 제일 높은 값을 속성값으로 출력하는 함수.
    > height: max(320px, 20%)

- min : 소괄호 안에 입력된 값 중 제일 낮은 값을 속성값으로 출력하는 함수.
    > height: min(1240px, 100%)


```
