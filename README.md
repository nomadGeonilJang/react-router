# Base for Front End Developer

## 🌟 WEB APIs

- 브라우저에 대해서 이해하자!

1. DOM APIs
2. NetWork APIs
3. Graphics APIs
4. Audio/Vidoe APIs
5. Device APIs
6. File APIs
7. Storage APIs

> 관련자료 읽어 보세요
>
> 1. [MDN Web API](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Introduction)
> 2. [Web API collection](https://developer.mozilla.org/en-US/docs/Web/API)
> 3. [Security](https://www.thoughtco.com/what-javascript-cannot-do-2037666)

### Browser 구조 분석

1. Window : 전체적인 창( size, scroll, load)
   - DOM + BOM(navigator, location, fetch, storage) + Javascript
2. Document : 작성한 HTML이 보이는 곳

> 1.  [size](https://nomadgeoniljang.github.io/2020-front-101/window-size/)
> 2.  [좌표](https://nomadgeoniljang.github.io/2020-front-101/window-position)

### load

1. async, defer("Contend Loaded 이전에")
   - <script src="" defer or async>
2. window.addEventListener("load",()=>{})
   - 모든리소스 로딩 (image, css, js...etc)
   - "DOMContentLoaded" : only HTML
   - "beforeunload" - 페이지에서 나갈떄 발생
   - "unload" - resource is being unload

### PROJECT

- [project1](https://nomadgeoniljang.github.io/2020-front-101/project1-coordinates/)
- [project2](https://nomadgeoniljang.github.io/2020-front-101/project2-rabbits/)

## 💥 DOM 정복하자!

- [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
- [DOM API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_DOM_API)

1. Document Object Model
   - 브라우저는 HTML tag를 분석해서 Node로 만든다 -> DOM Tree🌴 를 만든다!!!.
   - HTML tag는 그와 같은 엘레먼드가 있다. (Memory에 저장이 된다.)
   - Event Target <- Node <- (Document, Element(HTMLElement), Text)

### 1️⃣ Node

- [Node](https://developer.mozilla.org/en-US/docs/Web/API/Node)
- [Event Target](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)

1. 모든 노드는 이벤트 타겟이다.
   - addEventListener()
   - removeEventListener()
   - dispatchEvent()

### 2️⃣ CSSOM

- [CSSOM](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model)

1. (HTML)DOM + CSS(external, embedded, inline, user-aget stylesheet) = CSSON
   - compute styles based on CSS cascading rules

![CSSOM](https://raw.githubusercontent.com/nomadGeonilJang/2020-front-101/master/public/images/csson.png)

### 3️⃣ ⚜️ 성능보장 렌더링 순서!!!

1. Critical rendering path
   [css trigger](http://csstriggers.com)

   - request/response -> loading ->scripting -> redering -> layout -> painting

   1. Construction : time to first render
      - 불필요한 태그⬇️ + CSS⬇️
      - DOM + CSSOM + RenderTree
   2. Operation

      - Paint를 자주 발생하지 않게 만든다!!!
      - Composition만 발생할 수 있도록 한다.

      - Layer 별로 준비를 한다!
        - 브라우저가 스스로 성능을 개선하기 위해서 - 전체 적인 web을 그리는 것이아니라 layer만 그리면 된다.
      - Layout(배치) + Paint(각 요소, 비트맵 형태로 만들어서 준비 한다.) + Composition

![render](https://raw.githubusercontent.com/nomadGeonilJang/2020-front-101/master/public/images/render.png)

## 💥 DOM 정복하자 실전편!

- [Shopping](https://nomadgeoniljang.github.io/2020-front-101/project3-shopping/)
- [FontAwesome](https://fontawesome.com/)
- [CSS Gradient](https://cssgradient.io/)
- [Box Shadow CSS Generator](https://www.cssmatic.com/box-shadow)

### Bubbling and Capturing

- [Bubbling and Capturing](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#Event_bubbling_and_capture)

1. 버블링이란?
   - 자식에서 부모로 이벤트가 전파되는 현상
   - event.stopPropagation()
   - event.stopImmediatePropagation()
     - 하지만 사용하지 말자!! 다른 사람이 무엇을 하려고 리슨하고 있는거를 무시해버리는 것!!
   - target: 발생시킨 주체
   - currentTarget: this 바로 나를 가르킨다.

### 이벤트 위임 : Delegation

- 이벤트 등록을 부모에 하나 등록해서 자식에서 발생하는 이벤트를 ㅈ처리하게한다!
  - event.target과 event.currentTarget를 잘 활용하면 되요!!

## this의 바인딩

- bind, call, apply
- arrow function

1. document.addEventListener("click", this.onClick.bind(this))
   - 함수를 인자로 전달할 떄는 클래스 정보는 같이 전달 되지 않아요!!
   - 그렇기 때문에 클래스 내부의 정보를 전달할 수 없다!!

## Builder Patter

- 무언가 오브젝트를 만들 떄 Builder Pattern을 이용해서 오브젝트를 간단 명료하게 가독성이 좋게 만들 수 있다.
