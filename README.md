# NonMouse2
指で動かす実体のないマウス    
![nonmouse twi drug-アニメーションイメージ（大）](https://user-images.githubusercontent.com/22733958/121180947-7054ef80-c89c-11eb-9c7a-42a9e1f3f02a.gif)  
![nonmouse twi21 oe-アニメーションイメージ（大）](https://user-images.githubusercontent.com/22733958/121180967-75b23a00-c89c-11eb-82fa-4f5d9abda320.gif)  



Webカメラで自分の手元を写すことで、あたかも実体のないマウスがあるかのように見えるPythonスクリプトです。(感度調整なしのver.1は[こちら](https://github.com/takeyamayuki/NonMouse))  
動作状況は[Youtube](https://youtu.be/ufvOJUTCF8M)にも公開しています。

# Installation
### Install Mediapipe  
[公式ドキュメント](https://google.github.io/mediapipe/getting_started/install.html#installing-on-macos)に従って、Mediapipeのインストール


### Install pynput
```sh:Install
% pip install pynput  
```
macの場合、システム環境設定からセキリュティとプライバシーのアクセシビリティの項目にターミナルやVScodeなど、実行する場所を追加する必要があります。

# Usage
### run
NonMouseフォルダーをダウンロード、解凍する。
以下のスクリプトを実行。または、launch.scptを実行
```sh
% cd ~/.../NonMouse2-main
% python3 app.py
```

### args
* `--divice X`でカメラを複数搭載している場合、引数でカメラを選択できます(デフォルト0で0,1,2...が選択可能)  
```sh
% python3 app.py --device 0
```
* `--direciton X`で指の動かす向きに対するマウスカーソルの動く向きを指定できます(デフォルト0で0,1が選択可能)  
webカメラを下に向けて使用する場合：0     
ラップトップ付属のカメラを使用する場合：１    
```sh
% python3 app.py --direction 0
```
* `--distance X`でタッチ距離を定義（遠いほど小さく、近いほど大きい値にする）(デフォルト65で、整数で選択可能)  
[目安]
    * webカメラと手の距離が50cmのとき、65
    * webカメラと手の距離が110cmのとき、50
```sh
% python3 app.py --distance 50
```
* `--kando X`でマウス感度を定義（大きくしすぎると小刻みに震えるので大きくしすぎないこと）(デフォルト1.5で、小数で選択可能)  
[目安]
    * webカメラと手の距離が50のとき、1.5
    * webカメラと手の距離が110のとき、5
```sh
% python3 app.py --kando 5
```
これらの引数をまとめて指定できるようにシェルスクリプトにまとめました。  
* launch-frcam.shはラップトップのwebカメラを使用するためのスクリプト  
* launch-ceiling.shは天井に取り付けたwebカメラを使用するためのスクリプト

### hands movement
* 人差し指の先端がマウスカーソルに対応。

* 人指し指の指先と中指の指先をつけると、マウスカーソルの動きが止まる。

* 親指の指先と人差し指の第２関節をくっつけると左クリック、離すと左クリックのリリース

* スクロールと右クリックについては未実装です 

### quit
Ctrl+CかEscを押してください
