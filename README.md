# INFO3020 — Time-Series Air Pollution Analysis (Docs Mirror)

> **Môn học:** INFO3020 – Nhập môn Khoa học Dữ liệu (*Introduction to Data Science*)
> **Đề tài:** Phân tích mức độ ô nhiễm không khí theo chuỗi thời gian tại Hà Nội (*Time-Series Air Pollution Analysis*)
> **Kho mã nguồn chuẩn (canonical):** [`doctor-cato/air-pollution-analysis`](https://github.com/doctor-cato/air-pollution-analysis)
> **Kho tài liệu này:** [`ViolaPeracia/air-pollution-analysis`](https://github.com/ViolaPeracia/air-pollution-analysis)

---

## 1. Repo này chứa gì

Đây là **kho tài liệu dự án** (documentation-only mirror), không phải kho mã nguồn.

| | Kho mã nguồn chuẩn | Kho tài liệu này |
|---|---|---|
| **Owner** | `doctor-cato` | `ViolaPeracia` |
| **`src/`, `tests/`, `notebooks/`** | ✅ Có | ❌ Không — dùng bản chuẩn |
| **`data/`, `figures/`, `reports/`** | ✅ Có | ❌ Không — dữ liệu thô không Git-track |
| **`.github/workflows/ci.yml`** | ✅ Có | ❌ Không |
| **`docs/`** | ✅ Bản gốc | ✅ **Bản sao đồng bộ** |
| **`README.md`** | ✅ Bản gốc | ✅ Bản riêng (file này) |
| **Nhánh `gh-pages`** | ✅ Landing page | ✅ Bản sao đồng bộ |

> [!IMPORTANT]
> **Nguồn chân lý duy nhất:** mọi nội dung học thuật và số liệu trong `docs/` đều lấy từ kho chuẩn. Nếu hai nơi khác nhau, **kho chuẩn thắng**. Đừng chỉnh sửa trực tiếp vào `docs/` ở đây — hãy sửa ở kho chuẩn rồi đồng bộ (xem [§5](#5-quy-trình-đồng-bộ-tài-liệu)).

---

## 2. Landing Page

Trang tĩnh trình bày trực quan lộ trình 15 tuần theo chuẩn CRISP-DM nằm ở nhánh `gh-pages`:

```text
https://violaperacia.github.io/air-pollution-analysis/
```

Chạy cục bộ (không cần build, không cần thư viện):

```bash
git clone -b gh-pages https://github.com/ViolaPeracia/air-pollution-analysis.git
cd air-pollution-analysis
python -m http.server 8000
# → http://localhost:8000
```

| File | Vai trò |
|---|---|
| `index.html` | Giao diện chính — 15 phân mục học thuật, HTML5 semantic, WCAG 2.1 AA |
| `styles.css` | Design tokens, layout Flexbox/Grid, dark/light theme, `prefers-reduced-motion` |
| `script.js` | Vanilla JS ES6+: theme toggle, lọc tuần, checklist `localStorage`, tìm kiếm Ctrl+K |

**Zero dependency:** không npm, không Node.js, không CDN, không bước build.

---

## 3. Danh mục tài liệu (`docs/`)

Tất cả nội dung dưới đây được đồng bộ từ [`doctor-cato@main`](https://github.com/doctor-cato/air-pollution-analysis).

| Tài liệu | Issue | Nội dung |
|---|---|---|
| [`roadmap.md`](docs/roadmap.md) | — | **Lộ trình & đặc tả yêu cầu 15 tuần** — nguồn chuẩn cho mọi quyết định phạm vi |
| [`ROADMAP_INFO3020_Air_Pollution.md`](docs/ROADMAP_INFO3020_Air_Pollution.md) | — | Bản sao tham chiếu đề cương gốc của giảng viên (đã thay thế một phần) |
| [`air_quality_project_overview.md`](docs/air_quality_project_overview.md) | — | Tổng quan định hướng đề tài |
| [`research_questions.md`](docs/research_questions.md) | #2 | Câu hỏi nghiên cứu & khung phân tích SQ1–SQ4, trung lập khoa học |
| [`data_dictionary.md`](docs/data_dictionary.md) | #2 | Canonical Data Schema: 11 trường dữ liệu, 8 thuộc tính chuẩn hóa |
| [`source_profiling.md`](docs/source_profiling.md) | #19 | Mục lục hồ sơ thẩm định đa nguồn |
| [`source_profiling_decision.md`](docs/source_profiling_decision.md) | #19 | Báo cáo thẩm định & quyết định cổng nguồn dữ liệu |
| [`data_quality_audit.md`](docs/data_quality_audit.md) | #5 | Báo cáo kiểm toán chất lượng 6 chiều + phân tích khuyết thiếm Rubin |
| [`cleaning_log.md`](docs/cleaning_log.md) | #6 | Nhật ký làm sạch tất định (sinh tự động từ mã nguồn) |
| [`superpowers/plans/`](docs/superpowers/plans/) | #3 | Kế hoạch triển khai chi tiết từng tác vụ |

---

## 4. Hiện trạng dự án (tại thời điểm đồng bộ)

> Nguồn: [`README.md` của kho chuẩn](https://github.com/doctor-cato/air-pollution-analysis#2-hiện-trạng-triển-khai-vs-kế-hoạch-lộ-trình).

**Milestone 1–2 hoàn tất** (tuần 01–05). Issue **#1–#7 DONE**.

| Issue | Nội dung | Trạng thái |
|---|---|---|
| #1 | Khung dự án & môi trường | ✅ DONE |
| #2 | Câu hỏi nghiên cứu & từ điển dữ liệu | ✅ DONE |
| #3 | Pipeline thu thập OpenAQ | ✅ DONE |
| #4 | Pipeline khí tượng Open-Meteo ERA5 | ✅ DONE |
| #5 | Kiểm toán chất lượng 6 chiều | ✅ DONE |
| #6 | Làm sạch tất định + Cleaning Log | ✅ DONE |
| #7 | Pipeline chống rò rỉ dữ liệu | ✅ DONE |
| #8–#17 | EDA, suy luận, mô hình hóa, đạo đức | ⏳ Chưa bắt đầu |

**Chỉ số kỹ thuật hiện tại:**

- **259 unit test** tất định, chạy offline (`python -m unittest discover tests`)
- **Mutation score** `src/cleaning_pipeline.py`: **21/21 = 100%**
- Dữ liệu canonical đã làm sạch: **9.044 dòng × 18 cột** (`data/processed/air_pollution_final.parquet`, gitignored)
- Nguồn: OpenAQ S3 public (`location_id=4946811` — 556 Nguyễn Văn Cừ, Long Biên) + Open-Meteo ERA5 — **không cần API key**

---

## 5. Quy trình Đồng bộ Tài liệu

Repo này được cập nhật theo kiểu **one-way sync** từ kho chuẩn. Không có chỉnh sửa cục bộ nào được giữ lại.

```bash
# 1. Thêm kho chuẩn làm remote thứ hai
git remote add upstream https://github.com/doctor-cato/air-pollution-analysis.git

# 2. Tải và cập nhật tham chiếu
git fetch upstream main

# 3. Copy nguyên trạng docs/ từ kho chuẩn
git archive -o docs_sync.tar upstream/main docs
tar -xf docs_sync.tar
Remove-Item docs_sync.tar

# 4. Kiểm chứng đồng bộ (khung hằng 10/10)
git status --short docs/
```

**Kiểm chứng từng file (khung hằng):**

```bash
$files = @(
  "air_quality_project_overview.md", "cleaning_log.md", "data_dictionary.md",
  "data_quality_audit.md", "research_questions.md", "roadmap.md",
  "ROADMAP_INFO3020_Air_Pollution.md", "source_profiling.md",
  "source_profiling_decision.md",
  "superpowers/plans/2026-09-29-fix-issue-3-temporal-sync.md"
)
$ok = 0
foreach ($f in $files) {
  $local  = git hash-object "docs/$f"
  $remote = git rev-parse "upstream/main:docs/$f"
  if ($local -eq $remote) { $ok++ } else { Write-Host "MISMATCH $f" }
}
"MATCHED $ok / $($files.Count)"   # → MATCHED 10 / 10
```

**Đồng bộ nhánh `gh-pages`:**

```bash
git fetch upstream gh-pages
git checkout gh-pages
git merge --ff-only upstream/gh-pages   # nếu không có chỉnh sửa cục bộ
```

---

## 6. Muốn chạy code?

Repo này **không có mã nguồn**. Clone kho chuẩn:

```bash
git clone https://github.com/doctor-cato/air-pollution-analysis.git
cd air-pollution-analysis

python -m venv .venv
.\.venv\Scripts\Activate.ps1        # Windows PowerShell
# source .venv/bin/activate         # macOS / Linux

pip install -r requirements.txt
python scripts/fetch_dataset.py     # bước duy nhất cần mạng — 2 nguồn công khai, không API key
python -m unittest discover tests   # 259 test, offline
```

Hướng dẫn đầy đủ (8 bước tái lập, thứ tự notebook bắt buộc, xử lý sự cố) nằm trong [`README.md` kho chuẩn](https://github.com/doctor-cato/air-pollution-analysis#4-hướng-dẫn-thiết-lập--tái-lập-môi-trường).

---

## 7. Nguyên tắc Quản trị Dữ liệu

Áp dụng từ kho chuẩn — tóm tắt để tránh hiểu nhầm khi đọc `docs/`:

- **Dữ liệu thô không nằm trong Git.** Đây là *chính sách ba tầng* (Tầng C: tái tạo từ nguồn công khai), không phải thiếu sót. Toàn vẹn kiểm chứng bằng SHA-256 trong `data/raw/metadata.json`.
- **Không rò rỉ dữ liệu chuỗi thời gian.** Chia tập theo trình tự thời gian nghiêm ngặt ($T_{train} < T_{test}$). Tuyệt đối không chia ngẫu nhiên. Điểm cắt phải luận giải từ đặc tính thực nghiệm của tập đã đóng băng, không đặt trước tỷ lệ hay năm cố định.
- **Tính tất định.** Mọi phép biến đổi ngẫu nhiên cố định hạt giống `random_state=42`. Notebook chạy tuần tự qua **Restart Kernel & Run All**.
- **Không over-engineering.** Quy mô dữ liệu < 20 MB → Parquet (Snappy) + Pandas. Tuyệt đối không dùng Spark hay Deep Learning.

---

## 8. Cam kết Liêm chính Học thuật

- **Dữ liệu thật, nguồn xác thực** — thu thập từ nguồn công khai có thể kiểm chứng, đối chiếu QCVN 05:2023/BTNMT và khuyến cáo WHO 2021.
- **Không ngụy tạo số liệu** — không bịa đặt, can thiệp hay sửa dữ liệu thô; không xóa điểm dị biệt thực tế khi chưa có căn cứ vật lý.
- **Không ngụy tạo độ đo** — mọi chỉ số ($R^2$, RMSE, Recall, Precision, PR-AUC, $p$-value, Effect Size) là kết quả thật từ tập kiểm tra độc lập.
- **Minh bạch giả định** — luôn kiểm tra và báo cáo trung thực giả định thống kê (kiểm định phân phối, chẩn đoán 4 giả định LINE).

### Tuyên bố sử dụng Trí tuệ Nhân tạo

- **Phạm vi AI hỗ trợ:** sinh mã khung (*boilerplate*), rà soát cú pháp, tối ưu Markdown/biểu thức, gợi ý kỹ thuật kiểm tra tương thích đa nền tảng.
- **Trách nhiệm sinh viên:** mọi quyết định phương pháp luận, lựa chọn mô hình, suy luận thống kê, kiểm soát rò rỉ dữ liệu và bảo vệ mã nguồn **hoàn toàn thuộc về nhóm sinh viên**.

---

## 9. Nhóm thực hiện — Nhóm Chủ đề 6 (Topic 6 Team)

| STT | Thành viên | Tài khoản GitHub | Vai trò |
|:---:|---|---|---|
| 1 | Huy | [@doctor-cato](https://github.com/doctor-cato) | Nhóm trưởng (*Leader*) |
| 2 | Khương | [@lekhuong123456798-cpu](https://github.com/lekhuong123456798-cpu) | Thành viên |
| 3 | Khánh | [@nguyenphanminhkhanh9a-netizen](https://github.com/nguyenphanminhkhanh9a-netizen) | Thành viên |
| 4 | **Hưng** | [@ViolaPeracia](https://github.com/ViolaPeracia) | Thành viên — **duy trì kho tài liệu này** |
| 5 | Hùng | [@Izuki-1780N](https://github.com/Izuki-1780N) | Thành viên |

---

## 10. Liên kết nhanh

| Tài liệu | Link |
|---|---|
| Kho mã nguồn chuẩn | https://github.com/doctor-cato/air-pollution-analysis |
| Lộ trình (authoritative) | [`docs/roadmap.md`](docs/roadmap.md) |
| Landing page | https://violaperacia.github.io/air-pollution-analysis/ |
| Hướng dẫn đóng góp | [`CONTRIBUTING.md`](https://github.com/doctor-cato/air-pollution-analysis/blob/main/CONTRIBUTING.md) |
| Giấy phép | [MIT License](https://github.com/doctor-cato/air-pollution-analysis/blob/main/LICENSE) *(nằm ở kho chuẩn)* |
