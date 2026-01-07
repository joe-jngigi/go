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
```

## Check go version

```bash
go version

# Error

# go version Command 'go' not found, but can be installed with:
# sudo apt install gccgo-go 
# sudo apt install golang-go


```

Even after running the `PATH=$PATH:/usr/local/go/bin`, I encountered the error, because the `PATH` export only applied to the current terminal session. It means that I ran into a path persistence issue.

---
---

