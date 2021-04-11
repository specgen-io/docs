New Developer Environment Setup
===============================

Install go
----------
1. Install [Go compiler](https://golang.org/dl/). Currently version *1.15* is used. Check version of Go compiler with `$ go version` after installation.
2. Install Go dependency manager [dep](https://golang.github.io/dep/docs/installation.html):
    -  Create `bin` folder with `$ mkdir -p ~/go/bin`.
    -  Run installation script provided on `dep` page.
    -  Add following line `export PATH=$PATH:/Users/<username>/go/bin` into `~/.zshrc` file (`<username>` should be replaced with real user name).
    -  Restart shell session and check that `dep` is correctly installed with `$ dep version`.
3. Make sure you have IDE installed. JetBrains GoLand is preferred. It's better to install it via [Toolbox App](https://www.jetbrains.com/toolbox-app/).

Clone and compile spec code
---------------------------
1. Create following folder on the local machine: `$ mkdir -p ~/go/src` and to it: `$ cd ~/go/src`.
3. Clone spec code: `$ git clone https://github.com/specgen-io/spec.git`.
4. Go to `spec` source code with `$ cd spec`.
5. Install depencies with `$ dep ensure`.
6. Run unit tests with `$ go test -test.v` - unit tests results should appear.
