### Compilar proyecto en windows y copiar a docker

Si bien es cierto el proyecto ya cuenta con un archivo de docker file, puede iniciarse automaticamente en docker, pero esta vez compilaremos el proyecto y subiremos los archivos compilados a docker usando la terminal

Ubicarse en la carpeta principal del proyecto

```sh
dotnet publish -c Release -r linux-x64
```

vamos a copiar los archivos generados
En la termina de powershell de windows trasladaremos el compilado a nuestra maquina linux

```sh
docker cp C:\Users\ClementeCayllahua\source\repos\ApiClimaTesting222\ApiClimaTesting222\bin\Release\net8.0\linux-x64\publish serverlinuxPrueba:/bin/mydotnetproject
```


Ir al directorio linux y ejecutar el siguiente comando 

```sh
nohup dotnet ApiClimaTesting222.dll > ApiClimaTesting.log 2>&1 &
```

Guardar el ID generado

```sh
[1] 902
```

para

Instalar el comando CURL para validar que carga la aplicación, indicar Y para continuar la instalación
```sh
sudo apt update
sudo apt install curl
```