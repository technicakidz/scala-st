# Scala Dowango text memo
## 2019/1/15
### Scalaの基本
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
