FROM node:alpine

ENV NODE_ENV development
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY index.js .

EXPOSE 3000
CMD ["npm", "start"]
