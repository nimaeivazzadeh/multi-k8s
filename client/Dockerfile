FROM node:alpine as builder 
WORKDIR /app
COPY ./packaje.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/usr/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html