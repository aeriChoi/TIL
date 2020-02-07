# DOM

## DOM\(Document Object Model\)

DOM은 문서의 구조화된 표현을 제공하여 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법을 제공한다. 이를 통해 문서 구조, 스타일, 내용 등을 변경할 수 있게 돕는다. 

* 문서 객체 모델
* HTML, XML 문서의 프로그래밍 인터페이스 
* 원본 HTML 문서의 객체 기반 표현 방식
* 구조화된 nodes와 property 와 method 를 갖고 있는 objects로 문서를 표현한 것 
* 웹 페이지를 프로그래밍 언어가 사용 수 있게 연결 시켜주는 역할을 담당한다. \(동적 자원\)

### DOM인 것과 아닌 것 

#### 1. 원본 HTML문서는 DOM이 아니다.

작성한 HTML문서가 브라우저에 의해 파싱 되어 생성된 것이 DOM이다.

* _DOM이 원본 HTML 소스와 다를 때_
  * 작성된 HTML 문서가 유효하지 않을 때
  * JavaScript에 의해 DOM이 수정될 때
  * Ajax등의  [클라이언트 사이드 템플리팅](https://css-tricks.com/video-screencasts/127-basics-of-javascript-templating/)을 사용했을 

#### 2. DOM은 브라우저에서 보이는 것이 아니다.

브라우저에 보이는 것은 렌더 트리로 DOM과 CSSOM의 조합이며 시각적으로 보이지 않는 요소들은 제외되기 때문에 DOM과는 다르다.

#### 3. DOM은 개발도구에서 보이는 것이다?

개발자 도구의 요소 검사기는  DOM과 유사하나 완전히 일치하는 것은 아니다. 개발자 도구의 요소 검사기는 DOM 단순화시켜 표현한 것이며 DOM의 일부가 아닌 CSS 가상 요소를 포함하기에 완전히 DOM이라고 할 수는 없다.





### 참조

* [DOM 소개 - MDN](https://developer.mozilla.org/ko/docs/Web/API/Document_Object_Model/%EC%86%8C%EA%B0%9C)
* [DOM이란 무엇인가? - velog](https://velog.io/@surim014/DOM%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80) \([@surim014](https://velog.io/@surim014)\)
* [DOM이란 무엇인가? - velog](https://velog.io/@godori/DOM%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80) \([@godori](https://velog.io/@godori)\)

