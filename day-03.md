## 第3章 関数の構文

### 3.1 パターンマッチ
* 上から順にマッチする
* この場合、３は一番下にたどり着かない
* 一番最後に入力すべてに合致するパタンを入れておいた方がよい

```haskell
lucky :: Int -> String
lucky 7 = "LUCKY NUMBER SEVEN!!"
lucky x	= "Sorry, you're out of luck, pal!"
lucky 3 = "LUCKY NUMBER THREE!"
```

* _は予約語
* _の代わりに(x, x, z)とすると構文エラーになる

```haskell
third :: (a, b,	c) -> c
third (_, _, z) = z
```

* asパタン
* all@の部分がx:xsすべてを含む

```haskell
firstLetter :: String -> String
firstLetter "" = "Empty string, whoops!"
firstLetter all@(x:xs) = "The first letter of " ++ all ++ " is " ++ [x]
```

### 3.2 場合分けして、きっちりガード!

* 引数の構造はパターンマッチ、値はガードで分ける
* otherwiseはワイルドカード、なくてもエラーにならない
* すべてのガードにマッチししなかった場合、次のパターンマッチに移る
* いずれのパターンマッチにも合致しなかった場合エラーになる

```haskell
bmiTell :: Double -> String
bmiTell bmi
  | bmi <= 18.5 = "You' re underweight, you emo, you!"
  | bmi <= 25.0 = "You' re supposedly normal.\
                   \ Pffft, I bet you're ugly!"
  | bmi <= 30.0 = "You're fat! Lose some wieght, fatty!"
  | otherwise   = "You're a whale, congraturations!"
```

### 3.3 where?!

* 関数内でだけ、変数や関数を定義する
* where内でパターンマッチが可能

```haskell
bmiTell'' :: Double -> Double -> String
bmiTell'' weight height
  | bmi <= skinny = "You're underweight, you emo, you!"
  | bmi <= normal = "You're supposedly normal.\
                   \ Pffft, I bet you're ugly!"
  | bmi <= fat    = "You're fat! Lose some wieght, fatty!"
  | otherwise     = "You're a whale, congraturations!"
  where
     bmi = weight / height ^ 2
     (skinny, normal, fat) = (18.5, 25.0, 30.0)
```

* 異なる関数から利用するにはグローバルに定義する必要がある
* ~~where関係無くね?~~

```haskell
niceGreeting :: String
niceGreeting = "Hello! So very nice to see you,"
```

### 3.4 let It Be

### 3.5 case式
