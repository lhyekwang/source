# NaN

* [NaN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/NaN)
* [Number.NaN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Number/NaN)
* [Number.isNaN\(\)](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN)
* [isNaN\(\)](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/isNaN)

### 값 - NaN ,  IsNaN , Number.NaN 

NaN은 전역객체의 속성이다. Number.NaN 과 같음. Math함수시 에러가 나거나 parseInt 의 값이 에러가 날때 NaN을 반환한다.

```text
(Math.sqrt(-1)) // NaN
(parseInt("blabla")) // NaN
```

다른 모든 값과 비교\(`==`, `!=`, `===`, `!==`\)했을 때 같지 않으며, 다른 NaN과도 같지 않습니다. 

```text
Number.NaN === NaN; // false
isNaN(NaN);         // true
isNaN(Number.NaN);  // true
```

```text
function valueIsNaN(v) { return v !== v; }
valueIsNaN(1); //false
valueIsNaN(NaN); // true
valueIsNaN(Number.NaN) // true
```

> **isNaN**은 현재값이 NaN 이거나 숫자로 변환 했을때 NaN 이면 참을 반환하지만, 
>
> **Number.isNaN**은 현재값이 NaN 이어 야지 참을 반환한다.

```text
isNaN('hello world'); // true
Number.isNaN('hello world'); // false
```

**Number.NaN** 은 not-a-number을 나타내며, NaN과 같음

```text
function clean(x) {
  if (x === Number.NaN) {
    // can never be true
    return null;
  }
  if (isNaN(x)) {
    return 0;
  }
}

console.log(clean(Number.NaN));
// expected output:
```

### 메서드 -  Number.isNaN\(\) , isNaN\(\)

**Number.isNaN 이 엄격버전**

> 매개변수가 NaN\(Not a Number\)인지 판별 // 
>
> 반환값 주어진값이 Number 이고 값이 NaN이면 **True**, 아니면 **false**.

```text
function typeOfNaN(x) {
  if (Number.isNaN(x)) { // x가 숫자도 아니고, NaN이면 
    return 'Number NaN';
  }
  if (isNaN(x)) { // x가 숫자가 아니면 
    return 'NaN';
  }
}

console.log(typeOfNaN('100F')); // expected output: "NaN"
console.log(typeOfNaN(NaN)); // expected output: "Number NaN"
```

```text
isNaN = function(value) {
    Number.isNaN(Number(value));
} // 축약버전 
```

