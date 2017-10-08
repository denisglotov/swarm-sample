Swarm-sample
============

Minimalistic sample of the docker swarm network. Use it to test your swarm.

    ./run up
    sleep 10
    ./run logs
    ./run down


Firewall
--------

Make sure the following ports are open.

* TCP port 2377 for cluster management communications
* TCP and UDP port 7946 for communication among nodes
* UDP port 4789 for overlay network traffic

Source: https://docs.docker.com/engine/swarm/swarm-tutorial/


Additions
---------

To expose ports (now all data remains inside my_network):

    ports:
      - 3000:3000


To limit deployment instances (good for debugging, when your containers fail):

    deploy:
      restart_policy:
        condition: on-failure
        max_attempts: 1


To use a network alias:

    networks:
      my_network:
        aliases:
          - my-server.example.com


Happy coding 😺
