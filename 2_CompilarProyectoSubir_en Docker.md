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

Modificar el archivo appsetting.json, esta modificación lo puedes realizar al momento de crear tu proyecto .NET, para el 
caso estamos direccionando desde el puerto 8080 a 5000 por esa razon en la URL se visualiza http://0.0.0.0:5000 , al momento de crear se definió para redireccionar

```sh
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*",
  "Kestrel": {
    "Endpoints": {
      "Http": {
        "Url": "http://0.0.0.0:5000"
      }
    }
  }
}
```

Ir al directorio linux y ejecutar el siguiente comando 

```sh
nohup dotnet ApiClimaTesting222.dll > ApiClimaTesting.log 2>&1 &
```

Guardar el ID generado

```sh
[1] 902
```

Para validar ir a la pc principal en su navegador digitar el nombre del equipo

```sh
http://backend:8080/WeatherForecast
```