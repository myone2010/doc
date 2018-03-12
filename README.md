# 웹 콘솔/대시보드 문서

## 지원 브라우저

![Chrome](https://raw.github.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png) 
--- |
Latest ✔ 

## 주요 라이브러리
> Web-console 핵심 라이브러리만 기술

- Django 2.0
- Django REST Framework 3.7.7
- requests 2.18.4
- apscheduler 3.5.1
- Materialize CSS
- Wavesurfer.js

## 디렉토리 구조

### Top-level 디렉토리

    /web-console
    ├── Dockerfile              # Dockerfile
    ├── README.md               # Setup
    ├── docs                    # Webconsole docs
    ├── hana_project            # Django setting, root url
    ├── static                  # public files (js,css,img)
    ├── templates               # html templates
    ├── users                   # Login, Signup, Dashboard page (view, url)
    ├── fileupload              # Audio upload page (model, view, url, templatetags)
    ├── api                     # Api page (model : Decode, After, Cpu-usage, etc), view, url
    ├── result                  # Decode, After result page (view, url)
    ├── manage.py               # Django Main file
    ├── requirements.txt        # python package setup
    └── Pipfile                 # pipenv package setup


`hana_project` 폴더는 Django 기본 세팅 및 루트 URL 설정

`static` 폴더는 정적 파일 (js,css,img)

`templates` 폴더는 html 템플릿 (공통으로 사용)

`users` 폴더는 로그인, 가입, 대시보드 관련 View, URL

`fileupload` 폴더는 음성 업로드 페이지 관련 Model, View, Templatetags, URL

`api` 폴더는 Audio 모델을 제외한 모든 모델 정의 및 API 설정 (View, URL)

`result` 폴더는 음성인식 결과 페이지 조회 관련 View, URL



## 클래스 다이어그램

### 파일업로드, 음성인식, 후처리 모델 관계
> `Audio`의 기본키가 `Decode`의 file_id로 외부키 참조됨, 그리고 `Decode`의 기본키가 `After`의 decode_id로 외부키 참조됨.
> 외부키 설정에서 `on_delete=models.CASCADE` 사용으로 파일이 삭제되면 연결된 해당 Decode, After도 같이 삭제됨.



![alt text][class-image1]

### 대시보드 및 기타 API
>  테스트를 위한 REST API로 사용 (실제로는 마스터, 클러스터와 직접 연동)  


![alt text][class-image2]



[class-image1]: https://github.com/myone2010/doc/blob/master/%EA%B7%B8%EB%A6%BC1.png?raw=true
[class-image2]: https://github.com/myone2010/doc/blob/master/%EA%B7%B8%EB%A6%BC2.png?raw=true



## HTML 템플릿

### base.html
web-console/templates/base.html

```html
<html>
<head>
  ...
</head>
<body>
           {% block content %}
             <h1>No content set</h1>
           {% endblock %}
</body>
</html>
```

웹 콘솔의 헤더 NAV, 왼쪽 사이드 NAV 템플릿이 정의되어있고, 

{% block content %} {% endblock %} 사이에 해당 Contents가 연동됨.

### login.html
web-console/templates/registration/login.html

```html
{% extends 'base.html' %}

{% block title %}Login{% endblock %}

{% block content %}

<form method="POST" action="{% url 'login' %}" class="sign-in-form">
    
                      <!-- 로그인 양식 -->
    
<input type="submit" class="save btn btn-success" value="로그인">
</form>

{% endblock %}
``` 

블록으로 연결되는 base.html 정의 후 로그인 폼 생성 

Model : django.contrib.auth.models.User 내장 클래스 사용

View : Django에 내장된 로그인 View 사용

### signup.html
web-console/templates/registration/signup.html

```html
{% extends 'base.html' %}

{% block title %}Signup{% endblock %}

{% block content %}

<form method="post">
    
                      <!-- 가입 양식 -->
    
<input type="submit" class="save btn btn-success" value="생성">
</form>

{% endblock %}
``` 

블록으로 연결되는 base.html 정의 후 가입 폼 생성 

Model : django.contrib.auth.models.User 내장 클래스 사용

View : Django에 내장된 Signup View 사용 (users.views의 signup 클래스에서 커스텀화)


### home.html
web-console/templates/home.html

```html
{% extends 'base.html' %}

{% block title %}Home{% endblock %}

{% block content %}
{% if user.is_authenticated %}


    
                      <!-- 대시보드 내용 -->
    

{% else %}
<meta http-equiv='refresh' content='0;url={% url 'login' %}'>

{% endif %}

{% endblock %}

``` 


{% if user.is_authenticated %} 로 유저 로그인 여부 검사

아닐시 로그인 페이지로 강제 리플래시됨.

Model : api.models의 Decode, After 모델 사용

View : users.views의 dashboard 사용

