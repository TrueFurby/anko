我是光年实验室高级招聘经理。
我在github上访问了你的开源项目，你的代码超赞。你最近有没有在看工作机会，我们在招软件开发工程师，拉钩和BOSS等招聘网站也发布了相关岗位，有公司和职位的详细信息。
我们公司在杭州，业务主要做流量增长，是很多大型互联网公司的流量顾问。公司弹性工作制，福利齐全，发展潜力大，良好的办公环境和学习氛围。
公司官网是http://www.gnlab.com,公司地址是杭州市西湖区古墩路紫金广场B座，若你感兴趣，欢迎与我联系，
电话是0571-88839161，手机号：18668131388，微信号：echo 'bGhsaGxoMTEyNAo='|base64 -D ,静待佳音。如有打扰，还请见谅，祝生活愉快工作顺利。

# anko

[![Build Status](https://travis-ci.org/mattn/anko.png?branch=master)](https://travis-ci.org/mattn/anko)
[![GoDoc](https://godoc.org/github.com/mattn/anko/vm?status.svg)](https://godoc.org/github.com/mattn/anko/vm)

Anko is a scriptable interpreter written in Go.

![](https://raw.githubusercontent.com/mattn/anko/master/anko.png)

(Picture licensed under CC BY-SA 3.0 by wikipedia)

## Installation
Requires Go.
```
$ go get -u github.com/mattn/anko
```

## Examples

```bash
# declare function
func plus(n){
  return n + 1
}

# declare variables
x = 1
y = x + 1

# print values 
println(x * (y + 2 * x + plus(x) / 2))

# if/else condition
if plus(y) > 1 {
  println("こんにちわ世界")
} else {
  println("Hello, World")
}

# array type
a = [1,2,3]
println(a[2])
println(len(a))

# map type
m = {"foo": "bar", "far": "boo"}
m.foo = "baz"
for k in keys(m) {
  println(m[k])
}
```

See `_examples/scripts` for more examples.



## Usage

Embedding the interpreter into your own program:

```Go
var env = vm.NewEnv()

env.Define("foo", 1)
env.Define("bar", func() int {
	return 2
})

val, err := env.Execute(`foo + bar()`)
if err != nil {
	panic(err)
}

fmt.Println(val) 
// output:
// 3
```

Running scripts using anko command-line tool:

```
$ anko script.ank
```

# License

MIT

# Author

Yasuhiro Matsumoto (a.k.a mattn)

