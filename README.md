[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112942&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** vanhoang1412003@gmail.com
**Name:** Thân Văn Hoàng

---

## Mo ta

Bài lab thực hành xây dựng một đường ống ETL (Extract, Transform, Load) cơ bản bằng Python và Pandas. Các công việc đã thực hiện:
- Hoàn thiện script `solution.py` để trích xuất dữ liệu JSON, validate (loại bỏ dữ liệu lỗi, thiếu sót), transform (tính giảm giá, chuẩn hóa chữ hoa/thường), và load ra file CSV.
- Thực hiện giả lập Stress Test cho AI Agent bằng cách cho agent truy vấn trên dữ liệu sạch (`processed_data.csv`) và dữ liệu rác (`garbage_data.csv`).
- Phân tích và viết báo cáo về tầm quan trọng của Data Quality đối với độ chính xác của AI Agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Tao file du lieu rac truoc
python generate_garbage.py

# Chay test agent voi ca 2 bo du lieu
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- Data ban đầu (raw_data.json) có 5 records.
- Sau quá trình ETL, pipeline đã validate và loại bỏ 2 records không hợp lệ (một sản phẩm có giá trị âm, một sản phẩm thiếu category).
- Giữ lại và transform thành công 3 records hợp lệ vào file `processed_data.csv`.
- AI Agent trả lời hoàn toàn chính xác với `processed_data.csv`, nhưng trả lời sai lệch (khuyên mua Nuclear Reactor giá vô lý) với `garbage_data.csv`. Bài lab chứng minh rõ quan điểm Data Quality quan trọng hơn so với Prompt Engineering đơn thuần.
