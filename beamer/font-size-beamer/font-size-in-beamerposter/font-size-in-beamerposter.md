# Kích thước chữ trong Beamer với beamerposter

Sưu tầm: Thi Minh Nhựt - Email: thiminhnhut@gmail.com

Thời gian: Ngày 05 tháng 09 năm 2016

## Tài liệu tham khảo

1. [beamerposter – Extend beamer and a0poster for custom sized posters](https://www.ctan.org/pkg/beamerposter)

2. [Use 24 pt font size in my poster with beamerposter](http://tex.stackexchange.com/questions/305880/use-24-pt-font-size-in-my-poster-with-beamerposter)

3. [page size and font size in latex beamer](http://tex.stackexchange.com/questions/113914/page-size-and-font-size-in-latex-beamer)

4. [Beamerposter scale parameter, text font size and title font size](http://tex.stackexchange.com/questions/53561/beamerposter-scale-parameter-text-font-size-and-title-font-size)

## Hướng dẫn khác về cách thay đổi kích thước chữ không sử dụng `beamerposter`: [Font sizes extension in Beamer presentations](https://github.com/h3int2um/latex/blob/master/beamer/font-size-beamer/font-size-extension-beamer/font-size-in-beamer-presentations.md)

## Thay đổi font size trong Beamer

* Beamer hỗ trợ các font size: `8pt, 9pt, 10pt, 11pt, 12pt, 14pt, 17pt, 20pt`.

* Để sự dụng các font size khác (các font size trên), sử dụng gói `beamerposter` với khai báo như sau:

		\documentclass[20pt]{beamer} %8pt, 9pt, 10pt, 11pt, 12pt, 14pt, 17pt, 20pt
		
		\usepackage[orientation=landscape,size=a4, scale=2.3]{beamerposter} %landscape or portrait; a0, a1, a2, a3, a4 or  custom
		
* Thay đổi font size `20pt`, khổ giấy `size=a4` và hệ số `scale=2.3` cho đến khi được kích thước phù hợp.

* Có thể định nghĩa kích thước khổi giấy bằng khai báo sau:
		
		\documentclass[20pt]{beamer}

		\usepackage[orientation=portrait,size=custom,width=27.94,height=21.59, scale=2.3]{beamerposter}

## Ví dụ minh hoạ

Nội dung ví dụ trong thư mục `example`:

* Gồm các ví dụ minh hoạ cho font size `20pt`, `orientation = landscape`, `scale = 2.3`, `size = a4, a3, a2, a1, a0`.

* Nội dung của file `font-size-20pt-a4-a0-scale-2.3.pdf`: minh họa cho sự thay đổi kích thước của các size kể trên.
