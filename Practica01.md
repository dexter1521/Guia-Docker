_Antes que nada debemos de revisar si ya contamos con una instancia de docker o docker-compose dentro de nuestro host para ello ingresamos los siguientes comandos:_

```
$ docker --version
$ docker-compose --version
```

_En caso de que exista una versión previa y que tu no hayas instalado hacemos lo siguiente, con esto estariamos desinstalando cualquier version previa de docker, 
ojo se puede perder todo lo previo:_

```
$ yum remove docker docker-common docker-selinux docker-engine-selinux docker-engine docker-ce
```

_Antes de comenzar se recomienda tener actualizado nuestro host a sus últimas versiones de soft y repos para ello tiramos los suguientes comandos_

```
$ yum update
$ yum upgrade
$ yum install -y yum-utils net-tools nano
```

_Por fin vamos a instalar Docker!_

```
$ yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
$ yum install docker-ce -y
$ yum list docker-ce --showduplicates | sort -r
```

_Recordatorio el servicio de docker hay que habilitarlo e inicializarlo para que al proximo reinicio se encuentre disponible de otra manera habrá 
que hacerlo a mano blah, blah, blah!_

```
$ systemctl start docker
$ systemctl enable docker.service
$ systemctl status docker.service
```

_Una vez más comprobamos la versión de docker_
```
$ docker --version
```

_Instalamos docker-compose, hay que recordar que en este ejemplo estamos trabajando con 1.29.1 seguramente en un futuro esto cambiará_
```
$ curl -L "https://github.com/docker/compose/releases/download/1.29.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

_Damos permiso de ejecucion a nuestro archivo_
```
$ chmod +x /usr/local/bin/docker-compose
```

_Comprobamos la versión de Docker-compose_
```
$ docker-compose --version
$ yum update
```

_Verificamos la ip de nuestro docker, segura saldra algo así 172.16.0.1 sino no la misma no te preocupes suele suceder_
```
$ ip a list docker0
```

_Si queremos ver las caracteristicas de nuestro docker tiramos el  siguiente codigo_

```
$ docker info > dockerinfo.txt
```

_Con esto habriamos terminado nuestra primera práctica_

---
⌨️ con ❤️ por [Dexter1521](https://github.com/Dexter1521) 😊
