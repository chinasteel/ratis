# Raft Proto Shaded

This module is to shade protos, protobuf and other libraries such as Netty, gRPC and Hadoop
so that applications using Raft may use protobuf and other libraries with versions different 
from the versions used here.

Other modules require the shaded sources for compilation. To generate them,
run the following command under `ratis-proto-shaded/`

- `mvn package -Dcompile-protobuf -DskipTests`

The generated sources are stored in `ratis-proto-shaded/src/main/java/`.

## What are shaded?

| Original packages                 | Shaded packages                                          |
| ----------------------------------|----------------------------------------------------------|
| `com.google.protobuf`             | `org.apache.ratis.shaded.com.google.protobuf`             |
| `io.grpc`                         | `org.apache.ratis.shaded.io.grpc`                         |
| `io.netty.handler.codec.protobuf` | `org.apache.ratis.shaded.io.netty.handler.codec.protobuf` |
| `org.apache.hadoop.ipc.protobuf`  | `org.apache.ratis.shaded.org.apache.hadoop.ipc.protobuf`  |

The protos defined in this project are stored in the `org.apache.ratis.shaded.proto` package.
