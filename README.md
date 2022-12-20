# CSS study

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
- div, p, ul, dl, p, h~, ...

2) 인라인 요소 : 자동으로 다음 줄로 넘어가지 않는다.
- a, span, img, strong, em, input, button, textarea, select, ...
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
