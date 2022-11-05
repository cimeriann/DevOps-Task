FROM node:16 AS build

WORKDIR /DevOps-Task/frontend/

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build


FROM nginx:1.22

COPY ./nginx/nginx.conf /etc/nginx/nginx.conf

COPY --from=build /DevOps-Task/frontend/build /usr/share/nginx/html

CMD ["nginx", "-g", "daemon off;"]
