# Overview

본 문서는 Bootstrap과 Showdown을 이용하여 간단한 마크다운 기반 CMS(Content Management System)를 구축하는 방법에 대해 기술한다.

### Markdown

마크다운(markdown)은 태그를 사용하지 않는 대신 평문으로 된 텍스트 포맷팅 문법을 갖는 가벼운 마크업 언어이다. HTML 등의 다른 포맷으로 변환해서 보여주는 용도로 설계되었다. [1]

### Bootstrap

[Bootstrap](http://getbootstrap.com/)은 트위터에서 오픈소스로 개발한 웹UI 프레임웍이다. 반응형웹과 다양한 UI컴포넌트들을 제공하며, 쉽게 사용할 수 있는 장점이 있다.

### Showdown

[Showdown](http://showdownjs.com/)은 Javascript로 작성된 마크다운(markdown) 문서를 HTML 문서로 변환해주는 도구이다. Javascript로 작성되었기 때문에 웹 브라우저에서 실행할 수 있으며, NodeJS를 통해 서버에서도 실행이 가능하다.

### CMS 작동 원리

먼저 Bootstrap으로 웹문서 HTML 템플릿을 생성한다. 마크다운 포맷의 문서 파일을 작성한다. jQuery로 마크다운 문서를 로딩하고, Showdown을 통해 HTML로 변환한 다음, 문서의 특정 element에 삽입한다.

### 소스 코드

현재 웹페에지의 소스보기를 하면 문서에 사용된 HTML 템플릿과 Javascript를 확인할 수 있다.

---

[1]: https://en.wikipedia.org/wiki/Markdown