1. Клонируем git-репозиторий:
  git clone https://github.com/alexandrefimov/ELK-kafka.git

2. Задаем необходимые права для файлов конфигурации:
  chmod 0644 filebeat.yml logstash.conf

3. Для того, чтобы filebeat мог читать системные логи с хоста, меняем права:
  sudo chmod 0644 /var/log/messages

4. Для запуска ElasticSearch необходимо увеличить максимальное число доступных процессу областей памяти:
  4.1 Допишем в файл /etc/sysctl.conf:
    vm.max_map_count=262144
    
  4.2 Применим настройку:
    sudo sysctl -p

5. Поднимаем docker-compose:
  docker-compose up -d 

