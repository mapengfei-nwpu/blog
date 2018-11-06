[返回首页](../index.html)

## scala中的隐式变换

scala编译器会自动寻找命名空间中的隐式转换函数，把变量转换成需要的类型。隐式转换函数不是以函数名区分的，而是以函数类型区分的。同一个命名空间中不能有两个相同类型的隐式转换函数。

```scala
//隐式函数的使用
class IntWritable(_value:Int){
    def value = _value
    def +(that:Intwritable):IntWritable = {
        new IntWritable(that.value + value)
    }
}
implicit def intToWritable(int:Int) = new IntWritable(int)
val result = new IntWritable(10) + 10
```

implicit关键词还可以用来定义隐式参数，传入隐式变量。隐式变量和隐式转换函数一样，以变量类型区分，与变量名无关，每种类型的变量只能定义一个。

```scala
def person(implicit name: String) = name
implicit val p ="pengfei"
person       //调用时不用输入参数
```

隐式类

```c
//当一个变量的类型和隐式类的构造函数的参数类型匹配时，这个变量可以调用隐式类的函数。
```



隐式类

