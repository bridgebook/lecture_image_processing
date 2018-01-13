# 課題１

原画像を読み込み，表示した結果を図１に示す。

![kadai11](https://user-images.githubusercontent.com/35340807/34880905-4321aa60-f7f5-11e7-8aea-f775f7e11f8f.png)

図1 原画像

原画像を1/2サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大する。
1/2サンプリングの結果を図２に示す。

![kadai12](https://user-images.githubusercontent.com/35340807/34881249-5dec0bc8-f7f6-11e7-992d-92075734a55b.png)

図2 1/2サンプリング

同様に原画像を1/4サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大する。
1/4サンプリングの結果を図３に示す。

![kadai13](https://user-images.githubusercontent.com/35340807/34881238-5c34fa60-f7f6-11e7-920d-af161800956d.png)

図3 1/4サンプリング

1/8から1/32サンプリングは，

IMG = imresize(ORG,0.5); % 画像の縮小
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

を繰り返す．サンプリングの結果を図４～６に示す。

![kadai14](https://user-images.githubusercontent.com/35340807/34881239-5c62efba-f7f6-11e7-8e31-747598d0065f.png)

図4 1/8サンプリング

![kadai15](https://user-images.githubusercontent.com/35340807/34881240-5c895e48-f7f6-11e7-9151-c69956ac2260.png)

図5 1/16サンプリング

![kadai16](https://user-images.githubusercontent.com/35340807/34881241-5cb0a200-f7f6-11e7-8445-8c2dfd69213d.png)

図6 1/32サンプリング

サンプリング幅が大きくなると，モザイク状のサンプリング歪みが発生し、画像が粗くなっていく。
