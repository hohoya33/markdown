# 본문

네이게이션 클릭 시 링크 URL을 jQuery의 get 함수로 로딩하고, Showdown 으로 변환한 뒤 본문 영역에 추가한다.

```javascript
$('.sidebar').on('click', '.nav-link', function() {
    $.get($(this).attr('href'), function(md) {
        var html = converter.makeHtml(md);
        $('.main-content').html(html);
    });

    return false;
});
```

Bootstrap 의 스타일을 적용하기 위해 변환된 HTML 태그에 Bootstrap 의 class 를 추가해준다.

```javascript
var classmap = new Map([
    // ['<태그>', '<<Bootstrap class>'],
    ['h1', 'h2 py-3 mb-3 border-bottom'],
    ['table', 'table table-striped table-bordered'],
    ['pre', 'alert alert-secondary']
]);

$('.sidebar').on('click', '.nav-link', function() {
    $.get($(this).attr('href'), function(md) {
        var html = converter.makeHtml(md);
        classmap.forEach(function(value, key) {
            html = html.replace(new RegExp(`<${key}(.*)>`, 'g'), `<${key} class="${value}" $1>`);
        })
        $('.main-content').html(html);
    });

    return false;
});
```