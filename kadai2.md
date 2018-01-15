# 課題2　階調数と疑似輪郭
２階調，４階調，８階調の画像を生成する.

以下はソースコードである。

clear; % 変数のオールクリア


ORG=imread('C:\Users\bridgebook\Pictures\landmark.jpg'); % 原画像の入力

imagesc(ORG); axis image; % 画像の表示

pause;


ORG=imread('C:\Users\bridgebook\Pictures\landmark.jpg'); % 原画像の入力

ORG = rgb2gray(ORG); colormap(gray); colorbar;

imagesc(ORG); axis image; % 画像の表示

pause; % 一時停止


% ２階調画像の生成

IMG = ORG>128;

imagesc(IMG); colormap(gray); colorbar;  axis image;

pause;


% ４階調画像の生成

IMG0 = ORG>64;

IMG1 = ORG>128;


IMG2 = ORG>192;

IMG = IMG0 + IMG1 + IMG2;

imagesc(IMG); colormap(gray); colorbar;  axis image;

pause;


% ８階調画像の生成

IMG0 = ORG>32;

IMG1 = ORG>64;

IMG2 = ORG>96;

IMG3 = ORG>128;

IMG4 = ORG>160;

IMG5 = ORG>192;

IMG6 = ORG>224;

IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;

imagesc(IMG); colormap(gray); colorbar;  axis image;


原画像には図1を用いる。

![kadai21](https://user-images.githubusercontent.com/35340807/34881718-a95a9966-f7f7-11e7-87b9-a45660013616.png)

図1 原画像

2階調の画像は図2のように生成された。

![kadai23](https://user-images.githubusercontent.com/35340807/34881721-a9b8ce32-f7f7-11e7-8fe9-51a84010a7c9.png)

図2 2階調画像

4階調の画像は図3のように生成された。

![kadai24](https://user-images.githubusercontent.com/35340807/34881722-aa2a1524-f7f7-11e7-9501-fe8d7c86669b.png)

図3 4階調画像

![kadai25](https://user-images.githubusercontent.com/35340807/34881723-aa59ad70-f7f7-11e7-9175-8dc552aa8035.png)

図4 8階調画像
