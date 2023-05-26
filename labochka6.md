Помогал с работой товарищ Климов! 
Он посоветовал использовать приложения на vuejs и работать непосредственно в этой среде.
Далее требуется установка Node.js, создаем новую дерикторию и инициализировала проект vue create
Нужно установить зависимость npm install
далее нужно следующий прописать код в vue.config.js
module.exports = {
devServer: {
proxy: {
'/api': {
target: 'http://localhost:8000',
changeOrigin: true
      }
    }
  }
}
проверила работоспособность
нужно установить теперь конфигурацию
server {
listen 8000;

location / {
proxy_pass http://localhost:8080;
proxy_set_header Host $host;
proxy_set_header X-Real-IP $remote_addr;
     }
}
пишем nginx и запускаем
