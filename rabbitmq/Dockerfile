FROM rabbitmq:3-management

RUN apt-get update && \
    apt-get install -y wget unzip&& \
    rm -rf /var/lib/apt/lists/*

WORKDIR $RABBITMQ_HOME/plugins/

RUN wget https://dl.bintray.com/rabbitmq/community-plugins/3.7.x/rabbitmq_delayed_message_exchange/rabbitmq_delayed_message_exchange-20171201-3.7.x.zip
RUN unzip rabbitmq_delayed_message_exchange-20171201-3.7.x.zip
RUN rm -f rabbitmq_delayed_message_exchange-20171201-3.7.x.zip

RUN rabbitmq-plugins enable --offline rabbitmq_management && \
    rabbitmq-plugins enable --offline rabbitmq_delayed_message_exchange
