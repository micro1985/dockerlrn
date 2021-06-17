FROM node:10
LABEL maintainer micro1985@mail.ru
ENV HTTP_PROXY=http://192.168.5.9:8080
ENV HTTPS_PROXY=http://192.168.5.9:8080
ENV NO_PROXY=localhost,127.0.0.1
RUN git config --global https.proxy http://192.168.5.9:8080
RUN git clone -q https://github.com/docker-in-practice/todo.git
WORKDIR todo
RUN npm install > /dev/null
EXPOSE 8000
CMD ["npm", "start"]
