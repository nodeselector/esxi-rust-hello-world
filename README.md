# Rust on ESXi

Building a binary to run on ESXi is hard. Thanks VMWare.

Approach from: https://sbaronda.com/2020/09/20/esxi-binaries-with-rust/

# Building a binary

Build a binary with MUSL in a container:

```bash
$ ./script/build
```

To confirm it's statically linked you can do this:
```bash
$ docker run -v $PWD:/volume -w /volume -it ubuntu ldd target/x86_64-unknown-linux-musl/debug/hello-world

docker.io/clux/muslrust:latest
        not a dynamic executable
```