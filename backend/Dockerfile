FROM node:23-alpine3.21
RUN npm install -g json-server
WORKDIR /app
COPY db.json .
EXPOSE 3001
CMD ["json-server", "--watch", "db.json", "--host", "0.0.0.0", "--port", "3001"]
