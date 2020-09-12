FROM node:alpine3.12

# Add the following line 
ENV CI=true

WORKDIR /app
COPY ./package.json ./
COPY ./package-lock.json ./
RUN npm install
COPY ./ ./

CMD ["npm", "start"]