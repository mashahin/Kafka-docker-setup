
You can install Kafka on any OS, like Windows, Mac, or Linux, but the installation process is somewhat different for every OS. So, instead of covering all of them, my goal was to install Kafka in a virtual machine and use Linux Ubuntu as a distribution of choice.

So instead, you’ll use Docker. I think it’s an even better option, since you don’t have to install the tools manually. Instead, you’ll write one simple Docker compose file, which will take care of everything. And the best part is — it will work on any OS. So, if you are following this article on Windows or Linux, everything will still work. You only need to have Docker and Docker compose installed.


INSTALL KAFKA USING DOCKER

You will need two Docker images to get Kafka running:

wurstmeister/zookeeper 

wurstmeister/kafka 

You don’t have to download them manually, as a docker-compose.yml will do that for you. Clone this repo or copy the docker-compose.yml file on to your machine.
   
Make sure to edit the ports if either 2181 or 9092 aren’t available on your machine. You can now open up a Terminal and navigate to the folder where you saved docker-compose.yml file. Execute the following command to pull the images and create containers:

	docker-compose -f docker-compose.yml up -d

The -d means both Zookeeper and Kafka will run in the background, so you’ll have access to the Terminal after they start.

And that’s it! You can verify both Kafka and zookeeper are running by executing the following docker command:

	docker ps


CONNECT TO KAFKA SHELL

Once Zookeeper and Kafka containers are running, you can execute the following Terminal command to start a Kafka shell:

	docker exec -it kafka /bin/sh

Just replace kafka with the value of container_name, if you’ve decided to name it differently in the docker-compose.yml file.




