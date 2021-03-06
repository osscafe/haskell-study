# \#1 - 2014/3/29

## Haskell の練習場所

* ブラウザ: [Try Haskell](http://tryhaskell.org/)
* iPad/iPhone: [Raskell](https://itunes.apple.com/us/app/raskell/id783015132?mt=8)

## 今日のアジェンダ

第4章まで進める限り。...と思ったけど、第1章だけで時間切れ。

## 第1章

GHCiの使い方など、1.2あたりまでは day #0 で読了。

### 1.3 リスト入門

- `[]`で囲む
- `++`で連結可能
- **同じ型だけ**を要素にできる
- 要素数が違っても同じ型
- 先頭への追加は一瞬、末尾への追加は高負荷
- `[1,2,3,4,5]`は、`1:2:3:4:5:[]`の syntax sugar
- 要素へのアクセスは`!!`を使う: `[2,4,6,8,10]!!3`

#### リスト操作の関数

- `head [5,4,3,2,1]` → `5`
- `tail [5,4,3,2,1]` → `[4,3,2,1]`
- `last [5,4,3,2,1]` → `1`
- `init [5,4,3,2,1]` → `[5,4,3,2]`
- `length [5,4,3,2,1]` → `5`
- `null []` → `True`
- `take 3 [5,4,3,2,1]` → `[5,4,3]`
- `drop 3 [5,4,3,2,1]` → `[2,1]`
- `maximum`
- `mnimum`
- `sum`
- `product`
- `elem`

### 1.4 レンジでチン!

- `[1..100]`
- `['a'..'z']`
- `[2,4..20]`
- `[1..]` 無限リストが可能
- 無限リストを作るための関数: `cycle`, `repeat`

### 1.5 リスト内包表記

- 集合の内包的記法っぽい書き方
- `[x * 2 | x <- [1..]]`
- `[x * y | x <- [1..9], y <- [1..9]]`


### 1.6 タプル

- 要素の数を固定したい時に使う
- いろんな型を組み合わせることができる
- ペア : 2要素のタプルのこと
- トリプル : 3要素のタプルのこと
- zip関数を使うと、2つのリストからペアのリストを合成できる `zip [1..5] [3,6..]`

### 例題:直角三角形を見つける

3辺の長さを要素として持つタプルを考える。以下の条件を満たす直角三角形を、内包表記を使って見つけ出す。

- 3辺の長さはすべて整数
- 各辺の長さは10以下
- 周囲の長さは24
