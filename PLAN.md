# Kế hoạch hoàn thiện ứng dụng Piano bàn phím

Ứng dụng là một tệp `index.html` duy nhất (HTML + JS thuần, Web Audio API), không cần cài đặt hay build.

## Đã xong

| Giai đoạn | Nội dung |
|---|---|
| 1. Đàn cơ bản | 3 quãng (C3–E5), bàn phím máy tính, chuột/cảm ứng, pedal Space, đổi quãng tám, 4 âm sắc, âm lượng, vang |
| 2. Ghi âm | Ghi, phát lại, xoá bản ghi (giữ nhịp, pedal, quãng tám) |
| 3. Học bài hát | Nốt rơi trên canvas, thẳng hàng với phím; phím hiện tên nốt (C D E, Db Eb…) và ký tự bàn phím; 3 chế độ (chờ bạn bấm đúng, tự chạy tính điểm, nghe đàn mẫu); chỉnh tốc độ; 5 bài miền công cộng; soạn nốt bằng văn bản; học lại từ bản ghi của mình |

## Việc tiếp theo, theo thứ tự ưu tiên

### 4. Luyện tập hiệu quả
- Lặp một đoạn (chọn ô nhịp bắt đầu/kết thúc, lặp A–B).
- Phân tay trái / tay phải bằng hai màu nốt, cho phép chỉ luyện một tay.
- Đếm nhịp vào bài (metronome) và hiện thanh tiến độ bài hát.
- Chấm điểm chi tiết: chính xác theo từng nốt, sớm/muộn, chuỗi đúng liên tiếp, lưu điểm cao nhất.

### 5. Thư viện bài hát
- Nhập tệp MIDI (`.mid`) và chuyển thành nốt rơi; chia nhỏ bản nhạc dài thành các đoạn.
- Thêm nhiều bài miền công cộng (Canon in D, Gymnopédie, Amazing Grace, các bài thiếu nhi Việt Nam).
- Phân độ khó (số nốt/giây, số phím đen) và tự lọc bài theo trình độ.
- Lưu ý bản quyền: bài còn bản quyền (ví dụ nhạc phim) chỉ để người dùng tự nhập hoặc nhập MIDI của họ, không đóng gói sẵn.

### 6. Chất lượng âm thanh
- Thay bộ tổng hợp bằng mẫu âm piano thật (SoundFont hoặc mẫu ngắn nội suy).
- Độ nặng nhẹ (velocity) theo thời gian giữ phím hoặc phím cảm ứng lực.
- Pedal cho chế độ nghe mẫu, bật/tắt vang theo bài.

### 7. Trải nghiệm và thiết bị
- Bố cục điện thoại/máy tính bảng: 1 quãng tám lớn, cuộn ngang, nút to.
- Hỗ trợ đàn MIDI thật qua Web MIDI API.
- Cho chọn bố cục phím máy tính (QWERTY, AZERTY, Dvorak) và tuỳ chỉnh ánh xạ phím.
- Giao diện sáng/tối, cỡ chữ, trợ năng (focus rõ, nhãn ARIA cho nút).

### 8. Lưu trữ và chia sẻ
- Lưu bản ghi và bài tự soạn vào `localStorage`.
- Xuất bản ghi ra MIDI và WAV; chia sẻ bài qua link (mã hoá nốt trong URL).

### 9. Chất lượng mã
- Tách `index.html` thành `style.css`, `app.js` (module: audio, keyboard, recorder, learn) khi lớn thêm.
- Kiểm thử tự động bằng Playwright (đã dùng thủ công): luồng chơi, ghi/phát, học bài ở cả 3 chế độ.
- GitHub Pages hoặc Vercel để triển khai bản chạy thử.

## Quyết định cần bạn xác nhận
1. Có muốn dùng mẫu âm piano thật (tệp lớn hơn, cần mạng lần đầu) hay giữ âm tổng hợp nhẹ?
2. Ưu tiên nhập MIDI trước hay thêm bài có sẵn trước?
3. Nhắm máy tính là chính hay cần tối ưu cho điện thoại?
