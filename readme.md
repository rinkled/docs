# Setup Instructions

## Flutter Setup

1. Download the Flutter SDK from the [Flutter website](https://flutter.dev/docs/get-started/install).
2. Extract the file in the desired location.
3. Add Flutter to your PATH:
    ```bash
    export PATH="$PATH:`pwd`/flutter/bin"
    ```
4. Run the following command to check if everything is set up correctly:
    ```bash
    flutter doctor
    ```

## Go Setup

1. If you don't have Homebrew installed, install it by running the following command in your terminal:
    ```bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```
2. Install Go using Homebrew:
    ```bash
    brew install go
    ```
3. Set the Go workspace (optional):
    ```bash
    export GOPATH=$HOME/go
    ```
4. Add the Go binary to your PATH (optional):
    ```bash
    export PATH="$PATH:$(go env GOPATH)/bin"
    ```
5. Verify the installation by running:
    ```bash
    go version
    ```


## Protobuf with Go gRPC Setup using Buf

1. Install [Buf](https://buf.build/docs/ecosystem-overview) using Homebrew:
    ```bash
    brew install bufbuild/buf/buf
    ```

2. Install the protobuf compiler plugins for Go using the following commands:
    ```bash
    go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.32.0
    go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.3.0
    ```

    [Protobuf overview](https://protobuf.dev/overview/)


3. Update your PATH so that the protoc compiler can find the plugins:
    ```bash
    export PATH="$PATH:$(go env GOPATH)/bin"
    ```

4. Now you can compile your `.proto` files using Buf as follows:
    ```bash
    buf generate
    ```

Remember to place the export commands in ~/.zshrc or similar files. Also, these instructions are for macOS. If you're using a different operating system, the process will be slightly different.
