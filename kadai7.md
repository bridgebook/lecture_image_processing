# 課題7　ダイナミックレンジの拡大
画素のダイナミックレンジを0から255に変更する。

以下はソースコードである。

ORG = imread('C:\Users\bridgebook\Pictures\landmark.jpg'); % 画像の読み込み

ORG = rgb2gray(ORG); % 白黒濃淡画像に変換

imagesc(ORG); colormap(gray); colorbar; % 画像の表示

pause;

imhist(ORG); % 濃度ヒストグラムを生成、表示

pause;


ORG = double(ORG);

mn = min(ORG(:)); % 濃度値の最小値を算出

mx = max(ORG(:)); % 濃度値の最大値を算出

ORG = (ORG-mn)/(mx-mn)*255;

imagesc(ORG); colormap(gray); colorbar; % 画像の表示

pause;


ORG = uint8(ORG); % この行について考察せよ

imhist(ORG); % 濃度ヒストグラムを生成、表示

mn = min(ORG(:)); % 濃度値の最小値を算出

mx = max(ORG(:)); % 濃度値の最大値を算出

pause;


原画像には図1を用いる。

![kadai11](https://user-images.githubusercontent.com/35340807/34903547-2190a0fe-f877-11e7-8a4c-f1ff2ba06166.png)

図1 原画像

白黒濃淡画像は図2のようになり、濃度ヒストグラムは図3のように生成された。

![kadai71](https://user-images.githubusercontent.com/35340807/34904178-c14db1b6-f883-11e7-91d2-cc01ab0bc29f.PNG)

図2 白黒濃淡画像

![kadai72](https://user-images.githubusercontent.com/35340807/34904179-c17523f4-f883-11e7-8f89-dead9db4a9f0.PNG)

図3 濃度ヒストグラム

図3は図2のダイナミックレンジを拡大した画像であり、図4はそのヒストグラムである。

![kadai73](https://user-images.githubusercontent.com/35340807/34904180-c19e2268-f883-11e7-96b7-ad11454bd14c.PNG)

図3 ダイナミックレンジを拡大

![kadai74](https://user-images.githubusercontent.com/35340807/34904182-c1c5e960-f883-11e7-9687-08cbb095a00c.PNG)

図4 図3のヒストグラム

行 ORG = uint8(ORG);の考察
データがdouble の場合、double イメージが MATLABで解釈される方法に対応する範囲 [0 1] を返す。
しかし、クラスがunit8の場合はダイナミック レンジは [0 255]を返す。
実際に、初期の濃度と拡大後の濃度は図6,図7のように変化している。

![kadai75](https://user-images.githubusercontent.com/35340807/34904730-39ee2bfe-f88f-11e7-8fed-0b66717727d1.PNG)

図6 初期の濃度

![kadai76](https://user-images.githubusercontent.com/35340807/34904729-39af4d26-f88f-11e7-8293-ea14a9d2dfb6.PNG)

図7 ダイナミックレンジ拡大後の濃度
