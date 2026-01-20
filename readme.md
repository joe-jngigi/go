# INTRODUCING GO PROGRAMMING

Go is expressive, concise, clean, and efficient. Its concurrency mechanisms make it easy to write programs that get the most out of multicore and networked machines, while its novel type system enables flexible and modular program construction.

Golang is compiled, not interpreted like Java with JVM. This means runtime is baked into the final product. That means as long as `go` is installed, go can run the file directly. Go gives us great tools we can utilize; go takes advantages of an OS and give it to you directly.

Go is not fully object oriented. We have struct for classes, we do not have things like method overloading, and some other features. GO does not have things like try-catch.

## Installation of GO

We are using linux; we need to install go so that we can write, compile and run programs written in go, because it is an open-source language. To install go, we need to go to [GO Download](https://go.dev/doc/install) and follow the instructions. On linux, we need to remove any previous go installations, they exist. We can basically navigate to the `/usr/local/` directory and delete the **go** directory, or we can use the command on the commandline

```bash
$ rm -rf /usr/local/go
```

After that we can unzip the go compressed file into the local folder. If the file is in the download folder, we navigate the the downloads directory and use this command to untar the file.

```bash
sudo tar -C /usr/local -xzf go1.25.5.linux-amd64.tar.gz
```

`tar` is an archive too use to create or extract `.tar` files and other variants like `.tar.gz`. The `-C` flag tells tar to switch to the `/usr/local` before extracting so that the files are extracted into /usr/local, not the current directory.

`-x` will extract files from the archive and `-z` will use `gzip` to decompress(.gz). Gzip (GNU Zip) is a lossless data compression format and utility that shrinks files.

`-f` specifies tje archive file, and everthing after this is treated as a filename.

After the extraction of the file, we can now add `/usr/local/go/bin` to the PATH environment variable

```bash
export PATH=$PATH:/usr/local/go/bin
# export PATH=$PATH:/usr/local/go/bin
```

## Check go version

```bash
go version

# Error

# go version Command 'go' not found, but can be installed with:
# sudo apt install gccgo-go 
# sudo apt install golang-go


```

## Solving?

Even after running the `PATH=$PATH:/usr/local/go/bin`, I encountered the error ("Command 'go' not found"), from shell, indicating that it can't find `go` executable in any diretories listed in the `$PATH` varibales.

Running `export PATH=$PATH:/usr/local/go/bin` only updates the path for your current shell session. If you close the terminal or open a new session, If you close the terminal and open a new one. or if you're running this in a script the change will not persist.

 **Test go version**

We can use `/usr/local/go/bin/go version`

> If this works, the issue is definitely with your PATH. If it doesn't _(e.g., "permission denied" or "no such file")_, check file permissions with `ls -l /usr/local/go/bin/go` (it should be executable; fix with `chmod +x /usr/local/go/bin/go` if needed, possibly with sudo).

My system is using `zshrc` but you can identify what your system is using by running `echo $SHELL`. To solve the issue, we will edit the `.zshrc`, we use nano; 

```BASH 
nano ~/.zshrc
```

On opening the configuration file, we add the path to the bottom of the file; `export PATH=$PATH:/usr/local/go/bin`, save the file and run 

```BASH
source ~/.zshrc
```

## Pro Tip when Working with GO

As you plan to develop go projects,it is good to set the `GOPATH`, where your code and downloaded packages live, we can add the path to the shell configuration file

We will edit the `.zshrc` file, by adding the following configuration and the apply with `source .zshrc`

```BASH
# 1. Point to the compiler (System location)
export GOROOT=/usr/local/go

# 2. Point to your project drive (Your Odin location)
export GOPATH=/run/media/odin/Odin/GO

# 3. Add both to your system PATH
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
```

We can the run `go env GOPATH GOROOT` to see if our paths have been added.

In modern Go (version 1.11+), you aren't strictly forced to keep everything inside GOPATH/src. However, setting GOPATH to your external drive is still a smart move because:

1. Downloads: All the third-party libraries you download (`go get`) will be saved to your external drive instead of filling up your system SSD.

2. Binaries: Any tools you install will go into `/run/media/odin/Odin/GO/bin`.

So next, we can start writting GO

---
---

# GOLANG Programming

GO is very interesting. We use `main` keyword to name the main function. The function `main` is usually declared in the main package.