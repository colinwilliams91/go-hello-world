_first time playing with Go_

```go
mkdir go-hello-world
cd .\go-hello-world
```

_init go public module_
```go
go mod init github.com/colinwilliams91/go-hello-world
// this will set up the "dependency tracking" for your go module (like package.json)
```

_importing and adding packages from modules_
https://go.dev/doc/modules/managing-dependencies#naming_module
```go
import (
	"fmt"

	"rsc.io/quote"
)
// adding this import factor to your source code...
```
_"Using the set of packages imported in your code"..._

```go
go get .
// this will crawl the import directives and add the modules/packages sums
// and versions to your package/module go.mod & go.sum
```

_to add a specific dependency..._
https://pkg.go.dev/
```go
go get example.com/theirmodule
```
> The command also authenticates each module it downloads. This ensures that it’s unchanged from when the module was published.
> If the module has changed since it was published – for example, the developer changed the contents of the commit
> – Go tools will present a security error. This authentication check protects you from modules that might have been tampered with.

_synchronizing your code's dependencies..._
```go
go mod tidy
```

> You can ensure that you’re managing dependencies for all of your code’s imported packages while also removing dependencies for packages you’re no longer importing.
---
> When you ran go mod tidy, it located and downloaded the rsc.io/quote module that contains the package you imported. By default, it downloaded the latest version -- v1.5.2.