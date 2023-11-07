# softeng_2023_django


ref: <https://gist.github.com/rpq/4536415>

`-` static 폴더경로 문제

프로젝트 `urls.py` 파일 하단에 아래의 코드를 추가합니다.

```python
from django.contrib import admin
from django.urls import path, include
from django.contrib.staticfiles.urls import staticfiles_urlpatterns


urlpatterns = [
    path("admin/", admin.site.urls),
    path('', include('single_pages.urls')),
    path("blog/", include('blog.urls'))
]

urlpatterns += staticfiles_urlpatterns()
```
