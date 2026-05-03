# 📊 Cohort Analysis – Vòng đời & Sự trung thành của Khách hàng

---

## 🗂️ Cấu trúc Repository

```
cohort-analysis/
│
├── data/
│   ├── EcomSales.csv          # Dữ liệu giao dịch bán hàng (2020–2023)
│   ├── Customer.csv           # Thông tin khách hàng (AnnualIncome, Segment, ...)
│   ├── Product.csv            # Danh mục sản phẩm (Category, Subcategory)
│   └── Region.csv             # Thông tin khu vực, thị trường
│
├── Cohort_Analysis_Customer_Analysis.ipynb   # Notebook phân tích chính
├── slides/
│   └── Buổi_6_Cohort_Analysis.pdf            # Slide bài giảng
└── README.md
```

---

## 🎯 Mục tiêu phân tích

| # | Yêu cầu | Mô tả |
|---|---------|-------|
| 1 | **Retention Cohort** | Xác định Acquisition Month từng khách hàng, tính tỷ lệ giữ chân trong năm 2022 |
| 2 | **Drill-down Segment** | So sánh Retention Rate giữa nhóm **Corporate** và **Consumer** |
| 3 | **Income Insight** | Nhóm khách hàng có `AnnualIncome` nào mang lại lợi nhuận bền vững nhất? |

---

## 📦 Dataset

### `EcomSales.csv`
| Cột | Mô tả |
|-----|-------|
| `OrderID` | Mã đơn hàng |
| `OrderDate` | Ngày đặt hàng |
| `CustomerID` | Mã khách hàng |
| `Segment` | Phân khúc: `Corporate`, `Consumer`, `Self-Employed` |
| `RegionCode` | Mã khu vực |
| `ProductCode` | Mã sản phẩm |
| `Sales` | Doanh thu |
| `Profit` | Lợi nhuận |
| `Discount` | Chiết khấu |

### `Customer.csv`
Thông tin nhân khẩu học: `AnnualIncome`, `EducationLevel`, `Occupation`, `Gender`, `MaritalStatus`, `HomeOwner`.

### `Product.csv`
Danh mục sản phẩm: `Category`, `Subcategory`.

### `Region.csv`
Địa lý: `City`, `State`, `Country`, `Region`, `Market`.

---

## 🧠 Khái niệm cốt lõi

### Cohort là gì?
Một **Cohort** là tập hợp khách hàng có chung một đặc điểm trong một khoảng thời gian xác định — thường là **tháng mua hàng đầu tiên (Acquisition Month)**.

### Retention Rate
```
Retention Rate (Month N) = Số KH cohort còn mua hàng tại Month N
                           ─────────────────────────────────────────
                                  Tổng số KH trong cohort ban đầu
```

### Cấu trúc Cohort Table

| Cohort Month | Size | Month 0 | Month 1 | Month 2 | Month 3 |
|-------------|------|---------|---------|---------|---------|
| 2022-01 | 1,000 | 100% | 45% | 38% | 30% |
| 2022-02 | 1,200 | 100% | 20% | 15% | 10% |
| 2022-03 | 900 | 100% | 48% | 40% | — |

- **Hàng ngang** → Theo dõi vòng đời của 1 cohort theo thời gian
- **Cột dọc** → So sánh các cohort tại cùng 1 thời điểm

---

## ⚙️ Cách chạy

### Yêu cầu
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Chạy notebook
```bash
jupyter notebook Cohort_Analysis_Customer_Analysis.ipynb
```

---

## 🔍 Các bước thực hiện trong Notebook

```
1. Define    → Chọn metric: Retention % và Revenue
2. Structure → Cohort theo Tháng (phù hợp E-commerce)
3. Calculate → Gắn tag CohortMonth & ActivityMonth, pivot table
4. Visualize → Heatmap bằng Seaborn
5. Synthesis → Tìm insight, đề xuất hành động
```

---

## 📈 Kết quả mong đợi

- **Heatmap Retention** toàn bộ tập dữ liệu 2022
- **So sánh Corporate vs Consumer**: Nhóm nào trung thành hơn?
- **Insight theo AnnualIncome**: Phân khúc thu nhập nào mang lại lợi nhuận bền vững?

---


---

## 👤 Tác giả

**Tú Nguyễn** @ Xóm Data · 2026
