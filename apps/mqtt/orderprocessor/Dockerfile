FROM scratch AS build
WORKDIR /workspaces/wasm-orchestration-with-spin/apps/mqtt/orderprocessor
COPY . .

FROM scratch
COPY --from=build /workspaces/wasm-orchestration-with-spin/apps/mqtt/orderprocessor/spin.toml .
# Copy wasm components which are required to run the application
COPY --from=build /workspaces/wasm-orchestration-with-spin/apps/mqtt/orderprocessor/target/wasm32-wasi/release/orderprocessor_mqtt.wasm ./target/wasm32-wasi/release/orderprocessor_mqtt.wasm
