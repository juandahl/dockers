# Install Dependencies
FROM node:18-alpine as dependencies
RUN mkdir app
WORKDIR /app

COPY ./app/package.json .

RUN npm install

# Run Application
FROM node:18-slim
RUN mkdir app
WORKDIR /app
COPY --from=dependencies ./app .
COPY ./app .
CMD ["node", "index.js"]

EXPOSE 5000