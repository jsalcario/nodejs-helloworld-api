# Desafio2: Guia de configuracion y uso del job:

## Paso 1:
Creación del pipeline y configuración:
asociar el Jenkinsfile del repositorio, sin credenciales ya que es un repositorio público y utilizamos la rama main.

![imagen1](images/01.png)


![imagen2](images/02.png)

En Triggers marcamos el casillero "GitHub hook trigger for GITScm polling" que se usara mas adelante para la configuracion del webhook.

![imagen3](images/03.png)

## Paso 2:
Instalar en Jenkins el plugin de NodeJs y configurarlo:
Para eso iremos a Administrar Jenkins>Plugins y buscamos Nodejs:

![imagen4](images/04.png)

Luego de su instalación iremos a Administrar Jenkins> Tools y añadimos una configuracion de Nodejs, aplicamos y guardamos.

![imagen5](images/05.png)

## Paso 3:
Exponer la url privada en ngrok:
(previamente a esto se tuvo que crear cuenta en ngrok, instalarlo y añadir la clave token)
abrimos terminal donde esta ubicado Jenkins:
```bash
ngrok http http://localhost:8080/
```
![imagen6](images/06.png)

aparecera este resultado en la terminal y copiamos la url que termina ngrok-free.app

## Paso 4:
Configurar el repositorio añadiendo un weebhook:
Nos ubicamos en el repositorio de github y vamos a Settings > Webhooks > addwebhook y en Payloadurl pegamos la url que nos dio ngrok y hacemos click en Update webhook

![imagen7](images/07.png)

El job ya esta listo para usar, cada vez que se actualice y se haga un commit en la rama main un webhook se dispara y se registra en los Github Hook Log.

cambios




