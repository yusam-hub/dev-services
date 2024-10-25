FROM rabbitmq:3.11-management
LABEL Description="rabbitmq-3-11-management + delayed_message"

RUN apt-get update && \
	apt-get install -y \
	wget

RUN wget --no-check-certificate https://github.com/rabbitmq/rabbitmq-delayed-message-exchange/releases/download/3.11.1/rabbitmq_delayed_message_exchange-3.11.1.ez

RUN mv rabbitmq_delayed_message_exchange-3.11.1.ez plugins/

RUN rabbitmq-plugins enable rabbitmq_delayed_message_exchange