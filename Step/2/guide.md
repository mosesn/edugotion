#Step 2
gotour edition!

##Go Tour
The Go Tour!  Whoo!  You type in code on the browser, it gets sent to some
server somewhere, and is then evaluated.  Along the way, the tour suggests you
do some specific things so you are actually learning go.  Pretty sweet.

###Where is Go Tour?
[go tour](http://tour.golang.org/)

###How do I navigate Go Tour?
Page Down/Page Up is Next/Prev respectively
Shift+Enter evaluates code.

##Hello, 世界
Same as hello world in Step 1, let's keep moving.

##Go Offline
Man, what a call to action!  Go offline.  You can do it on the subway, or on a
plane.  Incredible.

###How to go offline
Can't you read? ```go get code.google.com/p/go-tour/gotour```.
This is going to dump a binary into /usr/local/go/bin called gotour.  You run
this like a normal file, not like a go file, and it spins up a server that
receives connections on 127.0.0.1:3999.  Point your browser there, and we can
continue.  This is an interesting little tidbit about go get: go get retrieves
the code off the internet, and then installs it too.  This is nice, but also
scary.

###What next?
Skip Hello, 世界, we already know how that story ends.  Package time!

##Packages
You specify the package by saying, ```package packageName```

###Main
Programs start running in package main, so you can break this by changing the
name fo the package.  Also, they will run the func main, so you can also break
it by changing the name of the function.  Interesting.

##Import
Convenient if you want stuff in your program.  fmt and math are neat examples
of things you might want to import.

###One Statement
Should be structured like so:
```go
import (
       "fmt"
       "math"
)
```  
You don't use commas to separate packages so you can import several, but
semicolons.  Semicolon insertion handles this here, and makes it nice and easy
to see what packages are being installed.  The final semicolon is optional.

###Many Statements
You can also just keep every import on its own line, old style, but it isn't
too common.
```go
import "fmt"
import "math"
```

###Exported Names
Names are only exported if they start with a capital letter.  This is why
fmt.Println is capitalized, as is math.Pi, although many common naming
conventions would leave them small.  That's pretty weird, but easier than
having complicated packaging rules.

##Functions
Type declarations explained [here](http://golang.org/doc/articles/gos_declaration_syntax.html)

tl;dr: variable declaration looks like:
```go
var x int
```

func variables look like:

```go
func add(x int, y int) int {

}
```

but you can also say, "oh, I have a few int, why do I need to keep on telling
you about my ints."

```go
func add(x, y int) int {

}
```

That works with regular type declaration too.

###Calling a Function
```go
package main

import "fmt"

func add(x, y int) int {
     return x + y
}

func main() {
     fmt.Println(add(2, 3));
}
```
Arguments are passed inside of parentheses, in the same order as in the
function declaration.  This program is also in the file add23.go in this
directory and can be run with go run add23.go from inside of this directory.

###Returning multiple values
just do it.
```go
func add(x1, y1, x2, y2 int) int, int {
     return x1 + x2, y1 + y2
}
```
boom.

###Returning Result Parameters
Go has a feature where if you want, you can name the variables you return,
probably in response to the pattern of having some variable that you
mutate throughout a function and then return at the end.  At the end of your
function, instead of saying return x, y, you can just say return, and it will
know what you're talking about.

```go
func double(start int) (end int) {
     end = start * 2
     return
}
```