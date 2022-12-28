# このパッケージについて

 * 以下の内容は大学の授業で制作したものです.

 * 扱い方は下記に示してあります.

![test](https://github.com/ryo0806/mypkg/actions/workflows/test.yml/badge.svg)
 * テストプログラム`.github/workfolw/test.yml`が通過していることを示しています.

# 内容について

 * .github/workflows/test.yml
	テストを通過しているか確認するプログラムです.

 * setup.py
	`launch/talk_listen.launch.py`でノードの短縮に用いているファイルです.

 * test/test.bash
	`talker.py`と`listener.py`が通信しているのかをテストするプログラムです.

 * package.xml
	モジュールの登録に用いたファイルです.

 * launch/talk_listen.launch.py
	`talker.py`と`listener`のノードを同時に実行できるノートです.
	* 以下使用方法
	`$ ros2 launch mypkg talk_listen.launch`
	 終了するには`Ctrl+c`で終了

 * mypkg/talker.py
	カウントを行い, `talker`というトピック名でトピック通信を行うノード
	* 以下実行方法
	`$ ros2 run mypkg talker`を実行
	__この時ここでは何も出力されない__
	ここから`listener.py`を実行する.

 * mypkg/listener.py
	`talker.py`から`listener`というトピック名でトピック通信し, 表示するノード
	このノードは`talker.py`を実行しているターミナルではなく, 別のターミナル上で実行を行ってください.
	* 以下実行方法
	`$ ros2 run mypkg listener`
	終了するには`ctrl+c`で終了

# パッケージの使用方法

 1.今回はubuntu22.04.1 LTS を用いてパッケージのコピーを行います.
	この時ros2のversionがhumbleなので対応しているか注意

 2.まずはコピーする場所のディレクトリを制作します. ディレクトリを制作しない場合は現在開いている場所にクローンしたリポジトリが作成されます.

 3.gitubのアカウントがある場合は`$ git clone git@github.com:ryo0806/mypkg.git`を実行.アカウントがない場合は`git clone https://github.com/ryo0806/mypkg.git`を実行

 4.実際にパッケージを用いるためにビルドを行う.

 5.コピーしたディレクトリの一番上で`$ colcon build`を実行

 6.パッケージを利用可能にするために以下を実行
	`$ source ~/mypkg/install/setup.bash`
	`$ source ~/mypkg/install/local_setup.bash`

 7.以下のコマンドを入力し, `mypkg`が赤く表示されれば成功です.
	`$ source ~/.bashrc`
	`$ ros2 pkg list | grep mypkg`
	`mypkg` 

 8.プログラムを実行する.

# 必要なソフトウェア

 * ROS2 humble(Ubuntu22.04用のROS2 vertion)

# 動作確認済み環境

 * ubuntu 22.04.1 LTS

# 権限について

 * このソフトウェアパッケージは, 3条項BSDライセンスの下, 再頒布および使用が許可されます.
 * 詳細は LICENSE をご覧ください.

 * © 2022 Ryo Yanagisawa
