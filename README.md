# go 설치

```
brew install golang
```

## 모듈 경로 지정

go.mod 파일을 만들어 코드에 대한 의존성 트래킹을 활성화

```
go mod init go_server
```

## hello.go 파일 생성

```
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

## go 실행

```
go run .
```

# go 서버 구축

```
package main

import (
	"fmt"
	"log"
	"net/http"
)

func index(w http.ResponseWriter, r *http.Request) {
	fmt.Fprintf(w, "hello, go! %s", r.URL.Path[1:])
}

func main() {
	http.HandleFunc("/", index)
	log.Fatal(http.ListenAndServe(":8080", nil))
}
```

## go 서버 실행

```
go run hello.go
```
