FROM node:18
WORKDIR /app

# Копируем файлы зависимостей
COPY package.json package.json
COPY package-lock.json package-lock.json

# Устанавливаем зависимости
RUN npm ci

# Копируем остальные файлы проекта (замените ... на нужные пути)
COPY . .

# Собираем проект
RUN npm run build

# Устанавливаем http-server глобально
RUN npm install --global http-server

# Запускаем сервер для статики
CMD ["npx", "-y", "http-server", "-p", "9000", "/app/build"]