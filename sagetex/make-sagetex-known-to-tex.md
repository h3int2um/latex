# Sử dụng Sage trong LaTeX với gói lệnh sagetex

Thực hiện: Thi Minh Nhựt - Email: thiminhnhut@gmail.com

Thời gian: Ngày 17 tháng 08 năm 2016

## Tài liệu học SageMath và SageTeX

1. [Binaries for Linux](http://www.sagemath.org/download-linux.html)

2. [Ubuntu Documentation - Sage](https://help.ubuntu.com/community/SAGE)

3. [Sage Tutorial](http://doc.sagemath.org/html/en/tutorial/)

4. [Using SageTeX](http://doc.sagemath.org/html/en/tutorial/sagetex.html)

## Hướng dẫn cài đặt các gói lệnh

* Vào mục [Download](http://www.sagemath.org/download.html "Download SageMath") 
của [SageMath](http://www.sagemath.org/ "sagemath.org"), chọn phiên bản phù hợp với hệ điều hành và làm theo hướng dẫn.

* **Cài đặt SageMath cho Ubuntu:**

	+ Thực hiện cài đặt từ `PPA`:
	
			$ sudo -E apt-add-repository -y ppa:aims/sagemath
			
			$ sudo -E apt-get update
			
			$ sudo -E apt-get install sagemath-upstream-binary
			
	+ Chạy `SageMath`:
		
		- Mở `SageMath`, thực hiện tính toán với chế độ dòng lệnh: `command line`.
			
			* Gõ lệnh:
			
					$ sage
			
			* Sau lệnh `sage`, sẽ xuất hiện như sau:
			
					sage:
			
			* Thực hiện gõ lệnh vào đây.					
		
		- Thao tác ở chế độ `GUI` với `notebook`:
		
			* Gõ lệnh:
					
					$ sage
					
			* Gõ tiếp `notebook()`:
			
					sage: notebook()
		
			* Nhập mật khẩu 2 lần nếu lần đầu sử dụng và copy địa chỉ dán vào trình duyệt web:
		
					http://localhost:8080
				
			* Chọn tab `Help` để đọc hướng dẫn sử dụng.

* **Làm cho SageTeX biết TeX:**

	+ Tìm thư mục chứa file `sagetex.sty`, dùng lệnh `find`:
	
			$ sudo find / -name sagetex.sty
			
			/usr/lib/sagemath/local/share/texmf/tex/latex/sagetex/sagetex.sty
						
	+ Nếu trong thư mục `/home/username/` (với `username` là tên tài khoản đăng nhập vào máy), 
	chưa có thư mục `texmf` thì khởi tạo nó:

			$ mkdir /home/username/texmf
			
	+ Copy tất cả các thư mục và file trong `/usr/lib/sagemath/local/share/texmf/` đến thư mục `/home/username/texmf/`:
	
			$ cp -r /usr/lib/sagemath/local/share/texmf/* /home/username/texmf/
			
	+ Làm cho TeX biết sự thay đổi này:
	
			$ texhash /home/username/texmf/

## Cách sử dụng gói lệnh sagetex

* Khai báo gói lệnh trong tài liệu `LaTeX`:

		\usepackage{sagetex}
		
* Các lệnh được sử dụng trong gói lệnh `sagetex`:

	+ Xem tài liệu về `sagetex` trên máy tính:
	
			$ ls /usr/lib/sagemath/local/share/doc/sagetex/
		
			example.pdf 		example.tex 		sagetex.pdf
		
	+ Dùng lệnh `gnome-open` để xem tài liệu:
	
			$ gnome-open /usr/lib/sagemath/local/share/doc/sagetex/sagetex.pdf
			
	+ Đọc file hướng dẫn `sagetex.pdf` để biết cách sử các lệnh, kết hợp thực hành với file  `example.tex`.
			
* Biên dịch một file `.tex` có nhúng mã `sage` vào: ví dụ, file tex là `/home/username/example/example.tex`

	+ Biên dịch file `example.tex` lần thứ nhất bằng cách thường dùng.
	
	+ Dùng lệnh `sage` để chạy file `example.sagetex.sage` (chuyển đến thư mục chứa file soạn thảo tài liệu LaTeX):
		
			$ sage /home/username/example/example.sagetex.sage
	
	+ Xuất hiện thông báo bên dưới là biên dịch file `.sage` thành công:
	
			Sage processing complete. Run LaTeX on learning-latex.tex again.
			
	+ Biên dịch lại file `example.tex` một lần nữa để nhận được kết quả tính toán tự động chèn vào tài liệu.
