# Retreat 構想

- Nimのサブセット言語で、一度書くと主要な言語にそのまま変換できる言語。
  - バージョンは今の最新の安定版
  - いっぱいある言語をどう書くかわかりにくい問題も簡単に解決する.
    - ただRetreatを書いて各々変換すればいいだけなので
- 主要な言語の共通部分に関するコードのみを記述できる
  - 移植性の高いコードが記述できる。
  - 特定の言語に依存したコードを書いてしまう心配がない。
    - 逆に言語固有の問題を把握することも可能。
  - 文法は簡素。最低限必要なことが処理できる。
  - 言語ごとの特性(loopが遅い, GCがない など) を意識するコード向けではない
  - 多くのesolangとの互換性も求める予定はない。
- Retreatから任意の言語のライブラリを叩ける。中間言語。
  - Retreatを介することで任意の言語から任意の言語を呼ぶコードが書ける
  - C言語バインディングを一つ書けば全部吐けるのはうれしい
  - Python ならPathを指定して読み込んでclassを解析して...となる
  - C++以外はパースできそう
  - ex: Python から Ruby の Nokogiri を呼ぶ
    1. Ruby の Gem でインストールし、そのパスを Retreat に指定する
    2. Retreat から Nokogiri のクラスが呼べる
    3. Python から Retreat 経由でNokogiriのクラスが呼べる

## 文法

- パーサを作るのも実はそんなにむずかしくない(LR2でも)
- [文法](./grammar/readme.md)
- 一番制約がきついのはRustのはず
- Genericが無いのはGoだが普通の型を書けばよさそう
