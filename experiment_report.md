# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600582
**Name:** Thân Văn Hoàng
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | "Agent: Based on my data, the best choice is Laptop at $1200." | 10 | The agent correctly recommended an electronics item. |
| Garbage Data (`garbage_data.csv`) | "Agent: Based on my data, the best choice is Nuclear Reactor at $999999." | 1 | The agent picked an outlier due to lack of validation. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent đã trả lời sai khi sử dụng Garbage Data vì dữ liệu đầu vào chứa các giá trị ngoại lệ (outliers) cực đoan. Cụ thể, sản phẩm "Nuclear Reactor" được gán sai vào danh mục "electronics" với mức giá vô lý ($999,999). Logic của Agent đơn giản là tìm sản phẩm có giá trị cao nhất trong danh mục. Do thiếu quy trình ETL (Extract, Transform, Load) để validate, chuẩn hóa kiểu dữ liệu (data types) hay loại bỏ duplicates/nulls/outliers, mô hình phải làm việc trên dữ liệu nhiễu loạn. Từ đó, Agent dễ dàng truy xuất sai và đưa ra tư vấn hoàn toàn sai lệch cho người dùng.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Đồng ý.

Một câu prompt tốt không thể sửa chữa được lỗ hổng của những dữ liệu rác, nhiễu và sai lệch (Garbage In, Garbage Out). Dữ liệu chất lượng cao là nền tảng cốt lõi giúp AI/Agent hiểu đúng thực tế và đưa ra phản hồi chính xác, an toàn, có ý nghĩa. Không có dữ liệu sạch, mọi mô hình và kĩ thuật prompting đều trở nên vô dụng.
