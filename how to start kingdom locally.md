cd ~/fabric-dev-servers

export FABRIC_VERSION=hlfv12
./startFabric

./createPeerCard

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
