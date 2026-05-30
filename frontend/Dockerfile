# El frontend son archivos estáticos (HTML/JS), no requiere build de Node.
# Se sirven directamente con Nginx.
FROM nginx:stable-alpine

# Copiar la configuración de Nginx (incluye el proxy /api/ hacia el backend)
COPY default.conf /etc/nginx/conf.d/default.conf

# Copiar los archivos estáticos del sitio
COPY index.html app.js /usr/share/nginx/html/

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
