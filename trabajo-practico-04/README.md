# Trabajo numero 4
## Arquitectura de Microservicios

Al levantar esta [aplicación](https://github.com/microservices-demo/microservices-demo) se generaron varios contenedores, entre ellos podemos ver: 

* Un traefik el cual es el punto de entrada al sistema.
* Aplicaciónes de node, go, java.
* Bases de datos MYSQL y Mongo.
* Cola de mensajes rabbitmq.

- - - 

En este sistema, se opto por utilizar una arquitectura de microservicios, donde cada uno de ellos se ocupan de una funcionalidad especifica. Esto se lo acompaño con una organización multi-repo, uno para cada microservicio.

Ventajas multi-repo:

* Independencia entre servicios y equipos.
* Cada repo tiene su propio CI.
* Se evita solapamientos entre configuraciones de los servicios.
* Cada servicio se puede versionar de forma independiente.

Desventajas multi-repo:

* Mayor complejidad para nuevos miembros.
* Se repiten artifacts comunes y soluciones comunes en los repos.
* Puede crecer la complejidad de gestionar al tener una gran cantidad de repositorios.

Una herramienta que puede contruibuir en el dilema Mono-repo vs Multi-repo es [meta](https://github.com/mateodelnorte/meta).

- - - 

Podemos observar que el contenedor front-end actua como API Gateway.

- - -

~~~
curl http://localhost/customers
~~~

El request anterior es procesado por el servicio user.  

~~~
curl http://localhost/catalogue
~~~

El request anterior es procesado por el servicio catalogue.

~~~
curl http://localhost/tags
~~~

El request anterior es procesado por el servicio catalogue.

- - -

Los servicios persisten los datos cada uno de forma independiente y utilizando diferentes tecnologias pero sin utilizar volumenes excepto el servicio __queue-master__ el cual procesa la cola de mensajes.

- - -

Por ultimo, podemos ver que se usa API REST como interfaz para comunicarse.
