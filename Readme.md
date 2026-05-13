### 1. Alta disponibilidad por hardware, almacenamiento, DNS, routers y switches
####	A) Hardware, almacenamiento y DNS
		I. Utilizaremos tres servidores fisicos para ofrecer alta disponibilidad en las maquinas virtuales o nodos contratados por los usuarios
		II. Utilizaremos dos servidores para alta disponibilidad del almacenamiento, junto con una copia adicional en un proveedor de nube como AWS, Azure u otro similar.
		III. El almacenamiento contará con redundancia total, replicación y respaldo externo para recuperación ante desastres.
			a) Posiblemente integraremos ciertos intervalos del respaldo para prevenir que algún virus corrompa los demás backups.
		IV. [REVISIÓN] - Se evaluará la alta disponibilidad del dominio mediante DNS redundante, certificados SSL y servicios externos de resolución.
		
####	B) Routers y Switches
		I. Utilizaremos VRRP para alta disponibilidad entre routers
		II. Utilizaremos EtherChannel mediante LACP para agrupar enlaces físicos y mejorar la disponibilidad en conexiones críticas.
		III. [REVISIÓN] - Se implementarán VLANs adaptadas a la red: 
			a. Administración
			b. Servicios/Clientes
			c. Almacenamiento
			d. Seguridad/monitoreo
			e. IoT
			f. Etc
		Iv. Se integrarán ACLs para controlar la comunicación entre segmentos de la red.
		V. Se implementará NAT/PAT para permitir la conexión con la red.
		VI. Se documentará la topología física y lógica de la red, incluyendo VLANs, enlaces, direccionamiento IP, rutas y reglas aplicadas.
		VII. Se realizarán pruebas de failover para validar la disponibilidad ante fallos de enlaces o dispositivos.

### 2. [REVISIÓN] - Implementación de Kubernetes como servicio complementario
	I. Se evaluará la implementación de Kubernetes sobre varios nodos para ofrecer despliegue, reinicio automático y balanceo de servicios.
	II. El almacenamiento utilizado por Kubernetes se integrará con la infraestructura de alta disponibilidad.
	Nota: Este servicio podrá ofrecerse como un nivel avanzado para usuarios que requieran aplicaciones conterizadas.
