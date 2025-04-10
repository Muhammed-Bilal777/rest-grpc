



#gRPC server can be started with just this code

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
