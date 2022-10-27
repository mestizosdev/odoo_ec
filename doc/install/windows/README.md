## Manual de Instalación de Oddo 15.0 en Windows 11

### Requerimientos 
 
| Versión  | Software       |
|----------|----------------|
| 3.8.10   | Python 64 bits |
| 16.11.4  | VS Build Tools |
| 0.12.5-1 | Wkhtmltopdf    |
| 2.33.0   | Git            |
| 13.4     | Postgresql     |
| 15.0     | Odoo           |

### 1. Instalación de Python
Descargar la versión de Python 3.8.10 (64 Bits) para Windows   [Información de la página oficial](https://www.python.org)


Instalar con las opciones recomendadas, incluyendo el path de Python:
La ruta del path se encontrara en las siguientes rutas:
```
C:\Users\......\AppData\Local\Programs\Python\Python38
```
```
C:\Users\......\AppData\Local\Programs\Python\Python38\Scripts
```
Se debe seleccionar las opciones, indicadas en la siguiente ilustración:

![img.png](images/i_python0.png)

Es opcional la actualización del pip
```
python -m pip install --upgrade pip 
```

### 2. Instalación de VS Build Tools

Descargar la versión de VS Build Tools 3.8.10 (64 Bits) para Windows 


[Información de la página oficial](https://visualstudio.microsoft.com/es/downloads/)

![img.png](images/v_VsBuildTools.png)

Una vez descargada la versión VS Build Tools 3.8.10 (64 Bits) para Windows, se debe seleccionar las opciones, mostradas en la siguiente ilustración: 

![img.png](images/i_vsbuildtools1.png)

### 3. Instalación de herramientas de línea de comandos (wkhtmltopdf)   

[Información de la página oficial](https://github.com/wkhtmltopdf/wkhtmltopdf/releases/tag/0.12.5)


Descargar las herramientas de línea de comandos de código abierto (LGPLv3) para convertir HTML en PDF y varios formatos de imagen utilizando el motor de renderizado Qt WebKit. La versión a descargar es la siguiente:
```
wkhtmltox-0.12.5-1.msvc2015-win64.exe
```

### 4. Instalación de Git  

[Información de la página oficial](https://git-scm.com/downloads)

Descargar la versión 2.33.0 (64 Bits) para Windows. En la instalación se deberá seleccionar las configuraciones señalados en la siguiente ilustración:


### 5. Instalación de PostgreSQL 13.4 (64 Bits)

[Información de la página oficial](https://www.postgresql.org)

Descargar la versión 13.4 (64 Bits) de PostgreSQL para Windows. En la instalación se deberan seleccionar los items señalados en las siguientes ilustraciones:


A continuación se deberá crear una nueva conexión con el servidor de PostgreSQL, para este caso la llamaremos ***localhost***

![img.png](images/i_postgresql2.png)

En el Tab ***Connection***, se deberá ingresar un Password

![img.png](images/i_postgresql3.png)

A continuación se deberá crear un Rol para gestionar las Bases de Datos

![img.png](images/i_postgresql4.png)

![img.png](images/i_postgresql15.png)

![img.png](images/i_postgresql6.png)

![img.png](images/i_postgresql7.png)

### 6. Clonación del Repositorio de Odoo 15.0  [Información de la página oficial](https://github.com/odoo/odoo)

Se deberá crear un directorio (carpeta), en la ubicación que el usuario a bien tuviere hacerlo, para clonar el repositorio de Odoo


Una vez seleccionada la versión 15.0 de Oddo, procedemos a seleccionar el comando de clonación

![img.png](images/i_odoo2.png)

Ejecutaremos el siguiente comando :
```
$ git clone https://github.com/odoo/odoo.git --depth=1 -b 15.0 
```
![img.png](images/i_odoo3.png)

La sección: $ ***git clone***, es propia del comando de clonación de Odoo  
```
$ git clone 
```
La sección: ***https://github.com/odoo/odoo.git***, corresponde al comando de clonación de Odoo  
```
https://github.com/odoo/odoo.git
```
La sección: ***--depth=1 -b 15.0***, corresponde a la última versión de Odoo 15.0
```
--depth=1 -b 15.0
```
Una vez clonado el repositorio de Odoo 15.0, se deberá ingresar en la carpeta creada, llamada odoo y se ejecutará el siguiente comando:
```
C:\odoo\odoo>pip install setuptools wheel
```

A continuación, en el directorio de clonación se deberá de editar el archivo : ***requeriments.txt***, de la siguiente manera:

```
python-stdnum==1.16
```
```
libsass==0.21.0
```
```
passlib==1.7.2
```
```
cryptography==3.4.8
```

### 7. Instalación de ***venv*** Python (Entorno Virtual de Python) 

***Únicamente en el caso***, que no se ejecutacen los comandos de Python en las carpetas de Windows, se deberán utilizar los siguientes comandos: 
### Paso 1:
```
C:\Users\admin\Projects\odoo> Get-ExecutionPolicy
```
### Paso 2:
```
C:\Users\admin\Projects\odoo> Get-ExecutionPolicy -List
```
### Paso 3:
Se deberá abrir otra terminal con permisos de Administrador y ejecutar el siguiente comando:
```
C:\Users\admin>Set-ExecutionPolicy  -ExecutionPolicy AllSigned
```
Una vez superados los pasos anteriores se deberá ejecutar el siguiente comando en la ruta (Ejemplo):
```
C:\Users\admin>pip install virtualenv
```
Para crear los Scripts del proyecto se deberá ejecutar el siguiente comando en la ruta (Ejemplo): 
```
C:\Users\admin\Projects\odoo>python -m venv ./venv
```
Una vez ejecutado el comando anterior se deberían crear los siguientes directorios 
```
C:\Users\admin\Projects\odoo\venv\Scripts
```
Para habilitar el ***entorno virtual*** de Python, se deberá ejecutar el siguiente comando en un ***terminal con privilegios de Administrador***, en  la ruta (Ejemplo):
```
C:\Users\admin\Projects\odoo> .\venv\Scripts\activate
```
Se deberá seleccionar la opción [E] Ejecutar para siempre:, y si todos los pasos anteriores se realizaron satisfactoriamente el ***Prompt***, tendrá el siguiente aspecto:
```
(venv)PS C:\Users\admin\Projects\odoo>
```
Para la instalación de todos los requerimientos de la instancia de odoo en la computadora local, se ejecutará el siguiente comando:

![img.png](images/i_odoo5.png)

### 8. Ejecución de Odoo 15.0

Se abrirá un terminal y se ejecutará el siguiente comando:

![img.png](images/e_odoo1.png)
```
El parametro: -d odoo15 es la conexión del servidor creada en la Sección 4. Instalación de PostgreSQL 13.4 (64 Bits)
```
```
El parametro: -r graham es el nombre del Rol, asignado en la Sección 4. Instalación de PostgreSQL 13.4 (64 Bits)
```
```
El parametro: -w mypassword es el password del Rol, asignado en la Sección 4. Instalación de PostgreSQL 13.4 (64 Bits)
```
Para Finalizar, si los pasos anteriores se realizaron satisfactoriamente se deberá abrir un navegador web y escribir la siguiente URL:
```