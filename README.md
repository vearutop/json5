gojson5
================

[JSON5](https://github.com/aseemk/json5) is Yet another JSON.

# example

```go
package main

import (
	"encoding/json"
	"fmt"
	"github.com/yosuke-furukawa/gojson5/encoding/json5"
	"os"
)

func main() {
	var data interface{}
	dec := json5.NewDecoder(os.Stdin)
	err := dec.Decode(&data)
	if err != nil {
		fmt.Println(err)
	}
	b, err := json.MarshalIndent(data, "", "    ")
	if err != nil {
		fmt.Println(err)
	}
	fmt.Println(string(b))
}
```

```js
// This is json5 demo
// json5 can write comment in your json
{
  key : "Key does not need double quote",
  // json specific
  "of" : "course we can use json as json5",
  trailing : "trailing comma is ok",
}
```

```
$ gojson5 example.json5
# output
#{
#    "key ": "Key does not need double quote",
#    "of": "course we can use json as json5",
#    "trailing ": "trailing comma is ok"
#}
```

# TODO
- block comment
- multiline string
- hexadicimal notation



