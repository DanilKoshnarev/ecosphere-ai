FROM node:18-alpine

WORKDIR /app

# Копирование файлов проекта
COPY package*.json ./
COPY . .

# Установка зависимостей
RUN npm ci

# Сборка приложения
RUN npm run build

# Запуск приложения
CMD ["npm", "start"]