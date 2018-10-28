# 네비게이션

템플릿 HTML 파일을 브라우저에서 로딩한 다음 네비게이션 파일을 로딩하여 표시한다. 네비게이션 파일 역시 마크다운으로 작성한다. 아래는 본 문서에서 사용한 네비게이션 마크다운 문서이다.

```markdown
###### Simple Markdown CMS

[Overview](overview.md)
[Bootstrap Template](bootstrap.md)
[Showdown](showdown.md)
[네비게이션](navigation.md)
[본문](content.md)

---

###### Examples

[REST API Document](rest-api.md)
[Markdown Example](markdown-example.md)
```

위 문서를 Showdown으로 HTML로 변환하고, 사이드바 영역에 추가한다.

```javascript
var html = converter.makeHtml(md);
$('.sidebar').html(html);
```

Showdown 으로 생성된 HTML은 다음과 같다.

```html
<p><a href="overview.md">Overview</a>
<a href="template.md">HTML 템플릿</a>
<a href="navigation.md">네비게이션</a>
<a href="content.md">본문</a></p>
<hr />
<p><a href="example.md">Example</a></p>
```

불필요한 여백이 생성되는 것을 방지하기 위해 p 태그를 제거하고, Bootstrap의 네비게이션 컴포넌트에서 사용하는 스타일 적용을 위해 a 태그에 클래스를 추가한다.

```javascript
var html = converter.makeHtml(md);
html = html.replace(/<[/]?p>/g, '');
html = html.replace(/<a href="/g, '<a class="nav-link" href="');
$('.sidebar').html(html);
```

그러면 다음과 같은 HTML이 생성된다.

```html
<a class="nav-link" href="overview.md">Overview</a>
<a class="nav-link" href="template.md">HTML 템플릿</a>
<a class="nav-link" href="navigation.md">네비게이션</a>
<a class="nav-link" href="content.md">본문</a>
<hr />
<a class="nav-link" href="example.md">Example</a>
```

첫번째 항목에 대해 click 이벤트를 발생시켜 문서가 로딩되도록 한다.

```javascript
$('.sidebar a.nav-link:first').click();
```