# 課題8 ラベリング

二値化された画像の連結成分にラベルをつける。
原画像には図1を用いる。

![kadai11](https://user-images.githubusercontent.com/35340807/34903547-2190a0fe-f877-11e7-8a4c-f1ff2ba06166.png)

図1 原画像

原画像を白黒濃淡画像に変換したものが図2である。

![kadai81](https://user-images.githubusercontent.com/35340807/34904853-439f7fac-f891-11e7-9286-50d15f32e09b.PNG)

図2 白黒濃淡画像

図2を閾値を輝度128として二値化した画像が図3である。

![kadai82](https://user-images.githubusercontent.com/35340807/34904854-43c55948-f891-11e7-995d-dfd3b7d93bbd.PNG)

図3 二値化した画像

図3をラベリングした画像が図4である。

![kadai83](https://user-images.githubusercontent.com/35340807/34904855-43eafb94-f891-11e7-921f-fe96d38ec6d4.PNG)

図4　ラベリング後の画像

ラベリングは二値化された画像の連続している部分を同じラベルにする処理である。そのため図4のような画像が生成される。
