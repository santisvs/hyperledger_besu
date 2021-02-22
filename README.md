# Red Hyperledger Besu

Este proyecto consiste en el desarrollo de una red **hyperledger besu** **permisionada** y con el protocolo de consenso **IBFT 2.0 (Proof Of Authority)**

1. [Comenzando](#comenzando-)
2. [Pre-requisitos](#pre-requisitos-)
3. [Instalación](#instalación-)
4. [Despliegue](#despliegue-)
5. [Autores](#autores-)
6. [Agradecimientos](#agradecimientos-)

## Comenzando 🚀

*La red esta configurada para 6 nodos estáticos. Incluyo la info de cada uno de los nodos que se van a crear:*

* Bootnode: Nodo que sirve para reconocer al resto de nodos. No es nodo validador

	```
	ip: 172.16.239.11:8545
	node Address: 0x4bbaf7ea4c84fd28ef1fa74f10366ad8ad15a692
	pub Key: 0xb8e6e68aa839fc9448f244ad1cb68c2f2352a3d02c8b86f25a5e0f1296031697834be3dd32647a315cfcfd8bfbb9e9fc79811cfd791abf699ef18f5c688e1ae3
	priv Key: 0xb3c3c806839de5edcd56be47a86d325db7e9e4274180ba619d6d81b91f9e95ca
	```
	
* Admin node: Nodo Administrador. No es nodo validador
	```
	ip: 172.16.239.12:8545
	node Address: 0x43804b7e227e3d4441386ae5ceb0d189b73bdcf1
	pub Key: 0x97b9e81627f4711897afa08e7452f8569255ae82590ec83c92a73d310712c0d92c23661a58e1fc7144ab82c90020420989ffe3b3024c12c0b7f4373fb8bdae61
	priv Key: 0xd0fe7f4f305504ca50fd5f10fee370213bdea2363ee8d3511150a5f6451b027a
	```

* Node Validador 1:
	```
	ip: 172.16.239.13:8545
	node Address: 0xa59acad67a278889e9ab16ba42eee24d006c7078
	pub Key: 0x10233ff4851c3ed23f4df90079732ab88597657b0937a8c10e61b8954e3b5094463bf3261fdc1ff518eb53c5e095b94a0353184007838df2158bccc0906017c0
	priv Key: 0xe1cc1fb3e74a30371127250027c3cef5bf41bf2cdf525ba593a379794ee69e50
	```	
* Node Validador 2:
	```
	ip: 172.16.239.14:8545
	node Address: 0xb274123aa2813517b1b93075c2ab2a66efd1af98
	pub Key: 0x44b8471832b79856b52a9195b956a33ff8aa34ad5a135f9046ca360b1bfe458c16ca4612f0967184ae70624b2808bb59e4bb6db5b168c3ab36de167ed826b14b
	priv Key: 0x6cb55a3b06fac9c9b4437a4a2204913ce8ef4e3d7ac22bb336d8ffa8bc3fce5d
	```	
* Node Validador 3:
	```
	ip: 172.16.239.15:8545
	node Address: 0xc7c787f7bba6ecca08c81a4287754bb85de324a9
	pub Key: 0xc454388bcf1d71d1ec0991a214bcd946e1763d505cebd1ef8a91e6698118982bd0ed6f343aec3c7ef8dee75371b7013bcd6743635697e0923da912a7d305cdcf
	priv Key: 0xfba1bfa36e898bf5a1917a855b0f58f8a8bacd448498021c77577d6e4ca4bee7
	```
* Node Validador 4:
	```
	ip: 172.16.239.16:8545
	node Address: 0xe3b196b362542424fc36692ad1105f8ec2c49ce6
	pub Key: 0x9ad61f91909757f993f52b91df0957211946e61d23a3cdd577262d93f93d901c9b351327f2c27c8901b695cd0ec88c24f91008a078760b31712a497c64004a24
	priv Key: 0x84b490f212644ebe8cb3d592f326c927094184a2718e153e6bfa89e97d0024da
	```	
* Node Miembro 1: No es nodo validador
	```
	ip: 172.16.239.17:8545
	node Address: 0xf792828cec953c9c6d929e0f3b1cc59c5674af12
	pub Key: 0x6b367a82f1e326a6f68259802c21cc06269a8343988166b3b246d49f0ef7a047db5a7603aa703ad3ff8f0812989e697200f9d986c11dd1182cb1b8b78d935c69
	priv Key: 0x16f989df8dc79a6558c46e69483575d78f06aabd5bda28f3ad313993e432f1cf
	```
Mira **Despliegue** para conocer como desplegar el proyecto.


### Pre-requisitos 📋

Para desplegar en maquina virtual, según se indica en la documentación oficial, mínimo se necesitan 4GB de RAM. En este caso, yo utilizo 11GB de RAM ya que levanto un docker por cada nodo y más adelante incluiré el explorador de tx, grafana y sistemas que tiene el quickstart y que requieren de memoria. Por lo tanto, para probar la red yo utilizo lo siguiente:

* virtual box o cualquier generador de máquinas vistuales
* open-jdk-11
* docker
* docker compose


### Instalación 🔧

1. Crear una maquina virtual con la imagen Ubuntu 20.04 con 11GB de memoria y 2 procesadores
1. Instalar open-jdk-11
1. Instalar git
1. Instalar docker
1. Instalar docker compose


## Despliegue 📦

Para poder desplegar la red en local, deberas descargarte el repositorio en un carpeta de tu maquina virtual (ejemplo: red)

_Para arrancar la red:_

```
>red>docker-compose up --detach
```

_Para parar la red:_

```
>red>docker-compose down
```

_Para resetear todos lo contenedores, redes e imagenes:_

```
>red>docker system prune
```
_Para acceder a uno de los nodos:_

```
>red>docker exec -it -u 0 <id_docker> /bin/bash
```
_Para poder interactuar con la red desplegada, podremos utilizar la API de Hyperledger Besu_

* [API Methods Besu](https://besu.hyperledger.org/en/stable/Reference/API-Methods/) - Los pétodos que se pueden utilizar hasta el momento son "ADMIN","ETH","NET","WEB3","DEBUG","IBFT","PERM"


## Autores ✒️

* **Santiago Vallejo** - *Trabajo Inicial* - [santisvs](https://github.com/santisvs)

## Expresiones de Gratitud 🎁

* He utilizado la plantilla de [Villanuevand](https://github.com/Villanuevand) para el README.md (GRACIAS!!) 📢
* Os agradecería cualquier comentario que me pudiese ayudar y cualquier pregunta que tengais, intentare ayudaros. GRACIAS!! 🤓.



---