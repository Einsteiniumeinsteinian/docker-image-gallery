FROM node:15.14-alpine As builder
WORKDIR /app
COPY package.json .
COPY package-lock.json .
RUN npm install
COPY . .
RUN npm run build

FROM nginx:alpine
WORKDIR /usr/share/nginx/html
RUN rm -rf *
COPY --from=builder /app/build .
CMD ["nginx","-g", "daemon off;"]