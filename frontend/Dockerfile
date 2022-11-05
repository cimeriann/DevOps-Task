FROM node:16

WORKDIR /devops-django-react-task/frontend/

COPY . .

RUN npm run build

FROM nginx:alpine

WORKDIR /usr/share/nginx/html

COPY --from=builder /devops-django-react-task/frontend/build .

CMD ["nginx", "-g", "daemon off;"]