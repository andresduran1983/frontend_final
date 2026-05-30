FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install --only=production
COPY . .
# Crear usuario de seguridad para la pauta
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser
EXPOSE 3001
CMD ["npm", "start"]