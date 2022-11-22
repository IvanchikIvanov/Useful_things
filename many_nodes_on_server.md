По умолчанию используются порты: 26656; 26657; 6060; 26658; 26660; 9090; 9091
config.toml

proxy_app = "tcp://127.0.0.1:26658"
rpc laddr = "tcp://127.0.0.1:26657"
pprof_laddr = "localhost:6060"
p2p laddr = "tcp://0.0.0.0:26656"
prometheus_listen_addr = ":26660"
app.toml

api address = "tcp://0.0.0.0:1317"
grpc address = "0.0.0.0:9090"
grpc-web address = "0.0.0.0:9091"
client.toml

node = "tcp://localhost:26657"
Соответственно для второй и последующих нод необходимо сменить данные порты, чтобы они не пересекались. Это можно сделать вручную $HOME/.defund/config/config.toml или используя следующие команды: 

# config.toml
___
# для 2 ноды
```
sed -i.bak -e "s%^proxy_app = \"tcp://127.0.0.1:26658\"%proxy_app = \"tcp://127.0.0.1:36658\"%; s%^laddr = \"tcp://127.0.0.1:26657\"%laddr = \"tcp://127.0.0.1:36657\"%; s%^pprof_laddr = \"localhost:6060\"%pprof_laddr = \"localhost:6061\"%; s%^laddr = \"tcp://0.0.0.0:26656\"%laddr = \"tcp://0.0.0.0:36656\"%; s%^prometheus_listen_addr = \":26660\"%prometheus_listen_addr = \":36660\"%" $HOME/.defund/config/config.toml
```
# для 3 ноды
```
sed -i.bak -e "s%^proxy_app = \"tcp://127.0.0.1:26658\"%proxy_app = \"tcp://127.0.0.1:46658\"%; s%^laddr = \"tcp://127.0.0.1:26657\"%laddr = \"tcp://127.0.0.1:46657\"%; s%^pprof_laddr = \"localhost:6060\"%pprof_laddr = \"localhost:6062\"%; s%^laddr = \"tcp://0.0.0.0:26656\"%laddr = \"tcp://0.0.0.0:46656\"%; s%^prometheus_listen_addr = \":26660\"%prometheus_listen_addr = \":46660\"%" $HOME/.defund/config/config.toml
```
# для 4 ноды
```
sed -i.bak -e "s%^proxy_app = \"tcp://127.0.0.1:26658\"%proxy_app = \"tcp://127.0.0.1:56658\"%; s%^laddr = \"tcp://127.0.0.1:26657\"%laddr = \"tcp://127.0.0.1:56657\"%; s%^pprof_laddr = \"localhost:6060\"%pprof_laddr = \"localhost:6063\"%; s%^laddr = \"tcp://0.0.0.0:26656\"%laddr = \"tcp://0.0.0.0:56656\"%; s%^prometheus_listen_addr = \":26660\"%prometheus_listen_addr = \":56660\"%" $HOME/.defund/config/config.toml
```
# для 5 ноды
```
sed -i.bak -e "s%^proxy_app = \"tcp://127.0.0.1:26658\"%proxy_app = \"tcp://127.0.0.1:60558\"%; s%^laddr = \"tcp://127.0.0.1:26657\"%laddr = \"tcp://127.0.0.1:60557\"%; s%^pprof_laddr = \"localhost:6060\"%pprof_laddr = \"localhost:6064\"%; s%^laddr = \"tcp://0.0.0.0:26656\"%laddr = \"tcp://0.0.0.0:60556\"%; s%^prometheus_listen_addr = \":26660\"%prometheus_listen_addr = \":60560\"%" $HOME/.defund/config/config.toml
```
# для 6 ноды
```
sed -i.bak -e "s%^proxy_app = \"tcp://127.0.0.1:26658\"%proxy_app = \"tcp://127.0.0.1:60658\"%; s%^laddr = \"tcp://127.0.0.1:26657\"%laddr = \"tcp://127.0.0.1:60657\"%; s%^pprof_laddr = \"localhost:6060\"%pprof_laddr = \"localhost:6065\"%; s%^laddr = \"tcp://0.0.0.0:26656\"%laddr = \"tcp://0.0.0.0:60656\"%; s%^prometheus_listen_addr = \":26660\"%prometheus_listen_addr = \":60660\"%" $HOME/.defund/config/config.toml
```
# для 7 ноды
```
sed -i.bak -e "s%^proxy_app = \"tcp://127.0.0.1:26658\"%proxy_app = \"tcp://127.0.0.1:60758\"%; s%^laddr = \"tcp://127.0.0.1:26657\"%laddr = \"tcp://127.0.0.1:60757\"%; s%^pprof_laddr = \"localhost:6060\"%pprof_laddr = \"localhost:6066\"%; s%^laddr = \"tcp://0.0.0.0:26656\"%laddr = \"tcp://0.0.0.0:60756\"%; s%^prometheus_listen_addr = \":26660\"%prometheus_listen_addr = \":60760\"%" $HOME/.defund/config/config.toml
```
# для 8 ноды
```
sed -i.bak -e "s%^proxy_app = \"tcp://127.0.0.1:26658\"%proxy_app = \"tcp://127.0.0.1:60858\"%; s%^laddr = \"tcp://127.0.0.1:26657\"%laddr = \"tcp://127.0.0.1:60857\"%; s%^pprof_laddr = \"localhost:6060\"%pprof_laddr = \"localhost:6067\"%; s%^laddr = \"tcp://0.0.0.0:26656\"%laddr = \"tcp://0.0.0.0:60856\"%; s%^prometheus_listen_addr = \":26660\"%prometheus_listen_addr = \":60860\"%" $HOME/.defund/config/config.toml
```
# для 9 ноды
```
sed -i.bak -e "s%^proxy_app = \"tcp://127.0.0.1:26658\"%proxy_app = \"tcp://127.0.0.1:60958\"%; s%^laddr = \"tcp://127.0.0.1:26657\"%laddr = \"tcp://127.0.0.1:60957\"%; s%^pprof_laddr = \"localhost:6060\"%pprof_laddr = \"localhost:6068\"%; s%^laddr = \"tcp://0.0.0.0:26656\"%laddr = \"tcp://0.0.0.0:60956\"%; s%^prometheus_listen_addr = \":26660\"%prometheus_listen_addr = \":60960\"%" $HOME/.defund/config/config.toml
```

# app.toml
____
# для 2 ноды
```
sed -i.bak -e "s%^address = \"0.0.0.0:9090\"%address = \"0.0.0.0:9190\"%; s%^address = \"0.0.0.0:9091\"%address = \"0.0.0.0:9191\"%; s%^address = \"tcp://0.0.0.0:1317\"%address = \"tcp://0.0.0.0:1327\"%" $HOME/.defund/config/app.toml
```
# для 3 ноды
```
sed -i.bak -e "s%^address = \"0.0.0.0:9090\"%address = \"0.0.0.0:9290\"%; s%^address = \"0.0.0.0:9091\"%address = \"0.0.0.0:9291\"%; s%^address = \"tcp://0.0.0.0:1317\"%address = \"tcp://0.0.0.0:1337\"%" $HOME/.defund/config/app.toml
```
# для 4 ноды
```
sed -i.bak -e "s%^address = \"0.0.0.0:9090\"%address = \"0.0.0.0:9390\"%; s%^address = \"0.0.0.0:9091\"%address = \"0.0.0.0:9391\"%; s%^address = \"tcp://0.0.0.0:1317\"%address = \"tcp://0.0.0.0:1347\"%" $HOME/.defund/config/app.toml
```
# для 5 ноды
```
sed -i.bak -e "s%^address = \"0.0.0.0:9090\"%address = \"0.0.0.0:9490\"%; s%^address = \"0.0.0.0:9091\"%address = \"0.0.0.0:9491\"%; s%^address = \"tcp://0.0.0.0:1317\"%address = \"tcp://0.0.0.0:1357\"%" $HOME/.defund/config/app.toml
```
# для 6 ноды
```
sed -i.bak -e "s%^address = \"0.0.0.0:9090\"%address = \"0.0.0.0:9590\"%; s%^address = \"0.0.0.0:9091\"%address = \"0.0.0.0:9591\"%; s%^address = \"tcp://0.0.0.0:1317\"%address = \"tcp://0.0.0.0:1367\"%" $HOME/.defund/config/app.toml
```
# для 7 ноды
```
sed -i.bak -e "s%^address = \"0.0.0.0:9090\"%address = \"0.0.0.0:9690\"%; s%^address = \"0.0.0.0:9091\"%address = \"0.0.0.0:9691\"%; s%^address = \"tcp://0.0.0.0:1317\"%address = \"tcp://0.0.0.0:1377\"%" $HOME/.defund/config/app.toml
```
# для 8 ноды
```
sed -i.bak -e "s%^address = \"0.0.0.0:9090\"%address = \"0.0.0.0:9790\"%; s%^address = \"0.0.0.0:9091\"%address = \"0.0.0.0:9791\"%; s%^address = \"tcp://0.0.0.0:1317\"%address = \"tcp://0.0.0.0:1387\"%" $HOME/.defund/config/app.toml
```
# для 9 ноды
```
sed -i.bak -e "s%^address = \"0.0.0.0:9090\"%address = \"0.0.0.0:9890\"%; s%^address = \"0.0.0.0:9091\"%address = \"0.0.0.0:9891\"%; s%^address = \"tcp://0.0.0.0:1317\"%address = \"tcp://0.0.0.0:1397\"%" $HOME/.defund/config/app.toml
```
___
##client.toml

# для 2 ноды
```
sed -i.bak -e "s%^node = \"tcp://localhost:26657\"%node = \"tcp://localhost:36657\"%" $HOME/.defund/config/client.toml
```
# для 3 ноды
```
sed -i.bak -e "s%^node = \"tcp://localhost:26657\"%node = \"tcp://localhost:46657\"%" $HOME/.defund/config/client.toml
```
# для 4 ноды
```
sed -i.bak -e "s%^node = \"tcp://localhost:26657\"%node = \"tcp://localhost:56657\"%" $HOME/.defund/config/client.toml
```
# для 5 ноды
```
sed -i.bak -e "s%^node = \"tcp://localhost:26657\"%node = \"tcp://localhost:60557\"%" $HOME/.defund/config/client.toml
```
# для 6 ноды
```
sed -i.bak -e "s%^node = \"tcp://localhost:26657\"%node = \"tcp://localhost:60657\"%" $HOME/.defund/config/client.toml
```
# для 7 ноды
```
sed -i.bak -e "s%^node = \"tcp://localhost:26657\"%node = \"tcp://localhost:60757\"%" $HOME/.defund/config/client.toml
```
# для 8 ноды
```
sed -i.bak -e "s%^node = \"tcp://localhost:26657\"%node = \"tcp://localhost:60857\"%" $HOME/.defund/config/client.toml
```
# для 9 ноды
```
sed -i.bak -e "s%^node = \"tcp://localhost:26657\"%node = \"tcp://localhost:60957\"%" $HOME/.defund/config/client.toml
```
После меняем external_address

external_address=$(wget -qO- eth0.me)

# для 2 ноды
```
sed -i.bak -e "s/^external_address *=.*/external_address = \"$external_address:36656\"/" $HOME/.defund/config/config.toml
```
# для 3 ноды
```
sed -i.bak -e "s/^external_address *=.*/external_address = \"$external_address:46656\"/" $HOME/.defund/config/config.toml
```
# для 4 ноды
```
sed -i.bak -e "s/^external_address *=.*/external_address = \"$external_address:56656\"/" $HOME/.defund/config/config.toml
```
# для 5 ноды
```
sed -i.bak -e "s/^external_address *=.*/external_address = \"$external_address:60556\"/" $HOME/.defund/config/config.toml
```
# для 6 ноды
```
sed -i.bak -e "s/^external_address *=.*/external_address = \"$external_address:60656\"/" $HOME/.defund/config/config.toml
```
# для 7 ноды
```
sed -i.bak -e "s/^external_address *=.*/external_address = \"$external_address:60756\"/" $HOME/.defund/config/config.toml
```
# для 8 ноды
```
sed -i.bak -e "s/^external_address *=.*/external_address = \"$external_address:60856\"/" $HOME/.defund/config/config.toml
```
# для 9 ноды
```
sed -i.bak -e "s/^external_address *=.*/external_address = \"$external_address:60956\"/" $HOME/.defund/config/config.toml
```
____
```
sudo systemctl restart defundd && sudo journalctl -u defundd -f -o cat
```
