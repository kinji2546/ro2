# mypkg
ロボットシステム学で使用したros2  

[![test](https://github.com/kinji2546/mypkg/actions/workflows/test.yml/badge.svg?branch=kada)](https://github.com/kinji2546/mypkg/actions/workflows/test.yml)



# リポジトリ内の主な内容一覧

## talker.py
* パブリッシャのノード.  
* モンテカルロ法を利用してπ（3．14）の近似値を求めて最終的にπ（3．14）に近くなる過程をトピック`/pi_setimate`を通じて送信する.

## talk_listen.launch.py
*  listener.py & talker.pyを同時に起動するもの.  

## listener.py
* サブスクライバのノード.  
* トピック`/pi_setimate`からメッセージを受け取り表示する.

# 実行手順  
## talkerとlistener
* `ros2 run`で実行する方法
```bash
端末1$ ros2 run mypkg talker
[INFO] [1702743288.403423539] [pi_calculator]: Publishing: "3.141496"
[INFO] [1702743288.467780713] [pi_calculator]: Publishing: "3.141496"
[INFO] [1702743288.522915170] [pi_calculator]: Publishing: "3.141497"
[INFO] [1702743288.562654672] [pi_calculator]: Publishing: "3.141498"
[INFO] [1702743288.610940721] [pi_calculator]: Publishing: "3.141500"
以下同じように出力される.
但し数値は変わる.プログラムを終わらせるときはコントロールキー＋C
```


端末2$ ros2 run mypkg listener
