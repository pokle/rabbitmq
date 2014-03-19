RabbitMQ for Docker based on Phusion's awesome baseimage for managebility

Quickstart
----------

Start a container, exposing RabbitMQ's ports to the outside host

	docker run -i -t -p 5672:5672 -p 55672:55672 poklet/rabbitmq

Now publish and consume a message to it.

	brew install rabbitmq-c

        OPTS=--url=amqp://192.168.67.142:5672

	amqp-declare-queue $OPTS --queue=sample-queue
	amqp-publish $OPTS --routing-key=sample-queue --body=hey
	amqp-get $OPTS --queue=sample-queue

That should print out 'hey'                                                                               

Security
--------
In its current form, as evidenced by the example above, there are no passwords!
