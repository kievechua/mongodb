FROM mongo:3.0.7
MAINTAINER Kieve Chua <kievechua@gmail.com>

RUN apt-get update && apt-get install -y pwgen sudo

# Change the docker default timezone from UTC to KLT
USER root
RUN sudo echo "Asia/Kuala_Lumpur" > /etc/timezone
RUN sudo dpkg-reconfigure -f noninteractive tzdata

ENV AUTH yes
ENV STORAGE_ENGINE wiredTiger
ENV JOURNALING yes

ADD run.sh /run.sh
ADD set_mongodb_password.sh /set_mongodb_password.sh

EXPOSE 27017 28017

CMD ["/run.sh"]
