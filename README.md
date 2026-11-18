# NoliKorea · V6.0.0 Final

Học tiếng Hàn Seoul 1A: 8 bài, 224 mục, 32 track CD Audio thực dùng trong `AUDIO_MAP` (4 file/bài). Phiên ngắn, đọc/nghe, Recall, tự viết, Đóng vai, Sổ tay sửa lỗi thông minh và lịch ôn. Dữ liệu lưu trên thiết bị; Gemini là lựa chọn riêng.

## Bản V6.0.0 Final (Big Update)

- **Mở trực tiếp 1-Click HTML & Zero-Install**: Mở trực tiếp `Mo_NoliKorea_V6.html` hoặc `dist/index.html` (`file://`), chạy local với Python (`python -m http.server 8000 --directory dist`), hoặc cài PWA trên GitHub Pages — không cần cài Node.js.
- **Giao diện khóa chuẩn Final**: Hoàn thiện 100% Dark Mode & Light Mode trên Desktop, Tablet và Mobile (Header đồng bộ trái–phải, 3 modal CRUD, chế độ quản lý giáo trình, bàn phím ảo Hàn, Noli AI và các banner thông báo).
- **Active Recall thế hệ mới (506 câu · 5 kỹ năng · Hiệp ngắn 12 câu)**:
  - 96 bài tập Điền từ ngữ pháp có dịch nghĩa cả câu + 64 tình huống giao tiếp Seoul 1A + dạng bài mới **🎧 Nghe phản xạ** (thường & chậm `0.72x`).
  - Mặc định chia **Hiệp 12 câu cân bằng 5 kỹ năng** theo chế độ **🃏 Từng câu 1 thẻ** (chuyển 1 chạm sang Danh sách / Cả kho bài / Làm lại câu sai).
- **🐶 Noli · Luyện theo sách 100% Offline (không cần API Key)**: Hội thoại nhiều lượt theo ngữ cảnh 8 bài Seoul 1A (Chat & Gọi), gợi ý trả lời động, tự bắt lỗi ngữ pháp/chia đuôi và tra từ ngay trong sách; tương thích mở rộng cho Seoul 1B, 2A+.
- **🎵 Nhạc nền khi học Offline + Icon âm lượng trên Header**: 3 không gian âm thanh Web Audio API (Lo-fi Piano Seoul, Mưa rơi Seoul, Ambient) + chọn file nhạc riêng, tự động hạ nhỏ/tắt khi nghe CD, phát âm hoặc bật Micro.
- **Gamification ⚡ XP & 🔥 Streak + Sổ tay Sửa Lỗi Thông Minh**: Thưởng XP ở đủ 5 luồng học tập, chấm chuẩn mọi từ có biến thể ngoặc đơn / gạch chéo, đồng bộ khi Đặt lại / Nhập / Khôi phục.
- **Lưu trữ IndexedDB & Audio Offline (32 tracks)**: Lưu song song `localStorage` + IndexedDB; tải 32 track CD Audio thực dùng từ `AUDIO_MAP`, Service Worker hỗ trợ cache mọi `/audio/**/*.mp3` bổ sung sau này.

## Bản 5.0.6

Dùng Shiba Noli làm logo đầu trang, favicon và icon cài đặt. Có icon riêng cho iOS và Android maskable để tránh cắt tai linh vật.

## Bản 5.0.5

Noli, linh vật Shiba, thay avatar Bạn học AI trong thanh đầu trang, giáo trình, chat và gọi thoại. Thu gọn nhãn, lời chào và khung giới thiệu; giải thích câu trong chat có thể mở khi cần. Giữ phạm vi luyện theo sách, mic và thời gian chờ AI.

## Bản 5.0.4

Bỏ 26 chú thích chữ Hán khỏi từ vựng và làm sạch chú thích trong bản lưu cũ, bài luyện, sổ lỗi và dữ liệu nhập. Giữ ghi chú phát âm, ID mục học, tiến độ và lịch ôn.

## Bản 5.0.3

Thu gọn lối tắt bài học và phiên ngắn thành hai nút trên cùng một hàng, kể cả trên điện thoại. Bỏ khối giới thiệu và thống kê lớn đầu trang để giáo trình là nội dung chính. Giữ nguyên luồng tiếp tục học và phiên ngắn.

## Bản 5.0.2

Tối ưu các luồng hiện có, không thêm chức năng hay thay đổi giáo trình:

- Giữ bản nháp Recall/Production khi đổi bộ lọc, đổi bài và mở lại phiên; phục hồi phản hồi của câu đã chấm.
- Dừng mic và TTS đúng lúc khi đổi màn; hủy callback, lịch phát và lời chào từ phiên AI đã đóng. Nút mic trở về trạng thái ban đầu khi dừng.
- Lưu kết quả ôn lỗi ngay khi trả lời; hủy tìm kiếm đang chờ khi xóa hoặc đóng kết quả.
- Chỉ xử lý các phần giao diện vừa thay đổi; giảm kiểm tra và chuyển đổi dữ liệu lặp khi lưu, giữ kiểm tra hợp lệ và chống ghi đè giữa các tab.
- Giữ thời gian chờ phản hồi AI 30 giây và hộp nghe CD chỉ trong Input.

## Chạy và sửa

Ứng dụng nằm trong `dist/`. Chạy `python -m http.server 8000 --directory dist`, mở http://localhost:8000.

Để phát triển: Node 22+, `npm ci`, `npm run build`, `npm test`.
`data/curriculum.json` là nguồn giáo trình duy nhất; không sửa trực tiếp hai bản curriculum được sinh trong dist. Giữ ID mục học khi sửa chữ/nghĩa để giữ lịch ôn.

## GitHub Pages

1. Tạo repository và đưa **toàn bộ dự án**, gồm `.github`, `data`, `scripts`, `tests`, `dist`, package*.json lên nhánh `main`. Không đưa node_modules, API key hoặc bản sao lưu cá nhân lên repository.
2. Settings → Pages → Source: **GitHub Actions**.
3. Workflow Pages kiểm thử, build và xuất ứng dụng. URL do Actions trả về thường là `https://USERNAME.github.io/REPOSITORY/`.
4. Safari → Chia sẻ → Thêm vào Màn hình chính. Android Chrome → ⋮ → Cài đặt ứng dụng.
5. Xuất dữ liệu ở địa chỉ cũ rồi nhập ở địa chỉ mới. Không có đồng bộ giữa thiết bị/địa chỉ.

Workflow Pages loại các tệp ZIP chia nhỏ khỏi thư mục triển khai. Đẩy tag dạng `v5.0.2` để workflow Release tạo ZIP đầy đủ ở GitHub Releases. Bản ZIP đầy đủ được cung cấp qua GitHub Releases.

## Dữ liệu và nâng cấp

Khóa lưu trữ cũ được giữ để tự chuyển dữ liệu V3/V4. Mỗi mục có ID; bản nhập cũ được gán ID và lịch ôn được nối lại nếu xác định đúng mục. Mục không khớp vẫn được giữ trong dữ liệu thay vì xóa. Sao lưu gồm tiến độ, nội dung tùy chỉnh, ghi chú và tùy chọn học, không gồm API key.

Cài đặt thông thường gồm giao diện, âm thanh, sao lưu. Khôi phục/đặt lại và công cụ sửa giáo trình nằm trong phần mở rộng. Các bài chưa có nội dung được ẩn khi học.

## Giới hạn xác minh

Đã kiểm thử Node/jsdom, dữ liệu, bài luyện, migration, lưu/khôi phục, AI giả lập và vòng đời service worker. Chưa kiểm thử thực tế iPhone/Android/Home Screen, micro và API key thật trong môi trường này. Chưa nghe đối chiếu 32 track tham chiếu với transcript; không tuyên bố học liệu đã được thẩm định ngôn ngữ hoàn toàn.

Hỗ trợ tải sẵn offline 32 track CD Audio đang dùng trong `AUDIO_MAP` và cache tự động theo yêu cầu cho mọi bài học mới. Nội dung tham khảo gốc được giữ riêng.
