FROM poklet/baseimage
MAINTAINER tushar.pokle@gmail.com

ADD rabbitmq.list /etc/apt/sources.list.d/rabbitmq.list
ADD http://www.rabbitmq.com/rabbitmq-signing-key-public.asc /etc/apt/sources.list.d/rabbitmq-signing-key-public.asc
RUN apt-key add /etc/apt/sources.list.d/rabbitmq-signing-key-public.asc
RUN apt-get update -y
RUN apt-get -f -y install rabbitmq-server
ADD etc-default-rabbitmq-server /etc/default/rabbitmq-server

EXPOSE 5672 55672
CMD rabbitmq-server
