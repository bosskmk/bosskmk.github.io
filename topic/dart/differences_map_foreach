### [Dart] map 과 forEach 차이점.

Dart 에서는 Map 이 Lazy 로 동작 합니다.  
때문에 Iteration 하지 않는 이상 Map 의 콜백 함수가 평가 되지 않습니다.

<br><br>

> 자바스크립트에서 map 은 바로 평가되므로 아래 코드는 모두 출력 됩니다.  

```javascript
var list = [1,2,3,4,5];

list.map(num => console.log(`map ${num}`));

list.forEach(num => console.log(`list ${num}`));
```

<br><br>

> Dart 에서 map 은 바로 평가되지 않아 아래 코드에서 forEach 구분의 print 만 출력 됩니다.  

```dart
Iterable.generate(5).map((e) {
  print('map $e');
});

Iterable.generate(5).forEach((e) {
  print('forEach $e');
});
```

<br><br>

> toList() 를 호출 하는 것과 같이 iteration 하게 되면 forEach 와 동일하게 바로 출력 됩니다.  

```dart
Iterable.generate(5).map((e) {
  print('map $e');
}).toList();
```

