---
title: |

  Manual para la generación del instalador Linux de AutoFirma
---

# Índice de contenidos

[1. Instalador .deb [3](#instalador-.deb)](#instalador-.deb)

[1.1. Preparación del entorno
[3](#preparación-del-entorno)](#preparación-del-entorno)

[1.1.1. Configuración de la dependencia con Java
[4](#configuración-de-la-dependencia-con-java)](#configuración-de-la-dependencia-con-java)

[1.1.2. Configuración de la versión de AutoFirma
[4](#configuración-de-la-versión-de-autofirma)](#configuración-de-la-versión-de-autofirma)

[1.2. Generación del instalador (.deb)
[4](#generación-del-instalador-.deb)](#generación-del-instalador-.deb)

[1.3. Instalación de la aplicación
[5](#instalación-de-la-aplicación)](#instalación-de-la-aplicación)

[1.4. Desinstalación de la aplicación
[5](#desinstalación-de-la-aplicación)](#desinstalación-de-la-aplicación)

[2. Instalador .rpm [5](#instalador-.rpm)](#instalador-.rpm)

[2.1. Preparación del entorno
[5](#preparación-del-entorno-1)](#preparación-del-entorno-1)

[1.1.1. Diferenciación de los entornos Fedora y OpenSUSE
[6](#diferenciación-de-los-entornos-fedora-y-opensuse)](#diferenciación-de-los-entornos-fedora-y-opensuse)

[1.1.2. Configuración de la versión de AutoFirma
[7](#configuración-de-la-versión-de-autofirma-1)](#configuración-de-la-versión-de-autofirma-1)

[2.2. Generación del instalador (.rpm)
[7](#generación-del-instalador-.rpm)](#generación-del-instalador-.rpm)

[2.3. Firma de los RPM [8](#firma-de-los-rpm)](#firma-de-los-rpm)

[2.3.1. Configurar entorno
[8](#configurar-entorno)](#configurar-entorno)

[2.3.2. Firmar RPM [9](#firmar-rpm)](#firmar-rpm)

[2.3.2.1. Comprobación de firma interna
[9](#comprobación-de-firma-interna)](#comprobación-de-firma-interna)

[2.3.2.2. Comprobación de firma externa
[9](#comprobación-de-firma-externa)](#comprobación-de-firma-externa)

[2.4. Generación de sha1sum
[9](#generación-de-sha1sum)](#generación-de-sha1sum)

[2.5. Instalación de la aplicación
[9](#instalación-de-la-aplicación-1)](#instalación-de-la-aplicación-1)

[2.6. Desinstalación de la aplicación
[10](#desinstalación-de-la-aplicación-1)](#desinstalación-de-la-aplicación-1)

[2.7. Actualización de la aplicación
[10](#actualización-de-la-aplicación)](#actualización-de-la-aplicación)

**  
**

1.  # Instalador .deb

    1.  # Preparación del entorno

Los recursos para la generación del instalador .deb de AutoFirma se
encuentran comprimidos en formato TAR en GitHub, en la dirección
<https://github.com/ctt-gob-es/clienteafirma/blob/master/afirma-simple-installer/linux/AutoFirmaLinuxInstaller_deb.tar.gz>

Este archivo contiene la estructura de directorios y los recursos
necesarios para generar el instalador de la aplicación. Este archivo
debe descomprimirse únicamente en un sistema Unix para garantizar que
los permisos de los ficheros no se ven alterados.

La estructura de directorios contenida en el archivo y su utilidad de
describe a continuación:

src -\> Directorio raíz

> /DEBIAN -\> Directorio donde se incluye la configuración y los
> *scripts*.

- control -\> fichero de configuración

- postint -\> script de post-instalación

- postrm -\> script de post-borrado

- prerm -\> script de pre-borrado

> /etc
>
> /firefox
>
> /pref

- AutoFirma.js -\> JavaScript que asocia el protocolo “afirma”

> /usr -\> Los ficheros de este directorio se copiarán en las carpetas
> respectivas de Linux
>
> /bin

- AutoFirma -\> Ejecuta AutoFirma.jar con los parámetros recibidos por
  URL

> /lib
>
> /AutoFirma -\> Directorio con los JAR de AutoFirma y su configurador

- AutoFirma.jar -\> Biblioteca de Autofirma. (DEBE INCLUIRLA EL
  ADMINISTRADOR).

- AutoFirmaConfigurador.jar -\> Biblioteca del instalador de AutoFirma.
  (DEBE INCLUIRLA EL ADMINISTRADOR).

> /share
>
> /applications

- afirma.desktop -\> Propiedades de AutoFirma como aplicación de
  escritorio

> /AutoFirma

- AutoFirma.png -\> Icono de la aplicación

> /doc
>
> /AutoFirma

- copyright -\> Información sobre la licencia de AutoFirma

## Configuración de la dependencia con Java

El instalador funciona indistintamente con Oracle JDK o con OpenJDK,
pero si se desea restringir a un entorno de ejecución de Java en
concreto o si se quiere cambiar de versión, en el fichero “control” hay
que editar la opción depends en función de la versión de java con la que
se quiere generar el instalador. En este caso:

- Depends: libnss3-tools

- Recomends : openjdk-11-jre

Adicionalmente, en este fichero se define la información de la
aplicación (versión, tamaño, etc.).

## Configuración de la versión de AutoFirma

Cada nueva versión de AutoFirma puede requerir que se actualicen
diversos textos de los ficheros de instalación. Ejemplos claros son el
número de versión y la fecha del *copyright*. Los textos susceptibles de
actualizarse se encuentran en los siguientes ficheros de la estructura
de directorios:

- src -\> DEBIAN -\> control

  - En este fichero se encuentran textos como el número de versión de
    AutoFirma, el correo de contacto, el tamaño que ocupa la aplicación
    una vez instalada o la URL de la página del producto.

- src -\> DEBIAN -\> copyright

  - En este fichero se muestra la información de licencia del producto y
    el año de *copyright*.

- src -\> usr -\> share -\> doc -\> AutoFirma -\> copyright

  - En este fichero se muestra la información de licencia del producto.

  1.  # Generación del instalador (.deb)

Para generar el instalador de AutoFirma es necesario añadir los JAR de
la última versión de AutoFirma y del configurador al directorio
“src/usr/lib/AutoFirma” de la estructura previamente comentada. Estos
ficheros deberán aparecer con los nombres:

- **AutoFirma.jar:** Última versión de AutoFirma (módulo “afirma-simple”
  de GitHub generado con la opción “-Denv=install” para que incluya
  todas las dependencias necesarias).

- **AutoFirmaConfigurador.jar**: Última versión del configurador de
  AutoFirma (módulo “afirma-ui-simple-configurator” de GitHub generado
  con la opción “-Denv=install” para que incluya todas las dependencias
  necesarias).

Para la generación crearemos el fichero por línea de comandos. Abriremos
una consola, nos situaremos a la altura del directorio “src” de la
estructura de directorios del paquete instalador y utilizaremos el
siguiente comando:

fakeroot dpkg-deb --build src AutoFirma_X\_Y.deb

Como resultado, se habrá generado en el directorio actual el archivo
instalador “AutoFirma_X\_Y.deb”.

La subcadena “X_Y” se deberá sustituir por el número de versión asignado
a la aplicación.

# Instalación de la aplicación

Para instalar el fichero generado existen dos opciones.

- Hacer doble clic sobre el fichero, el fichero se instalará mediante la
  instalación de paquetes de Ubuntu.

- Instalación por línea de comandos, ejecutando uno de los siguientes
  comandos (se supone que el *.deb* generado se llama
  AutoFirma_X\_Y.deb):

> sudo dpkg -i AutoFirma_X\_Y.deb

Si el comando anterior da un error por no encontrarse instaladas las
dependencias necesarias, se deberá ejecutar a continuación el comando:

> sudo apt-get –f install ./AutoFirma_X\_Y.deb

Según la versión de Ubuntu, también puede ser necesario ejecutar:

> sudo apt --fix-broken install

# Desinstalación de la aplicación

Para realizar la desinstalación de un fichero *.deb* en el sistema hay
que escribir el siguiente comando en la consola (requiere permisos de
administración)

sudo apt-get remove --purge autofirma

autofirma es el nombre del paquete con el que se ha instalado en la
aplicación, dicho nombre viene definido en el fichero control dentro de
src/DEBIAN

2.  # Instalador .rpm

    1.  # Preparación del entorno

En el repositorio se incluye por duplicado el directorio de recursos
necesario para generar el instalador de AutoFirma, uno pensado para la
generación del paquete RPM para Fedora y otro para OpenSuse. Este
directorio deberá situarse en su sistema de tal forma que en el
directorio raíz del usuario se encuentre inmediatamente el subdirectorio
“rpmbuild”.

La estructura de este directorio se describe a continuación:

> rpmbuild
>
> BUILD

- autofirma.js: Fichero que indica a Firefox como abrir AutoFirma.

- autofirma.png: Icono de la aplicación.

- autofirma.jar: Biblioteca de Autofirma. (DEBE INCLUIRLA EL
  > ADMINISTRADOR).

- autofirmaConfigurador.jar: Biblioteca del instalador de AutoFirma.
  > (DEBE INCLUIRLA EL ADMINISTRADOR).

- LICENSE: Fichero de licencia.

> BUILDROOT
>
> RPMS
>
> SOURCES

- autofirma.tar.gz: Archivo en el que se encuentra un fichero indicando
  donde se encuentra los ficheros fuente de la aplicación. Puede
  sustituirse por el mismo archivo con los auténticos ficheros fuente.

> SPECS

- autofirma.spec: Fichero de definición del proceso de instalación.

> SRPMS

## Diferenciación de los entornos Fedora y OpenSUSE

Los recursos utilizados para el empaquetado de las versiones de
AutoFirma para Fedora y OpenSUSE son muy similares. En ambos casos se
genera un instalador RPM, pero las diferencias entre ambas
distribuciones hacen necesario respetar una serie de diferencias. Se
proporciona un directorio con los recursos para cada instalador para que
no sea necesario modificar los distintos ficheros cada vez que deseen
construirse, pero se señalan a continuación las diferencias para que
quede constancia:

- Los nombres de las dependencias de NSS son distintos en ambos
  entornos, por ello, en el fichero “autofirma.spec”, esta dependencia
  se marca de la siguiente forma:

  - Fedora:

    - Requires: nss-tools

  - OpenSuse:

    - Requires: mozilla-nss-tools

- En OpenSuse, en el script de construcción, no se indicará en la
  primera línea el intérprete a utilizar. Por ello, en el apartado
  “%build” del fichero “autofirma.spec”:

  - Fedora:

    - La primera línea será “#!/bin/bash”.

  - OpenSuse:

    - Se escriben las líneas del script sin cabecera.

- Cambia el directorio clásico para los ficheros independientes de
  arquitectura. Por ello, en “autofirma.spec”, cambiarán algunas rutas:

  - Fedora:

    - Se utilizará la ruta “/usr/share/”.

  - OpenSuse:

    - Se utilizarán las rutas “/usr/share/” y “/usr/local/share/”.

- Indicaciones adicionales para el registro del esquema afirma en
  OpenSuse.

  - En OpenSuse se registra el esquema “afirma” también en los ficheros:

    - /usr/local/share/applications/mimeapps.list

    - /usr/share/applications/gnome-mimeapps.list

    - /usr/local/share/applications/gnome-mimeapps.list

    1.  ## Configuración de la versión de AutoFirma

Cada nueva versión de AutoFirma puede requerir que se actualicen
diversos textos de los ficheros de instalación. Ejemplos claros son el
número de versión y la fecha del *copyright*. Los textos susceptibles de
actualizarse se encuentran en los siguientes ficheros de la estructura
de directorios:

- rpmbuild -\> SPEC -\> autofirma.spec

  - En este fichero se encuentra el número de versión y revisión de la
    aplicación. Su licencia y el log de cambios de la versión.

- rpmbuild -\> BUILD -\> LICENSE

  - En este fichero se incluye el texto de licencia del producto.

  1.  # Generación del instalador (.rpm)

Para generar el instalador de AutoFirma es necesario añadir los JAR de
la última versión de AutoFirma y del configurador al directorio
“\~/rpmbuild/SOURCES” de la estructura previamente comentada. Estos
ficheros deberán aparecer con los nombres:

- **autofirma.jar:** Última versión de AutoFirma (módulo “afirma-simple”
  de GitHub generado con la opción “-Denv=install” para que incluya
  todas las dependencias necesarias).

- **autofirmaConfigurador.jar**: Última versión del configurador de
  AutoFirma (módulo “afirma-ui-simple-configurator” de GitHub generado
  con la opción “-Denv=install” para que incluya todas las dependencias
  necesarias).

Generaremos el instalador desde línea de comandos. Para ello, abriremos
una consola, nos situaremos a la altura del directorio “rpmbuild” de la
estructura de directorios del paquete instalador y utilizaremos el
siguiente comando:

rpmbuild -bb SPECS/autofirma.spec

Como resultado, se habrá generado en el directorio “RPMS” un directorio
“noarch” con el archivo instalador “autofirma-X.Y.Z-R.noarch.rpm”.

La subcadena “X.Y.Z-R” será el número de versión seguida de la revisión
de la aplicación.

# Firma de los RPM

Para la firma de los RPM utilizaremos una clave PGP.

# Configurar entorno

Para la firma con claves PGP, primeramente, será necesario configurar el
entorno:

1.  Instalar las claves en el almacén de claves local. Para ello,
    usaremos el comendo:

gpg --import private_key.asc

En este comando, “private_key.asc” será el fichero con las claves
pública y privada.

2.  Crearemos o editaremos el fichero "\~/.rpmmacros" con el siguiente
    contenido, indicando en el las rutas correspondientes:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p># Este valor siempre será “gpg”</p>
<p>%_signature gpg</p>
<p># Ruta completa al fichero “.gnupg”, comúnmente situado en el</p>
<p># directorio de usuario</p>
<p>%_gpg_path /home/usuario/.gnupg</p>
<p># Nombre con el que se creó la clave PGP. Se puede consultar con</p>
<p># el comando: gpg --list-secret-keys</p>
<p>%_gpg_name NOMBRE DE LA ENTIDAD</p>
<p># Ruta completa de ejecutable “gpg”. Puede obtenerse con el
comando:</p>
<p># which gpg</p>
<p>%_gpgbin /usr/bin/gpg</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

3.  Si no se tiene ya, instalar “rpm-sign” mediante el siguiente
    comando:

sudo yum install rpm-sign

# Firmar RPM

Para la firmar el instalador, basta con ejecutar el comando:

rpm --addsign autofirma-X.Y.Z.noarch.rpm

# Comprobación de firma interna

Para comprobar un RPM firmado usaremos el comando:

rpm --checksig autofirma-X.Y.Z.noarch.rpm

# Comprobación de firma externa

Para comprobar una firma externa (.sig) usaremos el comando:

gpg --verify autofirma-X.Y.Z.noarch.rpm.sig autofirma-X.Y.Z.noarch.rpm

# Generación de sha1sum

Al publicar el instalador es recomendable publicar también en la web las
huellas digitales de cada uno de los ficheros para que los usuarios
puedan comprobar la validez de los ficheros descargados. Se puede
generar la huella de todos los ficheros que deseemos con el comando:

sha1sum FICHERO

Para calcular la huella de todos los ficheros, se puede usar en el
directorio:

sha1sum \*

# Instalación de la aplicación

Antes de instalar la aplicación, si el instalador RPM de esta se ha
firmado, se debería agregar la clave pública PGP del firmante al almacén
de confianza del sistema. La clave pública PGP puede descargarse como un
fichero “.asc” junto al archivo de instalación. Para importar esta clave
PGP a nuestro almacén usaremos el comendo:

sudo rpm --import PUBLIC_KEY.asc

En este comando, “PUBLIC_KEY.asc” será el fichero con la clave pública.

Una vez importada la clave PGP, el sistema podrá validar automáticamente
la firma del instalador RPM. Para instalar AutoFirma a partir del
archivo RPM existen varias opciones, de las cuales se presentan dos:

1.  Hacer doble clic sobre el fichero, el fichero se instalará mediante
    el instalador de paquetes del sistema.

2.  Desde línea de comandos, ejecutar:

sudo rpm -i autofirma-X.Y.Z.noarch.rpm

En la sentencia anterior, “autofirma-X.Y.Z.noarch.rpm” sería el nombre
del fichero RPM que se desea instalar.

# Desinstalación de la aplicación

Para realizar la desinstalación de un fichero RPM en el sistema hay que
escribir el siguiente comando en la consola (requiere permisos de
administración)

sudo rpm –e autofirma

En la sentencia anterior, “autofirma” es el nombre predefinido del
paquete con el que se ha instalado en la aplicación, dicho nombre viene
definido en el fichero de especificación del instalador, por lo que la
sentencia debe escribirse tal cual.

# Actualización de la aplicación

El proceso de actualización de los RPM implica la instalación de una
versión y la desinstalación de la anterior. Debido a un problema en el
proceso de desinstalación de AutoFirma 1.7.1 y anteriores, al
desinstalarlas se eliminan también recursos de la versión a la que se
estaba desinstalando. Por este motivo, cuando queramos actualizar desde
AutoFirma 1.8 a una posterior, bastará usar el comando:

sudo rpm -U autofirma-X.Y.Z.noarch.rpm

Sin embargo, cuando estemos actualizando desde una versión anterior,
deberemos indicar que no se ejecute el proceso de desinstalación de esa
versión. Para ello usaremos el comando.

sudo rpm -U --nopreun --nopostun autofirma-X.Y.Z.noarch.rpm
