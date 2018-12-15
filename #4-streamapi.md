# 今こそStream API入門

## メモ

### Stream
- Streamはイテレータ
  - 簡単に言うとループ
  - 2種類
    - 外部イテレータ
      - 繰り返しの処理を自分で書く
      - 繰り返し制御+処理
      - 複雑
      - 記述力高い
    - 内部イテレータ
      - 処理
      - シンプル
- ラムダ式
  - 関数とクラスの中間の位置付け
  - 関数のように記述しクラスのように振る舞う

### 結局Streamとは
- Stream
  - 流れてくるデータを加工(処理)して最終的にまとめる仕組み

### ラムダ式
- 引数と返り値だけを決めた処理の記述法
  ```
  (引数) -> {
    何らかの処理
    return 返り値;
  }
  ```

#### よく使われるラムダ式
 - 1引数 返り値あり Function<T,R>
 - 1引数 返り値boolean

#### ラムダ式の記述

```
(String s) -> {return s.length();}

引数は省略可能
(s) -> {return s.length();}

１行の処理なら{return} 省略可能
(s) -> s.length();

1引数なら()を省略可能
s -> s.length();

```

#### 主な中間処理(中間操作)
- データを取捨選択
  - filter
  - dropWhile 1引数　返り値boolean
  - takeWhile
- データ変換
  - map 1引数 返り値あり
  - flatMap 1引数 返り値Stream

#### 主なまとめ処理(終端操作)
- 探す
  - findFirst/findAny ラムダ式なし
  - anyMatch/allMatch/noneMatch  1引数 返り値boolean
- まとめる
  - collect Collectors staticメソッド
  - toList ラムダ式なし
  - groupingBy 1引数 返り値あり
- 逐次処理
  - forEach 1引数 返り値なし

#### Streamで処理するには
- やりたいことをデータの加工という観点で組み直す
- 慣れないうちはfor文


