# Задание: создать плейбук `/home/user/task/site.yaml`

## Требования

1. **Обновить apt и установить последнюю версию nginx**  
   Использовать модуль `apt`.

2. **Добавить веб-сервер в автозагрузку системы**  
   Использовать модуль `service`.

3. **Обновить конфигурацию веб-сервера по умолчанию**  
   - Взять файл из репозитория:  
     `/home/user/task/DVPS-ANS-07/nginx.conf`  
   - Использовать модуль `copy`.  
   - Создать хэндлер **nginx reload** для перезапуска веб-сервера через модуль `service`.

4. **Удалить стандартные файлы nginx**  
   - Удалить:
     - `/etc/nginx/sites-enabled/default`
     - `/var/www/html/index.nginx-debian.html`  
   - Использовать модуль `file` и цикл `loop`.  
   - Применить хэндлер **nginx reload**.

5. **Добавить конфигурацию сайта**  
   - Использовать модуль `template`.  
   - Копировать из:  
     `/home/user/task/DVPS-ANS-07/site.conf.j2`  
   - В папку:  
     `/etc/nginx/sites-available/site.conf`.

6. **Создать символическую ссылку на сайт**  
   Использовать модуль `file`:
   ```yaml
   src: /etc/nginx/sites-available/site.conf
   dest: /etc/nginx/sites-enabled/site.conf
   state: link
