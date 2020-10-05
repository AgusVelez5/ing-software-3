# Trabajo numero 2
## Introducción Docker

### Install docker
![Image 1](./images/image_1.png)


### Docker hub
![Image 2](./images/image_2.png)


### Busybox
![Image 3](./images/image_3.png)

### Docker images
![Image 4](./images/image_4.png)

![Image 5](./images/image_5.png)

Al ejecutar el comando anterior no se obtiene ningun resultado por que no le estamos pasando ningun argumento al entrypoint.

![Image 6](./images/image_6.png)

![Image 7](./images/image_7.png)

### Remove exited containers

![Image 8](./images/image_8.png)

### Volumes

![Image 9](./images/image_9.png)

### Expose ports

![Image 10](./images/image_10.png)

Exponemos el puerto 80 del contenedor en el puerto 80 del host lo cual nos permite interactuar con la aplicación.

### Database

![Image 11](./images/image_11.png)

Con el comando docker run creamos el contenedor y con el comando docker exec ejecutamos un comando dentro del contenedor, en este caso, el bash.