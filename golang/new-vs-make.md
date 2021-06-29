# new vs make

## new

- 回傳 `pointer`
- 會初始對應的 `zero value` （方便的地方，可以快速初始化）

  int → `0`

  string → `""`

  slice, map, channel → `nil`

```go
package main

import "fmt"

func main() {
	// 可以快速的初始化，但無法客製化
	student := new(Student)           // pointer
	fmt.Printf("%#v\n", student)      // &main.Student{Name:"", Age:0}
	fmt.Printf("%#v\n", student.Name) // ""
	fmt.Println(student.Age)          // 0
}

// 比較常這樣做
func (s *Student) New(name string, age int) *Student {
	return &Student{
		Name: name,
		Age:  age,
	}
}

type Student struct {
	Name string
	Age  int
}
```

## make

- 回傳 type
- 通常用於 `slice`，`map`，`channel`

## Reference

[Go 語言內 new 跟 make 使用時機](https://blog.wu-boy.com/2021/06/what-is-different-between-new-and-make-in-golang/)
