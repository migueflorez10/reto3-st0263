### Info de la Materia: Topicos Especiales en Telematica-st0263

### Estudiantes:
- Miguel Angel Martinez Florez, mamartinef@eafit.edu.co
- Mateo Muñoz Cadavid, mmunozc4@eafit.edu.co

### Profesor:  Edwin Nelson Montoya Munera, emontoya@eafit.edu.co  

# Reto 3: Aplicación Monolítica con Balanceo y Datos Distribuidos (BD y archivos)

##  Objetivo 
El propósito de este reto es desplegar una aplicación monolítica en este caso, un CMS WordPress utilizando la tecnología de contenedores Docker para mejorar la 
disponibilidad y escalabilidad. La arquitectura está diseñada para ser robusta, con un enfoque en la alta disponibilidad y la persistencia de datos a través de servicios 
distribuidos de base de datos y almacenamiento de archivos.

##  Descripción de la Actividad
Se realizó la implementación de un sistema de gestión de contenido WordPress que se ejecuta en un ambiente de contenedores Docker distribuidos a lo largo de varias 
instancias de máquinas virtuales en AWS Academy. Este sistema integra un balanceador de cargas Nginx que maneja el tráfico web seguro HTTPS, proporcionando un punto 
de acceso unificado para el sistema.

##  Arquitectura del Reto
![image](https://github.com/migueflorez10/reto3-st0263/assets/68928440/d8145a8a-2b8c-41b0-9f21-5cf82eb27a02)

La arquitectura desplegada se compone de los siguientes elementos:
- **Balanceador de Cargas (LB):** Un contenedor Docker que ejecuta Nginx configurado para balancear las solicitudes entre dos instancias de la aplicación.
- **Instancias de Aplicación:** Dos contenedores Docker que ejecutan la aplicación WordPress, asegurando la disponibilidad del servicio mediante el balanceo de cargas.
- **Servidor de Base de Datos (DBServer):** Una instancia VM dedicada que ejecuta MySQL, proporcionando los servicios de base de datos a las instancias de WordPress.
- **Servidor de Archivos (FileServer):** Una instancia VM que implementa un servidor NFS, responsable de la gestión de archivos distribuidos, ofreciendo una solución de almacenamiento compartido para las instancias de WordPress.

La comunicación entre los usuarios finales y el sistema se realiza a través del dominio reto3miguelito.online, asegurado con un certificado SSL.

##  Descripción del Ambiente de Desarrollo y Técnico
La implementación fue realizada utilizando los servicios de AWS Academy, aprovechando las ventajas de la nube para facilitar el despliegue y la gestión de recursos. Las herramientas 
y tecnologías utilizadas incluyen:
- **AWS EC2:** Para la orquestación de las máquinas virtuales que alojan los contenedores Docker y servicios.
- **Docker:** Para la contenerización de la aplicación y los servicios relacionados, permitiendo un despliegue flexible y escalable.
- **Nginx:** Utilizado como un balanceador de cargas delante de las instancias de WordPress para distribuir el tráfico.
- **MySQL:** Seleccionado como el sistema de gestión de base de datos por su popularidad, rendimiento y compatibilidad con WordPress.
- **NFS:** Para un sistema de archivos en red que permite un almacenamiento compartido entre instancias.

##  Aspectos Relevantes
- **Escalabilidad:** La arquitectura soporta el escalamiento horizontal, permitiendo añadir más instancias según la demanda.
- **Seguridad:** La implementación de SSL garantiza la integridad y confidencialidad de los datos transmitidos.
- **Persistencia de Datos:** A través de volúmenes Docker y el almacenamiento NFS, se asegura la persistencia y la consistencia de los datos.
- **Alta Disponibilidad:** El diseño redundante y distribuido promueve un servicio ininterrumpido incluso en eventos de fallas parciales.
- **Despliegue Automatizado:** Utilizando scripts y plantillas de configuración, se facilita la replicación y el mantenimiento del sistema.

##  Referencias 
Las siguientes referencias han sido fundamentales para el desarrollo y la implementación de este proyecto:

- Video Tutoriales:
  - [Despliegue de Alta Disponibilidad en AWS](https://www.youtube.com/watch?v=vZjAhjqLakU) - Una guía visual sobre cómo desplegar aplicaciones en un entorno de alta disponibilidad utilizando AWS.
  - [Configuración de Nginx como Balanceador de Cargas](https://www.youtube.com/watch?v=px0A_P1V06k) - Un tutorial sobre la configuración de Nginx para actuar como un balanceador de carga.

- Código Fuente:
  - [Repositorio de Proyectos ST0263](https://github.com/jcmtya/st0263-20241/tree/main) - Repositorio que contiene los recursos y códigos de ejemplo para los tópicos especiales en telemática.

Estos recursos proporcionan información detallada y guías paso a paso que han sido esenciales para la comprensión y el éxito del proyecto.
