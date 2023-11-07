# softeng_2023_django




`-` static 폴더경로 문제

static 폴더를 만든 후 css파일을 넣고 경로지정까지 완료 한 후에도 웹에 스타일이 적용이 안되는 문제가 발생한다면 아래와 같이 해결할 수 있습니다.
static폴더의 경로를 못 찾는 문제


```python
# 프로젝트 `urls.py` 파일 하단에 코드를 추가합니다.

from django.contrib.staticfiles.urls import staticfiles_urlpatterns

# ... the rest of your URLconf goes here ...

urlpatterns += staticfiles_urlpatterns()
```
- ref: <https://gist.github.com/rpq/4536415>
