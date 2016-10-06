# Sử dụng phím tắt trong TeXMaker trên Ubuntu 16.04

Thực hiện: Thi Minh Nhựt - Email: thiminhnhut@gmail.com

Thời gian: Ngày 06 tháng 10 năm 2016

## Nguồn tham khảo

[Texmaker Shortcuts not working on Ubuntu 16.04](http://askubuntu.com/questions/786280/texmaker-shortcuts-not-working-on-ubuntu-16-04)

## Vấn đề phát sinh khi cài đặt TeXMaker trên Ubuntu 16.04

* Khi cài đặt `TeXMaker` trên `Ubuntu 16.04` bằng lệnh `sudo apt-get install texmaker`, khi mở giao diện 
soạn thảo tài liệu `LaTeX` với `TeXMaker` thì mặt định không sử dụng được các phím tắt (các phím tắt giúp 
quá trình soạn thảo nhanh hơn).

* Cần có giải pháp khắc phục vấn đề trên.

## Hướng dẫn thực hiện

* Bước 1: Tìm file `texmaker.desktop`:

		$ sudo find / -name texmaker.desktop
		
		/usr/share/applications/texmaker.desktop
		
* Bước 2: Mở file `texmaker.desktop`:

		$ sudo nano /usr/share/applications/texmaker.desktop
		
* Bước 3: Tìm đến dòng lệnh `Exec=texmaker %F` và thay đổi thành `Exec=env UBUNTU_MENUPROXY= texmaker %F`. 
Nội dung file `texmaker.desktop` sau khi thay đổi như bên dưới:

		[Desktop Entry]
		
		Categories=Office;Publishing;Qt;X-SuSE-Core-Office;X-Mandriva-Office-Publishing;X-Misc;
			
		Keywords=Editor;Latex;
		
		Exec=env UBUNTU_MENUPROXY= texmaker %F
		
		GenericName=LaTeX Editor
		
		GenericName[fr]=Editeur LaTeX
		
		Comment=LaTeX development environment
		
		Comment[fr]=Environnement de développement LaTeX
		
		Icon=texmaker
		
		MimeType=text/x-tex;
		
		Name=Texmaker
		
		Name[fr]=Texmaker
		
		StartupNotify=false
		
		Terminal=false
		
		Type=Application

* Bước 4: Nhấn `Ctrl + X + Y` và `Enter` để lưu và thoát.

* Bước 5: Mở trình soạn thảo `TeXMaker` lên để kiểm tra xem có sử dụng được phím tắt hay chưa.
