# Web

분류: Web
날짜: 2024년 1월 19일
설명: Web의 개념, 동작원리와 html, css, JavaScript의 기초
학습 목표: Web과 프론트엔드의 기초를 이해해 추후 다양한 직무와의 협업에 있어 타 팀에 대한 이해도와 식견을 넓힌다.

# ✅ Web

## ■ Web이란

- 최초의 웹사이트: info.cern.ch
- HTML을 토대로 CSS, JS가 입혀신 형식이 웹 사이트
- 인터넷을 활용해 거미줄처럼 연결된 정보 소통망 - World Wide Web

## ■Web의 발전 과정

- Web은 1989년 처음 탄생한 이래로 지속적으로 발전해왔다.
- Web 1.0(1990년 중반~2000년대 초반)
    - 문서를 기반으로한 정적 컨텐츠가 주였다.
    - HTML, CSS 같은 웹 표준이 등장했다.
- Web 2.0(2000년대 중반~)
    - 사용자 참여와 상호작용이 강조되었다.
    - JavaScript의 등장으로 동적 컨텐츠가 주가 되었다.
    - AJAX 기술의 도입으로 리로딩 없이 비동기적 데이터 교환이 가능해졌다.
- Web 3.0
    - CGI(common gateway interface) 기술의 도입으로 웹 서버-외부 프로그램 간의 데이터 교환 방법이 정립되었다.
- Web 4.0
    - HTML5 표준의 등장으로 Adobe Flash Player이 완전히 대체되었다.
    - 사용자 접근성을 중시하는 방식으로 HTML이 업그레이드되었다.
    - JavaScript가 표준 언어로 지정되었다.

## ■ Web의 동작방식

- Web이 동작하려면 최소 2대의 컴퓨터가 필요하다
- 한 대에는 정보를 저장하고(Server), 한 대는 정보를 열람한다.(Client)
- Client는 Server에 요청(request)을 보내고 Server는 Client에 응답(response)한다.
    
    ![Untitled](https://github.com/dotorimuk1112/TIL/blob/main/Web/Web/Untitled.png)
    
    <aside>
    💡 **HTTP
    HTML**로 이루어진 텍스트를 네트워크를 통해 송수신하는 규약(약속)
    HTML로 이루어진 소스 파일은 서버에 존재하고,
    브라우저는 서버로부터 HTML 소스 파일을 전송 받아서 화면에 표현한다.
    
    </aside>
    - HTML: 웹 페이지의 구조와 내용
    - CSS: 웹 페이지의 모양
    - JavaScript: 웹 페이지의 행동 및 응용 프로그램

---

# ✅ HTML

## ■ 기본 특징

- `< >`를 이용해 표현한다.
- 열리고 닫히는 태그 구조를 띈다.
    - `<제목 시작> 제목 내용 </제목 끝>`의 형태
- HTML 코드 내의 연속된 공백, 줄바꿈은 한 칸의 space로 취급한다.
    - 더 긴 공백은 &nbsp; 등으로 표현할 수 있다.
    - 줄바꿈은 <br>로 표현하거나 블록 기반 태그를 사용한다.
- 블록 기반 태그와 인라인 기반 태그
    - 블록 태그: h, p, ol, li, ul
        - 세로로 쌓이는 태그
        - 해당 태그를 사용하면 태그의 내용이 한 행을 모두 차지한다.
        - 자연히 줄이 바뀌어 출력된다.
            
            ```html
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.
            Dolore possimus consequuntur assumenda nam enim laudantium
            officia tempora doloremque, corrupti rerum.
            Mollitia quam quis provident quo, ut maxime sit corporis ex.</p>
            ```
            
            - <p> 태그를 이용해 긴 내용 아래에 입력하는 다른 태그는 줄이 바뀌어 출력된다.
    - 인라인 기반 태그: a, img, span <br>
        - 가로로 쌓이는 태그
        - 특별히 줄을 바꿔주지 않는 이상 연속된 태그는 아랫줄이 아닌 옆에 이어진다.
- 부모와 자식 요소
    - A태그가 B태그의 컨텐츠로 사용되면, 태그B는 태그A의 부모요소, 반대는 자식 요소가 된다.
    - 들여쓰기를 하지 않아도 작동하는 데에 문제는 없지만 가독성과 부모-자식 관계의 표현을 위해 들여쓰기를 한다.
    

## ■ 기본 태그

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

- vs code 환경에서 !를 입력하고 enter를 통해 자동완성을 사용하면 위와 같은 html 기본 양식을 바로 불러올 수 있다.

---

### 1. Heading

- 제목 표현 태그

```html
<h1> 가장 큰 제목 </h1>
<h3> 중간 제목 </h3>
<h5> 소제목 </h5>
```

- 출력 예시
    
    ![Untitled](Whttps://github.com/dotorimuk1112/TIL/blob/main/Web/Web/202.png)
    

### 2. Paragraph

- 문단, 단락 표현

```html
<p> 일반적으로 텍스트를 표현하는 용도로 사용이 됩니다 </p>
```

- 다음과 같이 단락 사이에 구분을 위한 공백이 생긴다.
    
    ![Untitled](https://github.com/dotorimuk1112/TIL/blob/main/Web/Web/203.png)
    

### 3. List

- List에는 세 가지 종류가 있다.
    - `<ol>`: Ordered LIst - 정렬 리스트
    - `<ul>`: Unordered List - 비정렬 리스트
    - `<dl>`: Description List - 정의, 설명을 위한 리스트
    
    ```html
          	<ol> 순서있는 리스트
                <li> 첫번째</li>
                <li> 두번째</li>
                <li> 세번째</li>
            </ol>
    
            <ul> 순서없는 리스트
                <li> 첫번째</li>
                <li> 두번째</li>
                <li> 세번째</li>
            </ul>
    ```
    
- 출력 결과
    
    ![Untitled](https://github.com/dotorimuk1112/TIL/blob/main/Web/Web/204.png)
    

### 4. Table

```html
<table border=1> <!-- 테이블의 시작 -->
    <thead> <!-- 제목 라인 -->
      <tr> <!-- 행을 표현 -->
        <th>제목</th> <!-- 컬럼 -->
        <th>날짜</th> <!-- 컬럼 -->
        <th>조회수</th> <!-- 컬럼 -->
      </tr>
    </thead>
   
    <tbody> <!-- 표에 들어갈 내용 -->
      <tr> <!-- 행을 표현 -->
        <td>안녕하세요</td> <!-- 컬럼 -->
        <td>2024-01-19</td> <!-- 컬럼 -->
        <td>3</td> <!-- 컬럼 -->
      </tr>
      <tr> <!-- 행을 표현 -->
        <td>안녕하세요2</td> <!-- 컬럼 -->
        <td>2024-01-20</td> <!-- 컬럼 -->
        <td>333</td> <!-- 컬럼 -->
      </tr>
    </tbody>
   </table> <!-- 테이블의 끝 -->
```

- 출력 결과
    
    ![Untitled](https://github.com/dotorimuk1112/TIL/blob/main/Web/Web/205.png)
    

### 5. anchor

- 하이퍼링크
    
    ```html
    <a href="https://www.google.com" target="_blank">구글로 이동</a>
    ```
    
    ![Untitled](https://github.com/dotorimuk1112/TIL/blob/main/Web/Web/206.png)
    
    - anchor 태그와 href 속성를 이용해 흔히 아는 하이퍼링크를 만들 수 있다.

## ■ 레이아웃

- div를 통해서 배치한다.
- semantic tag를 통해 배치한다.
- table을 이용해 배치한다.
    - 과거에 사용하는 표준 방식으로 HTML5 표준부터는 사용하지 않음

- **iframe**
    - inline frame의 약자로 웹 페이지 안에 또 다른 웹페이지를 표현하는 법
        
        ```html
        <iframe width="560" height="315"
        src="https://www.youtube.com/embed/링크"
        title="YouTube video player" frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
        picture-in-picture; web-share" allowfullscreen></iframe>
        ```
        
        - 이런 코드로 아래와 같이 유튜브 재생창을 웹 페이지로 불러올 수 있다.
        
        ![Untitled](https://github.com/dotorimuk1112/TIL/blob/main/Web/Web/207.png)
        

# ✅ Bootstrap