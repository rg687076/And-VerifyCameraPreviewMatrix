# And-VerifyCameraPreviewMatrix
TextureViewと、CameraPreviewのサイズが合ってないとき、TextureViewに、何の値のMatrixを設定すればいいのかを検証したコード。

- 画面は、縦画面固定。
``` AndroidManifest.xml
        <activity
            android:name=".MainActivity"
            android:screenOrientation="portrait"
            android:exported="true">
```
※回転する設定でも、問題ないはず(確認してないけど)。

- TextureViewのサイズは、画面サイズと同じ。
``` fragment_main.xml
    <TextureView
        android:id="@+id/tvw_preview"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:ignore="RelativeOverlap" />
```
※match_parentで、領域いっぱいになる様にしている。<br/>
※Pixel 4aだと、1080 x 2340[アスペクト比:2.166667]。

- カメラのサポートサイズ(s)
``` カメラのサポートサイズのリスト
4032 x 3024[アスペクト比1.333333]
4032 x 2268[アスペクト比1.777778]
4000 x 3000[アスペクト比1.333333]
4000 x 2000[アスペクト比2.000000]
3840 x 2160[アスペクト比1.777778]
3264 x 1836[アスペクト比1.777778]
3264 x 2448[アスペクト比1.333333]
3200 x 2400[アスペクト比1.333333]
2592 x 1944[アスペクト比1.333333]
2688 x 1512[アスペクト比1.777778]
2560 x 1280[アスペクト比2.000000]
2048 x 1536[アスペクト比1.333333]
1920 x 1440[アスペクト比1.333333]
1920 x 1080[アスペクト比1.777778]
1920 x 960[アスペクト比2.000000]
1600 x 1200[アスペクト比1.333333]
1440 x 1080[アスペクト比1.333333]
1280 x 960[アスペクト比1.333333]
1280 x 720[アスペクト比1.777778]
1024 x 768[アスペクト比1.333333]
800 x 600[アスペクト比1.333333]
720 x 480[アスペクト比1.500000]
640 x 360[アスペクト比1.777778]
640 x 480[アスペクト比1.333333]
352 x 288[アスペクト比1.222222]
320 x 240[アスペクト比1.333333]
176 x 144[アスペクト比1.222222]
```
