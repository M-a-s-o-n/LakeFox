<p align="center">
<img src="https://cdn.rawgit.com/lakefox/LakeFox/4dfc27d8/lakefox.png">
</p>

# What is LakeFox?
Multiplayer video games are huge, they have millions to hundreds of millions of players playing at a time. Most game development companies focuses on the game development (which make sense), but fail to realize how much goes into making the game multiplayer. Some developers will give up on making their game multiplayer and just make their game single player, while some will go through the pain staking process of doing it them selves. If they do succeeded in building the server, they have to host the server which is expensive, which discourages the little guys from building games and forces the big guys to charge or put ads on their games. While creating a game we realized how hard this should be simple process of making a multiplayer game is, so we created LakeFox. LakeFox simplfies the networking for video games and makes a peer to peer network for each player to communicate with each other.

### Peer to Peer?
Most prebuilt multiplayer server don't use p2p because having the player connect to 20 different computers (Full Mesh Topology) will slow their computers down taking away from the experince the game gives. The way they do it instead is a client server topology.

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b8/FullMeshNetwork.svg/2000px-FullMeshNetwork.svg.png" width="50%"><br>
  Full Mesh Topology<br>
  <img src="http://practice.geeksforgeeks.org/ckeditor/images/uploads/1491250148_client_server.png" width="50%"><br>
  Client Sever Topology
</p>

In this model all the clients send their game-state to the server, when the server gets all the game-states it sends all the clients the synced version. LakeFox Work by not connecting the players in a client server topology or full mesh topology, but a peer neighbor mesh topology.

<p align="center">
	<img src="https://cdn.rawgit.com/lakefox/LakeFox/76fedf98/topology.png" width="50%"><br>
  	Peer Neighbor Mesh Topology
</p>

In peer mesh toplogy each player (peer) is connected to two other players. When the (player) recives some data from another player (From) it keeps a copy of the data and sends the other player (To).

<p align="center">
	<img src="https://cdn.rawgit.com/lakefox/LakeFox/f7db608e/connections.png" width="50%"><br>
</p>

The network is self healing so when a player disconnects the server sends out a message to all the players in the room and they will automatically reconnect keeping the network running.

# How to use it?
## Downloading

Download [fox.min.js](https://github.com/lakefox/Fox)

## Include the script

``` html
<script src="fox.min.js"></script>
```

## Basic Usage

``` javascript
// LOBBY ROOM CALLBACK HOST HTTP
var fx = new fox(LOBBY, ROOM, (msg, senderId)=>{
  // Handle the msg
}, (HOST));

//Send a message
fx.msg("Send Message");

// Fires when a new users connects
fx.addUser = (id)=>{

}

// Fires when a user disconnects
fx.removeUser = (id)=>{
  
}
```

_For a real example go to [LakeFox.html](https://github.com/lakefox/Fox/blob/master/lakefox.html)_

# Configuration Options

### Lobby
Lobbies are basically the game, so if I created a game called Ninja's vs. Cowboy's TM my lobby name could be njvscb

### ROOM

Rooms are subcatagories for the lobbies, so in Ninja's vs. Cowboy's there are 2 v 2 room's that four people can fight each other. So I will create a room using a simple counter so the first room is room 0.

### (HOST)

HOST is the only optional parmeter it will only be used if you want to use a self hosted version of [lake.js](https://github.com/lakefox/Lake/blob/master/lake.js) it defaults to [https://pnm.lakefox.net](https://pnm.lakefox.net) (Recommended)

Also the connection to pnm.lakefox.net defaults to _https_ if you would like to run it off _http_ on the host opition just put "http"

# License

This is now open under MIT license feel free to add features of correct grammer in this readme

### Want to use LakeFox

If you are interested in using LakeFox for your project, or have any questions please email me at mason@lakefox.net

# Donate

This is a service free to use, but I'm broke and can't pay for everything so if you could please donate some btc

<img src="https://i.imgur.com/gKjjsVU.png">

126Z3E8KxHerSeV7edCjfp1zW48ZgPeEKy
