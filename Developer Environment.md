Developer Environment Setup
===========================

Install go lang and tools
-------------------------
1. Install [Go compiler](https://golang.org/dl/). Currently version *1.15* is used. Check version of Go compiler with `$ go version` after installation.
2. Create go development folder structure: `$ mkdir -p ~/go/bin` and `$ mkdir -p ~/go/src`.
3. Install Go dependency manager [dep](https://golang.github.io/dep/docs/installation.html):
    -  Run installation script provided on `dep` page.
    -  Add following line `export PATH=$PATH:/Users/<username>/go/bin` into `~/.zshrc` file (`<username>` should be replaced with real user name).
    -  Restart shell session and check that `dep` is correctly installed with `$ dep version`.
4. Make sure you have IDE installed. JetBrains GoLand is preferred. It's better to install it via [Toolbox App](https://www.jetbrains.com/toolbox-app/).

spec - clone and compile
------------------------
1. Change to `src` folder: `$ cd ~/go/src`.
2. Clone `spec` code: `$ git clone https://github.com/specgen-io/spec.git`.
3. Go to `spec` source code with `$ cd spec`.
4. Install depencies with `$ dep ensure`.
5. Run unit tests with `$ go test -test.v` - unit tests results should appear.

specgen - clone and compile
---------------------------
1. Change to `src` folder: `$ cd ~/go/src`.
2. Clone `specgen` code: `$ git clone https://github.com/specgen-io/specgen.git`.
3. Go to `specgen` source code with `$ cd specgen`.
4. Install depencies with `$ dep ensure`.
5. Set `GOPATH` environment variable: `$ export GOPATH=~/go`.
6. Build `specgen` binaries: `$ ./build.sh`. Binaries should appear in `dist` and `zips` folders.
