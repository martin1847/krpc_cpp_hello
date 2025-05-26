# gRPC C++ Hello World Example

## macos init

```bash
brew install autoconf automake libtool pkg-config
export MY_INSTALL_DIR=/usr/local/bin   

cmake -DgRPC_INSTALL=ON \
      -DgRPC_BUILD_TESTS=OFF \
      -DCMAKE_CXX_STANDARD=17 \
      -DCMAKE_INSTALL_PREFIX=$MY_INSTALL_DIR 

```

location: `grpc/examples/cpp/krpc_cpp_hello`

##  run krpc

```bash
cmake -DCMAKE_PREFIX_PATH=$MY_INSTALL_DIR
make -j 4
./krpc_server 
# Server listening on 0.0.0.0:50051
rpcurl $REMOTE/Demo/KrpcCpp/hello -d '12341'
# 
# {
#   "code": 0,
#   "data": "Hello KRPC : get 12341"
# }

```
