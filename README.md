# bt3
ĐINH VĂN TRƯỜNG-K59KMT-K235480106074
Nhiệm vụ 1: Thiết kế CSDL
<img width="1187" height="792" alt="image" src="https://github.com/user-attachments/assets/96d5d0af-4cb8-4192-9baf-3d8c26512ba4" />
<img width="1229" height="840" alt="image" src="https://github.com/user-attachments/assets/8dd1dfa1-4700-49a5-a8aa-b86aa3f95a90" />

Vẽ sơ đồ ERD: thể hiện rõ thực thể, thuộc tính, khóa chính, khóa ngoại.
Chuyển sơ đồ thành các bảng (Lưu ý chuẩn hóa tối thiểu mức 3NF).
Sơ đồ thực thể liên kết trong sql
<img width="1919" height="1079" alt="Screenshot 2026-05-12 190959" src="https://github.com/user-attachments/assets/603d77a9-0013-4631-9762-1ae68c925c37" />
hinh vẽ
<img width="830" height="725" alt="image" src="https://github.com/user-attachments/assets/4f20e4dc-1a69-43bb-bdf5-54ffbe7b71bf" />
Nhiệm vụ 2: Cài đặt SQL
Event 1: Đăng ký hợp đồng mới (Vay tiền)
Tạo database QuanLyCamCo và tất cả bảng dữ liệu
Viết Store Procedure tiếp nhận hợp đồng: Lưu thông tin khách hàng, danh sách tài sản (kèm giá trị định giá), số tiền vay gốc và thiết lập 2 mốc Deadline1, Deadline2.

SQL Server không truyền mảng trực tiếp vào Procedure nên ta cần tạo kiểu dữ liệu Table Type cho danh sách tài sản
<img width="1919" height="1079" alt="Screenshot 2026-05-12 200821" src="https://github.com/user-attachments/assets/7baf34ed-4830-4f30-9f70-d0994120a503" />
<img width="1919" height="1079" alt="Screenshot 2026-05-12 204557" src="https://github.com/user-attachments/assets/41f8df9f-fba0-4cb1-827c-4c147b2e75b3" />
Event 2: Tính toán công nợ thời gian thực viết Function fn_CalcMoneyTransaction(TransactionID, TargetDate) để tính số tiền phải trả của TransactionID này cho đến ngày TargetDate
Viết Function fn_CalcMoneyTransaction(TransactionID, TargetDate)

Function này tính:

số tiền phải trả của 1 giao dịch/hợp đồng

tại thời điểm TargetDate

Viết function
<img width="1919" height="1079" alt="Screenshot 2026-05-12 204632" src="https://github.com/user-attachments/assets/ef627ac7-4e42-456f-921f-8d154ba6ec1c" />
Event 3: Xử lý trả nợ và hoàn trả tài sản Viết Store Procedure xử lý khi khách mang tiền đến: Nếu tài sản đã bị thanh lý (sau Deadline 2 và có cờ IsSold): Thông báo không thu tiền, không trả đồ.
<img width="1919" height="1079" alt="Screenshot 2026-05-12 204702" src="https://github.com/user-attachments/assets/d7909aeb-8d52-46d2-aaef-efb05bd426d9" />
<img width="1919" height="1079" alt="Screenshot 2026-05-12 204741" src="https://github.com/user-attachments/assets/c686357a-c6a4-414c-85e2-b2ea7e48a563" />
Event 4: Truy vấn danh sách nợ xấu (Nợ khó đòi)
Viết function để truy vấn danh sách nợ xấu
<img width="1919" height="1079" alt="Screenshot 2026-05-12 205050" src="https://github.com/user-attachments/assets/eb45f7bd-146f-447b-ae66-7c8ad91b691b" />
Event 5: Quản lý thanh lý tài sản
Viết Trigger tự động chuyển trạng thái hợp đồng sang "Quá hạn (nợ xấu)" sau khi hợp đồng đang ở trạng thái "Đang vay" mà ngày vượt quá Deadline 1.
<img width="1919" height="1074" alt="Screenshot 2026-05-12 205122" src="https://github.com/user-attachments/assets/b4f8a7a6-a7aa-4bb6-aa52-3b3b89105c61" />
Trigger 2: Tự động chuyển tài sản sang sẵn sàng thanh lý khi vượt Deadline2
<img width="1919" height="1068" alt="Screenshot 2026-05-12 205154" src="https://github.com/user-attachments/assets/a7453804-214c-4a99-a4c7-59482e61196e" />

<img width="1918" height="1072" alt="Screenshot 2026-05-12 212950" src="https://github.com/user-attachments/assets/9cb2254b-abfd-4af4-ad24-274deee6b9be" />
<img width="1919" height="1079" alt="Screenshot 2026-05-12 213009" src="https://github.com/user-attachments/assets/d039c414-50ba-49f3-b338-87d52a4ffc45" />
<img width="1919" height="1078" alt="Screenshot 2026-05-12 213025" src="https://github.com/user-attachments/assets/27db1c80-3338-4760-b0de-7caa5936a170" />

