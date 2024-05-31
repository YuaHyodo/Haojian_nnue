# 概要
- 最近作っているPytorchでNNUEの学習ができるプログラム(nnue-pytorchとは別物 / https://github.com/YuaHyodo/Ari_Shogi_NNUE_train )のテストとして制作したHáo( https://github.com/nodchip/tanuki-/releases/tag/tanuki-.halfkp_256x2-32-32.2023-05-08 )をベースにした標準NNUE( halfkp_256x2-32-32 )タイプの評価関数。やねうら王( https://github.com/yaneurao/YaneuraOu )の評価関数として利用できる( 使い方はやねうら王の公式wiki( https://github.com/yaneurao/YaneuraOu/wiki )で調べてください )
- 出来はイマイチだが、特に何かに使う予定もなくもったいないので公開する事にした
- 名前の由来はHáo + 某ゲームに出てくる災いの剣。名前には「火力( 精度 )と素早さ( 動作速度 )を兼ね備え、強運を発揮すれば圧倒的に不利な相手にも勝てる無限の可能性を秘めた評価関数になってほしい」という願いが込められている。(後付け)

# Haojian_231225
- floodgateの棋譜から用意したデータでHáoを追加学習したもの
- Háoと同じか、ほんの少し弱いくらいの強さらしい

# Haojian_240101
- 第31回世界コンピュータ将棋選手権のdlshogi_with_GCTの公開教師データ( https://tadaoyamaoka.hatenablog.com/entry/2021/05/06/223701 )でHáoをファインチューニングしたもの
- リソースの都合で学習を途中で打ち切っている
- 強さの計測はできていない( 代わりに計測してくれる人を募集中 )

# HaojianQPD_231227
- Qhapaq Pretty Daabiの公開されている教師データ( https://qhapaq.hatenablog.com/entry/2021/11/23/220251 | https://github.com/qhapaq-49/qhapaq-bin/releases/tag/dataset )を利用してHáoをファインチューニングし飛車を振らせようとしたもの
- リソースの都合で途中で学習を打ち切っている
- Háoよりレート150くらい弱いらしい
- こいつが飛車を振っているのは見た事がない

# HaojianQPD_231230
- Qhapaq Pretty Daabiの公開されている教師データ( https://qhapaq.hatenablog.com/entry/2021/11/23/220251 | https://github.com/qhapaq-49/qhapaq-bin/releases/tag/dataset )を利用してHáoをファインチューニングし飛車を振らせようとしたもの
- リソースの都合で途中で学習を打ち切っている
- 強さの計測は一切できてない( 代わりに計測してくれる人を募集中 )
- テスト対局で振り飛車っぽいこと( 自分は将棋全然わからないのでこれが本当に振り飛車なのかは分からん )をしたので、ここに置いてあるもののなかでは飛車を振る可能性が最も高い評価関数だと思う
  ![スクリーンショット 2023-12-31 131419](https://github.com/YuaHyodo/Haojian_nnue/assets/66828980/36d18e1f-3497-4636-b55b-de0b5077a9a2)

# HaojianQPD_240320
- Qhapaq Pretty Daabiの公開されている教師データ( https://qhapaq.hatenablog.com/entry/2021/11/23/220251 | https://github.com/qhapaq-49/qhapaq-bin/releases/tag/dataset )を利用してHáoを追加学習した評価関数。学習の際のテストデータには、GCTの公開テストデータ( 参考: https://tadaoyamaoka.hatenablog.com/entry/2020/11/26/203912 )を利用している。
- 公開した学習部( https://github.com/YuaHyodo/Ari_Shogi_NNUE_train )のサンプルなので、学習ログも公開している( 学習ログは、学習データのディレクトリなどを一部人力で編集している )
- 自分の残したメモによると、FV_SCALEは11が1番強いらしく、その設定だとFV_SCALEを20にしたHáoに対し、1手1000ms、たややん互角局面集24手目～で、「1000戦488勝8分(レート-5.6)」という成績らしい。が、そんなに強くはなさそうな感じなので計測ミスしている気がする。 
- i5-13400F(4スレッド / Ponder無し / 定跡なし)でfloodgateに放流中( http://wdoor.c.u-tokyo.ac.jp/shogi/view/show-player.cgi?event=LATEST&filter=floodgate&show_self_play=1&user=HaojianQPD_240321_4t )。

# HB_Haojian_240517
## 概要
- Qhapaq Pretty Daabiの公開されている教師データ( https://qhapaq.hatenablog.com/entry/2021/11/23/220251 | https://github.com/qhapaq-49/qhapaq-bin/releases/tag/dataset )とfloodgateの2018～2023年の棋譜から「高レート帯で振り飛車が勝った棋譜」のみを抽出して作ったデータで、Háoを追加学習した評価関数。学習の際のテストデータには、GCTの公開テストデータ( 参考: https://tadaoyamaoka.hatenablog.com/entry/2020/11/26/203912 )を利用している。
- 学習ログも公開している( HB_Haojian_240517_train_log.txt / 学習データのディレクトリ名の余分な部分などは人力で削っている )。ちなみにこの評価関数はepoch=4の終了時の出力。
- floodgateに放流していた、HB_Haojian_test2( http://wdoor.c.u-tokyo.ac.jp/shogi/view/show-player.cgi?event=LATEST&filter=floodgate&show_self_play=1&user=HB_Haojian_test2%2B626ae87f72bb4da5f09f1bdb82c8c7c9 )、HB_Haojian_test2_with_HNW33book( http://wdoor.c.u-tokyo.ac.jp/shogi/view/show-player.cgi?event=LATEST&filter=floodgate&show_self_play=1&user=HB_Haojian_test2_with_HNW33book%2B45d07b00b0188a892509950ff919e14e )、HB_Haojian_240517_i5-13400F_8t( http://wdoor.c.u-tokyo.ac.jp/shogi/view/show-player.cgi?event=LATEST&filter=floodgate&show_self_play=1&user=HB_Haojian_240517_i5-13400F_8t%2Bfecf4d772f647e978c7daa4b3b446ada )、HB_Haojian_240517_i5-13400F8t_2( http://wdoor.c.u-tokyo.ac.jp/shogi/view/show-player.cgi?event=LATEST&filter=floodgate&show_self_play=1&user=HB_Haojian_240517_i5-13400F8t_2%2B8cee471e62c858d9ecf4b37aca73c677 )の中身。CPUは全部同じi5-13400F, 前の2つは4スレッド+Ponderなしで後ろの2つは8スレッド+Ponderあり。with_HNW33bookは、HoneyWaffleの公開されている定跡( https://github.com/32hiko/HoneyWaffleBook/releases/tag/wcsc33 )を搭載していて、それ以外は定跡を載せていない。
- 名前のHBはHuriBisyaの略
- FV_SCALEの最適値は不明なので、基本的には16で対局させている。floodgateのHB_Haojian_240517_i5-13400F_8tは連続対局で求めた別の値(12)を使っていたが、弱かったので16に戻した。
## 計測
- HB_Haojian_240517のFV_SCALEは16
- CPUはi5-13400F
- 計測にはTanukiColiseum( https://github.com/nodchip/TanukiColiseum )を利用
### たややん互角局面集24手目～, 2スレッド, 1手1000ms, 1000戦
- 対Háo(FV_SCALE=20): 勝ち502(50.8% R5.6 +-21.6) 先手勝ち258(26.1%) 後手勝ち244(24.7%) 引き分け12
- 対BLOSSOM(FV_SCALE=24): 勝ち560(56.4% R44.4 +-21.7) 先手勝ち293(29.5%) 後手勝ち267(26.9%) 引き分け7
- 対Lí(FV_SCALE=20): 勝ち535(54.4% R30.0 +-21.6) 先手勝ち278(28.3%) 後手勝ち257(26.1%) 引き分け16

# ライセンス
- 学習元のHáoがGPL3.0っぽいのでとりあえずGPL3.0としています
