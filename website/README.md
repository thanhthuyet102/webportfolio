# TRIAD — Portfolio nhóm 3 thành viên

Website tĩnh viết bằng **HTML, CSS và JavaScript thuần**, không cần framework hay cài thư viện.

## Mở website

Mở `index.html` trong thư mục website bằng Chrome, Edge, Firefox hoặc Safari. Các file CSS và JavaScript phải nằm cùng thư mục như trong gói mã nguồn.

Có thể mở thư mục bằng VS Code và dùng Live Server nếu muốn xem thay đổi sau khi sửa.

## Các file

| File | Chức năng |
| --- | --- |
| `index.html` | Bố cục, nội dung giới thiệu nhóm, quy trình và liên hệ |
| `styles.css` | Màu sắc, font, giao diện máy tính và điện thoại |
| `effects.css` | Giao diện nền tối, ánh sáng, khối kính và hiệu ứng hover |
| `data.js` | Thông tin nhóm, 3 thành viên, dự án và kỹ năng |
| `script.js` | Hiển thị dữ liệu, lọc dự án, mở hồ sơ và menu điện thoại |
| `effects.js` | Hiệu ứng khi cuộn, chiều sâu theo chuột và họa tiết nền |

## Điền thông tin cá nhân

Mở `data.js`. Thông tin cá nhân hiện là chuỗi rỗng `""`. Tìm từng phần tử trong `members` rồi điền:

```js
{
  id: "member-1", // Giữ nguyên để không mất liên kết đóng góp dự án.
  name: "Họ và tên",
  studentId: "Mã số sinh viên",
  school: "Tên trường",
  major: "Kỹ thuật phần mềm",
  email: "email@example.com",
  github: "https://github.com/ten-tai-khoan",
  linkedin: "https://www.linkedin.com/in/ten-tai-khoan/",
  cv: "assets/cv-thanh-vien-1.pdf",
  photo: "assets/thanh-vien-1.jpg",
  // ... giữ các trường role, bio, introduction, skills, focus, achievements.
}
```

- Thay `team.name` để đổi tên nhóm; sửa chữ `T` trong logo của `index.html` nếu cần.
- Thay `team.email` và `team.github` để bổ sung liên hệ chung.
- Sửa `role`, `bio`, `introduction`, `skills` và `focus` theo năng lực thực tế.
- Thêm thành tích thật vào `achievements`, ví dụ `["Chứng chỉ ...", "Tham gia cuộc thi ..."]`. Khi mảng rỗng, phần này không hiển thị.
- Tạo thư mục `assets` cùng cấp với `index.html` để lưu ảnh và CV.
- Nếu chưa có email, GitHub, LinkedIn hoặc CV, giữ `""`. Các liên kết chưa được điền sẽ không xuất hiện.

## Nội dung mẫu

Tên nhóm TRIAD, lời giới thiệu, vai trò, kỹ năng và quy trình làm việc là nội dung mẫu. Hãy điều chỉnh để phù hợp với nhóm.

**FlowTask, Campus Library và Mini Commerce là các ý tưởng dự án minh họa**, không phải sản phẩm đã hoàn thành. Không có thành tích, số liệu hay demo thực tế được gán cho nhóm.

Để thay bằng dự án thật, sửa phần `projects` trong `data.js`:

- `title`, `summary`, `problem`, `features`: tên, mô tả, bài toán và chức năng.
- `stack`: các công nghệ thực tế.
- `contributions`: đóng góp từng người, gắn bằng `memberId`.
- `learning`, `status`: bài học và tình trạng thực tế.
- `demo`, `github`: liên kết thật; nếu chưa có, để trống.
- `sample: false`: dùng sau khi đã thay bằng dự án thực tế.
- `year`: thay `Mẫu 01` bằng thời gian hoặc nhãn phù hợp.
- `category`: `web` hoặc `system` để dùng các bộ lọc đang có.
- `preview`: `tasks`, `library` hoặc `commerce` để chọn phần giao diện thu nhỏ có sẵn. Đây là hình minh họa bằng HTML/CSS, không phải ảnh chụp sản phẩm thực tế.

Khi toàn bộ dự án đã được thay bằng sản phẩm thật, bỏ dòng `Dự án mẫu · Nội dung minh họa` trong `index.html`. Để dùng ảnh chụp thật, thay phần `project-preview` trong `script.js` bằng thẻ `img` và bổ sung CSS phù hợp.

## Thay nội dung và giao diện

- Sửa phần Về nhóm, Cách làm việc và lời giới thiệu đầu trang trong `index.html`.
- Sửa `skillGroups` trong `data.js` để đổi năng lực chung của nhóm.
- Sửa biến màu trong `:root` ở đầu `effects.css` để đổi bảng màu của bản nâng cấp. `styles.css` giữ bố cục nền tảng.
- Website có menu điện thoại, bộ lọc dự án và hộp chi tiết dùng phần tử `dialog` tiêu chuẩn. Nút Esc đóng hộp chi tiết; nút đóng và thao tác ngoài hộp cũng được hỗ trợ.

Website không có backend và không có biểu mẫu gửi dữ liệu. Nút email dùng `mailto:` để mở ứng dụng email khi địa chỉ hợp lệ đã được điền.

## Nền và hiệu ứng của bản nâng cấp

- Nền xanh đen, lưới mảnh và các vùng sáng xanh ngọc / xanh lam.
- Ba khối chuyên môn có chiều sâu và chuyển động nhẹ theo chuột trên máy tính.
- Các phần nội dung xuất hiện một lần khi đi vào vùng nhìn thấy.
- Thẻ thành viên và dự án có ánh sáng theo chuột, hiệu ứng nâng nhẹ.
- Họa tiết nền dùng Canvas, giới hạn tốc độ khung hình và tự dừng khi ngoài màn hình hoặc tab không hiển thị.
- Khi thiết bị bật `prefers-reduced-motion`, các hiệu ứng chuyển động được giảm hoặc tắt; nội dung vẫn hiển thị.
- Website không dùng thư viện hiệu ứng bên ngoài. Để trở về giao diện cơ bản, bỏ dòng nạp `effects.css` và `effects.js` trong `index.html`; cấu trúc nền vẫn dùng nội dung mới.
