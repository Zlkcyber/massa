# Installing a node Massa

## on Ubuntu, these libs must be installed:
```
sudo apt install pkg-config curl git build-essential libssl-dev libclang-dev
```
## Install Curl
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
```
source $HOME/.cargo/env
```
## Install rustup
```
rustup toolchain install nightly-2022-11-14
```
### Set nightly to default
```
rustup default nightly-2022-11-14
```
### Check version
```
rustc --version
```

# Clone repository Massa

```
git clone --branch testnet https://github.com/massalabs/massa.git
```

# Set BOOSTRAP
```
ufw allow 31244 && ufw allow 31245
```
```
cd massa/massa-node/
sudo nano config/config.toml
```
```
[network]
routable_ip = "Your_ip"
[bootstrap]
retry_delay = 15000
```

# Install screen
```
sudo apt install screen
```
Buka screen tab baru
```
screen -Rd massanode
```
```
RUST_BACKTRACE=full cargo run --release -- -p Password123 |& tee logs.txt
```
Detach from screen
`CTR+A+D`
Open new screen tab
```
screen -Rd massaclient
```
cd
cd massa/massa-client/
```
Running client with this cmd
```
cargo run --release -- -p Password123
```

# Create wallet



