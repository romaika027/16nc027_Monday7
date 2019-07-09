# 課題6レポート

標準画像「hotate」を原画像とする。この画像は縦500画素、横500画素による正方形のディジタルカラー画像である。

ORG=imread('hotate.jpg'); % 原画像の入力  
ORG=rgb2gray(ORG);  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示  

によって、原画像を読み込み、グレースケールにしたものを図１に示す。

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai6_1.jpg)

図1 原画像(グレー)

IMG = ORG>128; % 128による二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

これにより閾値128で2値化した画像を図2に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai6_2.jpg)

図2 閾値128による2値化画像

IMG = dither(ORG); % ディザ法による二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

これによりディザ法で2値化した画像を図3に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai6_3.jpg)

図3 ディザ法による2値化画像

閾値で2値化する方法より、ディザ法で2値化する方が画像の濃淡をより鮮明に表示できることがわかった。