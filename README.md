# softeng_2023_django




`-` static 폴더경로 문제

static 폴더를 만든 후 css파일을 넣고 경로지정까지 완료 한 후에도 웹에 스타일이 적용이 안되는 문제가 발생한다면 아래와 같이 해결할 수 있습니다.
> static폴더의 경로를 못 찾는 문제


```python
# 프로젝트 `urls.py` 파일 하단에 코드를 추가합니다.

from django.contrib.staticfiles.urls import staticfiles_urlpatterns

# ... the rest of your URLconf goes here ...

urlpatterns += staticfiles_urlpatterns()
```
- ref: <https://gist.github.com/rpq/4536415>


`-` post_detail.html <body>에 아래의 코드 추가

```python
<div class="card mb-4">
    <img class="card-img-top" src="http://placehold.it/750x300" alt="Card image cap">
    <div class="card-body">
        <h2 class="card-title">{{ p.title }}</h2>
        <p class="card-text">{{ p.content }}</p>
        <a href="{{ p.get_absolute_url }}" class="btn btn-primary">Read More &rarr;</a>
    </div>
    <div class="card-footer text-muted">
        Posted on {{ p.created_at }} by
        <a href="#">작성자명 쓸 위치(개발예정)</a>
    </div>
</div>
```
***(주의)*** : `blog/templates/blog/index.html` 은 이제 필요없는 파일이다. (경로를 자동으로 post_detail로 잡아주면서 index.html은 필요없어졌다.)
