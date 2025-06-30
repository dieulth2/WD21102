# Kiểu dữ liệu

Mục tiêu bài học:
- Hiểu được khái niệm kiểu dữ liệu và vai trò của nó trong `JavaScript`.
- Phân biệt được kiểu dữ liệu nguyên thủy và kiểu dữ liệu tham chiếu.
- Kiểm tra kiểu dữ liệu bằng `typeof`.
- Hiểu và áp dụng được ép kiểu dữ liệu tường minh và ngầm định.

---
## Định nghĩa
Trong `JavaScript`, kiểu dữ liệu `(data type)` là cách để xác định loại giá trị mà một biến có thể chứa, từ đó giúp chương trình xử lý và quản lý dữ liệu đúng cách.

---
## Phân loại kiểu dữ liệu:
### A. Kiểu dữ liệu nguyên thủy (Primitive Types)
Là các giá trị đơn giản, không thể thay đổi `(immutable)`, gồm:

| Kiểu          | Mô tả                                    | Ví dụ                   |
| ------------- | ---------------------------------------- | ----------------------- |
| **String**    | Chuỗi văn bản                            | `"Hello"`, `'JS'`       |
| **Number**    | Số (cả số nguyên và số thực)             | `10`, `3.14`            |
| **Boolean**   | Đúng hoặc sai                            | `true`, `false`         |
| **Undefined** | Biến đã khai báo nhưng chưa gán giá trị  | `let x;`                |
| **Null**      | Đại diện cho "không có giá trị"          | `let y = null;`         |
| **BigInt**    | Số nguyên rất lớn (ES2020)               | `12345678901234567890n` |
| **Symbol**    | Giá trị duy nhất, thường dùng làm key ẩn | `Symbol("id")`          |

### B. Kiểu dữ liệu phức tạp - tham chiếu (Reference Types)
Là các đối tượng phức tạp, lưu theo địa chỉ bộ nhớ:

| Kiểu                             | Mô tả                        | Ví dụ                     |
| -------------------------------- | ---------------------------- | ------------------------- |
| **Object**                       | Tập hợp các cặp key-value    | `{ name: "JS", age: 25 }` |
| **Array**                        | Danh sách các phần tử        | `[1, 2, 3]`               |
| **Function**                     | Hàm (cũng là object)         | `function sayHi() {}`     |
| **Date, RegExp, Map, Set, v.v.** | Các kiểu đặc biệt của object | `new Date()`, `new Map()` |

---
## 1. String (chuỗi)
#### Lý thyết
Là chuỗi các ký tự nằm trong dấu ngoặc đơn: '', "" hoặc (template string).
```js
let name = "JavaScript";
let greeting = 'Hello';
let message = `Chào bạn, ${name}`; // Template Literal
```
### Kiểm tra kiểu:
```js
let name = "JavaScript";
console.log(typeof name);
```
### Lưu ý
Lưu ý để viết các ký đặc biệt trong chuỗi:
| Ký tự    | Mô tả                         | Cách viết           | Ví dụ                |
| -------- | ----------------------------- | ------------------- | -------------------- |
| `\n`     | Xuống dòng (newline)          | `"Hello\nWorld"`    | `Hello` <br> `World` |
| `\t`     | Tab (khoảng trắng ngang)      | `"A\tB"`            | `A    B`             |
| `\'`     | Dấu nháy đơn                  | `'It\'s OK'`        | `It's OK`            |
| `\"`     | Dấu nháy kép                  | `"He said: \"Hi\""` | `He said: "Hi"`      |
| `\\`     | Dấu gạch chéo ngược           | `"C:\\User\\Admin"` | `C:\User\Admin`      |
| `\uXXXX` | Unicode                       | `\u00A9`            | `©`                  |
| `\xXX`   | Mã hex                        | `\x41`              | `A`                  |

Trong `template string` (dùng dấu `), bạn có thể viết xuống dòng trực tiếp mà không cần \n:
```js
let msg = `Dòng 1
Dòng 2`;
```
### Các phương thức làm việc với chuỗi
- `length`: Trả về độ dài chuỗi (số ký tự).
```js
let name = "JavaScript";
console.log(name.length); // 10
```

- `toUpperCase()` / `toLowerCase()`: Chuyển chuỗi thành chữ hoa / chữ thường.
```js
"hello".toUpperCase(); // "HELLO"
"JS".toLowerCase();    // "js"
```

- `trim()`: Loại bỏ khoảng trắng dư thừa
```js
"  Hello   JS  ".trim(); // "Hello JS"
```

- `includes(substring)`: Kiểm tra chuỗi có chứa đoạn con không → trả về `true` hoặc `false`.
```js
"JavaScript".includes("Script"); // true
```

- `indexOf()` / `lastIndexOf()`: Tìm vị trí xuất hiện đầu tiên / cuối cùng của đoạn con.
```js
"banana".indexOf("a");     // 1
"banana".lastIndexOf("a"); // 5
```

- `slice(start, end)`: Cắt chuỗi từ vị trí start đến trước end.
```js
"JavaScript".slice(0, 4); // "Java"
"JavaScript".slice(-6);   // "Script"
```

- `replace(search, newText)`: Thay thế chuỗi con đầu tiên.
```js
"Hello JS JS".replace("JS", "JavaScript"); // "Hello JavaScript JS"
```
Thay thế tất cả dùng biểu thức chính quy:
```js
"Hello JS JS".replace(/JS/g, "JS"); // "Hello JavaScript JavaScript"
```
Thay thế tất cả  dùng `replaceAll(search, newText)` `(ES2021)`
```js
"Hello JS JS".replaceAll("JS", "JS"); // "Hello JavaScript JavaScript"
```

- `split(separator)`: Tách chuỗi thành mảng
```js
"1,2,3".split(","); // ["1", "2", "3"]
"hello".split("");  // ["h", "e", "l", "l", "o"]
```

- `concat(str)`: Nối chuỗi
```js
"Hello".concat(" ", "World"); // "Hello World"
```

- Ngoài ra còn 1 số phương thức khác như: `startsWith()`, `endsWith()`, `substring(start, end)`, `charAt(index)`, `charCodeAt(index)`, `repeat(count)`,`padStart(length, padText)`, `padEnd(length, padText)`,...

### Ép kiểu
- Ép kiểu tường minh
```js
String(123);         // "123"
String(true);        // "true"
String(null);        // "null"
String(undefined);   // "undefined"
String([1, 2, 3]);   // "1,2,3"
String({a: 1});      // "[object Object]"
```
- Dùng `.toString()`
```js
(123).toString();        // "123"
true.toString();         // "true"
[1, 2, 3].toString();    // "1,2,3"
new Date().toString();   // "Sat Jun 29 2025..." (tùy thời gian)

null.toString();        // ❌ lỗi
undefined.toString();   // ❌ lỗi
```
- Ép kiểu ngầm định `(implicit)`
```js
123 + "";             // "123"
true + "";            // "true"
null + "";            // "null"
"Hello " + 2025;      // "Hello 2025"
"Result: " + false;   // "Result: false"
"Array: " + [1, 2];   // "Array: 1,2"
```

---
## 2. Number (số)
### Định nghĩa
Đại diện cho cả số nguyên và số thực.
```js
let a = 10;
let b = 3.14;
let c = -100;
let d = NaN; // Not a Number
let e = Infinity;
let f = -Infinity
```
> NaN: Phép toán không hợp lệ `0/0`, Ép kiểu chuỗi không phải số `Number("hello")`, Trừ chuỗi không hợp lệ với số `let x = "abc" - 10;`, Hàm toán học với đầu vào không hợp lệ `let y = Math.sqrt(-1);`,...

Giá trị lớn nhất và nhỏ nhất
| Thuộc tính         | Mô tả                                               | Giá trị                     |
| ------------------ | --------------------------------------------------- | --------------------------- |
| `Number.MAX_VALUE` | Số lớn nhất có thể biểu diễn                        | ≈ `1.7976931348623157e+308` |
| `Number.MIN_VALUE` | Số dương nhỏ nhất gần 0 (không phải số âm nhỏ nhất) | ≈ `5e-324`                  |


### Kiểm tra kiểu giá trị:
```js
let a = 100;
console.log(typeof a); // number
```
> Cách để kiểm tra một giá trị có phải là số hợp lệ (number) trong JavaScript:
```js
function isValidNumber(val) {
  return typeof val === "number" && !isNaN(val);
}

isValidNumber(123);    // true
isValidNumber("123");  // false
isValidNumber(NaN);    // false

```

Các phương thức làm việc với số:
- `toFixed(n)`: Làm tròn số đến n chữ số thập phân, kết quả là chuỗi.
```js
let num = 3.14159;
num.toFixed(2);     // "3.14"
let num1 = 3.1665;
num1.toFixed(2);    // "3.15"
```

- `Number.isInteger(value)`: Kiểm tra giá trị có phải số nguyên không.
```js
Number.isInteger(5);     // true
Number.isInteger(3.14);  // false
```
- `Number.isNaN(value)`: Kiểm tra xem giá trị có phải là NaN (Not-a-Number) thật không.
```js
Number.isNaN(NaN);    // true
Number.isNaN(1);      // false
Number.isNaN("abc");  // false (khác với isNaN())
```
- `Number.isFinite(value)`: Kiểm tra xem giá trị có phải là số hữu hạn không.
```js
Number.isFinite(10);       // true
Number.isFinite(Infinity); // false
```

- Các phương thức làm việc với Math

| Phương thức         | Mô tả                                       | Ví dụ                    |
| ------------------- | --------------------------------------------| ------------------------ |
| `Math.round(x)`     | Làm tròn số x                               | `Math.round(3.6)` → `4`  |
| `Math.floor(x)`     | Làm tròn xuống                              | `Math.floor(3.9)` → `3`  |
| `Math.ceil(x)`      | Làm tròn lên                                | `Math.ceil(3.1)` → `4`   |
| `Math.trunc(x)`     | Lấy phần nguyên (cắt phần thập phân)        | `Math.trunc(3.99)` → `3` |
| `Math.abs(x)`       | Giá trị tuyệt đối                           | `Math.abs(-5)` → `5`     |
| `Math.pow(a, b)`    | Lũy thừa                                    | `Math.pow(2, 3)` → `8`   |
| `Math.sqrt(x)`      | Căn bậc hai                                 | `Math.sqrt(16)` → `4`    |
| `Math.min(...args)` | Tìm giá trị nhỏ nhất                        | `Math.min(1, 2, 3)` → `1`|
| `Math.max(...args)` | Tìm giá trị lớn nhất                        | `Math.max(1, 2, 3)` → `3`|
| `Math.random()`     | Trả về số ngẫu nhiên, từ 0 đến < 1          | `Math.random()`          |
| `Math.sign(x)`      | Trả về 1 nếu dương, -1 nếu âm, 0 nếu bằng 0 | `Math.sign(-5)` → `-1`   |               

### Ép kiểu
- Dùng hàm `Number()`:
```js
Number("123");      // → 123 (number)
Number("123.45");   // → 123.45 (number)
Number(true);       // → 1
Number(false);      // → 0
Number(null);       // → 0
Number(undefined);  // → NaN
Number("abc");      // → NaN
Number("123abc");      // → NaN
```
- Dùng `+`
```js
+"456";     // → 456
+true;      // → 1
+false;     // → 0
+null;      // → 0
+"abc";     // → NaN
```
- Dùng `parseInt()` hoặc `parseFloat()`
> Lưu ý: Chỉ dùng khi bạn biết đầu vào là chuỗi chứa số
```js
parseInt("123abc");    // → 123
parseFloat("123.45");  // → 123.45
```

---
## 3. Boolean (Đúng/Sai)
### Định nghĩa:
Chỉ nhận một trong hai giá trị: true hoặc false.
```js
let isActive = true;
let isLoggedIn = false;
```
> Lưu ý:
> + Dùng trong điều kiện `if`, `while`, v.v.
> + Giá trị `“falsy”`: false, 0, '', null, undefined, NaN
> + Giá trị `“truthy”`: tất cả các giá trị còn lại

---
## 4. Undefined
### Định nghĩa
Là giá trị mặc định của một biến khi chưa được gán.
```js
let x;
console.log(x); // undefined
```
> Lưu ý:
> + `typeof undefined === 'undefined'`
> + Không nên cố gán thủ công `undefined` → dùng `null` nếu muốn biểu thị "rỗng".

## 5. Null
### Định nghĩa
Đại diện cho “không có giá trị” một cách cố ý.
```js
let person = null;
```
> Lưu ý: 
> + `typeof null === 'object'` → Đây là lỗi lịch sử trong JS.
> + Dùng để reset biến hoặc làm giá trị mặc định ban đầu.

## 6. BigInt
### Định nghĩa: 
Cho phép làm việc với số nguyên rất lớn (vượt quá 2^53 - 1).
```js
let bigNumber = 123456789012345678901234567890n;
```

## 7. Symbol
### Định nghĩa
Tạo ra một giá trị duy nhất, thường dùng làm `key` cho `object`.
```js
const id = Symbol("userId");
const user = {
  [id]: 101,
  name: "Alice"
};

let a = Symbol("userId");
let b = Symbol("userId");
console.log(a === b); // false 
```
> Lưu ý:
> + Hai `Symbol("text")` luôn khác nhau, dù cùng chuỗi.
> + `Symbol` không hiển thị khi duyệt `object` bằng `for...in`.

---
## 8. Array (mảng)
### Định nghĩa
Mảng là một kiểu dữ liệu dùng để lưu nhiều giá trị trong một biến duy nhất, theo thứ tự và có thể truy cập bằng chỉ số `(index)`.
```js
let num = [1, -2, 0, 3.5];
let fruits = ["Apple", "Banana", "Cherry"];
let arr = [20, 'Banana', true, null];
```
> Lưu ý:
> + Mỗi phần tử trong mảng đều có chỉ số bắt đầu từ 0
> + Có thể chứa nhiều kiểu dữ liệu khác nhau
> + Có thể thay đổi, thêm, xóa phần tử

### Khai báo mảng
```js
// Cách 1: Dùng dấu ngoặc vuông []
let numbers = [1, 2, 3];

// Cách 2: Dùng từ khóa new
let colors = new Array("red", "green", "blue");
```

### Truy cập cách phần tử trong mảng
```js
let names = ["Alice", "Bob", "Charlie"];
console.log(names[0]); // Alice
console.log(names[2]); // Charlie
```
### Thay đổi các phần tử trong mảng
```js
names[1] = "David";
console.log(names); // ["Alice", "David", "Charlie"]
```

### Độ dài mảng
```js
console.log(names.length); // 3
```

### Các phương thức làm việc với mảng
| Phương thức            | Chức năng                                          | Ví dụ                              |
| ---------------------- | -------------------------------------------------- | ---------------------------------- |
| `push()`               | Thêm phần tử vào cuối mảng                         | `arr.push("new")`                  |
| `pop()`                | Xóa phần tử cuối và trả về phần tử đó              | `arr.pop()`                        |
| `unshift()`            | Thêm phần tử vào đầu mảng                          | `arr.unshift("new")`               |
| `shift()`              | Xóa phần tử đầu tiên và trả về phần tử đó          | `arr.shift()`                      |
| `includes()`           | Kiểm tra xem phần tử có tồn tại trong mảng không   | `arr.includes("abc")`              |
| `indexOf()`            | Trả về vị trí xuất hiện đầu tiên của phần tử       | `arr.indexOf("abc")`               |
| `splice(start, count)` | Xóa hoặc chèn phần tử ở vị trí bất kỳ              | `arr.splice(1, 2)`                 |
| `slice(start, end)`    | Cắt một mảng con mới (không làm thay đổi mảng gốc) | `arr.slice(1, 3)`                  |
| `sort()`               | Sắp xếp mảng                                       | `arr.sort((a,b)=> a - b)`          |
| `forEach()`            | Lặp qua từng phần tử                               | `arr.forEach(e => console.log(e))` |
| `map()`                | Tạo mảng mới sau khi biến đổi từng phần tử         | `arr.map(e => e * 2)`              |
| `filter()`             | Tạo mảng mới chỉ chứa phần tử thỏa điều kiện       | `arr.filter(e => e > 10)`          |
| `reduce()`             | Tính toán hoặc “rút gọn” mảng                      | `arr.reduct((a,c) => a+c,0)`       |

### Array với const
```js
const cars = ["Saab", "Volvo", "BMW"];
cars = ["Toyota", "Volvo", "Audi"]; // Lỗi

const cars = ["Saab", "Volvo", "BMW"];
cars[0] = "Toyota";
cars[3] = "Mercedes";
cars.push("Audi");
```

---
## Object 
### Định nghĩa
`Object` là một kiểu dữ liệu cho phép lưu trữ nhiều giá trị dưới dạng cặp khóa – giá trị `(key: value)`, tương tự như một bảng tra cứu.
```js
let person = {
  name: "Nguyễn Văn A",
  age: 20,
  gender: true,
  hobbies: ["Code", "Game", "Run"],
};
```
> Lưu ý:
> + `Key` (thuộc tính): là một chuỗi `(string)` hoặc ký hiệu `(Symbol)`
> + `Value`: có thể là bất kỳ kiểu dữ liệu nào (`string`, `number`, `boolean`, `function`, `array`, `object`, ...)

### Truy cập giá trị
```js
let user = {
  username: "duong123",
  email: "duong@example.com",
  age: 30,
};
console.log(user.username); // "duong123"
console.log(user["email"]); // "duong@example.com"
```

### Thêm, sửa, xóa thuộc tính:
```js
// Thêm mới
user.gender = false;
// Sửa
user.age = 35;
// Xóa
delete user.email; 
//hoặc
delete user.['email']; 
```

### Object lồng nhau
```js
let student = {
  name: "Hoa",
  class: {
    name: "12A1",
    teacher: "Mr. Tuan"
  }
};

console.log(student.class.name); // "12A1"
```

### Function trong Object
```js
let car = {
  brand: "Toyota",
  showInfo() {
    console.log(`My car is ${this.brand}`);
  }
};

car.start()
```

Hoặc viết ngắn hơn:
```js
let car = {
  brand: "Toyota",
  showInfo() {
    console.log(`My car is ${this.brand}`);
  }
};
```
