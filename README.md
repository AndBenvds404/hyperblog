  

# pasantes_back

<span>![</span><span>Aquí la descripción de la imagen por si no carga</span><span>]</span><span>(</span><span>https://raw.githubusercontent.com/parzibyte/WaterPy/master/assets/ImagenV1.png</span><span>)</span>
&#x25CF; asdasdasdasdasd adas das
Proyecto para cargar los códigos del proyecto backend pasantes 

![notificacion](https://github.com/AndBenvds404/hyperblog/assets/105686446/08016fc1-59e1-4380-9587-49d8602a385b)
![microfono](https://github.com/AndBenvds404/hyperblog/assets/105686446/8d547867-0c94-4858-a365-3187f69b7e5c)
![menu](https://github.com/AndBenvds404/hyperblog/assets/105686446/185def73-63fc-434a-b439-7a46db5af2dd)
![marvel_personajes](https://github.com/AndBenvds404/hyperblog/assets/105686446/aff2e878-e31b-458c-ba80-71104a4d5679)
![log_in](https://github.com/AndBenvds404/hyperblog/assets/105686446/06a83fe1-31d9-451b-a822-fd65205d5f03)
![detalle_personaje](https://github.com/AndBenvds404/hyperblog/assets/105686446/c4b2d509-c0c4-4582-b918-6fa984c48eb3)
![chatGpt](https://github.com/AndBenvds404/hyperblog/assets/105686446/ffc3f1e8-f47b-4f43-81f4-7435255ad17d)
![biometrico](https://github.com/AndBenvds404/hyperblog/assets/105686446/5f6f1c69-92aa-497e-b983-26cd75b6d416)
![bienvenido_marvel](https://github.com/AndBenvds404/hyperblog/assets/105686446/c81a62d3-c59b-4b75-b51d-e2ac66feb3d1)


## Configuración de proyecto
1. Descargar el proyecto "pasantes_back" del repositorio, en la direccion deseada mediante zip o usando la herramienta git con el comando "git clone https://github.com/juank20097/pasantes_back.git"
2. Descomprimir el proyecto
3. Abrir el proyecto descargado con Spring Framework
4. Configurar el archivo "docker-compose.yml" ubicado dentro de la carpeta "docker_compose"
5. Definir las credenciales de postgres en "environment" donde "POSTGRES_USER" es el usuario y "POSTGRES_PASSWORD" es la contraseña
7. Configurar los puertos "ports" de acuerdo a la necesidad o dejarlos por defecto.    
8. Configurar los puertos de pgadmin4 si se necesita o dejarlos por defecto.
9. Definir las credenciales de pgadmin4 en "environment" donde "PGADMIN_DEFAULT_EMAIL" es el usuario y "PGADMIN_DEFAULT_PASSWORD" es la contraseña
10. Dirigirse a la dirección del proyecto y dentro de la cartpeta "docker_compose" abrir una terminal
11. Ejecutar el comando  "Docker compose up" para el levantamiento del contenedor con PostgreSQL, PgAdmin
12. Una vez levantado el contenedor, acceder a "pgadmin4" por medio del navegador con la URL: http://LOCALHOSTIP:5050/login, reemplazar LOCALHOSTIP por la ip de su equipo y el puerto si se modificó.
13. Ingresar las credenciales en el login, cuyas credenciales son las configuradas en el "environment" de "pgadmin4"
14. Añadir un nuevo servidor, y colocar un nombre (cualquiera)
15. Abrir la pestaña de "Connection" y escribimos "postgres" en cajón de "Host name/address" que se refiere al nombre del servicio de PostgreSQL en el contenedor Docker.
16. En la misma pestaña, en el cajón de "Username" y "Password" escribir las credenciales definidas en "POSTGRES_USER" y "POSTGRES_PASSWORD" y hacer clic en "save".
17. Desplejar la base de datos y crear una base de datos con el nombre "devsecops" que esta definido proyecto "pasantes_back" en el archivo "application.properties" (modificar el nombre opcional)
18. En la base de datos creada (devsecops), diriguirse a la pestaña "Schemas" y creamos un nuevo esquema con el nombre "Andres", este atributo esta definido en las entidades del proyecto en la notacion @Table (modificar el nombre opcional)
19. 
## Ejecución del proyecto y consumo de servicios

13. Ejecutar el proyecto "pasantes_back"
14. Abrir el software Insomnia para el testeo de los Servicios
15. Seleccionar importar
16. Dirigirse a la direccion del proyecto y dentro de la carpeta "colleccion_insomnia" seleccionar el archivo "Insomnia_colleccion_devsecops"

*consumo de servicios en local (sin seguridades)*

17. Ejecutar los servicios de la carpeta "local" desde el Software Insomnia

*consumo de servicios en WSO2 (con seguridades)*

18. Ejecutar los servicios de la carpeta "WSO2" desde el Software Insomnia


19. En caso de errores con el token, podemos ejecutar los curls en una terminal y copiar el "access_token"

    curl para tokens
    
    empresa:
    
    curl -k -X POST https://localhost:9443/oauth2/token -d "grant_type=client_credentials" -H"Authorization: Basic dThzeDBaN1hCNWY5cmUzSkpmOUlnMFV5WTFFYTpCYzdTZEgyZVM5azRHajV2QjJPQzl3Z2VQS29h"
    
    departamento:
    curl -k -X POST https://localhost:9443/oauth2/token -d "grant_type=client_credentials" -H"Authorization: Basic dnZXV0J6ZkVQOW96SkVKUGRYV3Q0dVVjUElBYTpoR2s0QW9jUVAyRUdfSk5Fb2FxN3J4Um5YZ2th"
    
    empleado:
    curl -k -X POST https://localhost:9443/oauth2/token -d "grant_type=client_credentials" -H"Authorization: Basic aHFmQ0ZJbzd2OVpiU1hqOVRsUFRZbVl3SXdzYTpqZlViNGdOeURPbmNmTmw4VGFRNUFJV0pEcllh"
    
    departamento_empleado:
    curl -k -X POST https://localhost:9443/oauth2/token -d "grant_type=client_credentials" -H"Authorization: Basic ZTR0OU9yT0drZk9FTmlTcW9jY2pxcXNoY0ZRYTptUVdFSGVGSGduRHhpckpIWGZXM2tGekgzV0Fh" 
    
20. Volver a Insomnia, seleccionar el servicio y en la pestaña de "AUTH TYPE" selecionar "Bearer Token" y pegar el "access_token" en el campo "TOKEN" y hacer clic en el boton "send"
    
## Documentación en Swagger

21. Abrir el archivo "application.properties" y colocar la configuracion de la ruta para la interfaz swagger: "springdoc.swagger-ui.path=/swagger-ui.html"
    
22. La página de la interfaz de usuario de Swagger estará disponible en http://server:port/context-path/swagger-ui.html
    
23. La documentación estará disponible en la siguiente URL para formato json: http://server:port/context-path/v3/api-docs

24. La documentación también estará disponible en formato yaml, en la siguiente ruta: /v3/api-docs.yaml
    
    servidor: El nombre del servidor o IP
    
    puerto: El puerto del servidor
    
    context-path: la ruta de contexto de la aplicación (opcional)
!(https://github.com/AndBenvds404/Disp_Moviles/blob/main/capturas/bienvenido_marvel.png)
