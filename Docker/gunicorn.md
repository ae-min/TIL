# gunicorn

python WSGI로 WEB Server(Nginx)로부터 서버사이드 요청을 받으면
WSGI를 통해 서버 애플리케이션(Django)으로 전달해주는 역할 수행

Django의 python manage.py runserver 역시 똑같은 역할을 수행하지만,
보안 및 성능적으로 검증되지 않았기 때문에 배포용으로는 사용 불가함

client - nginx(web server) - gunicorn(WSGI) - django(application server)

---

## WSGI
파이썬 애플리케이션이 웹서버와 통신하기 위한 인터페이스.
웹서버에서의 요청을 해석하여 파이썬 애플리케이션 쪽으로 전달하는 역할 수행
