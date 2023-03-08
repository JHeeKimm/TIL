> innerText와의 차이점

- textContent는 <script>와 <style> 요소를 포함한 모든 요소의 콘텐츠를 가져옵니다. 반면 innerText는 "사람이 읽을 수 있는" 요소만 처리합니다.
- textContent는 노드의 모든 요소를 반환합니다. 그에 비해 innerText는 스타일링을 고려하며, "숨겨진" 요소의 텍스트는 반환하지 않습니다.
- 또한, innerText의 CSS 고려로 인해, innerText 값을 읽으면 최신 계산값을 반영하기 위해 리플로우가 발생합니다. (리플로우 계산은 비싸므로 가능하면 피해야 합니다)
- Internet Explorer 기준, innerText를 수정하면 요소의 모든 자식 노드를 제거하고, 모든 자손 텍스트 노드를 영구히 파괴합니다. 이로 인해, 해당 텍스트 노드를 이후에 다른 노드는 물론 같은 노드에 삽입하는 것도 불가능합니다.

> innerHTML과의 차이점

- Element.innerHTML는 이름 그대로 HTML을 반환합니다. 간혹 innerHTML을 사용해 요소의 텍스트를 가져오거나 쓰는 경우가 있지만, HTML로 분석할 필요가 없다는 점에서 textContent의 성능이 더 좋습니다.
- 이에 더해, textContent는 XSS 공격 (en-US)의 위험이 없습니다.
