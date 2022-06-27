# CSS RULE

Cấu trúc của một css bao gồm:
+ Selector: trỏ tới phần tử HTML mà bạn muốn tạo style.
+ Cụm declaration: bao gồm một hoặc nhiều declaration, phân biệt bằng dấu chấm phẩy ;
+ Mỗi declaration bao gồm một tên thuộc tính (property) CSS và một giá trị (value), ngăn cách bằng dấu hai chấm :
+ Cụm declaration được bao bộc bằng dấu ngoặc nhọn {}

``` css
selector { property: value; property: value; }
```

![CSS Syntax](/assets/img/css-syntax.svg)



## ❤ **QUY TẮC KHI VIẾT CSS**


### **1. Quy tắc chung**

1.1

Ưu tiên sử dụng Sass để viết css, và tách các style thành từng file nhỏ để dễ quản lý, dễ viết css.

[sass-lang.com](https://sass-lang.com/)

Quản lý các file scss thành nhiều file nhỏ

``` css
scss
| _reset.scss
| _common.scss
| _header.scss
| _footer.scss
| _button.scss
| ...
style.scss
```


1.2

Định nghĩa mã hoá ký tự bằng chuẩn `UTF-8` và được thiết lập ở các dòng đầu tiên của file css.

``` css
@charset "charset";
``` 


1.3

Indent nên sử dụng: 2 khoảng trắng (space).


1.4

Bắt buộc sử dụng dấu ; khi kết thúc 1 declaration.


1.5

Mỗi một declaration nên viết trên 1 dòng một, không nên gộp các declaration trên cùng 1 dòng.


1.6

Khi viết css phải có khoảng trắng giữa selector - property - value để trình bày rõ ràng và dễ nhìn hơn.

``` css
/* Không nên */
h1{color:blue;font-size:4em;}

/* Nên */
h1 {
  color: blue;
  font-size: 4em;
}
```


1.7

Các declaration được nhớm lại với nhau theo chức năng và sắp xếp theo thứ tự:

1. Vị trí
2. Kích thước
3. Khoảng cách
4. Màu sắc, Background và Border
5. Font và Text
6. Transition và Transform
7. Animation
8. Shadow, Outline và Filter
9. Còn lại

``` css
nav {
  /* 1. Vị trí */
  overflow: hidden;
  position: relative;
  left: 0;
  top: 0;
  z-index: 9;

  /* 2. Kích thước */
  display: flex;
  justify-content: center;
  align-items: center;
  width: 500px;
  height: 100px;

  /* 3. Khoảng cách */
  padding: 20px;
  margin: 0 20px 30px;

  /* 4. Màu sắc, background và border */
  color: #333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 4px;

  /* 5. Font và Text */
  font-family: 'Noto', san-serif;
  font-size: 16rem;
  font-weight: 400;
  text-decoration: none;
  text-transform: uppercase;
  letter-spacing: 1px;
  text-align: center;
  
  /* 6. Transform */
  transition: all .2s;
  transform-origin: center center;
  transform: translate3d(0,0,0);

  /* 7. Animation */
  animation-name: name-keyframe;
  animation-duration: 2s;
  animation-timing-function: linear;
  animation-delay: 1s;
  animation-fill-mode: both;
  animation-iteration-count: infinite;
  animation-direction: alternate;

  /* 8. Shadow - Outline - Filter */
  box-shadow: 0 2px 2px rgba(0,0,0,.2);
  outline: 10px solid #f22;
  backdrop-filter: saturate(180%) blur(20px);

  /* 9. Khác */
  opacity: .95;
}
```


1.8

Hạn chế sử dụng thuộc tính `!important`.
Chừng nào không tìm giải pháp thay thế và cần thiết lắm thì mới sử dụng thuộc tính `!important`.

``` css
/* Không nên */
h1 {
  color: #0cf !important;
}

/* Nên */
h1 {
  color: #0cf;
}
```


1.9

Ưu tiên viết `@media` trong từng block/section để kiểm soát css tốt hơn

``` css
/* Không nên */
.btn {}
@media (min-width: 991px) {}

/* Nên */
.btn {
  @media (min-width: 991px) {}
}
```



### **2. Đặt tên**

2.1

Nên sử dụng quy tắc BEM cho việc đặc tên.

[Get BEM](http://getbem.com/naming/)

``` css
.block {} /* Block */
.block__element {} /* Element */
.block--modefier {} /* Modefier */
```


2.2

Tên của css được viết bằng chữ thường (lowercase), hạn chế sử dụng tên viết hoa (capitalize), hoặc chữ in hoa (uppercase).

``` css
/* Không nên */
.Heading {}
.HEADING {}

/* Nên */
.heading {}
```



### **3. Viết ngắn gọn**

3.1

Hạn chế viết các selector lồng với nhau (nested) và các ancestor selector không cần thiết. Việc này giúp ít rất nhiều để code css dễ đọc, dễ tuỳ chỉnh, tiết kiệm thời gian khi chỉnh sửa.

``` css
/* Không nên */
nav ul li a {}
div.error {}

/* Nên */
nav a {}
.error {}
```


3.2

Loại bỏ đơn vị (unit) nếu giá trị là `0`

``` css
a {
  padding: 0;
  margin: 0;
}
```


3.3

Loại bỏ số `0` nếu giá trị có dáu thập phân

``` css
h1 {
  opacity: 0.5;
}

/* Nên */
h1 {
  opacity: .5;
}
```


3.4

Giá trị màu sắc HEX nên sử dụng hình thức giản lược (3 ký tự) nếu có thể.

``` css
/* Không nên */
a {
  color: #aabbcc;
}

/* Nên */
a {
  color: #abc;
}
```


3.5

a. Nên sử dụng cấu trúc shorthand khi selector có đầy đủ thuộc tính đó. Ví dụ selector có đầy đủ 4 thuộc tính của padding: `padding-top`, `padding-right`, `padding-bottom` và `padding-left` 

``` css
/* Không nên */
ul {
  padding-top: 10px;
  padding-right: 20px;
  padding-bottom: 30px;
  padding- left: 20px;
}

/* Nên */
ul {
  padding: 10px 20px 30px;
}
```


b. Nhưng khi chúng ta chỉ cần css một thuộc tính riêng lẻ (ví dụ: padding-top), thì ta cũng hạn ché sử dụng cấu trúc shorthand để tránh dư thừa và khó kiểm soát khi viết css.

``` css
/* Không nên */
ul {
  padding: 10px auto auto;
}

/* Nên */
ul {
  padding-top: 10px;
}
```