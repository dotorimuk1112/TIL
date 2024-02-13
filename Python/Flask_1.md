# Flask_1

분류: Python
날짜: 2024년 2월 13일

![Untitled](Flask_1/Untitled.png)

<aside>
💡 **Flask**
파이썬 기반의 웹 프레임워크.
웹 프레임워크 중에서도 쉽고 가볍다.
별다른 라이브러리 없이 독단적으로 기본적인 화면 구성이 가능하다.

</aside>

### 가장 기초적인 코드

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello World!"
```

- Flask를 import
- app이라는 객체에 Flask 선언
- 기본 사용 포트인 localhost:5000에 접속하게 되면 출력될 화면
    
    ![Untitled](Flask_1/Untitled%201.png)
    

### Blueprint(청사진) 사용하기

<aside>
💡 **Blueprint**
Flask의 모듈화, 구조화를 위한 도구
URL 라우팅과 view template을 분리해 적용함으로써 관리 및 유지보수가 쉬워진다.
예를 들면, 네이버의 ‘www.naver.com/blog’와 ‘www.naver.com/cafe’를 나누어 관리하는 기능이다.

</aside>

```python
from flask import Blueprint, render_template
from ..models import Question, Answer

# Blueprint 객체 정의, url 라우팅 설정
# 기본 url에 /blueprint를 붙인 url은 모두 해당 blueprint의 종속됨.
board = Blueprint('board', __name__, url_prefix="/board")

# localhost:5000/board/post
@board.route("/post")
def post_list():
    var = 1 + 2
    return render_template('question_list.html', var=var)

# 해당 url에 대한 작업을 수행한다.
```

### Jinja2

<aside>
💡 Jinja
Python으로 작성된 탬플릿 엔진
Java의 JSP와 동일하게 동적 웹 페이지 생성을 위해 사용되며, 문법 또한 유사하다.

</aside>

- JSP와 Jinja2의 문법 비교
    
    
    | JSP | Jinja2 |
    | --- | --- |
    | <% %> | {% %} |
    | <%= %> | {{ }} |
    | <%— —%> | {# ... #} |
    | <%@ include file="header.jsp" %> | {%include 'header.html' %} |
    
- **반복문**
    
    ```html
    <ul>
    {% for item in items %}
        <li>{{ item }}</li>
    {% endfor %}
    </ul>
    ```
    
    - 기본적으로 python 문법을 따름
    - endfor 구문이 반드시 포함되어야 함
- **조건문**
    
    ```html
    {% if user.is_authenticated %}
        <p>Welcome, {{ user.username }}!</p>
    {% else %}
        <p>Please log in.</p>
    {% endif %}
    ```
    
    - 마찬가지로 기본 python 문법과 같음
    - endif로 구문을 끝내야 정상작동함.
    

### ■ render_template

- render_template은 controller에서 처리한 변수를 html 화면으로 전송하는 방법임
    
    ```python
    @board.route("/calculate")
    def calculate():
        answer = 1+2
        return render_template("test.html", answer=answer)
    ```
    
    - calculate라는 화면으로 이동 시, 1 + 2를 answer 변수에 저장하고 test.html 화면으로 전달함
    
    ```python
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        test 화면입니다. <br>
        1 + 2 = <br>
        ------------ <br>
        {{ answer }} <br>
    </body>
    </html>
    ```
    
    - 전달 받은 answer 변수는 jinja 문법에 따라 중괄호 두 개로 출력함 → **{{ answer }}**
    - **출력 화면**
        
        ![Untitled](Flask_1/Untitled%202.png)