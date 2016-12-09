# Một số thủ thuật trong Beamer

Thực hiện: Thi Minh Nhựt - Email: thiminhnhut@gmail.com

Thời gian: Ngày 10 tháng 12 năm 2016

# Tài liệu tham khảo

1.[Option unicode and beamer with LuaLaTeX](http://tex.stackexchange.com/questions/308047/option-unicode-and-beamer-with-lualatex).

## Hiển thị tiếng Việt vào Bookmark của PDF trong Beamer

* Từ khóa tìm kiếm: `unicode in beamer`

* Thêm vào khai báo bên dưới trước `\documentclass`:
		
		\PassOptionsToPackage{unicode=true}{hyperref}

* Ví dụ:

	+ Trước khi dùng lệnh `\PassOptionsToPackage{unicode=true}{hyperref}`:
	
		![](https://raw.githubusercontent.com/h3int2um/latex/master/beamer/tips-beamer/example/bookmark-tiengviet/images/bookmark-khongtiengviet.png)
		
	+ Sau khi dùng lệnh `\PassOptionsToPackage{unicode=true}{hyperref}`:
	
		![](https://raw.githubusercontent.com/h3int2um/latex/master/beamer/tips-beamer/example/bookmark-tiengviet/images/bookmark-tiengviet.png)
		
* Source LaTeX của ví dụ mẫu: [Code LaTeX + File PDF](https://github.com/h3int2um/latex/tree/master/beamer/tips-beamer/example/bookmark-tiengviet)
