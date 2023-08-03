---
title: <span id="_Toc447205590" class="anchor"></span>Firma de AutoFirma
  en Linux
---

AutoFirma Linux es una aplicación Java que se empaqueta en un archivo
*.deb* para su instalación en sistemas Linux derivados o compatibles con
Debian.

En Linux, se ejecuta directamente el archivo JAR de AutoFirma. No existe
un ejecutable propio de Linux.

El fichero *.deb* mediante el que se instala AutoFirma **no irá
firmado**. Esto se debe a que en Unix existen varios mecanismos de firma
y el sistema operativo, que por defecto no comprueba las firmas, puede
ser compatible sólo con uno de ellos. Firmar las aplicaciones para el
instalador podría originar errores en algunos sistemas en los que se
hubiese habilitado la comprobación de firmas, mientras que al no
firmarlas esto no ocurriría.

Así pues, el proceso completo de firma y empaquetado de AutoFirma Linux
será:

- Firma de los archivos JAR “AutoFirma.jar” y
  “AutoFirmaConfigurador.jar”.

- Empaquetado de los JAR firmados en un paquete instalador (*.deb*).

# Firma de los JAR de AutoFirma

El proceso de firma de firma de los JAR de AutoFirma Linux es el mismo
que en el resto de sistemas operativos. Se deberán firmar los ficheros
“AutoFirma.jar” y “AutoFirmaConfigurator.jar”.

Se puede revisar la documentación del comando de firma en el siguiente
enlace:

<http://docs.oracle.com/javase/6/docs/technotes/tools/windows/jarsigner.html>
