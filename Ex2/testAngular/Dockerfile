# Step 1
FROM node:18 AS BUILD

WORKDIR /app

COPY package.json package-lock.json ./

RUN npm install

COPY . .

RUN npm run build --prod

# Step 2
FROM nginx:alpine

COPY --from=build /app/dist/test-angular/browser /usr/share/nginx/html

COPY nginx.conf /etc/nginx/nginx.conf

CMD ["nginx", "-g", "daemon off;"]
