# Ôn thi sát hạch Đấu thầu

Web app trắc nghiệm từ ngân hàng 390 câu (bản 9.9.2026). Đây là site tĩnh, không cần build hay backend.

## Tính năng
- Chọn số câu (25 / 50 / 100 / tất cả / tùy ý) và thời gian (không giới hạn hoặc số phút tùy ý; hết giờ sẽ tự nộp bài)
- Lọc theo phần: Luật, Nghị định, Thông tư, Vận dụng
- Cách chọn câu: ngẫu nhiên / ưu tiên câu chưa làm / chỉ câu từng sai
- 2 chế độ: Thi thử (chấm khi nộp) và Luyện tập (hiện đáp án + căn cứ ngay)
- Xem lại câu sai kèm căn cứ pháp lý, làm lại các câu sai
- Lưu lịch sử, thống kê đúng/sai và bài đang làm dở trên trình duyệt (localStorage)

## Cấu trúc
- `index.html`: toàn bộ giao diện và logic
- `questions.json`: dữ liệu câu hỏi. Mỗi câu gồm `id`, `p` (phần: luat/nd/tt/vd), `q` (câu hỏi), `o` (các phương án), `a` (chỉ số đáp án đúng, bắt đầu từ 0), `e` (căn cứ)

## Chạy thử trên máy
```
python3 -m http.server 8000
```
Sau đó mở http://localhost:8000. Không mở trực tiếp file index.html được, vì trình duyệt chặn đọc questions.json.

## Deploy lên Vercel
1. Tạo repo mới trên GitHub, upload 3 file `index.html`, `questions.json`, `README.md`.
2. Vào vercel.com, đăng nhập bằng GitHub, chọn **Add New → Project**, rồi chọn repo vừa tạo.
3. Ở mục Framework Preset để **Other**, không cần điền gì thêm, bấm **Deploy**.

Muốn sửa hoặc thêm câu hỏi thì sửa `questions.json` trên GitHub. Vercel sẽ tự deploy lại.
