# JavaScript 정리

사람: 김소연
생성 일시: 2025년 3월 10일 오후 1:12

## 1. 대문자 상수

기억하기 힘든 값을 변수에 할당할 때 별칭으로 사용하는 것, `대문자와 밑줄`로 구성된 이름으로 변수명을 명명한다.

```jsx
// 예를 들어, 다양한 색상 코드를 반복적으로 사용한다고 했을 때 색상 코드 다 외울 순 없잖아요.
// 그런 기억하기 힘든 값을 대문자 상수로 만들어주는 것.
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";
const COLOR_ORANGE = "#FF7F00";

// 색상을 고르고 싶을 때 별칭을 사용할 수 있게 되었습니다.
let color = COLOR_ORANGE;
alert(color); // #FF7F00
```

❗ 일반 상수와 대문자 상수

 - 일반 상수 : 코드가 실행된 이후 계산되어 할당되는 변하지 않는 상수

 - 대문자 상수 : 코드가 실행되기 전에도 이미 그 값을 알고 있는 (하드코딩해주는) 상수

## 2. 증가/ 감소 연산자

- 증가 연산자 :  `++`  /  감소 연산자 : `--`

 연산자가 변수 앞에 붇는지 뒤에 붙는지에 따라 반환 값이 다르다.

 - 뒤에 붙을 경우 : 기존 값이 증가한다.

```jsx
let counter = 2;
let a = counter++;

console.log(a) // 2
console.log(counter) // 3
```

 - 앞에 붙을 경우 : 반환 되는 현재 값도 변경되고, 기존 값도 증가한다.

```jsx
let counter = 2;
let a = ++counter;

console.log(a) // 3
console.log(counter) // 3
```

## 3. 논리 연산자

- `||` : or

```jsx
// 둘 중 하나라도 true면 true, 그렇지 않으면 false
console.log(true || true); // true
console.log(true || false); // true
console.log(false || true); // true
console.log(false || false); // false

// 단락 평가
// 여러개의 피연산자가 있을 때 왼쪽부터 truthy한지 판별해서, 만약 truthy 하면 원래 값을 반환
console.log(1 || 0); // 1

let nameA = ''
let nameB = ''
let nameC = 'C'
console.log(nameA || nameB || nameC) // C

let nameA = undefined
let nameB = null
console.log(nameA || nameB || 0) // 0 -> 셋다 falsy하기 때문에 그럴 땐 마지막 값 반환
```

❓ 단락 평가는 언제 사용할까?

연산자의 왼쪽 값이 falsy할 때만 명령어를 실행하고 싶을 때 사용한다.

```jsx
true || alert("not printed"); // 왼쪽이 truthy하니까 거기서 평가 멈추기 때문에 alert 실행안됨
false || alert("printed"); // 왼쪽이 falsy하니까 다음 피연산자를 평가하는데 명령어기 때문에 그대로 값 반환하며 alert() 실행됨
```

- `&&` : and

```jsx
// 둘 중 하나라도 false 면 무조건 false 반환
console.log(true && true); // true
console.log(true && false); // false
console.log(false && true); // false
console.log(false && false); // false
```

- `!` : not

```jsx
// 피연산자를 불린형으로 변환하고, 해당 불린형의 역을 반환합니다.
console.log(!true); // false
console.log(!0); // true
```

 ❗ `!!` : not을 연달아 2개 사용하면 값의 `불린형으로 변환`할 수 있다.

```jsx
console.log(!!null); // false
console.log(!!"HELLO"); // true
```

- `??` : nullish 병합 연산자
    
     - 왼쪽 피연산자가 null도 아니고 undefined도 아니면 a  값을 반환한다.
    
    ```jsx
    // 예시
    let height = 0
    
    // 0은 fasly하므로 해당 콘솔은 100을 반환합니다.
    console.log(height || 100) 
    
    // height가 null,undefined가 아닌 0이라는 값이 할당되었기 때문에 0이 출력됩니다.
    console.log(height ?? 100) 
    
    ---
    
    // 만약, height 값이 undefined 라면?
    let height; // 아무 값도 할당하지 않았으므로 undefined
    
    // undefined 가 falsy하므로 100 출력
    console.log(height || 100)
    
    // height가 undefined 이므로 100 출력됨
    console.log(height ?? 100) 
    ```
    

## 4. 반복문

- while 문

```jsx
while (조건) {
	반복할 코드
	
	// 탈출하고 싶다면?
	if(조건) break;
}
```

➕ do… while 문 : 반복할 본문 코드를 최소 1번은 실행하고 싶을 때만 사용.

```jsx
do{
	반복할 코드
} while (조건)
```

- for 문

```jsx
for(begin; condition; step) {
	반복할 코드
	
	// 일정 조건을 진행하지 않고 통과시키고 싶을 때
	if(조건) continue;
}
```

- switch 문

```jsx
// x 에는 변수 가 들어갑니다
switch(x) { 
  case 'value1':  // if (x === 'value1')
    ...
    break;

  case 'value2':  // if (x === 'value2')
    ...
    break;

  default:
    ...
    break;
}
```