<!-- DO NOT REMOVE - contributor_list:data:start:["gleich"]:end -->

# desktop

📦 Golang package for interfacing with desktop applications

![format](https://github.com/gleich/runningapps/workflows/format/badge.svg)

## 🚀 Install

```txt
go get github.com/gleich/desktop
```

## 📝 Documentation

### 🍎 MacOS

#### `MacOSApplications()`

Get a list of all running desktop applications for the mac operating system. Returns a list containing the names of the running applications and any error that might have occurred. There is also an optional `includeMenubarApps` parameter: if set to `true` it will also include applications running in the menubar.

Example:

```go
package main

import (
    "fmt"
    "os"

    "github.com/gleich/desktop"
)

func main() {
    apps, err := desktop.MacOSApplications(includeMenubarApps bool)
    if err != nil {
        fmt.Println(err)
        os.Exit(1)
    }
}
```

#### `MacOSQuitApp()`

Force quit an application by passing the name of the application. Returns any error that might have occurred.

```go
package main

import (
    "fmt"
    "os"

    "github.com/gleich/desktop"
)

func main() {
    err := desktop.MacOSQuitApp("Slack")
    if err != nil {
        fmt.Println(err)
        os.Exit(1)
    }
}
```

### 🐧 Linux

#### `LinuxApplications()`

⚠️ **Warning!! This function requires the `wmctrl` tool to be installed. Please install it with your package manager**

Get a list of all running desktop applications for any linux based operating system. Returns a map containing the names of the running desktop applications and their corresponding [PIDs](https://www.computerhope.com/jargon/p/pid.htm) and any error that might have occurred.

Example:

```go
package main

import (
    "fmt"
    "os"

    "github.com/gleich/desktop"
)

func main() {
    apps, err := desktop.LinuxApplications()
    if err != nil {
        fmt.Println(err)
        os.Exit(1)
    }
}
```

#### `LinuxQuitApp()`

Kill an application by passing the [PID](https://www.computerhope.com/jargon/p/pid.htm). Returns any error that might have occurred.

Example:

```go
package main

import (
    "fmt"
    "os"

    "github.com/gleich/desktop"
)

func main() {
    err := desktop.LinuxQuitApp(72667)
    if err != nil {
        fmt.Println(err)
        os.Exit(1)
    }
}
```

<!-- DO NOT REMOVE - contributor_list:start -->

## 👥 Contributors

- **[@gleich](https://github.com/gleich)**

<!-- DO NOT REMOVE - contributor_list:end -->
