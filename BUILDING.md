# BUILDING

## WASI
```bash
GOOS=wasip1 GOARCH=wasm go build -o ./primitive.wasi.wasm ./main.go
```

### Usage
```bash
IMAGE="[some base64 encoded image]" wasmtime run --env IMAGE ./primitive.wasi.wasm -i env_var_base64 -o - -n 50 -m 1 -s 2500 -rep 0 -a 128 -bg 344b57 -j 0 -vv
```
or
```bash
wasmtime run ./primitive.wasi.wasm -i ./mountains.jpg -o - -n 50 -m 1 -s 2500 -rep 0 -a 128 -bg 344b57 -j 0 -vv
```
or
```bash
cat ./mountains.jpg | wasmtime run ./primitive.wasi.wasm -i - -o - -n 50 -m 1 -s 2500 -rep 0 -a 128 -bg 344b57 -j 0 -vv
```

## Web WASM
```bash
GOOS=js GOARCH=wasm go build -o ./primitive.web.wasm ./main.go
```

### Usage
*To be determined when web MVP works*
