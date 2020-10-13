1) Which of the following is a valid JavaScript variable name (Multiple selection)
    A. 4G
    B. G7
    C. $_this_is_a_long_name
    D. aaa ddd
Select B and C: Bởi vì: 
    Trong Javascript:
    Tên biến chỉ có thể chứa chữ cái, số, dấu gạch dưới hoặc ký hiệu đô la.
    Tên biến phân biệt chữ hoa chữ thường.
    Tên biến phải bắt đầu bằng chữ cái, dấu gạch dưới (_) hoặc dấu đô la ($).

2) What will the code below output to the console? (Single selection)
(function(){
  var a = 35;
})();
A. a defined? null
B. a defined? true
C. a defined? false
D. a defined? undefined

 
console.log("a defined? " + (typeof a !== 'undefined'));
Select  C
    Bởi vì: ở trên dùng IIFE (Immediately Invoked Function Expression)
    nó sẽ tạo ra 1 block scope bên trong nó và biến a tuy rằng sử dung var ( cho global) 
    nhưng bên trong iffe thì nó sẽ thành local scope vậy nên khi console.log(a) ở ngoài 
    thì sẽ là chưa đc định nghĩa 

3. 	What will the code below output to the console? (Single selection)
function fn(name) {
   return //(1)
     	'Hello: ' + name; (2)
} 
console.log(fn('JS'));

A. Hello: JS
B. undefined
C. Hello: undefined
D. None of the above

Select B :
    Bởi vì: khi function chạy nó return ở (1) thì nó hiểu là k return ra cái gì cả 
    và kết thúc luôn cái chương trình đó và hiện ra undefined và k chạy ở cái dòng
    (2) nữa .

4.What will the code below output to the console? (Single selection)
console.log(0.1 + 0.2 == 0.3);
A. true
B. undefined
C. false
D. None of the above

Select C:
    Bởi vì: trong nhiều ngôn ngữ lập trình nói chung và javascript 
    nói riềng khi đoạn code thực thi nó sẽ quy về dạng bit (0,1) cho 
    máy tính hiểu, và máy tính không thể biểu diễn chính xác 0.1 và 0.2

    Ví dụ: Khi 0.1 dịch được làm tròn đến số gần nhất ở định dạng đó, điều này làm đến lỗi 
    nhỏ ngay cả khi phép + xảy ra. 

5. 	What will the code below output to the console? (Single selection)
var obj = {
   toString: function() {
     	return '' + new Date();
	}
}
console.log(+obj.toString()); (1)

A. Current time in milliseconds
B. undefined
C. null
D. NaN

Select D: 

    Vì ở (1) khi toán tử + thì phải + cho 2 hoặc nhiều số nhưng ở đây máy tính nói chung 
    và JS nói riêng sẽ không hiểu  cái trước dấu + là định dạng số hay string để nó +

6. 	What will the code below output to the console? (Single selection)
var obj = {
   valueOf: function() {
     	return 456;
	}
}
 
 
console.log([1, 2, 3] + obj);
A. ‘1,2,3456’
B. NaN
C. null
D. 123456

Select A:
// Trước tiên chúng ta cần hiểu 2 vấn đề :
    1) trong Javascript là có tính scope chain nghĩa là 
    thằng obj ở trên sinh ra thì nó sẽ nối liền với thằng Object mẹ bằng obj.__proto__
    Thàng Objet mẹ là 1 Prototype có khai báo hàm ValueOf() trong JS, hàm  valueOf tự động
    chạy khi nó thấy return ra 1 dạng kiểu "Primitives" ở đây là Number nên khi obj nó sẽ
    return ra 456
    
    2) Toán tử + không sử dụng trong Array mà array là 1 Object + Number như (1) => string 
    và nó sẽ + dồi lại với nhau thành như ở trên;

7. 	What will the code below output to the console? (Single selection)
(function() {
	console.log(1);
	setTimeout(function(){console.log(2)}, 1000);
	setTimeout(function(){console.log(3)}, 0);
	console.log(4);
})();
A. 1 2 3 4
B. 4 3 2 1
C. 2 3 1 4
D. 1 4 3 2
Select D: 
    khi chạy IFFE vì setTimeout là 1 async (bất đồng bộ) nên nó sẽ k chaỵ theo sync
    => 1 4 
    Tiếp đén setTimeOut(1s) => sẽ lâu hơn thằng 0s nên nó đc ném vào Queu trước
    và rồi FIFO của QUEU 

8. 	What will the code below output to the console? (Single selection)
(function(x) {
	return (function(y) {
    	console.log(x);
	})(2)
})(1);
A. 1
B. 2
C. undefined
D. null

Select A: 
    Theo em nghĩ đây là giống như CLOSURD nên thằng (x) 
    nó vẫn còn ở trong hộp thằng Gra (em hay gọi là thằng dọn rác)
    nên vẫn console.log(1) đc
9. 	What will the code below output to the console? (Single selection)
let x = 0;
async function r5() { (1)
  x += 1;
  console.log(x);
  return 5;
}

(async () => {
  x += await r5(); (2)
  console.log(x);
})();
A. null
B. 6
C. undefined
D. 5
Select D: 
    Hàm async (1) thật sự chỉ chạy khi nó (2) => thì lúc đó thằng x ở đây nó đang là 0; 
    và khi chạy thằng 0 + 5 là ra 5;
    còn thằng x+= 1; vẫn chạy nhưng ở ngoài global thì nó mới lên 1. 


Which function below will work as expected? (Multiple selection)
console.log(sum(5)(2)); // Expected output: 7
A. var sum = x => y => x * y
B. function sum(x, y) { return x + y; }
C. var sum = x => y => x + y
D. function sum(x) { return function(y) { return x + y;} }

Select D,C ( Tuỳ thuộc vào console.log(sum(5)(2)) )

    Nếu console.log(sum(5)(2)) nó đứng ở đầu thì loại thàng C 
    Liên quan tới HOISTING (Function Expression , arrows funcion)
    Nếu console.log(sum(5)(2)) nó đứng ở cuối các hàmg thì C,D