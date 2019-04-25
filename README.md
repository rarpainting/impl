`impl` generates method stubs for implementing an interface.

```bash
go get -u github.com/josharian/impl
```

Sample usage:

```bash
$ impl -iface io.ReadWriteCloser -struct file/file.go
func (f *File) Read(p []byte) (n int, err error) {
	panic("not implemented")
}

func (f *File) Write(p []byte) (n int, err error) {
	panic("not implemented")
}

func (f *File) Close() error {
	panic("not implemented")
}

# You can also provide a full name by specifying the package path.
# This helps in cases where the interface can't be guessed
# just from the package name and interface name.
$ impl -iface golang.org/x/oauth2.TokenSource -struct file/source.go
func (s *Source) Token() (*oauth2.Token, error) {
    panic("not implemented")
}
```

### TODO

- [ ] Add the first part of the file.
- [ ] Add features that match a specific structure.
