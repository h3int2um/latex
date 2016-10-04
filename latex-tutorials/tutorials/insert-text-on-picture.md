# Chèn chữ lên hình trong LaTeX

Thực hiện: Thi Minh Nhựt - Email: thiminhnhut@gmail.com

Thời gian: Ngày 04 tháng 10 năm 2016

## Tài liệu tham khảo

[How to put text in an existing figure/image (maybe with tikz?)](http://tex.stackexchange.com/questions/52544/how-to-put-text-in-an-existing-figure-image-maybe-with-tikz)

## Hướng dẫn thực hiện

* Ví dụ, cú pháp chính: sử dụng môi trường `picture` (không cần khai báo `\usepackage{picture}` ở phần đầu).

		\begin{picture}(100,100)
		
			\put(0,0){\includegraphics{....}}
		
			\put(10,10){hello}
			
		\end{picture}

	Ví dụ trên sẽ chèn dòng chữ `hello` lên hình.
	
* Code cho ví dụ minh họa: [Download code](https://github.com/h3int2um/latex/blob/master/latex-tutorials/code-latex-tutorials/insert-text-on-picture.tex). [Download image](https://github.com/h3int2um/latex/blob/master/latex-tutorials/code-latex-tutorials/ubuntu-logo.png). 
Nội dung code:

		\documentclass[border=12pt]{standalone}
		
		\usepackage[utf8]{inputenc}
		
		\usepackage[utf8]{vietnam}
		
		\usepackage{amsmath,amsfonts,amssymb}
		
		\usepackage{graphicx}
		
		\usepackage{xcolor}

		\begin{document}

			\begin{picture}(100,100)
				
				\put(0,0){\includegraphics[scale=.5]{ubuntu-logo.png}}
		
				\put(20,-10){\textbf{\textcolor{blue}{Logo Ubuntu}}}
				
			\end{picture}
		
		\end{document} 
		
* Xem kết quả của ví dụ minh họa: [Xem PDF](https://github.com/h3int2um/latex/blob/master/latex-tutorials/code-latex-tutorials/insert-text-on-picture.pdf). 
Kết quả: chèn dòng chữ `Logo Ubuntu` vào dưới hình ảnh `ubuntu-logo.png`
