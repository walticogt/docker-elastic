# Elastic sin SSL (sin autenticación):
      docker-compose up -d
      http://localhost:5601/

# El cluster Elasticsearch o localhost:9200 demora 50s en levantar.
      Integrations>System Metrics

# Para cliente Windows ejecutar: 
      .\install-service-metricbeat.ps1
      powershell.exe -ExecutionPolicy Bypass -File "C:\Program Files\Metricbeat\install-service-metricbeat.ps1"

# Para cliente Linux ejecutar (ejecutar con sudo el dpkg):
      curl -L -O https://artifacts.elastic.co/downloads/beats/metricbeat/metricbeat-8.10.1-amd64.deb
      dpkg -i metricbeat-8.10.1-amd64.deb

# Para clientes MAC ejecutar 
      curl -L -O https://artifacts.elastic.co/downloads/beats/metricbeat/metricbeat-8.10.1-darwin-x86_64.tar.gz
      tar xzvf metricbeat-8.10.1-darwin-x86_64.tar.gz
      cd metricbeat-8.10.1-darwin-x86_64/

# En la configuración de metricbeat.yml, agregrar:
# En Linux: 
      vi /etc/metricbeat/metricbeat.yml

# Cambiar la IP por la IP donde has montado el docker
      setup.kibana:
         setup.ilm.overwrite: true
         host: "http://192.168.18.x:5601"

      output.elasticsearch:
         hosts: ["192.168.18.x:9200"]
         username: "elastic"
         password: "Elastic123"

# Continuar con los pasos q indica en:
      http://192.168.18.x:5601/app/home#/tutorial/systemMetrics
      
