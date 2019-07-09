# 課題3レポート

標準画像「hotate」を原画像とする。この画像は縦500画素、横500画素による正方形のディジタルカラー画像である。

ORG=imread('hotate.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); axis image; % 画像の表示  

によって、原画像を読み込み、グレースケールにしたものを図１に示す。

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai3_1.jpg)

図1 原画像(グレー)

IMG = ORG > 64; % 輝度値が64以上の画素を1、その他を0に変換  
imagesc(IMG); colormap(gray); colorbar;  

これにより閾値を64に設定し、画像を2値化したものを図2に示す。

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai3_2.jpg)

図2 閾値64での2値化画像

IMG = ORG > 96;  
imagesc(IMG); colormap(gray); colorbar;  

これにより閾値を96に設定し、画像を2値化したものを図3に示す。

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai3_3.jpg)

図3 閾値96での2値化画像

IMG = ORG > 128;  
imagesc(IMG); colormap(gray); colorbar;  

これにより閾値を128に設定し、画像を2値化したものを図4に示す。

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai3_4.jpg)

図4 閾値128での2値化画像

IMG = ORG > 192;  
imagesc(IMG); colormap(gray); colorbar;  

により、閾値を192に設定し、画像を2値化したものを図5に示す。

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai3_5.jpg)

図5 閾値192での2値化画像

閾値が小さいほど画像が白っぽくなり、閾値が大きいほど画像が黒っぽくなることがわかった。