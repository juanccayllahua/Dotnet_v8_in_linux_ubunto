### DOTNET in Linux

Ingresar en el terminal de power shell

Ejecutar el siguiente comando docker 

```sh
docker run -it --name nameImagen ubuntu
```
En la consola de power shell se mostrará

```
docker run -it --name serverlinuxPrueba ubuntu
root@c28e4977f1d3:/#
```

Dentro del servidor de Ubuntu ejecutar el siguiente comando

Ejecutar el siguiente comando para ctualizar el sistema ubuntu

```sh 
apt-get update
```

Ejecutar el siguiente comando para instalar el comando sudo

```sh 
apt-get install sudo
```

Ejecutar el siguiente comando para instalar nano


```sh
sudo apt update
sudo apt install nano
```

## INSTALAR DOTNET v8 .NET 

En los siguientes pasos vamos a configurar el entorno de linux para correr nuestra aplicación NET CORE.

Instalar SDK .NET


```sh
sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-8.0
```

Instalar ASPNETCORE runtime

```sh
sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-8.0
```

Instalar dotnet runtime

```sh
sudo apt-get install -y dotnet-runtime-8.0
```

Instalar dependencias

```sh
sudo apt install zlib1g
```

Para validar la instalación de DOTNET ejecutar el siguiente comando


```sh
dotnet --version
```


Usando la terminal del servidor linux 

Ubicarse en la carpeta bin 

```sh
cd bin
```

Crear la carpeta para subir los proyectos NET

```sh
mkdir mydotnetapp
```

Asignar los permisos requeridos

```sh
chmod 400 nameFolder
```


Referencias


https://learn.microsoft.com/en-us/dotnet/core/install/linux-ubuntu-2204