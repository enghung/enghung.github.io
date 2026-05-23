# Ý tưởng bài viết

Thư mục này lưu **backlog ý tưởng** — không publish lên site. Dùng khi chưa chốt series, slug, hay thứ tự publish.

## Phân biệt với `docs/series/`

| | `docs/series/` | `docs/ideas/` |
|---|---|---|
| Mục đích | Chuỗi bài **đã cam kết**: order, slug, trạng thái | Ý tưởng chưa hoặc mới chốt hướng viết |
| Khi viết bài | Khớp `series.order`, cập nhật roadmap | **Promote** trước: vào series, standalone, hoặc gộp outline |

Index series: [docs/series/README.md](../series/README.md).

## Chủ đề

| File | Mô tả |
|------|--------|
| [vocabulary.md](vocabulary.md) | Ý tưởng từ vựng, collocation, học từ theo chủ đề |

Thêm file mới theo chủ đề (ví dụ `grammar.md`, `pronunciation.md`) khi backlog lớn hơn.

## Trạng thái ý tưởng

| Status | Ý nghĩa |
|--------|---------|
| `idea` | Mới ghi, chưa promote |
| `promoted` | Đã đưa vào roadmap series hoặc đang viết draft |
| `done` | Đã publish |
| `dropped` | Bỏ, không viết |

Ưu tiên tùy chọn: `P1`, `P2`.

## Workflow promote

1. Chọn ý tưởng → quyết định:
   - **Series part** — thêm dòng trong `docs/series/*.md`.
   - **Standalone** — bài không `series` trong `src/content/blog/`.
   - **Gộp outline** — bổ sung bullet trong phần `planned`.
2. Tạo hoặc cập nhật draft.
3. `status`: `promoted` → sau publish → `done`.

## Thêm ý tưởng mới

1. Mở hoặc tạo file chủ đề.
2. Thêm dòng bảng: `id`, `status`, ưu tiên, tiêu đề, liên quan.
3. Section `## <id>` với bullet **Gợi ý nội dung**.
