# auth-log-logstash
it's good to monitor your auth.log file to see who tries to login to your remote server. in this document i will show you how to pars your auth.log file to elasticsearch using logstash.

firs install logstah on your server using below commands:
```
    curl -fsSL https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
    echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list
    sudo apt update
    sudo apt install logstash
```

then head to /etc/logstash/conf.d and copy auth_log.conf inside it.
then head to /etc/systemd/system and copy auth_log.service inside it.

then use belowing commands to trigger it.

```
    systemctl daemon-reload
    systemctl start auth-log.service
```    

