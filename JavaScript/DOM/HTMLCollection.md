> HTMLCollection

- HTMLCollection 인터페이스는 요소의 문서 내 순서대로 정렬된 일반 컬렉션(arguments처럼 배열과 유사한 객체)을 나타내며 리스트에서 선택할 때 필요한 메서드와 속성을 제공한다.
- HTML DOM 내의 HTMLCollection은 문서가 바뀔 때 실시간으로 업데이트된다.
- 유사 배열이기 때문에, 배열에서 제공하는 모든 메서드를 가지고 있지 않는다.
- .forEach나 .map을 사용하려고 하면 해당 메서드가 존재하지 않는다는 오류가 발생한다. 배열 구조분나 Array.from()으로 HTMLCollection으로부터 배열을 생성해서 해당 메서드를 사용할 수 있다.

- childNodes와 querySelectorAll()의 차이
  - element.childNodes와 querySelectorAll()은 둘 다 ￿NodeList를 반환하지만 차이점을 가지고 있다. 바로 변경사항의 유무다.
  - Node.childNodes의 NodeList는 라이브 콜렉션으로, DOM의 변경사항을 실시간으로 반영한다. 반면에, document.querySelectorAll()의 NodeList는 정적 콜렉션으로, DOM이 변경되어도 collection의 내용에는 영향을 주지 않는다.
