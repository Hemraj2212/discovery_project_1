# ============================================
# Stage 1: Angular app build karo
# ============================================
FROM node:18-alpine AS build

WORKDIR /app

# Package files copy karo
COPY package*.json ./

# Dependencies install karo
RUN npm install

# Saara source code copy karo
COPY . .

# Angular production build banao
RUN npm run build -- --configuration production

# ============================================
# Stage 2: Nginx se serve karo (lightweight!)
# ============================================
FROM nginx:alpine

# Angular build output ko Nginx ke html folder mein copy karo
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html

# Custom Nginx config copy karo (Angular routing ke liye zaruri)
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Port 80 expose karo
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
