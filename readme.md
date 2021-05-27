# 本質的なコードを書けばいい
- 一回書いたら以下の全てに出力したい
  - C++,Rust (GCなし.)
  - C#,Go,Kotlin,Java,Nim,Haskell (GCあり)
  - Python,Ruby,Nodejs,PHP,Perl5 (eval可能. ループが遅い)
  - 言語のバージョンはいくら？今の最新の安定版でよさそう
  - その言語として自然なコードを吐きたい
    ループが遅くても問題なくないか / GCがなければコピーを返せばいい
    クリティカルなところは書かない(domain-specific性を帯びている)
  - 副作用のある(IOなど)コードを書くことは多いので、esolangは難しい
  - 一番制約がきついのはRustのはず
    Genericが無いのはGoだが普通の型を書けばよさそう
- domain-specific なコードやループの速度やライブラリの管理か
- domain-specific なライブラリを別のガワから呼べる？
- 競技プログラミングでいい感じにしたいな
- パーサを作るのも実はそんなにむずかしくない(LR2でも)
- ニーズ？ 以下を解決
  - いっぱいある言語をどう書くかわかりにくい問題
  - どういうコードはdomain-specificな箇所がないか分かりにくい問題
  - C言語バインディングを一つ書けば全部吐けるのはうれしい
  - 別の言語のライブラリを叩く際の中間言語にできる
    - Python ならPathを指定して読み込んでclassを解析して...となる
    - C++以外はパースできそう
