FROM node:11.9-alpine
RUN apk update && apk add bash curl jq grep
WORKDIR /usr/src/app
ENV containerized true
COPY package.json package-lock.json nightwatch-api-*.tgz ./
RUN npm install
COPY . .
RUN chmod +x ./wait-for-grid.sh
CMD [ "./wait-for-grid.sh", "npm", "test" ]
