#Step 1

##Installing Go for Linux
Download the go tar.gz to /usr/local, and extract it 
```bash
tar -xzf GO-PACKAGE-NAME.tar.gz
```  
Then, add /usr/local/go/bin to your path, by going to your shell's rc file.  I use zsh, so for me it's .zshrc, if you use bash it is .bashrc.  If you don't use bash, you almost certainly know what I'm talking about.  You can add 
```bash
PATH=$PATH:/usr/local/go/bin
```
.  If you put your installation elsewhere, add the installation's bin directory to the path, by replace /usr/local/go/bin with the new path's bin directory.

##Testing your installation
Change directory into Step/1, and run go run hello.go.  It should print hello world if you properly installed go.

##hello.go
```go
package main //signals to the compiler that this file is runnable

import "fmt" //import the string formatting library

func main() //the running function must be called main
{  //begin function
   fmt.Println("hello world\n") //prints a hello world\n to the screen
}  //end function
```go