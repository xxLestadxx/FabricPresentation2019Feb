OS: Ubuntu 16.04


Go to https://hyperledger-fabric.readthedocs.io/en/release-1.4/prereqs.html and follow the instructions to download the pre-req and to install docker and docker composer and then to download the docker images after that do the following : 


cd ~/fabric-dev-servers

export FABRIC_VERSION=hlfv12 (yours could be v14)

./startFabric

./createPeerAdminCard

( you can see this tutorial https://hyperledger.github.io/composer/v0.19/tutorials/deploy-to-fabric-single-org.html)

composer network install -a ./kingdom.bna -c PeerAdmin@hlfv1

composer network start -c PeerAdmin@hlfv1 -n kingdom -V 0.2.6-deploy.26 (you should see the right version from the playground) -A admin -S adminpw

(If you are not starting the project for the first time ) 
composer card delete --card admin@kingdom

composer card import -f admin@kingdom.card

composer-rest-server 
	- name of the bn card admin@kingdom
	- never use namespaces 
	- n
	- n
	- expolrer test interface - Y
	- 
	- WebSocket - Y
	- TLS - no 
