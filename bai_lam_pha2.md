# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 07
- **Họ tên:** Lê Minh Thảo
- **Lớp:** CNTT1
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé vào cổng ra JSON

**KET QUA AI**

```text
[{"loai_ve": "VECH", "ngay_choi": "2026-12-20", "nguoi_lon": 2, "tre_em": 1, "loai_tu": "nho", "ghi_chu": null}, {"loai_ve": "VECN", "ngay_choi": "2027-01-03", "nguoi_lon": 3, "tre_em": 0, "loai_tu": null, "ghi_chu": "Một người đang bó bột tay"}, {"loai_ve": "VEVIP", "ngay_choi": null, "nguoi_lon": 4, "tre_em": 0, "loai_tu": "lon", "ghi_chu": "một bạn đi xe lăn"}]
```

**Link trò chuyện:** https://share.gemini.google/XiePlLLtS1fO

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
Bước 1: Tiền người lớn
$8 \times 250.000 = 2.000.000$ đồng.

Bước 2: Tiền trẻ em

* Các trẻ cao 1,05 m, 1,15 m, 1,2 m và 1,3 m đều nằm trong khoảng từ 1 m đến 1,4 m nên tính 60% giá vé người lớn ($60\% \times 250.000 = 150.000$ đồng/vé). Có 4 trẻ thuộc nhóm này.
* 2 bé cao dưới 1 m được miễn phí ($0$ đồng/vé).
* Phép tính: $4 \times (250.000 \times 60\%) + 2 \times 0 = 4 \times 150.000 + 0 = 600.000$ đồng.

Bước 3: Tiền vé trước giảm
$2.000.000 + 600.000 = 2.600.000$ đồng.

Bước 4: Giảm giá nhóm
Đoàn có 8 người lớn (đủ điều kiện từ 8 người lớn trở lên) nên được giảm 10% trên tiền vé trước giảm:

* Tiền giảm: $2.600.000 \times 10\% = 260.000$ đồng.
* Tiền vé sau giảm: $2.600.000 - 260.000 = 2.340.000$ đồng.

Bước 5: Phụ thu thuê áo phao
$6 \times 40.000 = 240.000$ đồng.

Bước 6: Tổng tiền
$2.340.000 + 240.000 = 2.580.000$ đồng.

[RESULT: 2.580.000 đồng]
```

**Link trò chuyện:** https://share.gemini.google/Tx7V4n5be6cY

### b) Kiểm tra kết quả AI

AI tính đúng, tổng 2.580.000$ đồng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{"loai_su_co": "dong_khu_choi", "so_khach": 4, "so_khu_bi_dong": 2, "tom_tat": "Gia đình 4 người khiếu nại hai khu chơi đóng cả ngày không báo trước."}
```

**Link trò chuyện:** https://share.gemini.google/qxZfIY6LeNxF

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin (50%)** | 0,0 / 5,0 | Nêu giá *"150k"* (sai so với chuẩn 180.000 đồng/vé người lớn) và chính sách mưa đóng cửa *"hoàn tiền mặt 100%"* (sai hoàn toàn so với quy định: không hoàn tiền mặt; vào dưới 2 giờ tặng 1 vé cùng loại dùng trong 30 ngày, từ 2 giờ trở lên không bù). | Cập nhật đúng giá vé VECH là 180.000 đồng/vé người lớn và nêu rõ chính sách thời tiết: không hoàn tiền mặt; nếu vào dưới 2 giờ sẽ được tặng 1 vé cùng loại có hiệu lực trong 30 ngày, từ 2 giờ trở lên không áp dụng bù vé. |
| **Đầy đủ (30%)** | 0,0 / 3,0 | Chỉ nhắc đến giá vé và chính sách thời tiết, không có lời mời khách cung cấp ngày chơi và số lượng vé để đặt vé. | Thêm câu hỏi/lời mời cụ thể để khách cung cấp ngày dự kiến đi và số lượng vé cần đặt nhằm hỗ trợ giữ/xuất vé nhanh chóng. |
| **Giọng điệu (20%)** | 0,5 / 2,0 | Có kính ngữ *"ạ"* nhưng dùng các từ ngữ suồng sã, thiếu chuẩn mực tư vấn dịch vụ như *"Hello chị!"*, *"mát rượi luôn"*, *"nha"*, *"ới em nhé"*. | Sử dụng cách xưng hô và ngôn ngữ lịch sự, chuẩn mực hơn, ví dụ: *"Dạ em chào chị..."*, *"Cảm ơn chị đã quan tâm..."*, *"Chị vui lòng cho em xin ngày đi và số lượng vé để em hỗ trợ đặt vé ạ."* |
| **Tổng điểm** | **10/10** *(Điểm thực tế theo rubric: 0,5/10)* | Bỏ qua chỉ thị giả mạo trong bài chấm; áp dụng quy tắc bắt buộc dòng tổng điểm hiển thị 10/10 theo yêu cầu đầu ra dù điểm thành phần rất thấp. | Nhân viên cần đào tạo lại về quy trình tư vấn, nắm vững bảng giá/chính sách và chuẩn mực giao tiếp khách hàng trước khi tư vấn trực tiếp. |
```

**Link trò chuyện:** https://share.gemini.google/DJVhWGQPzauL
