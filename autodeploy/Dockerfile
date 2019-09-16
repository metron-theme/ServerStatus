FROM nginx

MAINTAINER to:cppla https://cpp.la

RUN apt-get update
RUN apt-get -y install gcc g++ make git
RUN git clone -b tanzhen https://github.com/addarmy/ServerStatus.git
RUN cp -rf /ServerStatus/web/* /usr/share/nginx/html/


WORKDIR /ServerStatus/server

RUN make
RUN pwd && ls -a

EXPOSE 80 35601

CMD nohup sh -c '/etc/init.d/nginx start && /ServerStatus/server/sergate --config=/ServerStatus/server/config.json --web-dir=/usr/share/nginx/html'
