# Dwango's Scala text memo
## 2019/1/15
https://dwango.github.io/scala_text/basic.html#scala%E3%81%AE%E5%9F%BA%E6%9C%AC
### Scalaの基本
練習問題

```
scala> "0xff"
res0: String = 0xff

scala> 0xff
res1: Int = 255

scala> 1.00000000000000000001 == 1
res2: Boolean = true

scala> 1e308
res3: Double = 1.0E308

scala> 9223372036854775807L
res4: Long = 9223372036854775807

scala> 9223372036854775808L
<console>:1: error: integer number too large
       9223372036854775808L
       ^

scala> 9223372036854775807
<console>:1: error: integer number too large
       9223372036854775807
       ^

scala> 922337203685477580.7
res5: Double = 9.2233720368547763E17

scala> "\u3042"
res6: String = あ

scala> "\ud842\udf9f"
res7: String = 𠮟
```

- 演算子
`asInstanceOf[Int]`: キャスト`Double`→`Int`

練習問題
```
scala> 2147483647 + 1
res24: Int = -2147483648

scala> 9223372036854775807L + 1
res25: Long = -9223372036854775808

scala> 1e308 + 1
res26: Double = 1.0E308

scala> 1 + 0.0000000000000000001
res27: Double = 1.0

scala> 1 - 1
res28: Int = 0

scala> 1 - 0.1
res29: Double = 0.9

scala> 0.1 - 1
res30: Double = -0.9

scala> 0.1 - 0.1
res31: Double = 0.0

scala> 0.0000000000000000001 - 1
res32: Double = -1.0

scala> 0.1 * 0.1
res33: Double = 0.010000000000000002

scala> 20 * 0.1
res34: Double = 2.0

scala> 1 / 3
res35: Int = 0

scala> 1.0 / 3
res36: Double = 0.3333333333333333

scala> 1 / 3.0
res37: Double = 0.3333333333333333

scala> 3.0 / 3.0
res38: Double = 1.0

scala> 1.0 / 10 * 1 / 10
res39: Double = 0.01

scala> 1 / 10 * 1 / 10.0
res40: Double = 0.0
```

- 変数の基本
コンパイラが変数で与える値から推論することを(ローカル)型推論という.
そのため別の型として扱おうとするとエラーを吐く.
`val`を使った変数は再代入不可.
Scalaでは基本的に`val`のみを使用する(`var`を使った場合は値変更可能).

明示的に型宣言する場合
→ `（'val'|'var'）<変数名> : <型名> = <式>`
ex.)
```
scala> val x: Int = 3 * 3
x: Int = 9
```
練習問題
> Q. ¥3,950,000を年利率2.3％の単利で8か月間借り入れた場合の利息はいくらか（円未満切り捨て）

```
scala> val a: Int = 3950000
a: Int = 3950000

scala> (a*0.023) * 8/12
res41: Double = 60566.666666666664
```
(答えは`a.asInstanceOf[Int]`でキャスト)
A. 60566円


> Q. 定価¥1,980,000の商品を値引きして販売したところ、原価1.6％にあたる¥26,400の損失となった。割引額は定価の何パーセントであったか

```
scala> var x: Double = 26400 / 0.016
x: Double = 1650000.0

scala> x = x - 26400
x: Double = 1623600.0

scala> x = 1980000 - x
x: Double = 356400.0

scala> x = x / 1980000
x: Double = 0.18
```
A.18%

## コンパイル

```
sandbox
├── HelloWorld.scala
├── User.scala
└── build.sbt
```
 
 - `Hello.scala`の実行
 
 ```
 sbt:scala-st> run
 ...
 [info] Running HelloWorld
Hello World [success] Total time: 30 s, completed 2019/01/16 13:15:13
 ```
 
 - `User.scala`の実行
 
 ```
 scala> val u = new User("Opt", 11)
u: User = User@1329534

scala> User.printUser(u)
Opt 11
 ```
 
