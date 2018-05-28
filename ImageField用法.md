# Step1:
    在settings.py 里加上url和root
    MEDIA_URL = '/lab/media/'
    MEDIA_ROOT = os.path.join(BASE_DIR, 'lab/media')
# Step2:
    在app/urls.py 里加上
    from django.conf.urls.static import static
    from django.conf import settings
    urlpatterns =[
      --snip--
    ]+static( settings.MEDIA_URL , document_root=settings.MEDIA_ROOT )
# Step3:
    在*.html里使用的时候，例如
    <img  src={{ article.photo.url }} width="200px" height="200px">
    <p><a href={{article.file.url}}>{{ article.title }}</a></p>
