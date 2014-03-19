RabbitMQ for Docker based on Phusion's awesome baseimage for managebility

Quickstart
----------

Start a container, exposing RabbitMQ's ports to the outside host

	docker run -i -t -p 5672:5672 -p 55672:55672 poklet/rabbitmq

Now publish and consume a message to it.

	# Install a simple client - https://github.com/alanxz/rabbitmq-c
	brew install rabbitmq-c

	# This is where my container was available
	OPTS=--url=amqp://192.168.67.142:5672

	# Send and consume a message to a queue
	amqp-declare-queue $OPTS --queue=sample-queue
	amqp-publish $OPTS --routing-key=sample-queue --body=hey
	amqp-get $OPTS --queue=sample-queue

That should print out 'hey'                                                                               

Security
--------
In its current form, as evidenced by the example above, there are no passwords!
