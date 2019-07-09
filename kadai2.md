# 課題2レポート

標準画像「hotate」を原画像とする。この画像は縦500画素、横500画素による正方形のディジタルカラー画像である。

ORG=imread('hotate.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % カラー画像を白黒濃淡画像へ変換  
imagesc(ORG); axis image; % 画像の表示  

によって、原画像を読み込み、グレースケールにしたものを図１に示す。

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai2_1.jpg)

図1 原画像(グレー)

IMG = ORG>128;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

これにより128より大きいものとそれ以下に分け、2階調画像を生成した。  
その結果を図2に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai2_2.jpg)

図2 2階調画像

IMG0 = ORG>64;  
IMG1 = ORG>128;  
IMG2 = ORG>192;  
IMG = IMG0 + IMG1 + IMG2;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

これにより64、128、192で区切って、4階調画像を生成した。  
その結果を図3に示す。

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai2_3.jpg)

図3 4階調画像

IMG0 = ORG>32;  
IMG1 = ORG>64;  
IMG2 = ORG>96;  
IMG3 = ORG>128;  
IMG4 = ORG>160;  
IMG5 = ORG>192;  
IMG6 = ORG>224;  
IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

これにより32、64、96、128、160、192、224で区切って、8階調画像を生成した。  
その結果を図4に示す。

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai2_4.jpg)

図4 8階調画像

2階調、4階調、8階調となるにつれて原画像に近い画像になることがわかった。