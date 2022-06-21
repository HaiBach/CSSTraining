# CSS RULE

Cấu trúc của một css bao gồm:
+ Selector: trỏ tới phần tử HTML mà bạn muốn tạo style.
+ Cụm declaration: bao gồm một hoặc nhiều declaration, phân biệt bằng dấu chấm phẩy ;
+ Mỗi declaration bao gồm một tên thuộc tính (property) CSS và một giá trị (value), ngăn cách bằng dấu hai chấm :
+ Cụm declaration được bao bộc bằng dấu ngoặc nhọn {}

``` css
selector { property: value; property: value; }
```

![CSS Syntax](/assets/img/css-syntax.png)



## ❤ **QUY TẮC KHI VIẾT CSS**

### **Quy tắc chung**

1.1 Định nghĩa mã hoá ký tự bằng chuẩn `UTF-8` và được thiết lập ở các dòng đầu tiên của file css.

``` css
@charset "charset";
``` 

1.1 Indent nên sử dụng: 2 khoảng trắng (space).

1.2 Bắt buộc sử dụng dấu ; khi kết thúc 1 declaration.

1.3 Mỗi một declaration nên viết trên 1 dòng một, không nên gộp các declaration trên cùng 1 dòng.

1.4 Khi viết css phải có khoảng trắng giữa selector - property - value để trình bày rõ ràng và dễ nhìn hơn.

``` css
// Không nên
h1{color:blue;font-size:4em;}

// Nên
h1 {
  color: blue;
  font-size: 4em;
}
```


### **Viết ngắn gọn**

1. Hạn chế viết các selector lồng với nhau (nested) và các ancestor selector không cần thiết. Việc này giúp ít rất nhiều để code css dễ đọc, dễ tuỳ chỉnh, tiết kiệm thời gian khi chỉnh sửa.

``` css
// Không nên
nav ul li a {}
div.error {}

// Nên
nav a {}
.error {}
```

2. Loại bỏ đơn vị (unit) nếu giá trị là `0`

``` css
a {
  padding: 0;
  margin: 0;
}
```

3. Loại bỏ số `0` nếu giá trị có dáu thập phân

``` css
h1 {
  opacity: 0.5;
}

// Nên
h1 {
  opacity: .5;
}
```

4. Giá trị màu sắc HEX nên sử dụng hình thức giản lược (3 ký tự) nếu có thể.

``` css
// Không nên
a {
  color: #aabbcc;
}

// Nên
a {
  color: #abc;
}
```

4. a. Nên sử dụng cấu trúc shorthand khi selector có đầy đủ thuộc tính đó. Ví dụ selector có đầy đủ 4 thuộc tính của padding: `padding-top`, `padding-right`, `padding-bottom` và `padding-left` 

``` css
// Không nên
ul {
  padding-top: 10px;
  padding-right: 20px;
  padding-bottom: 30px;
  padding- left: 20px;
}

// Nên
ul {
  padding: 10px 20px 30px;
}
```

b. Nhưng khi chúng ta chỉ cần css một thuộc tính riêng lẻ (ví dụ: padding-top), thì ta cũng hạn ché sử dụng cấu trúc shorthand để tránh dư thừa và khó kiểm soát khi viết css.

``` css
// Không nên
ul {
  padding: 10px auto auto;
}

// Nên
ul {
  padding-top: 10px;
}
```


