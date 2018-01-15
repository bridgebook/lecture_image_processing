# 課題6 画像の二値化

原画像(図1)を用いて画像の二値化を行う。

以下はソースコードである。

clear; % 変数のオールクリア
ORG=imread('C:\Users\bridgebook\Pictures\landmark.jpg'); % 原画像の入力
ORG = rgb2gray(ORG);
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause; % 一時停止


IMG = ORG>128; % 128による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;

IMG = dither(ORG); % ディザ法による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示


![kadai11](https://user-images.githubusercontent.com/35340807/34903547-2190a0fe-f877-11e7-8a4c-f1ff2ba06166.png)

図1 原画像

閾値を輝度128として二値化を行うと図2のような画像が得られた。

![kadai61](https://user-images.githubusercontent.com/35340807/34904094-af18032c-f881-11e7-858b-858cf9a2583f.PNG)

図2 閾値を輝度128として二値化

ディザ法を用いて二値化を行うと図3のような画像が得られた。

![kadai62](https://user-images.githubusercontent.com/35340807/34904095-af41fdb2-f881-11e7-9b79-ab9e0ff4a5e8.PNG)

図3 ディザ法による二値化
