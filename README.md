# 概要
- 最近作っているPytorchでNNUEの学習ができるプログラム(nnue-pytorchとは別物)のテストとして制作したHáo( https://github.com/nodchip/tanuki-/releases/tag/tanuki-.halfkp_256x2-32-32.2023-05-08 )をベースにした評価関数
- 出来はイマイチだが、特に何かに使う予定もなくもったいないので公開する事にした
- 3つともすべて標準NNUE( halfkp_256x2-32-32 )で、やねうら王( https://github.com/yaneurao/YaneuraOu )の評価関数として利用できる( 使い方はやねうら王の公式wiki( https://github.com/yaneurao/YaneuraOu/wiki )で調べてください )
- 名前の由来はHáo + 某ゲームに出てくる災いの剣

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

# ライセンス
- 学習元のHáoがGPL3.0っぽいのでとりあえずGPL3.0としています
