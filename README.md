# Hangul-toolkit
[Korean](https://github.com/LoperLee/golang-hangul-toolkit/blob/master/README-kr.md) | [English](https://github.com/LoperLee/golang-hangul-toolkit/blob/master/README.md)

This project is an open source project and can be used by anyone.

It provides the function of separating and combining the consonants of Hangul, and determining whether or not Hangul.

## 사용방법

```
$ go get github.com/LoperLee/golang-hangul-toolkit
```

## 문서

[Document](https://godoc.org/github.com/LoperLee/golang-hangul-toolkit)

## 예제

```
package main

import (
	"fmt"
	hangul "github.com/LoperLee/golang-hangul-toolkit"
)

func main() {
	s := "안녕하세요"

	han := hangul.ExtractHangul(s)
	gul := hangul.Hangul{Chosung: "ㅇ", Jungsung: "ㅏ", Jongsung: "ㄴ"}
	err := hangul.CombineHangul(gul)
	if err != nil {
		panic(err)
	}
	fmt.Println(han[0].Chosung, han[0].Jungsung, han[0].Jongsung) // ㅇ ㅏ ㄴ
	fmt.Println(gul.Word)                                         // 안
	fmt.Println(hangul.IsHangul(s))                               // true
}
```

## 라이선스

[MIT License](https://github.com/LoperLee/golang-hangul-toolkit/blob/master/LICENSE)