## 数组

```go
var a = [n]int{1,2,3}
var a = [...]int{1,2}
var a [10] int

package main
import "fmt"
func main(){
    var n [10] int
    var i,j int
    
    for i = 0; i < 10; i++{
        n[i] = i + 100;
    }
    for j = 0; j < 10; j++){
        fmt.Printf("sfjkls[%d] = %d\n",j,n[j]);
    }
}
```

go中，数组是值类型

```go
func changeLocal(num [5]int) {  
    num[0] = 55
    fmt.Println("inside function ", num)

}
作为参数时，[5]int
```



## 切片

Go语言切片是对数组的抽象

```
s := []int{1,2,3}
s := a[s:e]
s := a[s:]
s := a[:e]
s := make([]int,len,cap)
```

切片的引用类型

```go
func printSlice(x []int){
   fmt.Printf("len=%d cap=%d slice=%v\n",len(x),cap(x),x)
}
```

```go

   /* 打印子切片从索引1(包含) 到索引4(不包含)*/
   fmt.Println("numbers[1:4] ==", numbers[1:4])

   /* 默认下限为 0*/
   fmt.Println("numbers[:3] ==", numbers[:3])

   /* 默认上限为 len(s)*/
   fmt.Println("numbers[4:] ==", numbers[4:])

   numbers1 := make([]int,0,5)
   printSlice(numbers1)

   /* 打印子切片从索引  0(包含) 到索引 2(不包含) */
   number2 := numbers[:2]
   printSlice(number2)
```



##### 函数

###### len(x)



###### cap(x)



###### append(x)

append返回扩容后的引用

###### copy(x，y)

把y的内容复制到x

```go
func a(){
    var numbers []int
    
    numbers = append(numbers,0)     
    
    numbers = append(numbers,1,2,3,4)
    
    numbers1 := make([]int,len(numbers),(cap(numbers))*2)
    
    copy(numbers1,numbers)
    
    
}
```



## 结构体

```go
type Books struct {
   title string
   author string
   subject string
   book_id int
}

// 创建一个新的结构体
    fmt.Println(Books{"Go 语言", "www.runoob.com", "Go 语言教程", 6495407})

    // 也可以使用 key => value 格式
    fmt.Println(Books{title: "Go 语言", author: "www.runoob.com", subject: "Go 语言教程", book_id: 6495407})

    // 忽略的字段为 0 或 空
   fmt.Println(Books{title: "Go 语言", author: "www.runoob.com"})
```

