# Series — roadmap bài viết

Thư mục này lưu **kế hoạch chuỗi bài** (order, slug, trạng thái publish) — không publish lên site.

## Danh sách series

| Series | File | `series.id` |
|--------|------|-------------|
| Phát âm cơ bản | [phat-am-co-ban.md](phat-am-co-ban.md) | `phat-am-co-ban` |

## Ý tưởng chưa chốt series

Backlog: [docs/ideas/README.md](../ideas/README.md).

Ví dụ chủ đề từ vựng: [docs/ideas/vocabulary.md](../ideas/vocabulary.md).

## Khi publish phần mới

1. Đọc roadmap series (phụ thuộc, gợi ý nội dung).
2. Tạo `src/content/blog/{lang}/<slug>.md` với `series.order` khớp bảng.
3. `npm run build` (Node ≥ 22.12).
4. Cập nhật bảng: `status` → `published`, điền URL.
