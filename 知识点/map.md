## map



##### 创建map

```go
ages := make(map[string]int)

ages := map[string]int{
    "alice": 32,
    "ccc":12
}

=

ages := make(map[string]int)
ages["alice"] = 31
ages["charlie"] = 34
```

#### 删除



```go
/*删除元素*/ delete(countryCapitalMap, "France")  //key
```

**所有这些操作是安全的，即使这些元素不在map中也没有关系；如果一个查找失败将返回value类型对应的零值，**



#### 真没有和假没有



```go
if age, ok := ages["bob"]; !ok { /* ... */ }
在这种场景下，map的下标语法将产生两个值；第二个是一个布尔值，用于报告元素是否真的存在。布尔变量一般命名为ok，特别适合马上用于if条件判断部分。
```



#### 实例：



```go
var graph = make(map[string]map[string]bool)

func addEdge(from, to string){
    edges := graph[from]
    if edges == nil{
        edges = make(map[string]bool)
        graph[from] = edges
    }
    edges[to] = true
}

func hasEdge(from ,to string)bool{
    return graph[from][to]
}
```

