# 課題5　判別分析法

判別分析法を用いて画像二値化せよ.

以下はソースコードである。

ORG=imread('C:\Users\bridgebook\Pictures\landmark.jpg'); % 原画像の入力

ORG = rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換

imagesc(ORG); colormap(gray); colorbar

pause;


H = imhist(ORG); %ヒストグラムのデータを列ベクトルEに格納

myu_T = mean(H);

max_val = 0;

max_thres = 1;

for i=1:255

C1 = H(1:i); %ヒストグラムを2つのクラスに分ける

C2 = H(i+1:256);

n1 = sum(C1); %画素数の算出

n2 = sum(C2);

myu1 = mean(C1); %平均値の算出

myu2 = mean(C2);

sigma1 = var(C1); %分散の算出

sigma2 = var(C2);

sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散の算出

sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散の算出

if max_val<sigma_B/sigma_w

max_val = sigma_B/sigma_w;

max_thres =i;

end;

end;

IMG = ORG > max_thres;

imagesc(IMG); colormap(gray); colorbar;

pause;


原画像には図1を用いる。

![kadai11](https://user-images.githubusercontent.com/35340807/34903547-2190a0fe-f877-11e7-8a4c-f1ff2ba06166.png)

図1 原画像

原画像を白黒濃淡画像へ変換したものが図2である。

![kadai51](https://user-images.githubusercontent.com/35340807/34903660-9216fb0a-f879-11e7-9a89-338561a3cf14.PNG)

図2 白黒濃淡画像

判別分析法を用いて画像を二値化したものが図3である。

![kadai52](https://user-images.githubusercontent.com/35340807/34903659-91ef9a6a-f879-11e7-8cb5-a285df893a9d.PNG)

図3 二値化した画像
