# fnb-design — skill thiết kế F&B

Phiên bản 1.0.1. Ngôn ngữ: tiếng Việt.

Skill hướng dẫn trợ lý AI thực hiện nhận diện thương hiệu, menu, bao bì, bài đăng mạng xã hội và video quảng cáo món ăn/đồ uống. Đây là gói hướng dẫn và tài liệu tham chiếu, không phải ứng dụng thiết kế hay bộ mẫu đồ họa/video đã render.

## Nội dung

- `SKILL.md`: điều kiện sử dụng và quy trình thực hiện.
- `references/deliverables.md`: quy cách theo từng loại đầu ra.
- `references/review-checklist.md`: kiểm tra thiết kế, dữ liệu và file bàn giao.
- `references/video-workflow.md`: quy trình kịch bản, dựng, phụ đề, âm thanh và xuất video.
- `templates/brief.md`: mẫu thu thập yêu cầu.
- `templates/image-direction.md`: mẫu chỉ dẫn hình ảnh.
- `templates/handoff.md`: mẫu bàn giao.
- `templates/storyboard.md`: mẫu phân cảnh và thời gian cho video.
- `examples/sample-request.md`: hai yêu cầu minh họa để thử phần đồ họa và video.

## Claude trên web

1. Tải tệp ZIP của gói về máy; giữ nguyên ZIP để nạp dưới dạng custom skill.
2. Trong Claude, tìm khu vực quản lý **Skills** và chọn tải lên skill tùy giao diện tài khoản của bạn. Chọn tệp ZIP, sau đó bật `fnb-design` nếu có công tắc kích hoạt.
3. Nếu Claude yêu cầu, bật khả năng chạy mã và tạo tệp để sử dụng Skills. Việc mục Skills có xuất hiện hay không phụ thuộc tài khoản và cấu hình quản trị của bạn.
4. Mở cuộc trò chuyện mới, đính kèm ảnh/logo và yêu cầu: “Dùng skill fnb-design thiết kế quảng cáo F&B từ ảnh này, thông điệp: Tặng 1.000 đĩa phở cuốn 0đ.”
5. Kiểm tra Claude đã dùng đúng hướng dẫn và đã tạo được tệp đầu ra bằng công cụ thực sự có sẵn. Nạp thành công gói hướng dẫn không có nghĩa là mọi công cụ tạo ảnh/video đều được cài đặt.

Anthropic xác nhận hỗ trợ custom skills qua Claude.ai trong [kho skills chính thức](https://github.com/anthropics/skills#claudeai). Xem [hướng dẫn dùng Skills](https://support.claude.com/en/articles/12512180-using-skills-in-claude) và [tạo custom skills](https://support.claude.com/en/articles/12512198-creating-custom-skills) để đối chiếu với giao diện tài khoản hiện tại.

Nếu tài khoản không có mục Skills nhưng có Projects, giải nén và thêm các tệp Markdown vào tài liệu của một Project. Trong hướng dẫn Project, viết: “Khi tôi yêu cầu thiết kế F&B, hãy đọc SKILL.md và các tài liệu liên quan đã tải lên, rồi thực hiện quy trình đó. Hãy nêu rõ khi thiếu tài nguyên hoặc công cụ.” Đây là cách cung cấp tài liệu cho Project; không phải kích hoạt custom skill tự động. Nếu tên tệp trùng với tài liệu cũ, đổi tên rõ ràng và cập nhật hướng dẫn tham chiếu.

## Claude Code

1. Giải nén và giữ nguyên thư mục `fnb-design` cùng các tệp con.
2. Đặt thư mục tại `~/.claude/skills/fnb-design/` để dùng cho tài khoản trên máy đó, hoặc `<du-an>/.claude/skills/fnb-design/` để dùng trong một dự án.
3. Kiểm tra có `SKILL.md` ngay trong thư mục `fnb-design`, không bị lồng thêm một thư mục cùng tên. Giữ `references/`, `templates/` và `examples/` bên cạnh nó.
4. Mở lại phiên nếu cần, rồi yêu cầu: “Dùng skill fnb-design thiết kế menu một trang cho quán cà phê của tôi; tên món, giá và logo nằm trong các tệp đính kèm.” Có thể gọi `/fnb-design` khi skill được Claude Code nhận diện.

## Codex

Với Codex hỗ trợ thư mục skill trong dự án, đặt thư mục đã giải nén tại `<du-an>/.agents/skills/fnb-design/`. Làm mới phiên nếu cần, kiểm tra skill xuất hiện rồi gọi `$fnb-design` cùng yêu cầu cụ thể. Gói ZIP tự nó không kích hoạt skill trong một cuộc trò chuyện đang mở.

## Công cụ và phạm vi kiểm tra

Gói không có mã thực thi, không cần cài thư viện, token hay khóa API để đọc hướng dẫn. Việc tạo ảnh, chỉnh sửa thiết kế, xuất PDF/PNG, dựng video hoặc tạo giọng đọc cần công cụ tương ứng trong môi trường sử dụng. FFmpeg/ffprobe hữu ích cho dựng và kiểm tra video từ tài nguyên sẵn có; công cụ tạo video, HyperFrames và TTS là các lựa chọn khi có sẵn và phù hợp yêu cầu. Không có công cụ nào được ngầm cài hoặc cấp quyền bởi gói này.

Các tài liệu bao gồm thiết kế đồ họa và video quảng cáo F&B. Nội thất không nằm trong quy trình chuyên sâu của phiên bản này. Kích thước và thời lượng ví dụ là điểm bắt đầu, cần điều chỉnh theo kênh và yêu cầu thực tế.

Thử bằng yêu cầu trong `examples/sample-request.md`. Kết quả cần là file thiết kế thực tế nếu môi trường có công cụ tạo được, kèm báo cáo kiểm tra; không chỉ là prompt. Nội dung mẫu là thương hiệu hư cấu, không dùng làm dữ liệu kinh doanh thật.

Gói đã được kiểm tra cấu trúc và liên kết tài liệu. Việc cài/nạp trong công cụ đích và chạy một tác vụ thiết kế hoàn chỉnh cần được kiểm tra trong môi trường sử dụng.
