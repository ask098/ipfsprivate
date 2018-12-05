# Docker-IPFS

#### Inicio proyecto

Arrancar la red de IPFS:
```
docker-compose up -d
```

Arrancar la API en /node:
```
docker-compose up -d
```


# Notas

## Comandos Información IPFS:

Obtención información de nuestro peer:
```
ipfs id
```


## Comandos Bootstrap nodes:

Obtención todos los Bootstrap peers (Información replicada):
```
ipfs bootstrap list
```

Añadir un nuevo Bootstrap peer:

```
ipfs bootstrap add </ip4/{IP_Peer}/tcp/4001/ipfs/{Peer_ID}>
```

Eliminar un Bootstrap peer:
```
ipfs bootstrap rm </ip4/{IP_Peer}/tcp/4001/ipfs/{Peer_ID}>
```
Eliminar un Todos los Bootstrap peer's:
```
ipfs bootstrap rm --all
```

## Prueba de IPFS con la colección de Postman:

Descarga de la colección de Postman y el entorno de IPFS.
Colecciones:

- Files :
  - Add new File -> Añadir nuevo archivo
  - Get File -> Obtener archivo mediante su Hash
- Network :
  - Get Network Node Configuration -> obtener configuración de nodos (Bootstrap y Swarm)
  - Add Bootstrap Peer -> Añadir nuevo Nodo de tipo Bootstrap
- Healthcheck :
  - Healthcheck -> Comprobación de conectividad con la red IPFS
- Node Configuration
  - Get Node Configuration -> Obtención de la configuración del Nodo
  
  
  
  ## cluster section (service.json)
  
  {

// main cluster component configuration
  "cluster": {                                              

// peer ID
    "id": "QmZyXksFG3vmLdAnmkXreMVZvxc4sNi1u21VxbRdNa2S1b",

//node private key
    "private_key": "<base64 representation of the key>",

//above mentioned secret
    "secret": "<32-bit hex encoded secret>",

// List of peers' multiaddresses
    "peers": [],                                            

// List of bootstrap peers' multiaddresses
    "bootstrap": [],                                 
       
// Abandon cluster on shutdown
    "leave_on_shutdown": false,

// Cluster RPC listen
    "listen_multiaddress": "/ip4/0.0.0.0/tcp/9096",      
   
// Time between state syncs
    "state_sync_interval": "1m0s",                        
  
// Time between ipfs-state syncs
    "ipfs_sync_interval": "2m10s",

// Replication factor minimum threshold. -1 == all
    "replication_factor_min": -1,

// Replication factor maximum threshold. -1 == all
    "replication_factor_max": -1,

// Time between alive-pings. See cluster monitoring section
    "monitor_ping_interval": "15s"
  }
  
