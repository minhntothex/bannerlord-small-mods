# Quy ước dịch

Áp dụng cho các mod trong [phạm vi dự án](../README.md). Tài liệu này bổ sung [quy tắc dịch chung](../../../docs/translation-style.md) của workspace.

## Giọng văn

- Viết tiếng Việt tự nhiên, gọn và rõ chức năng. Nhãn, tùy chọn và thông báo giao diện cần ngắn; phần gợi ý phải giữ đủ điều kiện, con số và hệ quả.
- Với lời thoại trong Companion to Family, From Ranks to Lords và Heroes Evolve, giữ quan hệ giữa người nói, ý định và sắc thái câu. Chọn cách xưng hô theo cảnh; tránh tiếng lóng hiện đại và lối cổ trang gượng ép.
- Phân biệt lời thoại với nhãn giao diện, mô tả vật phẩm và thông báo hệ thống. Không làm nhẹ lời đe dọa, sự xúc phạm hay hậu quả được nêu trong nguồn.

## Tên riêng và thuật ngữ

- Dùng [glossary](glossary.md) cho thuật ngữ đã chốt. Giữ nguyên tên riêng khi chưa có căn cứ Việt hóa; ghi bản dịch đề xuất ở trạng thái chờ duyệt.
- Giữ nguyên tên chính thức của mod trong chuỗi giao diện, như `Agriculture Estate`, `Clan Migration Tweaks` và `Performance Tweaks`.
- Ưu tiên catalog tiếng Anh khi mod có catalog đó. Các catalog ngôn ngữ khác chỉ dùng để đối chiếu.
- Heroes Evolve không có catalog tiếng Anh trong bản cài hiện tại. Đối chiếu tiếng Đức, Pháp, Nga, Tây Ban Nha và Thổ Nhĩ Kỳ; ghi rõ chỗ còn mơ hồ thay vì tự đoán.
- Các tùy chọn của Xiangyong hiện chỉ có catalog tiếng Trung giản thể và phồn thể. Đối chiếu cả hai bản; giữ thuật ngữ chưa rõ ở trạng thái chờ xác minh.

## Bảo toàn dữ liệu

- Chỉ sửa văn bản cần dịch. Giữ nguyên ID, cấu trúc và thứ tự catalog, placeholder, markup, ký hiệu điều khiển, số liệu và xuống dòng có ý nghĩa.
- Giữ nguyên placeholder như `{HERO_NAME}`, `{SETTLEMENT_NAME}`, `{CLAN}`, `{KINGDOM}` và `{GOLD_ICON}`.
- Giữ XML hợp lệ; lưu catalog đích bằng UTF-8 và chuẩn hóa Unicode NFC.
