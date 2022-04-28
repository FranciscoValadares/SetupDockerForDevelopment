FROM node:lts

EXPOSE 4200

RUN mkdir /home/node/app && chown node:node /home/node/app
RUN mkdir /home/node/app/node_modules && chown node:node /home/node/app/node_modules
RUN chown -R node:node  /home/node/app
RUN chmod 755  /home/node/app

WORKDIR  /home/node/app

USER node

COPY --chown=node:node package.json package-lock.json ./

#RUN export NODE_OPTIONS=--openssl-legacy-provider

RUN npm ci --quiet

COPY --chown=node:node . .

