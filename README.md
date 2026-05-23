# EngHung

Blog cá nhân ghi lại **bài học khi học tiếng Anh** — ngữ pháp, từ vựng, phát âm, kỹ năng nghe–nói–đọc–viết, và những ghi chú trong quá trình học.

Site tĩnh, song ngữ (tiếng Anh / tiếng Việt), xây bằng [Astro](https://astro.build/) và deploy lên GitHub Pages.

## Yêu cầu

- Node.js `>=22.12.0`
- npm

```bash
node --version
npm --version
```

Nếu Node thấp hơn `22.12.0`, nâng cấp trước khi chạy lệnh Astro.

## Cài đặt

```bash
npm install
```

## Chạy local

```bash
npm run dev
```

Thường mở tại `http://localhost:4321`:

- Trang chủ tiếng Anh: `http://localhost:4321/en/`
- Trang chủ tiếng Việt: `http://localhost:4321/vi/`
- `/` redirect mặc định sang `/en/`

## Build & preview

```bash
npm run build
npm run preview
```

Build chạy `astro check && astro build`, output trong `dist/`.

## Cấu trúc dự án

```text
.
├── .github/workflows/deploy.yml
├── astro.config.mjs
├── docs/
│   ├── series/          # roadmap chuỗi bài (không publish)
│   └── ideas/           # backlog ý tưởng bài (không publish)
├── public/
├── src/
│   ├── components/
│   ├── content.config.ts
│   ├── content/blog/
│   │   ├── en/
│   │   └── vi/
│   ├── layouts/
│   ├── lib/i18n.ts
│   ├── pages/
│   └── styles/
└── README.md
```

File quan trọng:

- `src/content.config.ts` — schema bài viết, danh sách category.
- `src/lib/i18n.ts` — nhãn UI, nhãn category, helper URL.
- `src/content/blog/en/` — bài tiếng Anh.
- `src/content/blog/vi/` — bài tiếng Việt.

## Kế hoạch chuỗi bài

Roadmap từng series (thứ tự, slug, trạng thái) trong [`docs/series/`](docs/series/README.md).

Ví dụ: [Phát âm cơ bản](docs/series/phat-am-co-ban.md) — series id `phat-am-co-ban`.

Cập nhật roadmap khi publish phần mới.

## Ý tưởng bài

Backlog chưa chốt series trong [`docs/ideas/`](docs/ideas/README.md).

Ví dụ: [docs/ideas/vocabulary.md](docs/ideas/vocabulary.md). Khi viết bài, promote ý tưởng (`idea` → `promoted` → `done`).

## Viết bài mới

Bài nằm trong:

```text
src/content/blog/en/
src/content/blog/vi/
```

### Các bước

1. Chọn thư mục ngôn ngữ (`en` hoặc `vi`).
2. Tạo file kebab-case, ví dụ `present-perfect-notes.md`.
3. Điền frontmatter (xem bảng dưới).
4. Viết nội dung Markdown bên dưới frontmatter.
5. Chạy `npm run build` để kiểm tra schema.

### Frontmatter

| Field | Bắt buộc | Ví dụ | Ghi chú |
| --- | --- | --- | --- |
| `title` | Có | `"Present Perfect — What I Got Wrong"` | Tiêu đề hiển thị |
| `description` | Có | `"Common mistakes and fixes."` | Tóm tắt / meta |
| `pubDate` | Có | `2026-05-20` | `YYYY-MM-DD` |
| `category` | Có | `"grammar"` | Một trong các category cấu hình |
| `tags` | Có | `["tenses", "present-perfect"]` | kebab-case, có thể `[]` |
| `lang` | Có | `"en"` hoặc `"vi"` | Khớp thư mục |
| `slug` | Có | `"present-perfect-notes"` | URL: `/en/blog/.../` |
| `translationKey` | Có | `"present-perfect-notes"` | Liên kết bản dịch |
| `updatedDate` | Không | `2026-05-21` | Ngày cập nhật |
| `series` | Không | Xem dưới | Chuỗi nhiều phần |
| `draft` | Không | `true` | Không publish |

### Category hiện tại

| ID | Tiếng Anh | Tiếng Việt |
| --- | --- | --- |
| `grammar` | Grammar | Ngữ pháp |
| `vocabulary` | Vocabulary | Từ vựng |
| `pronunciation` | Pronunciation | Phát âm |
| `skills` | Listening, Speaking, Reading & Writing | Nghe – nói – đọc – viết |
| `culture` | Culture & Idioms | Văn hóa & thành ngữ |
| `study-notes` | Study Notes | Ghi chú học tập |
| `resources` | Resources | Tài nguyên |

Thêm/sửa category: cập nhật `src/content.config.ts` và `categoryLabels` trong `src/lib/i18n.ts`.

### Mẫu bài tiếng Anh

```md
---
title: "Present Perfect — What I Got Wrong"
description: "Mistakes I made with the present perfect and how I fixed them."
pubDate: 2026-05-20
category: "grammar"
tags: ["tenses", "present-perfect"]
lang: "en"
slug: "present-perfect-notes"
translationKey: "present-perfect-notes"
---

Write your lesson here.

## Why this tense confused me

...
```

### Mẫu bài tiếng Việt

```md
---
title: "Present Perfect — Lỗi mình hay mắc"
description: "Những lỗi thường gặp với thì hiện tại hoàn thành và cách sửa."
pubDate: 2026-05-20
category: "grammar"
tags: ["thi", "present-perfect"]
lang: "vi"
slug: "present-perfect-loi-hay-mac"
translationKey: "present-perfect-notes"
---

Viết bài học ở đây.
```

Hai bản dùng chung `translationKey`; `slug` có thể khác theo ngôn ngữ.

### Chuỗi bài (series)

```yaml
series:
  id: "phat-am-co-ban"
  title: "Pronunciation Basics"
  order: 1
```

- Cùng `series.id` cho mọi phần trong chuỗi.
- `series.title` theo ngôn ngữ.
- `series.order` — thứ tự trong chuỗi (unique trong cùng ngôn ngữ + series).

### Bản nháp

```yaml
draft: true
```

### Code & sơ đồ

- Code fence có language tag để highlight.
- `title` trong fence để hiện tên file: ` ```ts title="example.ts" ` `
- Mermaid: fence `mermaid` — cần Playwright khi build (`npm run setup:diagrams`).

Link ngoài (ví dụ Cambridge Dictionary) mở tab mới tự động.

## Ngôn ngữ site

- `en` — bài / giao diện tiếng Anh
- `vi` — bài / giao diện tiếng Việt

Một bài chỉ một ngôn ngữ vẫn publish bình thường. Nút đổi ngôn ngữ chỉ hiện khi có bài cùng `translationKey`.

## Deploy GitHub Pages

Workflow: `.github/workflows/deploy.yml` (push `main`).

1. Repo `enghung.github.io`
2. Settings → Pages → Source: **GitHub Actions**
3. Push `main`, đợi workflow xong

URL: `https://enghung.github.io`

## Lệnh hữu ích

```bash
npm install
npm run dev
npm run dev:fresh    # xóa cache .astro rồi dev
npm run build
npm run preview
npm run setup:diagrams
```

## Troubleshooting

**Node không đủ:** cần `>=22.12.0`, sau đó `rm -rf node_modules && npm install`.

**Xóa bài mà vẫn thấy cũ:** `rm -rf .astro dist` rồi `npm run dev` hoặc `npm run dev:fresh`.

**Trang category trống:** Astro chỉ tạo trang category khi có ít nhất một bài published dùng category đó.

**Không có link đổi ngôn ngữ:** kiểm tra `translationKey` trùng nhau giữa hai bài `en` / `vi`.
