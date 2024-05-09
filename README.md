Rodando a blockchain do anvil:

anvil -b 10

Criando o contrato
forge script script/Counter.s.sol:CounterScript \
 --rpc-url "http://127.0.0.1:8545" \
 --broadcast

Interagindo

recuperando valor:
cast call --private-key 0xac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80 \
--rpc-url "http://127.0.0.1:8545" \
"0x5FbDB2315678afecb367f032d93F642f64180aa3" "getNumber()(uint8)"

Onde "0x5FbDB2315678afecb367f032d93F642f64180aa3" é o address do contrato no momento do deploy.

setando valores
cast send --private-key 0xac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80 \
--rpc-url "http://127.0.0.1:8545" \
"0x5FbDB2315678afecb367f032d93F642f64180aa3" "increment()()"

cast send --private-key 0xac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80 \
--rpc-url "http://127.0.0.1:8545" \
"0x5FbDB2315678afecb367f032d93F642f64180aa3" "setNumber(uint8)()" 5
