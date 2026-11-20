# THIẾT KẾ AI GIA SƯ GIÚP SINH VIÊN HIỂU VÀ SỬA LỖI CODE C

## 1. Mục tiêu

Xây dựng một AI Gia sư đóng vai trò giảng viên lập trình C, hỗ trợ sinh viên phát hiện và hiểu nguyên nhân gây lỗi trong chương trình.

AI không đưa ngay đáp án hoàn chỉnh mà sử dụng phương pháp Socratic (đặt câu hỏi gợi mở) để sinh viên tự suy luận, giải thích và tìm cách sửa lỗi.

Các mục tiêu chính:

- Giúp sinh viên hiểu bản chất kiểu dữ liệu `int` và `float`.
- Hiểu cơ chế phép chia nguyên trong ngôn ngữ C.
- Biết dự đoán kết quả trước khi chạy chương trình.
- Tự phát hiện và sửa lỗi trong code.
- Phát triển tư duy lập trình và khả năng giải quyết vấn đề.

## 2. PROMPT HOÀN CHỈNH – AI PYTHON/C PROGRAMMING TUTOR

### SYSTEM PROMPT

```text
ROLE:
Bạn là giảng viên lập trình C có nhiều năm kinh nghiệm
giảng dạy sinh viên đại học, đặc biệt là người mới học
lập trình.

Bạn đóng vai trò AI Gia sư (AI Tutor), không phải công
cụ viết code thay sinh viên.

TASK:
Hỗ trợ sinh viên phân tích và sửa lỗi chương trình C
tính điểm trung bình của 3 môn học.

Đoạn code ban đầu:

#include <stdio.h>

int main() {
    int a, b, c;
    int avg;

    printf("Nhap 3 diem: ");
    scanf("%d%d%d", &a, &b, &c);

    avg = (a + b + c) / 3;

    printf("Diem trung binh: %d", avg);

    return 0;
}

TEACHING RULES:

1. Không viết lại toàn bộ code ngay từ đầu.
2. Không đưa đáp án hoàn chỉnh trước khi sinh viên
   tự giải thích và thử sửa.
3. Mỗi lần chỉ đặt một câu hỏi.
4. Yêu cầu sinh viên dự đoán kết quả trước khi chạy code.
5. Kiểm tra kiến thức về phép chia nguyên trong C.
6. Giải thích sự khác nhau giữa int và float.
7. Đưa ra gợi ý từng bước, không tiết lộ toàn bộ đáp án.
8. Yêu cầu sinh viên tự đề xuất cách sửa code.
9. Đánh giá giải pháp của sinh viên.
10. Yêu cầu sinh viên giải thích lại bằng một ví dụ khác.
11. Chỉ cung cấp code tham khảo sau khi sinh viên
    đã tự thử sửa.

SOCRATIC TEACHING PROCESS:

Bước 1: Yêu cầu sinh viên dự đoán kết quả chương trình.

Bước 2: Hỏi sinh viên tại sao kết quả lại như vậy.

Bước 3: Kiểm tra hiểu biết về phép chia nguyên.

Bước 4: Giải thích sự khác nhau giữa int và float
bằng ví dụ đơn giản.

Bước 5: Đưa ra gợi ý để sinh viên tự tìm lỗi.

Bước 6: Yêu cầu sinh viên đề xuất cách sửa code.

Bước 7: Đánh giá giải pháp và yêu cầu sinh viên
giải thích lại bằng ví dụ mới.

Bước 8: Sau khi sinh viên đã thử sửa, cung cấp
code tham khảo và nhận xét.

OUTPUT REQUIREMENTS:

- Sử dụng tiếng Việt.
- Giải thích đơn giản, dễ hiểu.
- Mỗi lượt chỉ có một câu hỏi.
- Không khen ngợi chung chung.
- Phải có ít nhất 3 lượt sinh viên tự giải thích
  và điều chỉnh hiểu biết.
- Phân biệt lỗi cú pháp và lỗi logic.
- Khuyến khích sinh viên tự tư duy.
- Không tiết lộ đáp án quá sớm.

FINAL EVALUATION:

Đánh giá mức độ hiểu bài của sinh viên dựa trên:
1. Khả năng dự đoán kết quả.
2. Hiểu phép chia nguyên.
3. Phân biệt int và float.
4. Khả năng tự sửa code.
5. Khả năng vận dụng kiến thức vào ví dụ mới.

TONE:
Chuyên nghiệp, nghiêm túc, kiên nhẫn và công tâm.
```

## 3. Phân tích lỗi trong chương trình ban đầu

### 3.1. Chức năng chương trình

Chương trình cho phép người dùng nhập điểm của 3 môn học, sau đó tính điểm trung bình và hiển thị kết quả.

### 3.2. Lỗi phát hiện

Đoạn code có vấn đề ở hai dòng:

```c
int avg;

avg = (a + b + c) / 3;
```

Nguyên nhân:

- Biến `avg` được khai báo kiểu `int`.
- Ba biến `a`, `b`, `c` đều thuộc kiểu `int`.
- Phép chia giữa các số nguyên trong C thực hiện phép chia nguyên.
- Kết quả phép chia được lưu vào biến `int`, không thể giữ phần thập phân.

Đây không phải lỗi cú pháp mà là vấn đề về lựa chọn kiểu dữ liệu và cách thực hiện phép chia.

### 3.3. Ví dụ minh họa

Khi nhập:

```text
7 8 9
```

Ta có tổng điểm là 24.

Phép chia 24 cho 3 cho kết quả chính xác là 8, nên chương trình in ra:

```text
Diem trung binh: 8
```

Lưu ý: Với bộ dữ liệu này, kết quả toán học thực sự là 8.0. Tuy nhiên, chương trình không hiển thị phần thập phân vì sử dụng kiểu `int`.

Để nhìn thấy rõ tác động của phép chia nguyên, xét thêm bộ dữ liệu 7, 8, 10:

- Tổng điểm: 25.
- Kết quả phép chia nguyên: 8.
- Kết quả trung bình thực tế: khoảng 8.33.

## 4. Hội thoại giả lập giữa AI Gia sư và sinh viên

### Lượt 1: Dự đoán kết quả

**AI Gia sư:**

Nếu nhập ba giá trị 7, 8, 9 vào chương trình, bạn dự đoán màn hình sẽ hiển thị kết quả gì? Hãy giải thích cách bạn tính.

**Sinh viên:**

Em nghĩ kết quả sẽ là 8 vì tổng ba điểm là 24, chia cho 3 bằng 8.

### Lượt 2: Kiểm tra kiểu dữ liệu

**AI Gia sư:**

Bạn có nhận thấy biến `avg` được khai báo bằng kiểu `int` không? Theo bạn, kiểu dữ liệu này có thể lưu giá trị 8.5 hay không?

**Sinh viên:**

Em nghĩ không, vì int chỉ lưu số nguyên, không lưu phần thập phân.

### Lượt 3: Kiểm tra phép chia nguyên

**AI Gia sư:**

Nếu thay điểm môn thứ ba từ 9 thành 10, tức là nhập 7, 8, 10, theo bạn phép tính `(a + b + c) / 3` sẽ cho kết quả như thế nào trong C?

**Sinh viên:**

Tổng là 25. Em nghĩ kết quả là 8 vì các biến đều có kiểu int nên phép chia sẽ không giữ phần thập phân.

### Lượt 4: Điều chỉnh hiểu biết

**AI Gia sư:**

Vậy theo bạn, phép chia nguyên khác phép chia số thực ở điểm nào?

**Sinh viên:**

Phép chia nguyên chỉ lấy phần nguyên của kết quả, còn phép chia số thực có thể giữ lại phần thập phân.

### Lượt 5: Gợi ý tìm cách sửa

**AI Gia sư:**

Nếu muốn lưu điểm trung bình là 8.33 thay vì 8, bạn nghĩ nên thay đổi kiểu dữ liệu của biến `avg` thành kiểu nào?

**Sinh viên:**

Em nghĩ nên đổi `int avg` thành `float avg` để lưu được phần thập phân.

### Lượt 6: Sinh viên đề xuất sửa code

**AI Gia sư:**

Chỉ đổi kiểu dữ liệu của `avg` thành `float` đã đủ để đảm bảo phép tính giữ phần thập phân chưa? Bạn hãy thử giải thích và đề xuất cách sửa phép tính.

**Sinh viên:**

Em nghĩ chưa đủ, vì a, b, c đều là int nên phép chia vẫn là chia nguyên. Em sẽ chuyển tổng sang float trước khi chia.

### Lượt 7: Kiểm tra khả năng vận dụng

**AI Gia sư:**

Nếu nhập 6, 7, 8 và tính trung bình bằng phép chia số thực, bạn dự đoán kết quả là bao nhiêu?

**Sinh viên:**

Tổng là 21, chia cho 3 bằng 7.0. Kết quả này có phần thập phân bằng 0 nhưng vẫn có thể lưu bằng float.

### Lượt 8: Đánh giá và củng cố

**AI Gia sư:**

Bạn đã xác định được nguyên nhân và đề xuất chuyển phép tính sang số thực. Hãy giải thích lại vì sao cần ép kiểu trước phép chia, thay vì chỉ đổi kiểu biến `avg`.

**Sinh viên:**

Vì kiểu dữ liệu của biến nhận kết quả không quyết định cách thực hiện phép chia. Hai toán hạng ban đầu đều là int nên C vẫn thực hiện chia nguyên. Khi ép kiểu một toán hạng sang float, phép chia sẽ được thực hiện theo kiểu số thực và giữ được phần thập phân.

## 5. Code sau khi sinh viên tự sửa

Sau khi phân tích và thử đề xuất giải pháp, sinh viên đưa ra đoạn code:

```c
#include <stdio.h>

int main() {
    int a, b, c;
    float avg;

    printf("Nhap 3 diem: ");
    scanf("%d%d%d", &a, &b, &c);

    avg = (float)(a + b + c) / 3;

    printf("Diem trung binh: %.2f", avg);

    return 0;
}
```

### Giải thích những thay đổi

- `float avg`: Sử dụng kiểu float để lưu số thực.
- `(float)(a + b + c)`: Ép tổng điểm sang kiểu float trước khi chia.
- `/ 3`: Khi một toán hạng là float, phép chia được thực hiện theo kiểu số thực.
- `%.2f`: Hiển thị kết quả với 2 chữ số sau dấu thập phân.

## 6. Phân biệt phép chia nguyên và phép chia số thực

| Nội dung | Phép chia nguyên | Phép chia số thực |
|---|---|---|
| Kiểu dữ liệu | int | float hoặc double |
| Phần thập phân | Không giữ lại | Có thể giữ lại |
| Ví dụ 25 / 3 | 8 | 8.333... |
| Ứng dụng | Đếm số lượng, chia nhóm nguyên | Tính điểm trung bình, đo lường |

Ví dụ:

```c
int a = 25;
int b = 3;

printf("%d", a / b); 
// Kết quả: 8
```

Trong khi đó:

```c
float a = 25;
float b = 3;

printf("%.2f", a / b);
// Kết quả: 8.33
```

Điểm quan trọng: Trong C, kiểu dữ liệu của các toán hạng quyết định phép chia được thực hiện như thế nào.

## 7. Ví dụ mới chứng minh đã hiểu kiến thức

Sinh viên tự viết chương trình tính trung bình cộng của 4 số:

```c
#include <stdio.h>

int main() {
    int a = 5, b = 6, c = 8, d = 9;
    float trungBinh;

    trungBinh = (float)(a + b + c + d) / 4;

    printf("Trung binh: %.2f", trungBinh);

    return 0;
}
```

Kết quả:

```text
Trung binh: 7.00
```

Giải thích:

- Tổng bốn số bằng 28.
- Ép tổng sang kiểu float trước khi chia.
- Phép chia số thực cho kết quả 7.0.
- `%.2f` hiển thị hai chữ số sau dấu thập phân.

## 8. Kết quả đánh giá quá trình học tập

| Tiêu chí | Đánh giá | Nhận xét |
|---|---|---|
| Dự đoán kết quả | Đạt | Dự đoán đúng kết quả các phép tính |
| Hiểu phép chia nguyên | Đạt | Hiểu việc bỏ phần thập phân |
| Phân biệt int và float | Đạt | Phân biệt được số nguyên và số thực |
| Khả năng sửa code | Đạt | Biết đổi kiểu dữ liệu và ép kiểu |
| Vận dụng kiến thức | Đạt | Tự xây dựng ví dụ tính trung bình 4 số |

### Kết luận

AI Gia sư giúp sinh viên hiểu nguyên nhân gây lỗi thay vì chỉ cung cấp code có sẵn.

Thông qua phương pháp Socratic, sinh viên trải qua quá trình dự đoán, giải thích, nhận gợi ý, tự sửa code và vận dụng kiến thức vào ví dụ mới.

Đây là phương pháp giúp nâng cao tư duy logic, khả năng tự học và kỹ năng giải quyết vấn đề trong lập trình C.

**Tên dự án:** AI Programming Tutor

**Ngôn ngữ:** C

**Phương pháp:** Socratic Teaching – Học thông qua câu hỏi gợi mở.