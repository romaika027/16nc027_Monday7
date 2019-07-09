# 課題4レポート

標準画像「hotate」を原画像とする。この画像は縦500画素、横500画素による正方形のディジタルカラー画像である。

ORG=imread('hotate.jpg'); % 原画像の入力  
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); colormap(gray); colorbar;  

によって、原画像を読み込み、グレースケールにしたものを図１に示す。

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai4_1.jpg)

図1 原画像(グレー)

imhist(ORG);   

これによりヒストグラムを表示する。以下の図2に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai4_2.jpg)

図2 ヒストグラム

これにより、「hotate.jpg」のヒストグラムがどのような形なのかを把握することができた。