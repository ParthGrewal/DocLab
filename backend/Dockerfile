# Stage 1: Dependencies ko install aur compile karne ke liye
FROM node:18 AS builder
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install

# Stage 2: Final application image ke liye
FROM node:18-alpine
WORKDIR /app
COPY --from=builder /app/node_modules ./node_modules
COPY . .
EXPOSE 4000
CMD ["npm", "start"]
