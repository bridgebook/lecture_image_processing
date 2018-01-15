# 課題9 メディアンフィルタと先鋭化

メディアンフィルタを適用し、ノイズ除去を体験する。

以下はソースコードである。

ORG = imread('C:\Users\bridgebook\Pictures\landmark.jpg'); % 画像の読み込み

ORG = rgb2gray(ORG); % 白黒濃淡画像に変換

imagesc(ORG); colormap(gray); colorbar; % 画像の表示

pause;

ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付

imagesc(ORG); colormap(gray); colorbar; % 画像の表示

pause;

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去

imagesc(IMG); colormap(gray); colorbar; % 画像の表示

pause;

IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去

imagesc(IMG); colormap(gray); colorbar; % 画像の表示

pause;

f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計

IMG = filter2(f,IMG,'same'); % フィルタの適用

imagesc(IMG); colormap(gray); colorbar; % 画像の表示

pause;


原画像には図1を使用する。

![kadai91](https://user-images.githubusercontent.com/35340807/34905079-decc46a6-f894-11e7-8823-681f76f1cb3c.PNG)

図1 原画像

![kadai92](https://user-images.githubusercontent.com/35340807/34905080-def46140-f894-11e7-9068-21d49b5f03c8.PNG)

図1を白黒濃淡画像に変更したものが図2である。そして図2にノイズを加えたノイズを加えた結果を図3に示す。

![kadai92](https://user-images.githubusercontent.com/35340807/34905080-def46140-f894-11e7-9068-21d49b5f03c8.PNG)

図2 白黒濃淡画像

![kadai93](https://user-images.githubusercontent.com/35340807/34905081-df1ac132-f894-11e7-8b79-4216dd2473e3.PNG)

図3 ノイズを追加した画像

図3のノイズを除去するために平滑化フィルタを適用したものが図4である。

![kadai93](https://user-images.githubusercontent.com/35340807/34905081-df1ac132-f894-11e7-8b79-4216dd2473e3.PNG)

図4 平滑化フィルタの適用

また、メディアンフィルタを適用した画像が図5である。

![kadai94](https://user-images.githubusercontent.com/35340807/34905082-df425238-f894-11e7-8ed4-5af736963c26.PNG)

図5 メディアンフィルタの適用

f=[0,-1,0;-1,5,-1;0,-1,0];として設計したフィルタを適用した画像が図6である。

![kadai95](https://user-images.githubusercontent.com/35340807/34905083-df69cb10-f894-11e7-85b7-7b5fb326d2b0.PNG)

図6 設計したフィルタの適用
