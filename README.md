sudo geth --datadir="/home/zuoqin/ethereum/db" -verbosity 6 --ipcdisable --port 30301 --rpcport 8101 console 2>> /home/zuoqin/ethereum/db/01.log


https://github.com/ethereum/go-ethereum/wiki/Managing-your-accounts


function checkAllBalances() {
    var totalBal = 0;
    for (var acctNum in eth.accounts) {
        var acct = eth.accounts[acctNum];
        var acctBal = web3.fromWei(eth.getBalance(acct), "ether");
        totalBal += parseFloat(acctBal);
        console.log("  eth.accounts[" + acctNum + "]: \t" + acct + " \tbalance: " + acctBal + " ether");
    }
    console.log("  Total balance: " + totalBal + " ether");
};

web3.fromWei(eth.getBalance(eth.coinbase), "ether")







# This file describes the network interfaces available on your system
# and how to activate them. For more information, see interfaces(5).



sudo nano /etc/network/interfaces


source /etc/network/interfaces.d/*

# The loopback network interface
auto lo
iface lo inet loopback

# The primary network interface
auto enp0s3
iface enp0s3 inet dhcp
# iface enp0s3 inet static
# address 10.10.246.147
# netmask 255.255.255.0
# gateway 10.10.244.1
# dns-nameservers 192.168.56.1 8.8.8.8
auto enp0s3


auto enp0s8
iface enp0s8 inet static
address 192.168.56.107
netmask 255.255.255.0





geth --identity "miner1" --networkid 42 --datadir "~/ChainSkills/miner1" --nodiscover --mine --rpc --rpcport "8042" --port "30303" --unlock 0 --password ~/ChainSkills/miner1/password.sec --ipcpath "~/Library/Ethereum/geth.ipc"
sudo geth attach ipc:/home/zuoqin/Library/Ethereum/geth.ipc



http://chainskills.com/2017/03/10/part-3-setup-the-private-chain-miners/




var browser_ballot_sol_testContract = web3.eth.contract([{"constant":false,"inputs":[{"name":"a","type":"uint256"}],"name":"multiply","outputs":[{"name":"d","type":"uint256"}],"payable":false,"type":"function"}]);
var browser_ballot_sol_test = browser_ballot_sol_testContract.new(
   {
     from: web3.eth.accounts[0], 
     data: '0x6060604052341561000f57600080fd5b5b60ab8061001e6000396000f30060606040526000357c0100000000000000000000000000000000000000000000000000000000900463ffffffff168063c6888fa114603d575b600080fd5b3415604757600080fd5b605b60048080359060200190919050506071565b6040518082815260200191505060405180910390f35b60006007820290505b9190505600a165627a7a7230582053946085292565f44bbaa38608694e8a5aa6fb031af7f5a55c048db26f27ecba0029', 
     gas: '4700000'
   }, function (e, contract){
    console.log(e, contract);
    if (typeof contract.address !== 'undefined') {
         console.log('Contract mined! address: ' + contract.address + ' transactionHash: ' + contract.transactionHash);
    }
 })





var untitled_testContract = web3.eth.contract([{"constant":false,"inputs":[{"name":"a","type":"uint256"}],"name":"multiply","outputs":[{"name":"d","type":"uint256"}],"payable":false,"type":"function"}]);
var untitled_test = untitled_testContract.new(
   {
     from: web3.eth.accounts[0],
     data: '0x60606040523415600b57fe5b5b607b6000819055505b5b608f806100246000396000f30060606040526000357c0100000000000000000000000000000000000000000000000000000000900463ffffffff1680633fa4f24514603a575bfe5b3415604157fe5b6047605d565b6040518082815260200191505060405180910390f35b600054815600a165627a7a72305820a4fac284b98d43538f802082b0db8c67ddd6d72df4e8d9fbccb4cec0e52ea0df0029',
     gas: '4700000'
   }, function (e, contract){
    console.log(e, contract);
    if (typeof contract.address !== 'undefined') {
         console.log('Contract mined! address: ' + contract.address + ' transactionHash: ' + contract.transactionHash);
    }
 })

eth.defaultAccount=eth.coinbase;
eth.getCode(untitled_test.address)