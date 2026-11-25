# Hướng dẫn đưa "Sổ tay của Anna" lên mạng (miễn phí)

Website được làm bằng **Hugo** và đăng lên **GitHub Pages**, giống bài hướng dẫn trên Viblo. Có 2 điểm khác để bạn dễ làm hơn:

1. **Không cần cài Hugo hay Git trên máy.** GitHub sẽ tự build website mỗi khi bạn sửa nội dung, nhờ file `.github/workflows/hugo.yml`.
2. **Dùng theme riêng (`themes/sotay`)** thay cho theme ananke. Theme này làm theo đúng cấu trúc đã lên kế hoạch: trang chủ, blog, kho đồ affiliate, review, trang nhận quà và trang cảm ơn.

---

## Phần 1. Đưa website lên mạng (khoảng 15 phút)

**Bước 1: Tạo tài khoản GitHub**
Vào https://github.com và đăng ký miễn phí. Nên chọn tên ngắn, vì tên này sẽ nằm trong địa chỉ web, ví dụ `annasotay` → `annasotay.github.io`.

**Bước 2: Tạo kho chứa (repository)**
- Bấm dấu **+** ở góc trên bên phải → **New repository**
- Ô *Repository name*: gõ `ten-github-cua-ban.github.io` (thay bằng tên của bạn, ví dụ `annasotay.github.io`)
- Chọn **Public** → bấm **Create repository**

**Bước 3: Tải các file lên**
- Giải nén file zip mình gửi
- Trong trang repository vừa tạo, bấm **uploading an existing file**
- Mở thư mục `sotay-anna`, chọn **tất cả** file và thư mục bên trong, rồi kéo thả vào trang GitHub
- ⚠️ Phải có thư mục `.github`. Đây là thư mục ẩn:
  - Trên Mac, trong Finder bấm `Cmd + Shift + .` để hiện file ẩn
  - Trên Windows: vào View → tích Hidden items
- Kéo xuống dưới, bấm **Commit changes**

> Nếu GitHub không nhận thư mục `.github`, hãy tạo file thủ công: **Add file → Create new file**, gõ tên `.github/workflows/hugo.yml`, rồi dán nội dung của file đó vào.

**Bước 4: Bật GitHub Pages**
- Trong repository, vào **Settings → Pages**
- Ở mục *Source*, chọn **GitHub Actions**

**Bước 5: Chờ khoảng 1–2 phút**
- Vào tab **Actions**. Khi thấy dấu ✅ xanh là website đã được đăng
- Mở `https://ten-github-cua-ban.github.io` để xem website

---

## Phần 2. Điền thông tin của bạn (file `hugo.yaml`)

Trên GitHub, mở file `hugo.yaml` → bấm biểu tượng bút chì ✏️ để sửa:

| Dòng | Điền gì |
|---|---|
| `baseURL` | `https://ten-github-cua-ban.github.io/` |
| `leadFormURL` | Link Google Form đăng ký nhận quà (xem Phần 4) |
| `giftDownloadURL` | Link Google Drive của file Excel làm quà |
| `tiktok`, `facebook` | Link kênh của bạn |
| `email` | Email nhận liên hệ hợp tác |

Bấm **Commit changes**, website sẽ tự cập nhật sau khoảng 1 phút.

---

## Phần 3. Viết bài mới

1. Vào thư mục `content/posts` → **Add file → Create new file**
2. Đặt tên file không dấu, nối bằng gạch ngang, ví dụ `cho-con-ngu-xuyen-dem.md`
3. Dán mẫu sau rồi sửa:

```
---
title: "Tiêu đề bài viết"
date: 2026-12-01
description: "Một câu tóm tắt, hiện trên Google và thẻ bài."
categories: ["Nuôi con nhỏ"]
affiliate: true
---

Mở bài bằng câu chuyện thật của bạn...

## Ý chính thứ nhất

{{< nhanqua >}}

## Ý chính thứ hai

{{< sanpham id="may-ham-sua" >}}
```

- `categories` chỉ chọn 1 trong 4: **Nuôi con nhỏ**, **Mẹ đi làm**, **Chi tiêu thông minh**, **Daily life của Anna**
- `{{< nhanqua >}}` chèn ô "Nhận file miễn phí" vào giữa bài
- `{{< sanpham id="..." >}}` chèn thẻ sản phẩm (lấy `id` trong file `data/products.yaml`)
- Bài review/so sánh thì đặt trong thư mục `content/review`

Định dạng chữ trong bài (Markdown):
- `## Tiêu đề phụ`
- `**chữ đậm**`
- `- gạch đầu dòng`
- `> câu trích dẫn`

---

## Phần 4. Thêm sản phẩm affiliate

Mở `data/products.yaml`. Mỗi sản phẩm là một khối như sau:

```
- id: ten-khong-dau
  group: so-sinh          # so-sinh / an-dam / cho-me / gia-dung
  name: Tên sản phẩm
  why: Một câu vì sao bạn chọn nó
  badge: Dùng mỗi ngày    # hoặc để trống ""
  price: ""
  shop: Shopee
  link: "DÁN LINK AFFILIATE CỦA BẠN"
  featured: true          # true = hiện ở trang chủ (nên chọn 3 món)
```

⚠️ Các sản phẩm và bài viết hiện có đều là **MẪU**. Hãy thay bằng đồ bạn dùng thật và link affiliate thật của bạn (Shopee Affiliate, TikTok Shop Affiliate...).

---

## Phần 5. Thu lead bằng Google Form (cách đơn giản nhất)

1. Vào https://forms.google.com → tạo form gồm 2 câu hỏi: **Tên** và **Email**
2. Vào **Cài đặt → Bản trình bày → Thông báo xác nhận**, dán link trang cảm ơn: `https://ten-github-cua-ban.github.io/cam-on/`
3. Bấm **Gửi** → biểu tượng liên kết → copy link, dán vào `leadFormURL` trong `hugo.yaml`
4. Danh sách người đăng ký sẽ nằm ở tab **Câu trả lời**, có thể xuất ra Google Sheets

Khi có khoảng vài trăm người đăng ký, bạn có thể chuyển sang công cụ email marketing (như MailerLite) để gửi chuỗi email tự động.

---

## Cấu trúc thư mục

```
sotay-anna/
├── hugo.yaml              ← cấu hình: tên web, link form, mạng xã hội, menu
├── content/
│   ├── posts/             ← bài blog
│   ├── review/            ← bài review & so sánh
│   ├── do-anna-dung.md    ← trang kho đồ
│   ├── qua-tang.md        ← trang nhận quà (không có menu)
│   ├── cam-on.md          ← trang cảm ơn
│   ├── ve-anna.md, hop-tac.md, cong-khai-affiliate.md, chinh-sach-bao-mat.md
├── data/
│   ├── products.yaml      ← danh sách sản phẩm affiliate
│   └── product_groups.yaml
├── themes/sotay/          ← giao diện (không cần sửa)
└── .github/workflows/     ← tự build & đăng web
```

## (Tuỳ chọn) Xem thử trên máy

Nếu muốn xem trước trên máy như bài Viblo, hãy cài Hugo (bản **extended**), mở terminal trong thư mục `sotay-anna` và chạy `hugo server`. Sau đó mở http://localhost:1313.
