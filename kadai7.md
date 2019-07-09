# 課題7レポート

標準画像「hotate」を原画像とする。この画像は縦500画素、横500画素による正方形のディジタルカラー画像である。

ORG=imread('hotate.jpg'); % 原画像の入力  
ORG=rgb2gray(ORG);  
imagesc(ORG); colormap(gray); colorbar;  
imhist(ORG); % 濃度ヒストグラムを生成、表示  

によって、原画像を読み込み、グレースケールにしたものを図１に示す。  
また、その画像の濃度ヒストグラムを図2に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai7_1.jpg)

図1 原画像(グレー)   

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai7_2.jpg)

図2 濃度ヒストグラム

ORG = double(ORG);  
mn = min(ORG(:)); % 濃度値の最小値を算出  
mx = max(ORG(:)); % 濃度値の最大値を算出  
ORG = (ORG-mn)/(mx-mn)*255;  

これにより画素のダイナミックレンジを0〜255に拡大する。  

imagesc(ORG); colormap(gray); colorbar;  
ORG = uint8(ORG); % 8ビットの符号なし整数に変換  
imhist(ORG); % 濃度ヒストグラムを生成、表示  

uint8を使用する理由は、ダイナミックレンジを拡大した時にORGを少数に変換(double)したため、そのままではヒストグラムを生成することができないのでuint8を用いて8ビットの符号なし整数に変換することでヒストグラムの生成を可能にしている。  
ダイナミックレンジを拡大した画像を図3に示す。  
また、その画像の濃度ヒストグラムを図4に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai7_3.jpg)

図3 ダイナミックレンジを拡大したグレースケール画像

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai7_4.jpg)

図4 ダイナミックレンジを拡大した濃度ヒストグラム

今回、図1の原画像と図3のダイナミックレンジを拡大した画像の違い、図2のヒストグラムと図4のダイナミックレンジを拡大したヒストグラムの違いは見られなかった。
これは最近のカメラはすでにダイナミックレンジが広いため、今回使用した画像の濃度の最小値が0で最大値が255であったため変化がなかったと考えられる。