# Setting up custom Blockchain
<p align="center">
<img src="./images/blockchain.png?raw=true" alt="Sublime's custom image"/>
</p>

We'll use the following tools to create the blockchain network:

1. Puppeth - to generate the genesis block.
2. Geth - to create keys, initialize nodes, and connect the nodes together.
<br>
<br>

## _Setting up the network and running the nodes:_
<br>

a) Run gitbash and change to directory containing the blockchain tools.

b) Run puppeth command and choose the options as shown in the screen shot below.
<br>
<br>

   You will have to provide a network name to start with. Then you wil be propmted with option related to the genesis configuration. 

   Use "Clique (Proof of Authority)" as consensus algorithm and provide a network ID that you will use later in mycrypto to connect to this network. 

<p align="center">
<img src="./images/Puppeth1.png?raw=true" alt="Sublime's custom image"/>
</p>
<br>

   Export the genesis specs and exit the setup using CTRL-C.
   Run geth command as shown below and create two nodes. You can save the public address and path to secret key file.

<p align="center">
<img src="./images/Puppeth2.png?raw=true" alt="Sublime's custom image"/>
</p>
<br>

   After the nodes are created, they need to be initialized. Use the commands shown below to intialise "both" nodes using the <netwrok name>.json file that was created in the genesis export step earlier. The below screen shot shows only node2.

<p align="center">
<img src="./images/Puppeth3.png?raw=true" alt="Sublime's custom image"/>
</p>

 
<br>

   After the nodes are intialised, it's time to run the nodes. Run the first node in the same window you have been using for running the above steps. Use the command shown below to run the first node and leave it running in window1.

   Copy the enode address shown below and save it. This will be used to run the second node.

<p align="center">
<img src="./images/Puppeth4.png?raw=true" alt="Sublime's custom image"/>
</p>


<br>

   The second node should be started in a new gitbash window. Open a new gitbash window, change the current working directory to blockchain tools folder and run the following command. Be sure to use the correct enode address from node1 above in the command below.

   _./geth --datadir node2 --port 30304 --rpc --bootnodes "enode://50a899805348bbf2d62767147e3925cb2e9bd844cefd2f1ea66ed8fa433cb26a3682ef7ae206ec9ebe143a95383754dc3827d4aa833297782a0f10486dc9b379@127.0.0.1:30303" --ipcdisable_


<p align="center">
<img src="./images/Puppeth5.png?raw=true" alt="Sublime's custom image"/>
</p>
<br>
<br>

## _Connecting MyCrypto app to the custom network and making a transaction:_
<br>
 Open MyCrypto app and change network to the network created above using "Add Custom Node" link in the left pane. Use the network name and ID's created above in the configuration. Fill in other details as shown below:
 

<p align="center">
<img src="./images/customnetwork.png?raw=true" alt="Sublime's custom image"/>
</p>
<br>

 Use the keystore file to open the wallet.

<p align="center">
<img src="./images/wallet2.png?raw=true" alt="Sublime's custom image"/>
</p>
<br>
<p align="center">
<img src="./images/wallet3.png?raw=true" alt="Sublime's custom image"/>
</p>
<br>

 Make a transaction and check its status:
 <br>
 <p align="center">
<img src="./images/Transaction1.png?raw=true" alt="Sublime's custom image"/>
</p>
<br>
 <p align="center">
<img src="./images/Transaction2.png?raw=true" alt="Sublime's custom image"/>
<br>
</p>
 <p align="center">
<img src="./images/Transaction4.png?raw=true" alt="Sublime's custom image"/>
</p>

<br>
## *Because of some unknown issue, Proof of authority is preventing the node 1 from mining so we didn't get any confirmations. It worked fine when we used the "Proof of work".

