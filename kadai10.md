# 課題10レポート

標準画像「hotate」を原画像とする。この画像は縦500画素、横500画素による正方形のディジタルカラー画像である。

ORG = imread('hotate.jpg'); % 画像の読み込み  
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示  

によって、原画像を読み込み、グレースケールにしたものを図１に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai10_1.jpg)

図1 原画像(グレー)  

IMG = edge(ORG,'prewitt'); % エッジ抽出(プレウィット法)  
imagesc(IMG); colormap('gray'); colorbar; % 画像表示  

これによりプレウィット法でエッジ抽出を行なった結果を図2に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai10_2.jpg)

図2 プレウィット法によるエッジ抽出

IMG = edge(ORG,'sobel'); % エッジ抽出(ソベル法)  
imagesc(IMG); colormap('gray'); colorbar; % 画像表示  

これによりソベル法でエッジ抽出を行なった結果を図3に示す。  

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai10_3.jpg)

図3 ソベル法によるエッジ抽出

IMG = edge(ORG,'canny'); % エッジ抽出(キャニー法)  
imagesc(IMG); colormap('gray'); colorbar; % 画像表示  

これによりキャニー法でエッジ抽出を行なった結果を図4に示す。 

![原画像](https://github.com/romaika027/16nc027_lecture_image_processing/blob/master/images/kadai10_4.jpg)

図4 キャニー法によるエッジ抽出

プレウィット法とソベル法ではソベル法の方がわずかに多くのエッジを抽出できることが確認できた。
またキャニー法は多くのエッジを抽出できることがわかった。
