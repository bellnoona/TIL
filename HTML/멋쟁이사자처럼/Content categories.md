# Content categories (컨텐츠 카테고리)

> HTML5 이전에는 HTML 태그 요소를 inline(인라인) 요소와 block(블록) 요소를 구분하는 정도로만 분류했었다.<br>
> HTML5 이후부터는 요소별로 공통 특성을 공유하는 것끼리 그룹화하여 카테고리를 나누었다. 이렇게 그룹화한 것들을 **Contents Model (컨텐츠 모델)** 이라고 한다.<br>
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

## Metadata content

메타데이터 컨텐츠 카테고리에 속한 요소는 문서의 표현이나 동작을 수정하거나, 다른 문서를 가리키는 링크를 설정하거나, 기타 정보를 전달한다.<br>
이 카테고리에 속하는 요소는 `<base>`, `<link>`, `<meta>`, `<noscript>`, `<script>`, `<style>`, `<title>`이다.

## Sectioning Content (구획 컨텐츠)

**Sectioning Content** 란 의미가 연결되는 컨텐츠의 집합을 나타낸다.<br>
Sectioning Content 는 일반적인 컨테이너 요소가 아니며, 일반적인 컨테이너 요소는 표현을 목적으로 그룹핑해 주는 목적(단순히 묶어주는 역할)으로 한다면 섹션 요소는 각 카테고리별 주제에 해당되는 것들이 섹션이 될 수 있습니다. 일반적인 컨테이너 요소로는 `<div>`, `<span>` 등이 있다.
