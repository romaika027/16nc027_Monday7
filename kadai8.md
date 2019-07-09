# 課題8レポート

標準画像「hotate」を原画像とする。この画像は縦500画素、横500画素による正方形のディジタルカラー画像である。

ORG = imread('hotate.jpg'); % 画像の読み込み  
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示  

によって、原画像を読み込み、グレースケールにしたものを図１に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai8_1.jpg)

図1 原画像(グレー)  

IMG = ORG > 128; % 閾値128で二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

によって閾値128で二値化した画像を図2に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai8_2.jpg)

図2 二値化画像

IMG = bwlabeln(IMG); % ラベリング  
imagesc(IMG); colormap(jet); colorbar; % 画像の表示  

二値化した画像にラベリングを行う。  
ラベリングした画像を図3に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai8_3.jpg)

図3 二値化画像をラベリングした画像  

ラベリングを行うことによって、二値化された画像の連結成分を色ごとに分けることができた。