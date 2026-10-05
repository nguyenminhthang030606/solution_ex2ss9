1. Phân tích lỗi & Bảng Test Cases (README.md)
Phân tích nguyên nhân lỗi:

Lỗi truy xuất thuộc tính động (Dot Notation vs Bracket Notation): Biến priceKey mang giá trị là chuỗi "roomPrice". Việc dùng bookingReservation.priceKey sẽ làm hệ thống tìm kiếm thuộc tính có tên tĩnh là "priceKey", dẫn đến trả về undefined và làm tổng tiền hóa đơn thành NaN. Cần sửa thành bookingReservation[priceKey].

Lỗi xóa thuộc tính trong đối tượng: Khi voucher không hợp lệ, lập trình viên gán bookingReservation.discountCode = undefined. Thao tác này chỉ thay đổi giá trị thành undefined chứ không xóa thuộc tính đó, khiến vòng lặp phía dưới vẫn duyệt qua và in ra màn hình. Cần sử dụng từ khóa delete (delete bookingReservation.discountCode;) để loại bỏ hoàn toàn key ra khỏi đối tượng.

Lỗi hiển thị giá trị trong vòng lặp for...in: Bên trong vòng lặp, biến key đại diện cho tên các thuộc tính (dưới dạng chuỗi). Dòng mã bookingReservation.key bị sai tương tự lỗi số 1 (tìm thuộc tính tên là "key"). Cần sửa lại thành bookingReservation[key] để lấy đúng giá trị tương ứng của từng thuộc tính.
