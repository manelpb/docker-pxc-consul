FROM centos:6

# Install consul and ui; not much else going on here
RUN yum install -y wget
RUN yum install -y unzip 
RUN wget -q https://releases.hashicorp.com/consul/0.6.4/consul_0.6.4_linux_amd64.zip
RUN unzip consul_0.6.4_linux_amd64.zip
RUN rm -f consul_0.6.4_linux_amd64.zip
RUN mv consul /usr/bin/ 

RUN mkdir /ui
WORKDIR /ui

RUN wget -q https://releases.hashicorp.com/consul/0.6.4/consul_0.6.4_web_ui.zip
RUN unzip consul_0.6.4_web_ui.zip
RUN rm -f consul_0.6.4_web_ui.zip

RUN mkdir /etc/consul.d /config /data

ADD config.json /config/config.json

CMD [ "consul", "help" ]
