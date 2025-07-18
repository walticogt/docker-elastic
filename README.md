# docker-elastic
Ejecuta: docker-compose up -d

Para detener: docker-compose down

En el navegador: http://localhost:5601/

# El cluster Elasticsearch o localhost:9200 demora 50s en levantar.
# Al iniciar http://192.168.18.52:5601/ -> Integrations>System Metrics

# Antes de continuar desde el cliente Windows ejecutar: .\install-service-metricbeat.ps1
# powershell.exe -ExecutionPolicy Bypass -File "C:\Program Files\Metricbeat\install-service-metricbeat.ps1"

# En la configuración de metricbeat.yml, agregrar:
# Cambiar la IP por la IP donde has montado el docker

setup.kibana:
   setup.ilm.overwrite: true
   host: "http://192.168.18.52:5601"
output.elasticsearch:
   hosts: ["192.168.18.52:9200"]
   username: "elastic"
   password: "Elastic123"
