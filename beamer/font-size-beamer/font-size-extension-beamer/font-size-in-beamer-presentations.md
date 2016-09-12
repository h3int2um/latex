# Kích thước chữ trong trình chiếu với Beamer

Sưu tầm: Thi Minh Nhựt - Email: thiminhnhut@gmail.com

Thời gian: Ngày 05 tháng 09 năm 2016

## Tài liệu tham khảo

Chủ đề: [Font sizes in Beamer presentations](http://www.stat.berkeley.edu/~paciorek/computingTips/Font_sizes_in_Beamer_presen.html)

Tác giả: `Chris Paciorek` - Thời gian: `12/22/09`.

## Hướng dẫn sử dụng

Khi muốn sử dụng các cỡ chữ lớn hơn trong Beamer (khác các cỡ `8pt, 9pt, 10pt, 11pt, 12pt, 14pt, 17pt, 20pt`), 
cần có những file `size.clo` thích hợp.

* Ví dụ, cần thêm 2 cỡ chữ mở rộng là `24pt` và `28pt` thì cần có 2 file: 
[size24.clo](http://www.stat.berkeley.edu/~paciorek/size24.clo) 
và [size28.clo](http://www.stat.berkeley.edu/~paciorek/size28.clo)

* Tải các file [size24.clo](http://www.stat.berkeley.edu/~paciorek/size24.clo) 
và [size28.clo](http://www.stat.berkeley.edu/~paciorek/size28.clo) về máy 
và lưu vào thư mục `extsizes` trên máy tính `Linux`.
	
	+ Tìm đường dẫn của thư mục `extsizes`: 
	
			$ sudo find / -name size20.clo
			
			/usr/share/texlive/texmf-dist/tex/latex/extsizes/size20.clo
	
	+ Copy 2 file `size24.clo` và `size28.clo` vào thư mục `extsizes`: chuyển đến nơi lưu 
	2 file `size24.clo` và `size28.clo` rồi dùng lệnh sau:
	
			$ sudo cp size24.clo size28.clo /usr/share/texlive/texmf-dist/tex/latex/extsizes/
	

* Trong file `/usr/share/texmf/tex/latex/beamer/base/beamer.cls`, thêm vào 2 dòng sau vào bên dưới dòng 
`\DeclareOptionBeamer{20pt}{\def\beamer@size{{size20.clo}}}`:

		\DeclareOptionBeamer{24pt}{\def\beamer@size{{size24.clo}}}
		
		\DeclareOptionBeamer{28pt}{\def\beamer@size{{size28.clo}}}

	+ Dùng lệnh sau để mở file:
	
			$ sudo nano /usr/share/texmf/tex/latex/beamer/base/beamer.cls
			
	+ Sau khi thêm 2 dòng trên vào, nội dung file `beamer.cls` trong giống như sau:
	
			...
			
			\DeclareOptionBeamer{20pt}{\def\beamer@size{{size20.clo}}}
			
			\DeclareOptionBeamer{24pt}{\def\beamer@size{{size24.clo}}} %Font size extension in Beamer presentations
			
			\DeclareOptionBeamer{28pt}{\def\beamer@size{{size28.clo}}}
			
			...
			
	+ Nhấn `Ctrl + X + Y` và `Enter` để lưu và thoát.
	
* Cập nhật lại các gói trong `Texlive`:
	
		$ sudo texhash

* Khi sử dụng, khai báo bình thường như những font size trước đó, ví dụ:

		\documentclass[24pt,a4paper]{beamer}	%Font size 24pt
		
		\documentclass[28pt,a4paper]{beamer}	%Fontsize 28pt
	
## Ví dụ minh họa

Nội dung ví dụ trong thư mục `example`:

* Gồm các ví dụ minh hoạ cho các font size: `8pt, 9pt, 10pt, 11pt, 12pt, 14pt, 17pt, 20pt, 24pt, 28pt`.

* Nội dung của file `font-size-8-28pt.pdf`: minh họa cho sự thay đổi kích thước của các font size kể trên.
