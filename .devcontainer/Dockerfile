FROM ubuntu:18.04

ENV TZ=America/Indiana/Indianapolis
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone


RUN apt-get update && apt-get install -y git curl gnupg 

# Get Node 12
RUN curl -sL https://deb.nodesource.com/setup_12.x  | bash -
RUN apt-get update && apt-get -y install nodejs

#Setup user that is same name and group as user on local machine
RUN addgroup --gid 1000 jim
RUN adduser --disabled-password --gecos "" --uid 1000 --gid 1000 jim
ENV HOME /home/jim

USER jim

#RUN npm install @cloudflare/wrangler
