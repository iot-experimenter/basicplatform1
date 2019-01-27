# "`-._,-'"`-._,-'"`-._,-'"`-._,-'"`-._,-'"`-._,-'"`-._,-'"`-._,-'"`-._,-'"`-._,-'"`-._,-
# Portainer - influxdb - chronograf - grafana - node red - mosquitto - kafka - zookeeper
# ---------------------------------------------------------------------------------------
# vm.max_map_count in /etc/sysctl.conf toevoegen :
#  vm.max_map_count=262144
# 
# ---------------------------------------------------------------------------------------

# ****** voeg volgende regels toe aan etc/hosts ***************
   127.0.0.1       localhost
   192.168.43.78 kafka-1 kafka-2 kafka-3 
# ***** opmerking 192.168.43.78 = ip adres van machine waar kafka op draait ***
# ---------------------------------------------------------------------------------------

#  ***controle :
  nslookup kafka-1
  ping -c 4 kafka1

# *****dockers opspinnen met :****************
sudo docker-compose up -d --build

****** kafka-test ******
kafkacat -P -b kafka-1:19092 -t testtopic1
kafkacat -C -b kafka-3:39092 -t testtopic1

**** gebruikte URL's :
*portainer : indien gebruikt eerst commentaar# deleten in portainer-sectie docker-compose
http://localhost:9000/#/dashboard

*node-red :
http://localhost:1880
http://localhost:1880/ui

*andere :
http://localhost:5601/
http://localhost:9200/
http://localhost:3000/
http://localhost:32768/nifi/
