## 1. Regex với grep
![alt text](https://viblo.asia/uploads/eab2c004-9fee-4804-a921-8e41ee2076e3.png)

## 2. Cách viết regex.

+ Kí tự thường

| STT | Biểu thức | Mô tả                                     | Ghi chú                                                           |
|-----|-----------|-------------------------------------------|-------------------------------------------------------------------|
| 01  | a｜b      | Khớp với a hoặc b                         |                                                                   |
| 02  | [0-9]     | Khớp với một trong số từ 0 tới 9          |                                                                   |
| 03  | [a-z]     | Khớp với một trong chữ từ a tới z         |                                                                   |
| 04  | [abc]     | Có thể khớp với a, b hoặc c               |                                                                   |
| 05  | [^abc]    | Khớp với bất kì kí tự nào ngoài a, b và c | Nếu ^ xuất hiện đầu tiên sau ngoặc vuông, nó có nghĩa là phủ định |


| STT | Biểu thức | Mô tả                                    | Ghi chú                   |
|-----|-----------|------------------------------------------|---------------------------|
| 06  | \d        | Số bất kì                                | Thay thế cho [0-9]        |
| 07  | \D        | Ký tự không phải là số                   | Thay thế cho [^0-9]       |
| 08  | \s        | Kí tự khoảng trắng                       |                           |
| 09  | \S        | Không phải kí tự khoẳng trắng            | Thay thế cho [^\s]        |
| 10  | \S+       | Một số kí tự không phải khoẳng trắng     | Một hoặc một số           |
| 11  | \w        | Kí tự chữ                                | Thay thế cho [a-zA-Z0-9]  |
| 12  | \W        | Kí tự không phải chữ                     | Thay thế cho [^\w]        |
| 13  | \b        | Ký tự thuộc a-z hoặc A-Z hoặc 0-9 hoặc _ | Thay thế cho [a-zA-Z0-9_] |

+ Kí tự đặc biệt

| STT | Biểu thức | Mô tả                                                                             | Ghi chú                                                                                       |
|-----|-----------|-----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| 14  | .         | Khớp với bất kỳ ký tự đơn nào ngoại trừ \                                         |                                                                                               |
| 15  | ^         | Bắt đầu của từ                                                                    |                                                                                               |
| 16  | $         | Kết thúc của từ                                                                   |                                                                                               |
| 17  | /         | Bắt đầu hoặc kết thúc chuỗi regex                                                 |                                                                                               |
| 18  | ｜        | Sủ dụng tương đương phép or                                                       | Hay dùng trong cặp ngặc tròn                                                                  |
| 19  | \         | Biểu diễn một kí tự ngay sau nó từ kí tự đặc biệt thành kí tự thường và ngược lại | VD: \b sẽ trở thành như mình nói ở trên, * sẽ trở thành kí tự * chứ không phải số lần lặp nữa |

+ Lặp

| STT | Biểu thức | Mô tả                                                                                   | Ghi chú                 |
|-----|-----------|-----------------------------------------------------------------------------------------|-------------------------|
| 20  | *         | Xuất hiện 0 hoặc nhiều lần                                                              | viết ngắn gọn cho {0,}  |
| 21  | +         | Xuất hiện 1 hoặc nhiều lần                                                              | viết ngắn gọn cho {1,}  |
| 22  | ?         | Xuất hiện 0 hoặc 1 lần                                                                  | viết ngắn gọn cho {0,1} |
| 23  | {X}       | Xuất hiện X lần                                                                         | X không phải số âm      |
| 24  | {X,Y}     | Xuất hiện trong khoảng X tới Y lần                                                      | X,Y không phải số âm    |
| 25  | ?         | có nghĩa là xuất hiện 0 hoặc nhiều lần, thêm ? phía sau nghĩa là tìm kiếm khớp nhỏ nhất | Thay thế cho [^\w]      |

+ Khớp nhóm

| STT | Biểu thức | Mô tả                                                  | Ghi chú                                                                                    |
|-----|-----------|--------------------------------------------------------|--------------------------------------------------------------------------------------------|
| 26  | ()        | Khớp với một nhóm các kí tự đồng thời nhớ kết quả khớp | Ví dụ (e｜g)mail sẽ khớp với email hoặc gmail. /(ab) (cd) \1 \2/ sẽ khớp với "ab cd ab cd" |
| 27  | (?:x)     | Khớp với x nhưng không nhớ kết quả khớp                | "foo foo" sẽ khớp với /(foo) \1/ chứ không khớp với (?:foo) \1                             |
| 28  | x(?=y)    | Chỉ khớp x nếu ngay sau x là y                         | "hello" sẽ khớp với /h(?=e)/ nhưng kết quả trả về chỉ có h                                 |
| 29  | x(?!y)    | Chỉ khớp x nếu ngay sau x không phải là y              |                                                                                            |
