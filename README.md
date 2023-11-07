# softeng_2023_django




`-` static 폴더경로 문제

static 폴더를 만든 후 css파일을 넣고 경로지
프로젝트 `urls.py` 파일 하단에 아래의 코드를 추가합니다.

```python
from django.contrib.staticfiles.urls import staticfiles_urlpatterns

# ... the rest of your URLconf goes here ...

urlpatterns += staticfiles_urlpatterns()
```
- ref: <https://gist.github.com/rpq/4536415>
