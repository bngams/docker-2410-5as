FROM node:20.18.0-alpine

WORKDIR /app

COPY package.json .
RUN npm i

COPY src/* ./src/

# override on exec
ENV PUBLIC_PORT=80

# use  variables
EXPOSE ${PUBLIC_PORT}

CMD [ "npm", "run", "start"]


