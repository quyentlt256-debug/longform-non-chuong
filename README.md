# NÓN LÁ LONGFORM — BẢN DÀNH CHO VERCEL

Đây là website HTML tĩnh: chỉ cần đăng **toàn bộ nội dung thư mục này** lên Vercel.
Bên trong có `index.html` và thư mục `assets/` cùng cấp. Không tải mỗi `index.html` nếu dùng bản này.

## 1. Cấu trúc
```
index.html
assets/
  anh-cho-que.jpg
  anh-nghe-nhan.jpg
  anh-thu-ha-tot-nghiep-sac-net.jpg
  infographic-quy-trinh.png
  infographic-truoc-sau.png
  non-truyen-thong.jpg
  non-lua-la-hong-hoa.jpg
  video-1-quy-trinh-lam-non.mp4
  video-2-nguoi-tre-noi-nghiep.mp4
  video-3-nghe-nhan-lao-lang.mp4
  video-ket-hai-the-he-noi-nghe.mp4
  ...
```

## 2. Đăng lên Vercel
- Giải nén toàn bộ file ZIP.
- Đăng cả `index.html` **và** thư mục `assets` lên project.
- Với static HTML, để framework là **Other**, root directory là thư mục chứa `index.html`; không cần Build Command. Nếu deploy qua GitHub, commit cả thư mục `assets/`.
- Nếu Vercel có mục Output Directory đặt nhầm, sửa hoặc để trống theo cấu hình dự án static.
- Sau khi deploy, thử truy cập `https://ten-mien-cua-ban.vercel.app/assets/anh-cho-que.jpg`. Nếu 404, chưa đưa đúng `assets/` lên hoặc project root bị sai.

## 3. Thay ảnh, video
- Thay ảnh tại vị trí thẻ `<figure data-media="image" data-src="assets/ten-anh.jpg">` bằng tên file mới trong `assets/`.
- Thay video tại `<figure data-media="video" data-src="assets/video-ten.mp4" data-poster="assets/poster.jpg">`.
- Ảnh Before/After: tìm `id="compare-before"` và `id="compare-after"`, thay `data-image="assets/...jpg"`.
- Flashcard: tìm `const flashcards = [` cuối `index.html`, thay trường `image:'assets/...jpg'` từng thẻ.
- Ảnh/GIF nơi khác có thể nằm ở CSS `background-image` hoặc thẻ `<img src>`; tìm tên file bằng Ctrl+F.
- Video nên là MP4 H.264 + AAC, tạo phiên bản web và để dưới `assets/`.

## 4. Lỗi thường gặp
- Lưu `index.html` nhưng không upload thư mục `assets/`: ảnh/video 404.
- Đổi đuôi `.webp` thành `.jpg` **chỉ bằng Rename**: sai! Phải xuất/convert file thực tế sang JPEG/PNG.
- Tên file viết hoa/viết thường hoặc dấu cách không giống đường dẫn: dễ lỗi khi deploy.
- Chỉ dán đường dẫn file `C:\...` trên máy cá nhân: Vercel không thể đọc.
- Dùng bản HTML một file đã nhúng media nhưng cố thay đường dẫn trong zip; hai phiên bản không đồng nhất. Nên dùng bản ZIP này để sửa và deploy.

## 5. Lưu ý biên tập
Các lời trích dẫn/quan hệ nhân vật trong bản thảo chưa được kiểm chứng độc lập; cần xác minh trước khi xuất bản.
