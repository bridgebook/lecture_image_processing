# 課題4　画像のヒストグラム

画素の濃度ヒストグラムを生成せよ．

以下はソースコードである。

clear; % 変数のオールクリア


ORG=imread('C:\Users\bridgebook\Pictures\landmark.jpg'); % 原画像の入力

ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換

imagesc(ORG); colormap(gray); colorbar;

pause;

imhist(ORG); % ヒストグラムの表示


原画像には図1を用いる。

![kadai11](https://user-images.githubusercontent.com/35340807/34903547-2190a0fe-f877-11e7-8a4c-f1ff2ba06166.png)

図1 原画像

原画像を白黒濃淡画像へ変換

![kadai41](https://user-images.githubusercontent.com/35340807/34903617-a754cee4-f878-11e7-8f6e-7d92b8f81978.PNG)

図2 白黒濃淡画像

ヒストグラムは図3のように表示された。

![kadai42](https://user-images.githubusercontent.com/35340807/34903616-a72bb4a0-f878-11e7-889d-db5db6d432b5.PNG)

図3 ヒストグラム
