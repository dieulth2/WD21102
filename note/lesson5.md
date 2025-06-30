# Operator - Toán tử

Mục tiêu:
Tìm hiểu cơ bản về các toán tử trong JavaScript.
Ứng dụng toán tử.

---
## Định nghĩa
Toán tử `(operator)` là ký hiệu dùng để thực hiện thao tác trên các giá trị (toán hạng – operands), như tính toán, so sánh, gán giá trị, kiểm tra logic...

Các loại toán tử cơ bản:
1. Toán tử số học `(Arithmetic Operators)`.
2. Toán tử gán `(Assignment Operators)`.
3. Toán tử so sánh `(Comparison Operators)`.
4. Toán tử logic `(Logical Operators)`.

---
## 1. Toán tử số học (Arithmetic Operators)
| Toán tử | Ý nghĩa        | Ví dụ            |
| ------- | -------------- | ---------------- |
| `+`     | Cộng           | `a + b`          |
| `-`     | Trừ            | `a - b`          |
| `*`     | Nhân           | `a * b`          |
| `/`     | Chia           | `a / b`          |
| `%`     | Chia lấy dư    | `a % b`          |
| `**`    | Lũy thừa (ES6) | `a ** b`         |
| `++`    | Tăng 1 đơn vị  | `a++` hoặc `++a` |
| `--`    | Giảm 1 đơn vị  | `a--` hoặc `--a` |

Bài tập: Tính nhẩm?
```js
let x = 3;
let y = 4;

let result = x++ + --x + ++y + y--;
```

---
## 2. Toán tử gán (Assignment Operators)
| Toán tử | Ý nghĩa             | Ví dụ                    |
| ------- | ------------------- | ------------------------ |
| `=`     | Gán                 | `a = 10`                 |
| `+=`    | Cộng rồi gán        | `a += 5` <=> `a = a + 5` |
| `-=`    | Trừ rồi gán         | `a -= 2` <=> `a = a - 2` |
| `*=`    | Nhân rồi gán        | `a *= 3` <=> `a = a * 3` |
| `/=`    | Chia rồi gán        | `a /= 2` <=> `a = a \ 2` |
| `%=`    | Chia lấy dư rồi gán | `a %= 3` <=> `a = a % 3` |

---
## 3. Toán tử so sánh (Comparison Operators)
| Toán tử | Ý nghĩa                    | Ví dụ       | Kết quả |
| ------- | -------------------------- | ----------- | ------- |
| `==`    | So sánh bằng (lỏng)        | `5 == '5'`  | `true`  |
| `===`   | So sánh bằng (nghiêm ngặt) | `5 === '5'` | `false` |
| `!=`    | Khác (lỏng)                | `5 != '5'`  | `false` |
| `!==`   | Khác (nghiêm ngặt)         | `5 !== '5'` | `true`  |
| `>`     | Lớn hơn                    | `6 > 3`     | `true`  |
| `<`     | Nhỏ hơn                    | `2 < 5`     | `true`  |
| `>=`    | Lớn hơn hoặc bằng          | `5 >= 5`    | `true`  |
| `<=`    | Nhỏ hơn hoặc bằng          | `3 <= 4`    | `true`  |

---
## 4. Toán tử logic (Logical Operators)
| Toán tử   | Ý nghĩa        | Ví dụ             | Kết quả   | 
| --------- | -------------- | ------------------| --------- | 
| `&&`      | AND (và)       | `true && false`   | `false`   |
| `\|\|`    | OR (hoặc)      | `true \|\| false` | `true`    |  
| `!`       | NOT (phủ định) | `!true`           | `false`   |
