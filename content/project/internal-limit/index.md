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
$$\lim_{x \to \frac{\pi}{4}} \frac{\sin 2x}{\cos x-\sin x}$$
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

$\hspace{3.7 cm}$$=2 \sin 2x \cdot \cos(-c)$

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





















