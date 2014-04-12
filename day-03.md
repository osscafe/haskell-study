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

### 3.3 where?!

### 3.4 let It Be

### 3.5 case式
