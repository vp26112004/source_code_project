using System;

class Program
{
    static void Main()
    {
        try
        {
            // Yêu cầu người dùng nhập số lượng mặt hàng
            Console.Write("Nhập số lượng mặt hàng: ");
            int soLuongMatHang = int.Parse(Console.ReadLine());

            decimal tongGiaTriDonHang = 0;

            // Duyệt qua từng mặt hàng để nhập giá tiền
            for (int i = 1; i <= soLuongMatHang; i++)
            {
                Console.Write($"Nhập số tiền của mặt hàng {i}: ");
                decimal giaMatHang = decimal.Parse(Console.ReadLine());

                // Cộng giá của mặt hàng vào tổng giá trị đơn hàng
                tongGiaTriDonHang += giaMatHang;
            }

            // In ra tổng giá trị đơn hàng
            Console.WriteLine("Tổng giá trị đơn hàng: " + tongGiaTriDonHang + " VND");
        }
        catch (FormatException)
        {
            Console.WriteLine("Dữ liệu nhập vào không hợp lệ! Vui lòng nhập số hợp lệ.");
        }
        catch (Exception ex)
        {
            Console.WriteLine("Đã xảy ra lỗi: " + ex.Message);
        }
    }
}
