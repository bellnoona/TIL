# Position

> - absolute
> - relative
> - fixed
> - top, left, right, bottom
> - z-index

<br><br>

<h2> <span style="color: #808080; background-color: #fff5b1;">1. position이란?<span> </h2>
이름에서처럼, <span style="color: #ffd33d;">position</span>이란 웹 페이지에서 우리가 만들었던 html 태그나 id, class 박스 등의 <span style="color: #ffd33d;">위치를 지정해주는 속성</span>이다. position 속성을 이용해 우리는 페이지의 <span style="color: #ffd33d;">레이아웃</span>을 결정할 수 있다.

<br>

<h2> <span style="color: #808080; background-color: #fff5b1;">2. Position의 종류<span> </h2>

<h3> <span style="color: #808080; background-color: #fff5b1;">2.1 static<span> </h3>
<span style="color: #ffd33d;">기본적으로</span> 모든 태그들은 따로 position 속성값을 주지 않았다면 <span style="color: #ffd33d;">static 값</span>을 가진다. 즉 html에 쓴 태그 순으로 위치가 지정되게 됩니다. 그래서 굳이 기입할 필요는 없지만, 부모 객체에서 다른 position 속성값이 주어졌을 때, 그를 무시하기 위해 사용될 때가 있다.

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <title>static</title>
    <style>
      .box1 {
        position: static;
        background-color: green;
        color: white;
        width: 100px;
        height: 100px;
      }
      .box2 {
        position: static;
        background-color: red;
        color: white;
        width: 100px;
        height: 100px;
      }
      .box3 {
        position: static;
        background-color: blue;
        color: white;
        width: 100px;
        height: 100px;
      }
    </style>
  </head>
  <body>
    <div class="box1">box1</div>
    <div class="box2">box2</div>
    <div class="box3">box3</div>
  </body>
</html>
```

![position static 이미지](/imgs/static.png)  
▶️ 이렇게 static은 차례대로 엘리먼트를 놓습니다!

<br>

<h3> <span style="color: #808080; background-color: #fff5b1;">2.2 relative<span> </h3>

단어 자체의 뜻처럼 <span style="color: #ffd33d;">'상대적'</span>인 속성을 가지고 있다. 그럼 대체 <span style="color: #ffd33d;">'무엇'</span>에 상대적일까? 바로 static, 즉 <span style="color: #ffd33d;">원래 자신이 있어야 하는 위치</span>에 상대적이다. relative는 그 누구보다도 자신이 원래 있던 자리를 기억하는 요소이다. 그래서 `position: relative;`라는 값을 주고 `left: 50px;` 이라고 추가적으로 적어 주면, 본인의 static 자리에서 왼쪽으로 50px만큼 떨어진 자리에 위치하게 된다.

- 내가(relative를 준 태그) 밀리는 만큼 다음 콘텐츠들이 밀리지 않는다는 것이다.
- 하단에 로렘입숨을 넣어 콘텐츠가 어떻게 인식되고 있는지 확인할 것.

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <title>relative</title>
    <style>
      .box1 {
        position: static;
        background-color: green;
        color: white;
        width: 100px;
        height: 100px;
      }
      .box2 {
        position: relative;
        left: 40px;
        background-color: red;
        color: white;
        width: 100px;
        height: 100px;
      }
    </style>
  </head>
  <body>
    <div class="box1">box1</div>
    <div class="box2">box2</div>
  </body>
</html>
```

![position relative 이미지](https://paullabworkspace.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F125f0653-a389-4383-997f-bd0b4927e51b%2FUntitled.png?table=block&id=d955177a-378c-4a0c-bbaa-3087e80c9f7e&spaceId=579fe283-28aa-489d-ae65-d683304becfc&width=2000&userId=&cache=v2)   
▶️ relative 속성을 주어 box2가 원래 있어야 할 자리에서 왼쪽으로 40px 떨어뜨린 모습이다.

<br>

<h3> <span style="color: #808080; background-color: #fff5b1;">2.3 absolute<span> </h3>

absolute의 특징을 굳이 한 단어로 설명하자면 <span style="color: #ffd33d;">'my way'</span>라고 할 수 있다. `position: absolute;`라고 한 뒤 `top : 20px; right: 30px;`이라고 추가적 값을 주면, 오른쪽 상단에 동떨어진 박스가 하나 놓여있는 것을 보실 수 있다. 이들은 기준점이 html 위치에 있기에, 왼쪽 제일 상단이 본래 자신의 위치라고 생각하고 움직이게 된다.

그러나, 이 absolute도 눈치를 보는 녀석이 있는데, 바로 부모 요소이다. relative, absolute, fixed 같은 position 속성이 부모에 놓여있다면, absolute는 position 속성을 가진 가장 가까운 부모의 박스 내를 기준으로 위치하게 된다. 마치 relative가 static의 자리를 유념하고 있는 것처럼 말이다.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>relative-absolute</title>
    <style>
      .box1 {
        position: relative;
        top: 40px;
        background-color: green;
        color: white;
        width: 100px;
        height: 100px;
      }
      .box2 {
        position: absolute;
        top: 40px;
        background-color: red;
        color: white;
        width: 100px;
        height: 100px;
      }
      .box3 {
        position: absolute;
        top: 30px;
        left: 30px;
        background-color: blue;
        color: white;
        width: 100px;
        height: 100px;
      }
    </style>
  </head>
  <body>
    <div class="box3">box3</div>
    <div class="box1">
      box1
      <div class="box2">box2</div>
    </div>
  </body>
</html>
```

![position absolute 이미지](https://paullabworkspace.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F772bfe1b-c72c-4426-b21c-894b731e191e%2FUntitled.png?table=block&id=b5e63ea3-d241-4eac-8e64-a2f6915529cd&spaceId=579fe283-28aa-489d-ae65-d683304becfc&width=2000&userId=&cache=v2)

❕ <span style="color: #808080; background-color: #f7ddbe;">결과 상세설명</span>  
상단의 코드를 웹페이지에 구현한 사진이다. 이처럼 relative 속성에 구애받지 않는 box3은 left와 top에 어느 정도 px을 두어 떨어뜨렸을 때 상단 제일 왼쪽을 기준점으로 움직였다면, relative 속성인 box1 내에 구속받는 box2는 `top: 40px;` 값을 주었을 때, box1의 위치를 기준으로 움직였음을 확인하실 수 있다. 즉 box2와 3에서 확인할 수 있듯 똑같이 `position: absolute;` 의 속성을 가지고 있어도, 상위 엘리먼트가 relative 속성을 가졌는지 아닌지에 따라 서로 다른 위치 결과가 나타난다는 것이다.

▶️ box3의 부모 = html 이므로 화면 맨윗부분 왼쪽에서 밑, 오른쪽으로 30px씩 떨어진 부분에 위치.  
▶️ box2(absolute)의 부모 = box1(relative => static이 아닌 가장 가까운 부모 요소) 아므로 box1에서 위로 40px 떨어진 부분에 위치.

<br>

<h3> <span style="color: #808080; background-color: #fff5b1;">2.4 fixed<span> </h3>

스크롤을 올리거나 내릴 때, 특정 박스가 고정되어 움직이지 않았으면 한다면, 이 fixed 속성을 이용하면 된다! `position: fixed`를 기입하면, `absolute` 가 `position` 속성을 가진 가장 가까운 부모를 기준으로 위치를 정하는 것처럼, fixed는 현재 사용자가 보고 있는 뷰포트를 기준으로 마치 화면에 붙은 것처럼 그 자리에 계속해서 위치할 것이다. 요즘 많은 사이트들이 페이지가 스크롤 되어도 중요한 정보(네비게이션 같은)를 화면에 계속 노출 시켜주기 위해 많이 사용하는 속성이다.

![position fixed gif파일](https://velog.velcdn.com/images/tngusglaso/post/672b6530-0746-46fc-950c-3e766b681ad1/image.gif)

위 검색 결과 화면에서 스크롤을 내려도 상단의 검색 창은 사라지지 않고 뷰포트 상단에 고정되어 있는 모습을 확인할 수 있다.  
▶️ 아래 이미지처럼 크롬 개발자 도구에서 header 클래스에 적용된 `position: fixed` 속성을 직접 확인해볼 수 있다.  
![naver fixed 이미지](/imgs/naver_fixed.png)

<br>

<h3> <span style="color: #808080; background-color: #fff5b1;">2.5 sticky<span> </h3>

아래 예제에서 스크롤을 내려보면 sticky된 요소는 부모에 붙는 것을 볼 수 있다.

- IE 지원하지 않는다!([https://caniuse.com/?search=sticky](https://caniuse.com/?search=sticky))
- ❕ <span style="color: #ffd33d;">fixed는 스크롤에서 차이가 발생</span>한다.(sticky는 부모요소에 달라붙는다.) => 아래에서 자세히 설명!

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <style>
      section {
        height: 1000px;
        border: 3px solid black;
      }

      h2 {
        position: -webkit-sticky;
        position: sticky;
        top: 0;
        background: greenyellow;
      }
    </style>
  </head>

  <body>
    <h1>sticky test</h1>
    <section>
      <h2>오늘의 메뉴1</h2>
      <ul>
        <li>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Laborum
          dolore distinctio doloremque, modi repudiandae officiis ullam eos
          iusto ea quis incidunt quisquam excepturi quas fugiat, architecto cum
          natus eligendi culpa?
        </li>
        <li>
          Sed, accusamus a quos, unde in ad adipisci enim libero nesciunt
          suscipit eveniet ut quisquam! Nam molestias alias aperiam saepe id at
          voluptate iusto explicabo. Ea ratione doloremque saepe perspiciatis!
        </li>
        <li>
          Non, quam labore reprehenderit eligendi voluptatem porro? Vel a vitae
          non voluptate, doloribus culpa reiciendis nemo! Est voluptates soluta
          sint officia autem, nisi doloribus cum quod iusto, rerum aut
          voluptatibus?
        </li>
      </ul>
    </section>
    <section>
      <h2>오늘의 메뉴2</h2>
      <ul>
        <li>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. In mollitia
          fugit minima facere voluptatum labore hic tenetur, molestiae
          asperiores. Facilis repellendus harum ullam debitis possimus non
          cumque, beatae nemo ducimus.
        </li>
        <li>
          Laborum cum molestias, unde ea magnam eligendi quod aspernatur tempora
          ullam quos facilis quaerat quas iste sed animi voluptas nostrum
          laboriosam eius repellat voluptate corrupti aut. Ratione corporis quod
          velit.
        </li>
        <li>
          Mollitia quod quae tempore eum reiciendis beatae dolorem animi, in hic
          error quaerat eius tenetur, distinctio, esse nesciunt? Quae eligendi
          facere corrupti aspernatur? Rem quo eos fuga! Asperiores, voluptatem
          iusto!
        </li>
      </ul>
    </section>
    <section>
      <h2>오늘의 메뉴3</h2>
      <ul>
        <li>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam
          excepturi sed dicta quasi unde porro aperiam illo placeat eos ducimus
          repellendus eum minus modi alias dolores laudantium quod, tempore ab!
        </li>
        <li>
          Unde iusto aliquam eum ullam perspiciatis quis laborum tenetur cum
          quia iste. Nesciunt aperiam soluta quo impedit voluptatum sunt iure,
          architecto odio ut perspiciatis fuga ad corporis. Repellendus, quo
          sunt.
        </li>
        <li>
          Sit omnis sed, distinctio atque dolor dicta possimus voluptas,
          repellendus vel non consequuntur ducimus ipsa? Numquam et minus
          repudiandae enim sit necessitatibus. Aliquam culpa quisquam cupiditate
          exercitationem, eveniet earum autem?
        </li>
      </ul>
    </section>
  </body>
</html>
```

![position sticky gif파일](/imgs/sticky.gif)

<br>

<span style="font-size: 20px; font-weight: 600;"> ⁉️ `position: fixed;` vs `position: sticky;`</span>  
▶️ 아래 두개의 git 같은 예제로 position 속성만 fixed, sticky로 변경한 결과이다.

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <style>
      .container:after {
        content: ' ';
        display: block;
        clear: both;
      }
      section {
        width: 800px;
        padding: 50px;
        float: left;
      }
      aside {
        border: solid 1px black;
        float: left;
        width: 200px;
        height: 800px;
        padding: 20px;
        /* fixed로 고치고 그 차이를 설명해보세요. */
        position: sticky;
        top: 50px;
      }
    </style>
  </head>
  <body>
    h1{hello world}+(p>lorem)*2 .container>(section>h2{hello
    world}+(p>lorem)*20)+aside>h3{hello world}+p>lorem
  </body>
</html>
```

1️⃣ `position: fixed;`   
![position fixed 비교 예제](/imgs/fixed-ex.gif)

2️⃣ `position: sticky;`   
![position sticky 비교 예제](/imgs/sticky-ex.gif)   
  
 
▶️ `fixed`는 문서 흐름에서 완전히 이탈된다. viewport에 고정되어서 스크롤을 해도 지정된 자기 위치에서 절대 움직이지 않는다.  
반면, `sticky`는 일반적인 문서 흐름에 따라 배치된다. 스크롤을 따라 움직이다가 가장 가까운 부모 element 기준으로 배치된다. 내가 정한 offset에 닿으면 그 순간부터 fixed 처럼 고정이 되다가 해당 부모의 위치가 스크롤에서 벗어나면 고정되던 위치가 사라진다. 최초에 relative 속성처럼 동작하다가 스크롤이 특정 지점에 도달하면 fixed 속성으로 동작하는 것이다.

<br>

<h3> <span style="color: #808080; background-color: #fff5b1;">2.6 z-index<span> </h3>   

z-index는 자신이 있어야하는 위치에 상대적인 값을 가진다. 단, 부모가 z-index를 높여 자식 앞으로 나올 수 없다. 자식은 z-index를 낮춰 부모 뒤로 가는 것은 가능하다.
![z-index 이미지](https://paullabworkspace.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fb4b18be5-cc40-4f7f-b8cb-0ef49084ae15%2Fx-index.png?table=block&id=afc1c9e6-4ad5-4f3d-9c52-972cf5a9665a&spaceId=579fe283-28aa-489d-ae65-d683304becfc&width=2000&userId=&cache=v2)  

```htlm
<!DOCTYPE html>
<html lang="ko">
<head>
    <style>
        div {
            /* 같이 움직이는지 확인 */
            /* margin: 100px; */
            width: 800px;
            height: 800px;
            position: relative;
            background-color: blanchedalmond;
            border: 1px solid black;
            /* 부모에 달아도 수정이 안됨 */
            /* z-index: 1; */
        }

        img {
            padding: 10px;
            position: absolute;
        }

        img:nth-child(1) {
            top: 100px;
            left: 100px;
            background-color: red;
            /* 자식에게 값을 주면 부모 뒤로 감 */
            z-index: 0;
        }

        img:nth-child(2) {
            top: 150px;
            left: 150px;
            background-color: green;
            z-index: 0;
        }

        img:nth-child(3) {
            top: 200px;
            left: 200px;
            background-color: blue;
            z-index: 0;
        }
    </style>
</head>
<body>
    <div>
        <img src="https://via.placeholder.com/300" alt="">
        <img src="https://via.placeholder.com/400" alt="">
        <img src="https://via.placeholder.com/500" alt="">
    </div>
</body>
</html>
```

![z-index 이미지](/imgs/z-index.png)

<br>

---

▶️ 참고  
<https://velog.io/@moripark32/%EB%82%B4%EA%B0%80-%EB%AA%B0%EB%9E%90%EB%8D%98-HTMLCSS-part-5.-postionfixed-%EC%99%80-sticky%EC%9D%98-%EC%B0%A8%EC%9D%B4>  
<https://ordinary-code.tistory.com/106>
