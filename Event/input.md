✨ 동작 순서  
onFocus >> onKeyDown > onKeyPress > onInput > onChange > onKeyUp > onBlur

1. onBlur

- 요소에 focus가 헤재되었을 때 발생하는 이벤트

2. onFocus

- 요소에 focus시 발생하는 이벤트

3. onKeyPress

- 문자 값을 생성하는 키를 눌렀을 때 발생하는 이벤트

- 기기 의존도가 높아 현재는 더이상 사용되지 않음.

- 한글, 기능키 입력 시 동작하지 않음

4. onInput

- input의 value 속성 값이 변경될 때 발생하는이벤트

5. onKeyDown

- key를 눌렀을 때 발생하는 이벤트

6. onKeyUp

- key를 눌렀다가 떼었을때 발생하는 이벤트

7. onChange

- html요소가 바뀌었을 때 즉 focus 발생 전과 후를 비교하여 변화가 일어났을 경우 발생하는 이벤트
