# \#2 - 2014/4/5

## 第2章

### 2.1 明示的な型宣言

Haskellの型推論に任せず、明示的に関数の型を宣言する。次の関数は、戻り値の精度が違う。

```hs
circumference :: Float -> Float
circumference r = 2 * pi * r

circumference' :: Double -> Double
circumference' r = 2 * pi * r
```

関数については、一般に型宣言をすることが望ましいとされる。値についても、非決定な場合は、明示する必要がある。

```hs
read "1"
```

は型が曖昧なのでエラー。型宣言すればOK!

```hs
read "1" :: Int
```


### 2.2 一般的なHaskellの型

### 2.3 型変数

```hs
[a] -> a
[a,a,a] -> [a,a]
```

みたいなやつ。

### 2.4 型クラス 初級講座

#### Eq型クラス

2つの要素について、同じか、違うかが定義されている型(のクラス)

#### Ord型クラス

2つの要素について、どちらが大きいか(小さいか)定義されている型(のクラス)

伊藤さんの名言「性別はOrd型クラスではない」

#### Enum型クラス

次の要素が定義されている型(のクラス)

```hs
succ 0
succ 'a'
```

↑それぞれ、1, 'b'を返す。

#### Num型クラス

- *Num*
  - *Integral*
    - Int
    - Integer
  - *Floating*
    - Float
    - Double
