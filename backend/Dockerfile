# Node.js ka official image use kar rahe hain (LTS version)
FROM node:18-alpine

# Working directory set karo container ke andar
WORKDIR /app

# Pehle sirf package files copy karo (caching ke liye)
COPY package*.json ./

# Dependencies install karo
RUN npm install

# Baaki saara code copy karo
COPY . .

# Backend port 8080 pe sunne wala hai
EXPOSE 8080

# Server start karo
CMD ["node", "server.js"]
