# Realizar la instalación de Java en el SO
# Ruben Abreu Gonzalez

- [¿Cómo instalar Java en Ubuntu desde repositorios](#¿cómo-instalar-java-en-ubuntu-desde-repositorios)
- [¿Cómo instalar una versión específica de Java?](#¿cómo-instalar-una-versión-específica-de-java)
- [Listar la versiones de OpenJDK instaladas](#listar-la-versiones-de-openjdk-instaladas)
- [Actualización de las variables de entorno](#actualización-de-las-variables-de-entorno)

## ¿Cómo instalar Java en Ubuntu desde repositorios?
- Lo primero debemos de actualizar el sistema con:
- sudo apt-get update
<details>
<summary>salida</summary>

```code
[sudo] contraseña para rabgonzalez:      	 
Ign:1 http://packages.linuxmint.com victoria InRelease
Obj:2 http://packages.linuxmint.com victoria Release              	 
Obj:4 http://archive.ubuntu.com/ubuntu jammy InRelease                    	 
Des:5 http://archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]  	 
Des:6 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]
Obj:7 http://archive.ubuntu.com/ubuntu jammy-backports InRelease    
Descargados 229 kB en 2s (143 kB/s)
Leyendo lista de paquetes... Hecho
```
</details>

- e instalamos Java con este comando:
- sudo apt-get install default-jdk
<details>
<summary>salida</summary>

```code
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
Se instalarán los siguientes paquetes adicionales:
  default-jdk-headless libice-dev libpthread-stubs0-dev libsm-dev libx11-6
  libx11-dev libx11-xcb1 libxau-dev libxcb1-dev libxdmcp-dev libxt-dev
  openjdk-11-jdk openjdk-11-jdk-headless openjdk-11-jre
  openjdk-11-jre-headless x11proto-dev xorg-sgml-doctools xtrans-dev
```
</details>

- comprobamos que tenemos instalado Java en nuestro sistema solo debemos de ejecutar:
- java --version
<details>
<summary>salida</summary>

```code
openjdk 11.0.20.1 2023-08-24
OpenJDK Runtime Environment (build 11.0.20.1+1-post-Ubuntu-0ubuntu122.04)
OpenJDK 64-Bit Server VM (build 11.0.20.1+1-post-Ubuntu-0ubuntu122.04, mixed mode, sharing)
```
</details>

## ¿Cómo instalar una versión específica de Java?
- Para instalar Ubuntu Java Open JDK ("la que utilizaremos en 1º").
OpenJDK:
- sudo apt install openjdk-11-jdk
<details>
<summary>salida</summary>

```code
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
openjdk-11-jdk ya está en su versión más reciente (11.0.20.1+1-0ubuntu1~22.04).
fijado openjdk-11-jdk como instalado manualmente.
0 actualizados, 0 nuevos se instalarán, 0 para eliminar y 204 no actualizados.
```
</details>

- sudo apt install openjdk-13-jdk
<details>
<summary>salida</summary>

```code
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
E: No se ha podido localizar el paquete openjdk-13-jdk
```
</details>

- sudo apt install openjdk-8-jdk
<details>
<summary>salida</summary>

```code
    Leyendo lista de paquetes... Hecho
    Creando árbol de dependencias... Hecho
    Leyendo la información de estado... Hecho
    Se instalarán los siguientes paquetes adicionales:
    fonts-dejavu-extra libatk-wrapper-java libatk-wrapper-java-jni openjdk-8-jdk-headless openjdk-8-jre openjdk-8-jre-headless
    Paquetes sugeridos:
    openjdk-8-demo openjdk-8-source visualvm fonts-nanum fonts-ipafont-gothic fonts-ipafont-mincho fonts-wqy-microhei fonts-wqy-zenhei
    Se instalarán los siguientes paquetes NUEVOS:
    fonts-dejavu-extra libatk-wrapper-java libatk-wrapper-java-jni openjdk-8-jdk openjdk-8-jdk-headless openjdk-8-jre openjdk-8-jre-headless
    0 actualizados, 7 nuevos se instalarán, 0 para eliminar y 204 no actualizados.
    Se necesita descargar 45,8 MB de archivos.
    Se utilizarán 156 MB de espacio de disco adicional después de esta operación.
    ¿Desea continuar? [S/n] S
```
</details>

- La versión que se debe de trabajar es la versión 8. Para ello verificaremos la versión de java que se está ejecutando con la sentencia:
- java --version
<details>
<summary>salida</summary>

```code
openjdk 11.0.20.1 2023-08-24
OpenJDK Runtime Environment (build 11.0.20.1+1-post-Ubuntu-0ubuntu122.04)
OpenJDK 64-Bit Server VM (build 11.0.20.1+1-post-Ubuntu-0ubuntu122.04, mixed mode, sharing)
```
</details>

## Listar la versiones de OpenJDK instaladas
- Ejecuta el siguiente comando para verificar que se han descargado las diferentes versiones de OpenJDK.
- ls /usr/lib/jvm
<details>
<summary>salida</summary>

```code
default-java  java-1.11.0-openjdk-amd64  java-11-openjdk-amd64  java-1.8.0-openjdk-amd64  java-8-openjdk-amd64  openjdk-11
```
</details>

## Actualización de las variables de entorno
- Edita y modifica el fichero profile, con los comandos:
- sudo update-alternatives --config java
<details>
<summary>salida</summary>

```code
Existen 2 opciones para la alternativa java (que provee /usr/bin/java).

  Selección   Ruta                                        	Prioridad  Estado
------------------------------------------------------------
* 0        	/usr/lib/jvm/java-11-openjdk-amd64/bin/java  	1111  	modo automático
  1        	/usr/lib/jvm/java-11-openjdk-amd64/bin/java  	1111  	modo manual
  2        	/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java   1081  	modo manual

Pulse <Intro> para mantener el valor por omisión [*] o pulse un número de selección: 1
```
</details>


- Otra opción es : añadir el siguiente código:
- Java version JAVA_HOME=/usr/lib/jvm/(SELECCIONA UN PATH DE LA VERSION QUE DESEAS QUE SE EJECUTE) PATH=$PATH:$HOME/bin:$JAVA_HOME/bin export JAVA_HOME export JRE_HOME export PATH
<details>
<summary>salida</summary>

```
```
</details>

- cd /etc/profile.d/
<details>
<summary>salida</summary>

```
```
</details>

- sudo nano java.sh
<details>
<summary>salida</summary>

```
```
</details>

- Haga que el script sea ejecutable con chmod:
- sudo chmod +x java.sh
<details>
<summary>salida</summary>

```code
```
</details>

- Finalmente, cargue las variables de entorno usando el comando de source
- source java.sh
<details>
<summary>salida</summary>

```
```
</details>
