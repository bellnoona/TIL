# Grouping Contents

<br>

그룹화 관련 요소는 아래와 같다.

> `<ol>`, `<ul>`, `<li>`  
> `<dl>`, `<dt>`, `<dd>`  
> `<div>`  
> `<figure>`, `<figcaption>`  
> `<p>`  
> `<pre>`  
> `<blockquote>`  
> `<main>`  
> `<hr>`

<br><h2> <span style="color: #808080; background-color: #fff5b1;"> `<ol>`, `<ul>`, `<li>`<span> </h2>

`<ol>`은 ordered list의 약자로 **순서가 있는 목록**을 뜻하며, `<ul>`은 unordered list의 약자로 **순서가 없는 목록**을 뜻한다. `<li>`는 각 **항목**들을 나열하는 태그로 list item을 뜻한다.  
❗️ 주의할 점은 `<li>` 요소는 `<ol>` 혹은 `<ul>` 요소 안에서만 사용되어야 하며, `<ol>`, `<ul>` 의 직계 자식 요소로는 `<li>` 요소만 사용되어야 한다.

```html
<h1>분야별 공부 분야 추천</h1>
<h2>Front-End</h2>
<ol type="A">
  <li>HTML</li>
  <li>CSS</li>
  <li>Javacript</li>
  <li>Jquery</li>
  <li>Bootsrap</li>
</ol>
<h2>Back-End</h2>
<ul>
  <li>Python</li>
  <li>Django</li>
</ul>
```

![ol, ul, li 예제](/imgs/ol_ul_li.png)

<br><h2> <span style="color: #808080; background-color: #fff5b1;"> `<dl>`, `<dt>`, `<dd>`<span> </h2>

`<ol>`, `<ul>`, `<li>`가 목록을 정의할 때 쓰였듯이 `<dl>`, `<dt>`, `<dd>` 도 목록을 정의할 때 쓰인다.  
❔ 차이점이 있다면 `<dl>`, `<dt>`, `<dd>`는 사전처럼 어떠한 것을 **정의**할 때 쓰이는 목록이다.  
`<dl>`은 **정의 목록**(definition list)이며 `<dt>`는 **정의할 용어**(definition term)을 뜻한다. `<dd>`는 **용
어를 설명**(definition description)할 때 쓰인다.

```html
<dl>
  <dt>HTML</dt>
  <dd>마크업 언어입니다.</dd>
</dl>
```

![dl, dt, dd 예제](/imgs/dl_dt_dd.png)

<br><h2> <span style="color: #808080; background-color: #fff5b1;"> `<div>`<span> </h2>

`<div>`는 레이아웃을 나눌 때 사용하는 태그이다. 이 태그는 컨텐츠의 형태를 변형시키지는 않지만 **하위에 있는 여러 요소를 묶어 스타일을 변경**시킬 수 있다.  
`<article>`, `<section>`, `<header>`, `<nav>`는 기본적으로 **`<div>`와 같은 역할**을 한다.  
❔ 차이점이 있다면 **태그에 의미를 부여한 것**이다. 예를 들어 내용이 하나의 독립된 컨텐츠라면 `<div>` 대신 `<article>`을 사용한다. 바꿔 말해 `<article>`, `<section>`, `<header>`, `<nav>` 모두 `<div>`로 대신 사용할 수 있으나, 보다 적합한 요소를 찾아본 후에도 대용할 태그가 없을 경우 사용하길 바란다.

```html
<div>hello</div>
```

![div 예제](/imgs/div.png)

<br><h2> <span style="color: #808080; background-color: #fff5b1;"> `<figure>`, `<figcaption>`<span> </h2>

웹페이지를 탐색하다보면 가끔, 아래 이미지처럼 캡션(자막, 설명)이 있는 이미지를 접할 때가 있다.  
![figure 이미지](https://paullabworkspace.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F28afb5bd-2e99-4dc1-a8f6-c047f5c112a3%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-10-30_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_7.15.01.png?table=block&id=d3b0319d-b21e-4d1d-8e97-894912f8711f&spaceId=579fe283-28aa-489d-ae65-d683304becfc&width=2000&userId=&cache=v2)

이러한 컨텐츠의 경우 이미지와 캡션이 연결되도록 `<figure>` 요소를 도입할 수 있다.

```html
<figure>
  <img src="images/baby.jpg" alt="엄마 코끼리와 아기 코끼리" />
  <figcaption>관심 받고싶어하는 아기</figcaption>
</figure>
```

`<figcaption>` 요소는 이미지에 캡션을 추가하기 위해 도입되었으며 `<figure>`, `<figcaption>`요소가 나오기 이전에는 `<img>` 요소와 해당하는 캡션을 연결할 방법이 없었다.

<br><h2> <span style="color: #808080; background-color: #fff5b1;"> `<p>`<span> </h2>

`<p>`태그는 단락을 표시하는 태그이다. **하나의 완결된 문단**을 의미하기 때문에 **<p>태그 안에 자식으로 `<p>`를 또 사용하지 않으며**, 줄바꿈의 용도로 사용해서도 안된다.  
❕ p태그 안에 p태그 ❌  
❕ 줄바꿈 용도 사용 ❌

```html
<h1>hello world</h1>
<p>hello world</p>
```

![p태그 예제](/imgs/p.png)

<br><h2> <span style="color: #808080; background-color: #fff5b1;"> `<pre>`<span> </h2>

HTML에 작성한 내용 그대로 화면에 표현한다. 주로 컴퓨터 코드를 표현할 때 사용한다.

```html
<pre>
  <code>
    let val= 1;
    function myFunc(value){
      return value;
    }
    myFunc(val);
  </code>
</pre>
```

![pre태그 예제](/imgs/pre.png)

<br><h2> <span style="color: #808080; background-color: #fff5b1;"> `<blockquote>`<span> </h2>

- 인용 블록이다.
- q는 인용구 이다. 주로 문장 안에서 사용된다.
- `<cite>`요소는 저작물의 출처를 표기할 때 사용하며, 제목을 반드시 포함해야 한다.

```html
<blockquote>
  <p>제발 그만해.. 이러다가 다~~ 죽어!</p>
  <cite>오징어게임 오일남</cite>
</blockquote>

<p><q>제발 그만해.. 이러다 다~~ 죽어!</q>라고 오일남이 소리쳤습니다.</p>
<p></p>
```

![blockquote 예제](/imgs/blockquote.png)

<br><h2> <span style="color: #808080; background-color: #fff5b1;"> `<main>`<span> </h2>

HTML `<main>` 요소는 **문서의 주요 컨텐츠**를 나타낸다.

주요 컨텐츠 영역이란 문서의 **핵심 주제나 웹어플리케이션의 핵심 기능에 직접적으로 연결**되어 있는 부분을 뜻한다. 메인 요소안에 들어가는 내용은 문서의 **유일한 내용**이어야 한다.

다른 페이지나 섹션에서 반복적으로 표시될 수 있는 정보, 예를 들어 사이트 로고, 검색 폼, 저작권 정보 등은 들어가지 않는다.

❕ IE 에서는 지원하지 않는 **비교적 최근에 등장**한 요소임으로 사용에 주의가 필요하다.

![main요소 예제](https://paullabworkspace.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fb0d8d4eb-cc42-4d31-b16c-708714bd2dff%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-10-31_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_12.34.16.png?table=block&id=78c3f694-3614-41cd-96fe-e21ecb315b16&spaceId=579fe283-28aa-489d-ae65-d683304becfc&width=2000&userId=&cache=v2)  
▶️ _main 요소안에 사이트의 메인 컨텐츠를 모두 담아두고 있는 에어비엔비 사이트 예시_

<br><h2> <span style="color: #808080; background-color: #fff5b1;"> `<hr>`<span> </h2>

`<hr>` 태그는 원래는 가로줄을 표현하기 위해 사용했으나 HTML5에 오면서 **의미가 생긴** 요소이다. 이야기에서의 장면 전환 혹은 문단 안에서 주제가 변경되었을 때 그 구별을 위해 사용한다.  
❕ 단락을 구분할 때 사용하므로 `<p>`태그 내 사용은 웹 표준에 어긋난다.

```html
<h1>hello world</h1>
<hr />
<p>
  hello <br />
  world
</p>
<hr width="300px" align="left" size="3" color="red" noshade />
```

![hr 예제](/imgs/hr.png)
