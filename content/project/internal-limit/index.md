---
date: "2023-11-11T00:00:00Z"
external_link: ""
image:
  caption: Photo by Harun Deppalallo
  focal_point: Smart
links:
- icon: instagram
  icon_pack: fab
  name: Follow
  url: https://www.instagram.com/hd03.00/
slides: example
summary: Beberapa Soal Limit trigonometri dan penyelesaiannya
tags:
- Mathematics
title: Limit (Soal Fungsi trigonometri)
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""
markup: "mmark"
math: true
---

1. Tentukan Nilai dari
$$\lim_{x \to \frac{\pi}{3}} \frac{2 \tan x-\sin x}{\cos x}$$
Penyelesaian :
$$\frac{2 \tan \frac{\pi}{3}-\sin \frac{\pi}{3}}{\cos \frac{\pi}{3}}=\frac{2\sqrt{3}-\frac{\sqrt{3}}{2}}{\frac{1}{2}}=\frac{\frac{4\sqrt{3}}{2}-\frac{\sqrt{3}}{2}}{\frac{1}{2}}=\frac{\frac{3 \sqrt{3}}{2}}{\frac{1}{2}}=\frac{6 \sqrt{3}}{2}=3 \sqrt{3}$$

$\space$

2. Tentukan Nilai dari
$$\lim_{x \to \frac{\pi}{4}} \frac{\sin 2x}{\sin x+\cos x}$$
Penyelesaian :
$$\frac{\sin 2(\frac{\pi}{4})}{\sin \frac{\pi}{4}+\cos \frac{\pi}{4}}=\frac{1}{\frac{1}{2}\sqrt{2}+\frac{1}{2}\sqrt{2}}=\frac{1}{\sqrt{2}}=\frac{1}{\sqrt{2}}\times \frac{\sqrt{2}}{\sqrt{2}}=\frac{1}{2}\sqrt{2}$$

$\space$

3. Tentukan Nilai dari
$$\lim_{x \to \frac{\pi}{4}} \frac{\cos 2x}{\cos x-\sin x}$$
Penyelesaian :
$$\lim_{x \to \frac{\pi}{4}}\frac{\cos 2x}{\cos x-\sin x}=\lim_{x \to \frac{\pi}{4}}\frac{\cos^2x-\sin^2x}{\cos x-\sin x}$$
$$=\lim_{x \to \frac{\pi}{4}} \frac{(\cos x-\sin x)(\cos x+\sin x)}{\cos x-\sin x}$$
$$=\lim_{x \to \frac{\pi}{4}} \cos x+\sin x=\cos \frac{\pi}{4}+\sin \frac{\pi}{4}$$
$$=\frac{1}{2}\sqrt{2}+\frac{1}{2}\sqrt{2}=\sqrt{2}$$

$\space$

4. Tentukan nilai dari
$$\lim_{x \to 0}\frac{\sin 3x}{2x}$$
Penyelesaian :
Gunakan sifat Limit $$\lim_{x \to 0} \frac{\sin ax}{bx}=\frac{a}{b}$$
$$\lim_{x \to 0}\frac{\sin 3x}{2x}=\frac{3}{2}=1 \frac{1}{2}$$

$\space$

5. Tentukan nilai dari
$$\lim_{x \to 0} \frac{\sin 8x}{\tan2x}$$
Penyelesaian :
Gunakan sifat Limit
$$->\lim_{x \to 0} \frac{\sin ax}{\tan bx}=\frac{a}{b}$$
$$->\lim_{x \to 0} \frac{\tan ax}{\sin bx}=\frac{a}{b}$$
$$\lim_{x \to 0} \frac{\sin 8x}{\tan2x}=\frac{8}{2}=4$$

$\space$

6. Tentukan nilai dari
$$\lim_{x \to 0} \frac{x \cos 2x}{\sin x}$$
Penyelesaian :
$$\lim_{x \to 0} \frac{x}{\sin x} \cdot \cos 2x$$
$$=\lim_{x \to 0} \frac{x}{\sin x} \cdot \lim_{x \to 0} \cos 2x$$
$$\lim_{x \to 0} \frac{x}{\sin x}=1, \space \lim_{x \to 0} \cos 2x=1$$
$$maka, \space \lim_{x \to 0} \frac{x}{\sin x} \cdot \lim_{x \to 0} \cos 2x=1 \cdot 1=1$$

$\space$

7. Tentukan nilai dari
$$\lim_{x \to 0} \frac{4x \cos x}{\sin x+ \sin 3x}$$
Penyelesaian :

Kita menyelesaikan pembaginya terlebih dahulu. Ingat sifat trigonometri

$\sin A + \sin B= 2 \sin \frac{1}{2}(A+B)\cdot \cos \frac{1}{2}(A-B)$

$Jadi, \space \sin x+ \sin 3x=2 \sin \frac{1}{2}(x+3x)\cdot \cos \frac{1}{2}(x-3x)$

$\hspace{3.7 cm}$$=2 \sin 2x \cdot \cos(-x)$

$\hspace{3.7 cm}$$=2 \sin 2x \cdot \cos x$

Sekarang kita lanjutkan soal diatas dengan mengganti pembagi yg telah dihitung terlebih dahulu
$$\lim_{x \to 0} \frac{\textcolor{red}4x \textcolor{red}\cos \textcolor{red}x}{\textcolor{red}2 \sin 2x \cdot \textcolor{red}\cos \textcolor{red}x}$$
$$=\lim_{x \to 0} \frac{\textcolor{blue}2 x}{\sin 2x}$$
2 dipindah kedepan sehinggah menjadi :
$$=\textcolor{blue}2 \cdot \lim_{x \to 0} \frac{x}{\sin 2x}$$
Untuk menyelesaikan hasil di atas,ingat sifat limit $$\lim_{x \to 0} \frac{\sin ax}{bx}=\lim_{x \to 0} \frac{ax}{\sin bx}=\frac{a}{b}$$

$$Jadi, \space 2 \cdot \lim_{x \to 0} \frac{x}{\sin 2x}=2 \cdot \frac{1}{2}=1$$

$\space$

8. Tentukan nilai dari 
$$\lim_{x \to 0} \frac{x^4-4x}{3x^2+x^2}$$
Penyelesaian :

$$\lim_{x \to 0} \frac{x^4-4x}{3x^2+x^2}=\lim_{x \to 0} \frac{\textcolor{red}x (x^3-4)}{\textcolor{red}x(3x+x)}$$$$=\lim_{x \to 0}\frac{x^3-4}{3x+x}=\frac{0^3-4}{3\cdot 0+0}=\frac{-4}{0}=Tidak \space terdefinisi$$

Cara penyelesaian dengan cara yang lain :

karena hasilnya $\frac{0}{0}$ bisa juga menyelesaikan soal diatas saya menggunakan l'Hopital. Teknik l'hopital dilakukan dengan menurunkan pembilang dan penyebut masing-masing.

$$\lim_{x \to 0} \frac{x^4-4x}{3x^2+x^2}=\lim_{x \to 0} \frac{4x^3-4}{6x+2x}=\frac{4\cdot 0^3-4}{6\cdot 0+2\cdot 0}=\frac{-4}{0}= Tidak \space terdefinisi$$

$\space$

9. Tentukan nilai dari
$$\lim_{x \to \infty} \frac{(2x-3)(3x+1)}{2x^2+x+1}$$
Penyelesaian :

Sebelum masuk dalam penyelesaian, kita akan melihat salah satu sifat limit yang akan menjadi pedoman untuk menyelesaikan soal diatas.

$$\lim_{x \to \infty} \frac{Ax^m+Bx^{m-1}+Cx^{m-2}+ \cdots}{Px^n+Qx^{n-1}+Rx^{n-2}+ \cdots}=$$

* Bernilai $0$ jika $m<n$
* Bernilai $\frac{A}{P}$ jika $m=n$
* Bernilai $\infty$ jika $m>n$

Selanjutnya kita mengerjakan soal
$$\lim_{x \to \infty} \frac{(2x-3)(3x+1)}{2x^2+x+1}$$
Kalikan pembilangnya 
$$\lim_{x \to \infty} \frac{6x^2+2x-9x-3}{2x^2+x+1}=\lim_{x \to \infty} \frac{6x^2-7x-3}{2x^2+x+1}$$
limit diatas sama persis dengan sifat yang telah kita tuliskan sebelumnya, maka untuk melanjutkan peyelesaiannya tinggal mengambil nilai berdasarkan sifat

$$m=2, \space n=2$$
$$A=6, \space P=2$$

Karena $m=n$, maka kita gunakan 
* Bernilai $\frac{A}{P}$ jika $m=n$

$$\lim_{x \to \infty} \frac{6x^2-7x-3}{2x^2+x+1}=\frac{6}{2}=3$$

$\space$

10. Nilai dari
$$\frac{2x^3+3x^2-5x+4}{2x^4-4x^2+9}$$

Penyelesaian :

Untuk menyelesaikan soal tersebut, pembilang dan penyebutnya dikalikan dengan $\frac{1}{pangkat \space tertinggi}$

Kita lihat bahwa pangkat tertinggi dari soal diatas adalah $x^4$.

maka, 
$$\lim_{x \to \infty} \frac{2x^3+3x^2-5x+4}{2x^4-4x^2+9} \times \frac{\frac{1}{x^4}}{\frac{1}{x^4}}$$
$$\lim_{x \to \infty} \frac{2x^3(\frac{1}{x^4})+3x^2(\frac{1}{x^4})-5x+4(\frac{1}{x^4})}{2x^4(\frac{1}{x^4})-4x^2(\frac{1}{x^4})+9(\frac{1}{x^4})}$$
$$\lim_{x \to \infty} \frac{\frac{2}{x}+\frac{3}{x^2}-\frac{5}{x^2}+\frac{4}{x^4}}{2-\frac{4}{x^2}+\frac{9}{x^4}}$$

Subtitusi $x=\infty$

$$ \frac{\frac{2}{\infty}+\frac{3}{\infty^2}-\frac{5}{\infty^2}+\frac{4}{\infty^4}}{2-\frac{4}{\infty^2}+\frac{9}{\infty^4}}$$
Ingat bahwa bilangan yang dibagi $\infty$ hasilnya sama dengan $0$
$$ \frac{\frac{2}{\infty}+\frac{3}{\infty^2}-\frac{5}{\infty^2}+\frac{4}{\infty^4}}{2-\frac{4}{\infty^2}+\frac{9}{\infty^4}}=\frac{0+0-0+0}{2-0+0}=\frac{0}{2}=0$$

$\space$

11. Nilai dari
$$\lim_{x \to \infty} \left( 3x + \sin \frac{1}{x} \right)$$
Penyelesaian :

Untuk menyelesaikan soal diatas, gunakan konsep limit.
$$\lim_{x \to c} (f(x)+g(x))=\lim_{x \to c} f(x) + \lim_{x \to c} g(x)$$

misalkan
$$p=\frac{1}{x}, \space sehingga \space x=\frac{1}{p}$$
$$Jika \space x \to \infty, \space maka \space p \to 0$$

jadi soal diatas kita akan merobah dari $x \to \infty$ menjadi $p \to 0$ dan mensubtitusi nilai $x=\frac{1}{p}$

$$\lim_{p \to 0} \left( 3 \left(\frac{1}{p} \right) + \sin \frac{1}{\frac{1}{p}} \right)$$
$$=\lim_{p \to 0} \left( \frac{3}{p}+ \sin p \right)= \lim_{p \to 0} \frac{3}{p} + \lim_{p \to 0} \sin p$$
$$=\infty + \sin 0= \infty +0=\infty$$

$\space$

12. Nilai dari
$$\lim_{x \to \infty} y \sin \frac{3}{y} \cdot \cos \frac{5}{y}$$

Penyelesaian :

$$Misal \space y = \frac{1}{a}$$
$$Maka \space \infty = \frac{1}{a}$$
$$a=0$$

$$\lim_{a \to 0} \frac{1}{a} \sin3a \cdot \cos 5a=\lim_{a \to 0} \frac{\sin3a \cdot \cos 5a}{a} \times \frac{3}{3}$$
$$=\lim_{a \to 0} \frac{3\sin3a \cdot 3\cos 5a}{3a}$$
$$=\lim_{a \to 0} \frac{\sin 3a}{3a}\cdot \lim_{a \to 0} 3 \cos 5a$$

Ingat sifat limit
$$\lim_{x \to 0} \frac{\sin mx}{nx}=\frac{m}{n}$$

maka,
$$\frac{3}{3} \cdot 3 \cos 5(0)=1 \cdot 3 \cos 0=1 \cdot 3(1)=3$$

$\space$

13. Asimtot datar dari fungsi $f$ dengan
$$f(x)=\frac{x^3+2x+1}{x^3-x}$$

Penyelesaian :

Asimtot datar(Asimtot Horizontal)
$$y=\lim_{x \to \infty} f(x)$$
$$y=\lim_{x \to \infty} \frac{x^3+2x+1}{x^3-x}$$

sama dengan no. 9, kita gunakan sifat berikut
$$\lim_{x \to \infty} \frac{Ax^m+Bx^{m-1}+Cx^{m-2}+ \cdots}{Px^n+Qx^{n-1}+Rx^{n-2}+ \cdots}=$$
* Bernilai $\frac{A}{P}$ jika $m=n$

$$y=\lim_{x \to \infty} \frac{x^3+2x+1}{x^3-x}$$
$$y=\frac{1}{1}=1$$
















