# Content categories (컨텐츠 카테고리) / Sections

> HTML5 이전에는 HTML 태그 요소를 inline(인라인) 요소와 block(블록) 요소를 구분하는 정도로만 분류했었다.  
> HTML5 이후부터는 요소별로 공통 특성을 공유하는 것끼리 그룹화하여 **카테고리**를 나누었다. 이렇게 그룹화한 것들을 **Contents Model (컨텐츠 모델)** 이라고 한다.  
> 아래의 그림과 같이 요소의 특성에 따라 총 7개의 카테고리로 분류한다.

- Metadata Content
- Flow Content
- Sectioning Content
- Heading Content
- Phrasing Content
- Embedded Content
- Interacitve Content

[![Sectioning Content](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories/content_categories_venn.png)](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories)

<br>

## Metadata Content

메타데이터 컨텐츠 카테고리에 속한 요소는 문서의 표현이나 동작을 수정하거나, 다른 문서를 가리키는 링크를 설정하거나, 기타 정보를 전달한다.  
이 카테고리에 속하는 요소는 `<base>`, `<link>`, `<meta>`, `<noscript>`, `<script>`, `<style>`, `<title>` 이다. 대부분 `<head>` 내에 들어간다는 것이 특징이다.

- `<meta>` : 문서의 정보를 포함하는 메타데이터
- `<style>` : 스타일 표현을 위한 스타일
- `<script>` : 행동 설정을 하는 스크립트 요소
- `<link>` : 외부의 자원을 문서와 연결하는 역할
- `<title>` : 문서의 제목을 의미하는 것으로 반드시 한번만 사용되어야 한다.

## Sectioning Content (구획 컨텐츠)

**Sectioning Content** 란 의미가 연결되는 컨텐츠의 집합을 나타낸다.  
Heading Content와 `<footer>` 를 정의하는 컨텐츠이다.  
이 범주에 속하는 요소는 `<article>`, `<aside>`, `<nav>` 및 `<section>` 이다.

## Heading Content (제목 컨텐츠)

Sectioning Content의 제목을 정의하는 컨텐츠이다.  
이 카테고리에 속하는 요소는 `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>` 및 `<hgroup>` 이다.  
<br>
![HTML Sections](https://paullabworkspace.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Faf935819-7f52-4de6-bdcb-a658a4ed1d01%2Fsection_fin.png?table=block&id=7af6cb15-bf67-4339-9e44-42c5ac77ded8&spaceId=579fe283-28aa-489d-ae65-d683304becfc&width=2000&userId=&cache=v2)
![Sectioning Content](https://paullabworkspace.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F561ed611-72a9-4e72-af3a-4daeb19c9909%2FUntitled.png?table=block&id=0905182b-4083-40d3-9314-aae473fc6ddf&spaceId=579fe283-28aa-489d-ae65-d683304becfc&width=2000&userId=&cache=v2)

- `<body>` : 실제 사용자에게 보여지는 문서의 컨텐츠를 나타내는 요소이다.

- `<header>` : 특정한 컨텐츠의 시작 부분을 나타내는 요소이다. 일반적으로 구역의 제목을 포함한다.

<br>

> ⭐️ `article` 개념이 다소 헷갈리기 때문에 확실히 기록하고 넘어가고자 한다! ⭐️

- `<section>` : 일반적으로 연관성 있는 문서의 구획을 나누고자 할 때 사용하는 요소이다.

- `<article>` : 독립적으로 재사용하거나 구분할 수 있는 구획을 나타낸다.  
  예를 들면, 블로그 게시물, 신문 기사, 제품 카드, 위젯 등이 있다.  
  아래 이미지는 mdn 사이트 예시인 날씨 위젯 이미지다.  
  이처럼, `article` 이라는 요소는 **독립적이어야** 한다!  
  혼자만 똑 떼어놓고 봤을 때도 무슨 내용인지 알 수 있고, 또 어색함이 없어야 한다.  
  그렇지 않은데 `article` 로 감싼다면 어색하다.

  (재현 강사님께서는 비유를 하자면, 미니 html 파일이라고 보면 이해가 쉽다고 하셨다.  
  `article` 안에도 조그맣게 `header`, `main`, `footer`가 있을 수 있다.  
  독립적인 컨텐츠이니 그 안에서도 또 주제, 내용이 있을 수 있으니 말이다.)

  하나의 문서에 여러 개의 `article`이 포함될 수 있다.  
  예컨대 사용자가 스크롤하면 계속해서 다음 글을 보여주는 블로그의 경우, 각각의 글이 `article` 요소가 되며, 그 안에는 또 여러 개의 `section`이 존재할 수 있다.

  ![mdn 날씨 위젯](/imgs/widget.png)

> 💡 **`section`** vs **`article`**
>
> - `article` 요소는 독립적 콘텐츠 (다른 서비스에 가져다 놔도 이상하지 않음)
> - `section` 요소는 사이트 내 연관 콘텐츠 (다른 서비스에 가져다 놓으면 이상함)
> - `article`과 `section` 요소는 **heading 요소와 함께 사용**하는 것을 권장 (높이 없이 비워두기도 함)

- `<nav>` : `nav` (네비게이션, 탐색) 요소는 보통 메뉴에 사용된다.

```html
<nav>
  <a href="https://paullab.co.kr">바울랩</a>
  <a href="https://naver.com">네이버</a>
  <a href="https://google.com">구글</a>
</nav>
```

- `<aside>` : 해당 컨텐츠와는 별개 컨텐츠 (메인 컨텐츠와 간접적으로 관련된 부분)  
  보통 사이드바나 광고 영역으로 활용한다.  
  이미지처럼 꼭 오른쪽일 필요는 없다.(다른 요소도 마찬가지)
  ![aside 예시 이미지](https://paullabworkspace.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fa95fa398-2fb0-48ca-8371-9550dbc0535c%2FUntitled.png?table=block&id=35739c03-d01f-4a2d-9121-744d15d4cdf3&spaceId=579fe283-28aa-489d-ae65-d683304becfc&width=2000&userId=&cache=v2)  
  ![mdn aside 이미지](/imgs/aside-img.png)

- `<h1>` ... `<h6>` : heading은 제목을 지정하기 위해 사용된다.  
   `<h1>내용</h1> ~ <h6>내용</h6>` 까지 중요도에 따라 사용되며, **단순히 글자를 크게 하거나 굵게 하기 위해 사용되지 않는다.**(이런 부분은 css로 처리하면 된다!)  
   `<h1>` 요소는 페이지당 한번만 사용할 것을 권장한다.  
   heading 요소를 사용하면 익명 영역(anonymous section)을 생성한다. 같은 레벨의 헤딩요소를 만나기 전까지가 모두 해당 헤딩 요소의 익명영역이라 생각하면 된다.  
   ![heading Tag 익명영역](/imgs/heading_Tag_anonymous_section.png)

  > ▶︎ 참고만 하기!  
  > 익명영역이 너무 이해가 안가서 우여곡절이 있었다.  
  > 결론은, 헤딩 태그가 열리면 익명영역이 생성되고, 새로운 같은 헤딩태그를 만나면 익명영역이 종료된다.  
  > `<h1>` 태그의 경우, 만약 페이지 안에서 한번만 쓰였다 하더라도, 해당 Document가 끝나면 익명영역도 종료된다.  
  > 이게 다다!  
  > 원범 멘토님이 말씀하시기를, 너무 어렵게 생각하지 말라 이르셨다...  
  > 헤딩은 그저 제목일 뿐!
  >
  > ⭐️ 그리고 그림은 내가 한땀한땀 그린 것이다.. 나는 너무 힘들었다.. ⭐️

<br>

---

<br>

> ▶︎참조  
> <https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories>  
> <https://velog.io/@simoniful/HTML-CSS-HTML-Basics-2>
