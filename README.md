# Neo4j Example with FLOW

I created this repository for the [Neo4j example with flow](https://github.com/Inchie/FlowGraph.Neo4jExample). 
This example shows how you can run the PHP framework [Flow](https://flow.neos.io) with the graph 
database [Neo4j](https://neo4j.com/).  

### Installation (Linux)

Create the directory 

```bash
 cd /var/www/ && mkdir graph.app
```

Be sure that you have installed [docker](https://docs.docker.com/install/). 
You can clone the repository with the following command (I normally clone the repository 
into the directory */opt/docker*):

```bash
git clone https://github.com/Inchie/FlowGraph.Docker.git
```

That creates a directory named FlowGraph.Docker. 

Before you can run the command 'docker-compose up -d' in the created directory you have
 to create the network 'nw_shared'.

```bash
docker network create \
  --driver=bridge \
  --subnet=172.16.239.0/24 \
  --ip-range=172.16.239.0/24 \
  --gateway=172.16.239.10\
  nw_shared
```

After you have created the network you can start the app with the following command:

```bash
docker-compose up -d
```

### Neo4j

After you start the Neo4j container you have access to the grap database through your browser 
at http://localhost:7474.

This requires you to login with *neo4j/test*. If the login failed, try the passwword 
*neo4j* and change the password to **test** so that the example works. 

More information you can find on [hub.docker.com/_/neo4j](https://hub.docker.com/_/neo4j/) 






    
