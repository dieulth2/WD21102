# Function - Hàm

Mục tiêu bài học
- Tìm hiểu và khai báo hàm
- Tham số trong hàm
- Hàm trả về

## Định nghĩa
Hàm `(function)` là một khối mã được định nghĩa để thực hiện một nhiệm vụ cụ thể. Hàm giúp chia nhỏ chương trình thành các phần riêng biệt, dễ đọc, dễ quản lý và tái sử dụng.
Cách đặt tên hàm giống với các đặt tên biến.
>Nên đặt tên hàm theo camelCase

## 1. Declaration Function (Khai báo hàm truyền thống)
```js
function tenHam() {
  // nội dung hàm
}

tenham();
```
> + Có thể gọi trước khi khai báo (do hoisting).
> + Là cách khai báo truyền thống và rõ ràng.
> Ví dụ:
```js
sayHello();

function sayHello() {
  console.log("Hello world!");
}
```
### Tham số trong hàm (parameter)
Tham số là biến được khai báo trong định nghĩa của hàm. Khi bạn gọi hàm, bạn sẽ truyền đối số `(argument)` vào các tham số này để hàm xử lý.
> Tham số `(parameter)`: Là biến định nghĩa trong hàm.
> Đối số `(argument)`: Là giá trị thực tế được truyền vào khi gọi hàm.
```js
function tinhTong(a, b) {   // a và b là THAM SỐ
  console.log(a + b); // Kết quả: 8
}

tinhTong(5, 3); // 5 và 3 là ĐỐI SỐ
```

### return trong hàm
Trả về giá trị từ một hàm.
```js
function tinhTong(a, b) {
  return a + b; // trả về tổng của a và b
}
let kq = tinhTong(3, 5);
console.log(kq); //8
```
> Khi `return` được gọi: 
> + Hàm dừng lại ngay lập tức.
```js
function test() {
  console.log("Bắt đầu");
  return;
  console.log("Dòng này sẽ không chạy");
}
test(); // Chỉ in "Bắt đầu"
```
> + Giá trị đi sau `return` sẽ được trả về cho nơi gọi hàm.
```js
function tinhTong(a, b) {
  return 10;
  return a + b; // trả về tổng của a và b
}
let kq = tinhTong(3, 5);
console.log(kq); 10
```

## 2. Expression Function (Hàm gán cho biến)

```js
const tenHam = function(thamSo1, thamSo2) {
  // nội dung
  return giaTri;
};
tenHam();
```
> + Không thể gọi trước khi khai báo.

### 3. Arrow Function*
```js
const tenHam = (thamSo1, thamSo2) => {
  // nội dung
  return giaTri;
};
tenHam();
```

Viết ngắn gọn hơn nếu chỉ có 1 dòng return:
```js
const add = (a, b) => a + b;
```
