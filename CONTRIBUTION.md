# Coding Standard

## HTML Norm
* 모든 파일은 [W3 validator](https://validator.w3.org/)를 통과하여야 합니다.
* Tab size는 2개의 space로 이루어져야 합니다.
 
## CSS Norm

* Block별로 CSS file을 만들어야 합니다.
* Tab size는 2개의 space로 이루어져야 합니다.
* CSS file은 100줄을 넘지 않아야 합니다.
* 모든 block에 적용되는 스타일의 경우 reset.css/layout.css에 명시하여야 합니다.
* CSS 방법론인 [BEM](#bem) 따라야 합니다.

## BEM
 
BEM은 기본적으로 id와 CSS tag가 아닌 class만 사용해야 합니다.

```css
.class #test_id { ... } ❌
.class div { ... } ❌

.class__test { ... } 👌
```
### Block
* block은 문단 전체에 적용된 element 또는 element를 담고 있는 컨테이너를 말합니다.
&nbsp;ex) logo / login form / menu / search from / content / footer
```html
<div class="header">
  <div class="menu">....</div>
  <div class="search">....</div>
</div>
```

### Element
- element는 block 안에서 특정 기능을 수행하는 컴포넌트 입니다. element는 상황에 따라 달라집니다. 각 element는 두 개의 밑줄표시로 연결하여 block 다음에 작성합니다.
```css
.header__logo { … }
.header__menu { … }
.header__search { … }
.header__login { … }
```
- block 이름이나 element 이름이 길 경우 하이픈(-)으로 연결합니다. 
```css
.block-name__element-name
```

### Modifiers
* Modifier은 block 또는 element의 속성입니다.
  * 이 속성은 block 또는 element의 외관이나 상태를 변화시킵니다.
  * Class명은 “–“를 추가하여 modifier를 추가하여야 합니다.
```css
.block‐‐modifier { … }
.block__element--modifier { … }
```
* 탭 메뉴가 다른 영역에서 다른 스타일로 사용된다면 메인 속성을 복사하여 추가하여야 합니다.
```css
.header__navigation {
      background: #008cba;
      padding: 1px 0;
      margin: 2px 0;
}
```
* class명이 길다면
	* BEM의 class명은 구체적이고 명료하여 HTML안에서도 읽기 쉬워야 합니다.
	* class명이 무엇을 나타내는지 분명하게 전달돼야 합니다.
  