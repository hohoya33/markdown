# Showdown

Showdown은 CDN으로 제공되는 스크립트를 웹페이지에 삽입한다. 그리고, 마크다운을 HTML로 변환하기 위해 Converter 객체를 생성한다. 본 문서에서는 table 마크다운을 사용하기 위해 tables 옵션을 추가하였다.

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/showdown/1.8.6/showdown.min.js" 
    integrity="sha256-dwhppIrxD8qC6lNulndZgtIm4XBU9zoMd9OUoXzIDAE=" crossorigin="anonymous"></script>
<script type="text/javascript">
var converter = new showdown.Converter({
    tables: true
});
</script>
```

