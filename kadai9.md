# 課題9レポート

標準画像「hotate」を原画像とする。この画像は縦500画素、横500画素による正方形のディジタルカラー画像である。

ORG = imread('hotate.jpg'); % 画像の読み込み  
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示  

によって、原画像を読み込み、グレースケールにしたものを図１に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai9_1.jpg)

図1 原画像(グレー)  

ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示    

によってノイズを添付した画像を図2に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai9_2.jpg)

図2 ノイズ添付画像

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

これによりノイズ添付画像をフィルタを使用することでノイズを除去する。  
平滑化フィルタでノイズ除去した画像を図3に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai9_3.jpg)

図3 平滑化フィルタでノイズ除去した画像  

IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

これによりメディアンフィルタでノイズ除去した画像を図4に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai9_4.jpg)

図4 メディアンフィルタでノイズ除去した画像  

f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計  
IMG = filter2(f,IMG,'same'); % フィルタの適用  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

これにより設計したフィルタでノイズ除去した画像を図5に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai9_5.jpg)

図5 設計したフィルタでノイズ除去した画像  

平滑化フィルタでノイズ除去するとノイズの部分とその近傍の画素の濃度値を平均化するため、ノイズ部分とともに画像の輪郭がぼやけてしまうことがわかった。    
メディアンフィルタでノイズ除去するとノイズの部分とその近傍の画素の濃度値を中央値化するため、画像の輪郭がぼやけることなくノイズが除去できている。  
設計したフィルタでノイズ除去すると全体的に灰色になることがわかった。