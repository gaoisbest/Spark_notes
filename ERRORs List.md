[1] **ERROR**:

`org.apache.spark.network.server.TransportRequestHandler: Error while invoking RpcHandler#receive() for one-way message.
java.lang.IllegalStateException: unread block data`

**SOLUTION**: 

increase the Driver memory (i.e., `--driver-memory xxg`). It seems that any `RPC` related error is relevant to memory.

reference:

https://stackoverflow.com/questions/38312655/pyspark-standalone-java-lang-illegalstateexception-unread-block-data
