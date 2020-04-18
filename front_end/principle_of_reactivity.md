Principle of reactivity
===

dom으로 가져온 객체를 변화시킨 다음 다시 변화시키고자 하면 코딩이 필요하다.

Object.defineProperty()를 사용하여 기존 동작을 재정의하면 객체의 변화가 페이지로 바로 반영되는 'reactivity'를 가질 수 있다.

이게 vue의 원리

ref: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty
