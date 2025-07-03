# Biến và Cú pháp

---
Mục tiêu bài học
- Biến trong `JavaScript` là gì?
- Quy tắc đặt tên biến.
- Phân biệt var, let, const.
- Cú pháp cơ bản trong `JavaScript`

---
## Biến là gì?
Biến là **tên đại diện** cho một vùng nhớ dùng để **lưu trữ dữ liệu tạm thời** trong chương trình.

---
## Từ khóa khai báo biến
- var
- let
- const
```js
var name = 'Nguyễn Văn A';
let age = 20;
const PI = 3.14;
```

---
## Quy tắc đặt tên biến
- Tên biến phân biệt chữ hoa và chữ thường.
- Không bắt đầu bằng số.
- Không chứa khoảng trắng hoặc ký tự đặc biệt (ngoại trừ `_` và `$`).
- Kiểu đặt `PascalCase`, `camelCase`, `snake_case`, `kebab-case`
> `Pascal Case`: 
> + Các từ được viết liền nhau không có dấu cách hoặc dấu gạch dưới (_)
> + Chữ cái đầu của mỗi từ đều được viết hoa.
> + Ví dụ: `StudentName`, `UserAccountManager`, ...

> `Camel Case`:
> + Từ đầu tiên viết thường toàn bộ.
> + Chữ cái đầu tiên của mỗi từ tiếp theo được viết hoa.
> + Ví dụ: `studentName`, `userAccountManager`, ...

---
## Cụ thể

### var
- Từ khóa `var` được sử dụng trong toàn bộ mã `JavaScript` từ năm 1995 đến năm 2015.
- Từ khóa `var` chỉ nên được sử dụng trong mã được viết cho các trình duyệt cũ.
```js
var a = 1;
var b = 2;

// Lưu ý với từ khóa var có thể
var name = "a";
var name = "b";
```

- Phạm vi:
```js
var x = 1;
{
    // block
    var x = 2;
    console.log(x); // 2
}
console.log(x); // 2
```

### let
- Từ khóa `let` được giới thiệu trong `ES6 (2015)`
```js
let home = 'Hà Nội';
```
- Các biến được khai báo bằng `let` phải được khai báo trước khi sử dụng (`hoisted`).
```js
home = 'Hà Nội';
console.log(home); // lỗi
let home;
```
- Các biến được khai báo bằng `let` không thể được khai báo lại trong cùng phạm vi. (chỉ được gán lại)
```js
let home = 'Hà Nội';
let home = 'Đà Nẵng'; // lỗi
{
    let home = 'Hải Phòng'; // Hải Phòng
}
```
- Các biến được khai báo bằng từ khóa `let` có phạm vi khối `(block scope)`
```js
{
    // block
    let x = 2;
    console.log(x); // 2
}
console.log(x); // lỗi
```

### const
- Từ khóa `const` được giới thiệu trong `ES6 (2015)`.
```js
const PI = 3.14;
```
- Các biến được định nghĩa với `const` không thể được khai báo lại hoặc gán lại.
```js
const PI = 3.14;
const PI = 3; // lỗi
PI = 3; // lỗi
```
- Các biến được định nghĩa `const` có Phạm vi Khối
```js
const PI = 3.14; // 3.14
{
    const PI = 3; // 3
}
```

---
## Cú pháp
- Comment
```js
// Đây là comment 1 dòng

/*
    Đây là comment nhiều dòng
    Đây là comment nhiều dòng
*/
```
- Chấm phẩm `;`:
+ Dấu chấm phẩy `;` trong JavaScript được dùng để kết thúc một câu lệnh `(statement)`. Nó giúp trình biên dịch hiểu rằng câu lệnh đã kết thúc, và chuẩn bị bắt đầu một câu lệnh mới.
+ Không bắt buộc – JavaScript có một cơ chế gọi là `Automatic Semicolon Insertion (ASI)` – tự động thêm `;` khi không có.

- Khoảng trắng
Nên thêm khoảng trắng vào giữa để dễ đọc hơn, ví dụ:
```js
let person = "Nguyễn Văn A";
let person="Nguyễn Văn A";
```


