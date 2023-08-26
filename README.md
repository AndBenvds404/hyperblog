  

# pasantes_back
### &#x25CF; Firebase Authentication
### &#x25CF; DataStore
### &#x25CF; Intent
&#x25CF; Coroutines
&#x25CF; Picasso
&#x25CF; Notification
&#x25CF; Biometric
&#x25CF; Speech
&#x25CF; Databinding Camera
&#x25CF; Location
&#x25CF; Firebase
&#x25CF; Volley

Proyecto para cargar los códigos del proyecto backend pasantes 
![notificacion9](https://github.com/AndBenvds404/hyperblog/assets/105686446/536687c4-2bd2-4b01-a039-3cb438708b4a)
![microfono8](https://github.com/AndBenvds404/hyperblog/assets/105686446/fce80ce1-d00f-4351-b81d-fb4484f5cb9f)
![menu7](https://github.com/AndBenvds404/hyperblog/assets/105686446/fe341006-3b56-405d-bd6e-b5e36995d92d)
![marvel_personajes6](https://github.com/AndBenvds404/hyperblog/assets/105686446/bec7adf4-7506-4452-b156-a62b14b01ced)
![log_in5](https://github.com/AndBenvds404/hyperblog/assets/105686446/fe921cdb-73ea-47f5-96fd-09a50c78981d)
![detalle_personaje4](https://github.com/AndBenvds404/hyperblog/assets/105686446/c6d232b9-0a8c-4d2d-965a-a0bddd22e583)
![chatGpt3](https://github.com/AndBenvds404/hyperblog/assets/105686446/318db76e-24a2-44ad-98b1-54a5629a619d)
![biometrico2](https://github.com/AndBenvds404/hyperblog/assets/105686446/28f8817a-27fe-4975-adc8-2f72daf415d5)
![bienvenido_marvel1](https://github.com/AndBenvds404/hyperblog/assets/105686446/2a58014c-bb6d-4df4-aa3e-a7f6c68acf1b)



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
