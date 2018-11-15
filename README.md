# Kibana Swarm service to connect ES Cluster

- El stack se compone de:
  3 nodos de almacenamiento ES instalados sobre los nodos. (No containers)
  1 container ES para coordinación (Docker stack)
  1 container ES para ingesta (Docker stack)
  1 container Kibana (Docker stack)
  1 IP virtual mediante corosync + crm. 

## Desplegar el stack

- docker stack deploy elk --compose-file=docker-stack.yml

## Monitorizar servicios

- docker servive ls
- docker service logs elk_XXXX -f

# Redesplegar un servicio por un cambio de configuracion o problema con el mismo

- docker sevice rm elk_XXXX
- docker stack deploy elk --compose-file=docker-stack.yml

