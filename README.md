# gRPC Server Example

This is a simple example of how to start a gRPC server using Node.js and the `@grpc/grpc-js` library.

## Code Example

```javascript
import { Server, ServerCredentials } from "@grpc/grpc-js";

const startGRPCServer = () => {
  const server = new Server();

  // No services added yet
  const address = "0.0.0.0:50051";

  server.bindAsync(address, ServerCredentials.createInsecure(), (err, port) => {
    if (err) {
      console.error("❌ Failed to start gRPC server:", err);
      return;
    }

    console.log(`🚀 gRPC Server running at ${address}`);
  });
};

export default startGRPCServer;
