<img src="media/image2.wmf" style="width:6in;height:2.52222in" />

<img src="media/image3.png" style="width:0.91667in;height:0.32292in"
alt="Creative Commons License" />

Esta obra está bajo una licencia [Creative Commons
Reconocimiento-NoComercial-CompartirIgual 3.0
Unported](#cliente-v3.2.0).

1.  Índice

    [1 Introducción [3](#introducción)](#introducción)

    [1.1 Objeto [3](#objeto)](#objeto)

    [2 Gestión de versiones
    [4](#gestión-de-versiones)](#gestión-de-versiones)

    [2.1 Cliente @firma [4](#cliente-firma)](#cliente-firma)

    [2.1.1 Cliente v1.1 [4](#cliente-v1.1)](#cliente-v1.1)

    [2.1.2 Cliente v1.2 [4](#cliente-v1.2)](#cliente-v1.2)

    [2.1.3 Cliente v2.1 [5](#cliente-v2.1)](#cliente-v2.1)

    [2.1.4 Cliente v2.3 [5](#cliente-v2.3)](#cliente-v2.3)

    [2.1.5 Cliente v2.3.1 [6](#cliente-v2.3.1)](#cliente-v2.3.1)

    [2.1.6 Cliente v2.3.2 [6](#cliente-v2.3.2)](#cliente-v2.3.2)

    [2.1.7 Cliente v2.3.3 [6](#cliente-v2.3.3)](#cliente-v2.3.3)

    [2.1.8 Cliente v2.3.5 [7](#cliente-v2.3.5)](#cliente-v2.3.5)

    [2.1.9 Cliente v2.4 [8](#cliente-v2.4)](#cliente-v2.4)

    [2.1.10 Cliente v3.0.1 [8](#cliente-v3.0.1)](#cliente-v3.0.1)

    [2.1.11 Cliente v3.0.2 [9](#cliente-v3.0.2)](#cliente-v3.0.2)

    [2.1.12 Cliente v3.1.0 [10](#cliente-v3.1.0)](#cliente-v3.1.0)

    [2.1.13 Cliente v3.2.0 [11](#cliente-v3.2.0)](#cliente-v3.2.0)

    [2.1.14 Cliente v3.3.0 [13](#cliente-v3.3.0)](#cliente-v3.3.0)

    [2.1.15 Cliente v3.3.1 [14](#cliente-v3.3.1)](#cliente-v3.3.1)

    [2.1.16 Cliente v3.4 [15](#cliente-v3.4)](#cliente-v3.4)

    [Creative Commons [16](#_Toc417992902)](#_Toc417992902)

# Introducción

El Cliente de Firma es una herramienta de Firma Electrónica que funciona
en forma de Applet de Java integrado en una página Web mediante
JavaScript.

El Cliente hace uso de los certificados digitales X.509 y de las claves
privadas asociadas a los mismos que estén instalados en el repositorio o
almacén de claves y certificados (*keystore*) del navegador web
(*Internet Explorer, Mozilla, Firefox*) o el sistema operativo así como
de los que estén en dispositivos (tarjetas inteligentes*,* dispositivos
*USB*) configurados en el mismo (el caso de los DNI-e).

El Cliente de Firma, como su nombre indica, es una aplicación que se
ejecuta en cliente (en el ordenador del usuario, no en el servidor Web).
Esto es así para evitar que la clave privada asociada a un certificado
tenga que “salir” del contenedor del usuario (tarjeta, dispositivo USB o
navegador) ubicado en su PC. De hecho, nunca llega a salir del
navegador, el Cliente le envía los datos a firmar y éste los devuelve
firmados.

El Cliente de Firma contiene las interfaces y componentes web necesarios
para la realización de los siguientes procesos (además de otros
auxiliares como cálculos de hash, lectura de ficheros, etc…):

- Firma de datos y ficheros.

- Multifirma masiva de datos y ficheros.

- Cofirma (CoSignature) Multifirma al mismo nivel.

- Contrafirma (CounterSignature) Multifirma en cascada.

Como complemento al cliente de firma, se encuentra un cliente de cifrado
que nos permite realizar las funciones de encriptación y desencriptación
de datos atendiendo a diferentes algoritmos y configuraciones. Además
permite la generación de sobres digitales.

## Objeto

1.  El presente documento lista los cambios y agregados sufridos por el
    cliente @firma en cada una de sus versiones publicadas.

# Gestión de versiones

## Cliente @firma

### Cliente v1.1

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>1.1</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>11/2006</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Nuevas Funcionalidades</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Incorporación de funciones de cifrado simétrico.</p></li>
<li><p>Incorporación de modos de firma explícito e implícito en formato
CMS.</p></li>
<li><p>Añadida compatibilidad entre CMS y PKCS#7.</p></li>
<li><p>Añadidos demostraciones de uso.</p></li>
</ul></td>
</tr>
</tbody>
</table>

### Cliente v1.2

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>1.2</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>12/2006</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Nuevas Funcionalidades</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Incorporación de los formatos de firma XMLDSignature y XAdES
v1.1.1 como plugin.</p></li>
<li><p>Mejoras en el módulo de cifrado. Incorporación de claves
alfanuméricas no seguras.</p></li>
<li><p>Añadida la capacidad de introducir atributos firmados y no
firmados.</p></li>
<li><p>Añadidos ejemplos en código.</p></li>
<li><p>Mejorada la instalación e integración de plugins.</p></li>
</ul></td>
</tr>
</tbody>
</table>

### Cliente v2.1

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>2.1</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>3/2007</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Nuevas Funcionalidades</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Adaptación del formato de firma XADES a estándar 1.3.2.</p></li>
<li><p>Nueva distribución de elementos de firma XML.</p></li>
<li><p>Corrección de bugs relativos a representación gráfica en
Linux.</p></li>
<li><p>Corrección de bugs en generación de firmas XML.</p></li>
<li><p>Mejora del sistema de firmado en bloque.</p></li>
</ul></td>
</tr>
</tbody>
</table>

### Cliente v2.3

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>2.3</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>05/2007</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Nuevas Funcionalidades y corrección de bugs</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Corrección de bug de interpretación del árbol de firmas
CMS.</p></li>
<li><p>Corrección de contrafirma y cofirma CMS.</p></li>
<li><p>Capacidad de firma de ficheros remotos.</p></li>
</ul></td>
</tr>
</tbody>
</table>

###  Cliente v2.3.1

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>2.3.1</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>06/2007</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Corrección de bugs</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Corrección de bug relativo al filtrado de los certificados
durante el proceso de firma.</p></li>
</ul></td>
</tr>
</tbody>
</table>

### Cliente v2.3.2

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>2.3.2</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>08/2007</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Petición de la Junta de Andalucía</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Posibilidad de parametrización de la aparición de la ventana que
informa al usuario acerca del hash que va a proceder a firmar.</p></li>
<li><p>Aparición del disclaimer del instalador en negrita.</p></li>
</ul></td>
</tr>
</tbody>
</table>

### Cliente v2.3.3

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>2.3.3</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>07/09/2007</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Petición de la Junta de Andalucía</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Modificación de la DLL y del cliente para adaptación a formato
propietario de tarjetas SIEMENS, que no utilizan como alias de
certificados cadenas con codificación UTF-8.</p></li>
</ul></td>
</tr>
</tbody>
</table>

### Cliente v2.3.5

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>2.3.5</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>17/03/2008</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Nuevas Funcionalidades</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Soporte para Windows Vista e Internet Explorer 7, Red Hat 4 y
Guadalinex 4.</p></li>
<li><p>Mejora del sistema de instalación, se han quitado mensajes
redundantes en la instalación y desinstalación en lo referente a
sobrescritura de librerías y elementos compartidos.</p></li>
<li><p>Se han incorporados avisos informativos para las versiones beta
del cliente.</p></li>
<li><p>Se ha mejorado la distribución de librerías, reduciendo su
peso.</p></li>
<li><p>Mejora de la gestión de librarías dinámicas. Se ha creado un
sistema de factoría de las librerías requeridas por los sistemas
operativos (dll y so). Este sistema facilita la multiinstanciación del
applet.</p></li>
<li><p>Mejora/ampliación del plugin XAdES. Se han añadido modos de firma
(enveloped, enveloping y detached). Se permite tanto especificar un
mimetype a los datos de entrada como selección automática de éste
(siempre que sea posible). Mejorado el sistema de asignación de
identificadores. Mejorado el tratamiento interno del DOM. Se han quitado
las librerías antiguas y la dependencia de XALAN y XERCES.</p></li>
<li><p>Descifrado de sobres digitales. Totalmente funcional en XP. En
firefox funciona también en Vista, Windows 2000, Guadalinex, Ubuntu y
RedHat.</p></li>
<li><p>Mejorado el sistema de mensajes de error.</p></li>
<li><p>Corregido bug de Mozillla Firefox sobre SSL.</p></li>
<li><p>Mejora del sistema de carga específica para librerías.</p></li>
<li><p>Incluido soporte para la instalación de distintas distribuciones
en la misma máquina cliente.</p></li>
</ul></td>
</tr>
</tbody>
</table>

###  Cliente v2.4

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>2.4</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>14/04/2008</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Corrección de problemas conocidos en el cliente v2.3.5</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><p>Parametrización en properties de los mensajes de
usuario.</p>
<p>Modificación de mensajes de usuario para hacer el funcionamiento más
intuitivo, e inclusión de referencias a manuales de errores
conocidos.</p></td>
</tr>
</tbody>
</table>

### Cliente v3.0.1

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>3.0.1</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>23/03/2010</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Restructuración y nuevas funcionalidades</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Re-implementación completa del Cliente de firma, con los
siguientes objetivos:</p></li>
</ul>
<ul>
<li><blockquote>
<p>El cliente se basa ahora en la arquitectura de certificación y firma
electrónica definida en JCA (<em>Java Cryptography Architecture</em>),
omitiendo API propietarios siempre que es posible. (DigiDoc, IAIK,
etc.).</p>
</blockquote></li>
<li><blockquote>
<p>Cese de la compatibilidad con Java 1.4, permite usar ahora las
funcionalidades avanzadas de firma electrónica de Java 6 (incluso en
Java 5).</p>
</blockquote></li>
<li><blockquote>
<p>El soporte de Windows CAPI pasa a ser el estándar de Java, omitiendo
bibliotecas a medida, lo cual garantiza la compatibilidad con cualquier
versión y arquitectura de Windows soportada por el proveedor de
seguridad estándar de Java SunMSCAPI.</p>
</blockquote></li>
<li><blockquote>
<p>Eliminación de JSS y uso directo de NSS como dispositivo PKCS#11.
Esto proporciona compatibilidad con cualquier versión de Mozilla /
Firefox actual y futura.</p>
</blockquote></li>
<li><blockquote>
<p>Mejora del proceso de instalación, eliminando por completo la
necesidad de permisos de Administrador en JRE 6.</p>
</blockquote></li>
</ul>
<ul>
<li><p>Actualización de la firma ODF a la versión 3 (y superiores) de
OppenOffice.org, que difiere notablemente respecto a la versión 2 (y
rompe la retro-compatibilidad).</p></li>
<li><p>Soporte de SHA-2 en firmas PDF y ODF.</p></li>
<li><p>Soporte parcial de SHA-2 en firmas binarias.</p></li>
<li><p>Soporte preliminar de SHA-2 en firmas XML.</p></li>
<li><p>Inclusión de la cadena de certificación en las firmas siempre que
es posible.</p></li>
<li><p>Adecuación de los diálogos de usuario a las recomendaciones de
“Java Look and Feel” y “Windows Power Experience”.</p></li>
<li><p>Uso de “Java Logging API” para el registro de errores, mensajes y
advertencias.</p></li>
<li><p>Eliminación del sistema de plugins para adecuarse a las
necesidades de despliegue de Applets de Java 1.6u17 y
superiores.</p></li>
<li><p>Distribución del cliente en 3 configuraciones distintas: LITE
(con las funcionalidades genéricas del cliente y los formatos de firma
PKCS#7/CMS y CADES), MEDIA (con las capacidades de la configuración LITE
más los formatos de firma XMLdSig, XAdES y ODF) y COMPLETA (con las
capacidades de la configuración MEDIA más los formatos de firma
PDF).</p></li>
</ul>
<ul>
<li><p>Sólo se llega a publicar la construcción LITE.</p></li>
</ul></td>
</tr>
</tbody>
</table>

### Cliente v3.0.2

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>3.0.2</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>05/04/2010</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Corrección de bugs y mejoras generales.</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Mejoras en el sistema de identificación del formato de
ficheros.</p></li>
<li><p>Se agrega un mensaje de advertencia al cargar el almacén de
Firefox para avisar de que deben introducirse las tarjetas inteligentes
en ese momento.</p></li>
<li><p>Se soluciona el problema derivado de disponer de varios
certificados con el mismo alias en el almacén de Windows
(CAPI).</p></li>
</ul></td>
</tr>
</tbody>
</table>

###  Cliente v3.1.0

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>3.1.0</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>30/07/2010</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Corrección de bugs y mejoras generales.</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Se corrigen problemas en la carga del cliente.</p></li>
<li><p>Se habilita el uso de filtros de certificados acordes a la RFC
2254.</p></li>
<li><p>Se agrega soporte para el acceso al almacén con los certificados
de "Otras Personas" (WINDOWS ADDRESSBOOK) en Windows.</p></li>
<li><p>Siempre se accede al almacén del repositorio activo de Mozilla
Firefox.</p></li>
<li><p>Se añade la funcionalidad SignText análoga a la de los
navegadores Netscape.</p></li>
<li><p>Agregado nuevo sistema de despliegue basado en JNLP (necesario
Java 6).</p></li>
<li><p>Interfaz de escritorio para la ejecución del cliente (necesario
Java 6 u18 o superior).</p></li>
<li><p>Intalador offline para la instalación del cliente, la interfaz de
escritorio y documentación.</p></li>
<li><p>Se eliminan dependencias nativas en sistemas Windows.</p></li>
<li><p>Nuevo Formato de firma. Firmas OOXML compatible con Microsoft
Office 2007, 2008 y 2010.</p></li>
<li><p>Generación de firmas PDF compatibles con el estándar PAdES
(manteniendo compatibilidad con Adobe Reader y el estándar ISO
32000-1).</p></li>
<li><p>Se permite la generación de firmas binarias conforme al estándar
CAdES 1.8.1.</p></li>
<li><p>Se permite la generación de firmas XML conforme al estándar XAdES
1.4.1.</p></li>
<li><p>Se agrega la funcionalidad de firma de hojas de estilo
XML.</p></li>
<li><p>Soporte para agregar transformaciones personalizadas en las
firmas XML.</p></li>
<li><p>Corrección en la adecuación a estándar de las firmas
XAdES.</p></li>
<li><p>Se incorpora la funcionalidad de la selección del almacén de
certificados (incluidos certificados en disco).</p></li>
<li><p>Se incorpora la funcionalidad de la recuperación de certificados
en base 64 desde servidores LDAP.</p></li>
<li><p>Se incorpora la funcionalidad de almacenamiento y recuperación de
claves de cifrado en un almacén del usuario del sistema asociado al
cliente @firma.</p></li>
</ul></td>
</tr>
</tbody>
</table>

### Cliente v3.2.0

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>3.2.0</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>28/04/2011</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Despliegue a prueba de fallos y mejoras generales.</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Inclusión de un comprobador de entorno (en sustitución del
instalador clásico) que instala los componentes necesarios para
compatibilizar el entorno de ejecución de Java con el Cliente @firma
(bibliotecas <em>endorsed</em>, proveedores criptográficos,
etc.).</p></li>
<li><p>Se elimina el modo de despliegue con instalación local de código
Java y sus funcionalidades asociadas (actualizar, etc.).</p></li>
<li><p>Se comprueba que todos los ficheros instalados por el BootLoader
estén firmados, bien por el integrador, bien por Sun Microsystems /
Oracle.</p></li>
<li><p>Se utiliza el sistema de versionado de JNLP para reducir el
tráfico de red que causa solicitudes de autenticación con HTTPS (Ticket
143881).</p></li>
<li><p>Compatibilidad (limitada) con NSS 64 bits en Mac OS X con Java 64
bits.</p></li>
<li><p>Compatibilidad con Opera.</p></li>
<li><p>Se anexa el número de serie de certificado en el texto del
diálogo de selección para evitar problemas causados por dos certificados
(casi) iguales y el error 4165344 de Java (Ticket 145250).</p></li>
<li><p>Cuando se convierte de texto a Base64 mediante
getBase64FromText() se detecta la codificación en el caso de que el
texto fuese un XML bien formado y declarase el "encoding" en su cabecera
(Ticket 147618).</p></li>
<li><p>Uso de iText 2.1.7 para mejor compatibilidad de
licencias.</p></li>
<li><p>Compatibilidad con Java 7.</p></li>
<li><p>Actualización a BouncyCastle 1.46.</p></li>
<li><p>Se unifican las listas de destinatarios establecidas mediante los
métodos "setRecipientsToCMS()" y "addRecipientToCMS()".</p></li>
<li><p>Se permite que los sobres "Envuelto", "Firmado y Envuelto" y
"Autenticado y Envuelto" declaren varios remitentes.</p></li>
<li><p>Mejorada la identificación de ficheros PDF.</p></li>
<li><p>Compatibilidad con PDF cifrados con contraseña (no se soporta
AES256 ni certificados).</p></li>
<li><p>Advertencia cuando se intenta firmar un PDF certificado.</p></li>
<li><p>Compatibilidad con firmas LibreOffice / OpenOffice.org 3.2 /
3.3.</p></li>
<li><p>Creación de un nodo UnsignedProperties en firmas XAdES
independientemente si la firma incluye o no atributos sin firmar, para
facilitar la introducción posterior de estos.</p></li>
<li><p>Solventados errores en la cofirma de árboles complejos de
contrafirmas.</p></li>
<li><p>Se elimina la generación de firmas Externally Detached desde el
Applet de firma.</p></li>
<li><p>Cambio en el orden de las transformadas XML (enveloped siempre la
primera) para evitar errores en analizadores XML estrictos.</p></li>
<li><p>Tratamiento especial de los certificados sin cadena de confianza
para evitar la aparición de problemas asociados al error 4906869 de
Java.</p></li>
<li><p>Compatibilidad con Firefox 4.</p></li>
<li><p>Se introduce el método “changeLanguage()” para cambiar el idioma
del Cliente a otro disponible.</p></li>
<li><p>Mejoras genéricas en el despliegue en navegadores
Safari.</p></li>
<li><p>La licencia del producto se mostrará si está disponible en el
idioma del sistema del usuario, si no lo está se mostrará en
español.</p></li>
</ul></td>
</tr>
</tbody>
</table>

### Cliente v3.3.0

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>3.3.0</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>17/04/2012</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Actualización a las nuevas versiones de navegadores y JRE,
ampliación de entornos compatibles, inclusión de medidas de seguridad y
resolución de errores.</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Organización interna según la nueva arquitectura modular del
proyecto.</p></li>
<li><p>El método getSignCertificateBase64Encoded() devuelve siempre el
certificado seleccionado, incluso si no hay filtros
establecidos.</p></li>
<li><p>El método getFileBase64Encoded(URI, boolean) ya no muestra
diálogos modales innecesarios.</p></li>
<li><p>Ahora, el método setElectronicSignature(String) sustituye la
entrada de setElectronicSignatureFile(String) y viceversa.</p></li>
<li><p>Se eliminan los métodos Firma(), cipherData(byte[]),
decipherData(byte[]) y getCMSData().</p></li>
<li><p>El método setPlainData() siempre recibe una cadena en Base64 y
getPlainData() la devuelve en Base64.</p></li>
<li><p>Cuando no se indica el tipo de envoltura CMS que se desea
generar, el método buildCMSStructure() genera una firma
EnvelopedData.</p></li>
<li><p>El formato de firma por defecto pasa a ser CAdES.</p></li>
<li><p>Se agregan nuevos parámetros al método setpolicy() del Applet, el
cualificador de la política y su hash.</p></li>
<li><p>Por motivos de seguridad se pide permiso al usuario mediante un
diálogo modal cada vez que se vaya a cargar o guardar un fichero en
disco sin que este lo haya seleccionado explícitamente.</p></li>
<li><p>Se depreca el método getTextFromBase64() en favor del nuevo
método getTextFromBase64(charsetName).</p></li>
<li><p>Se depreca el método getBase64FromText() en favor del nuevo
método getBase64FromText(charsetName).</p></li>
<li><p>Se depreca el método getSignatureText() en favor del nuevo método
getSignatureText(charsetName).</p></li>
<li><p>Se depreca el método getTextFileContent() en favor del método
getFileBase64Encoded(String, boolean).</p></li>
<li><p>Se agrega compatibilidad con Firefox 9.</p></li>
<li><p>Se agrega compatibilidad con el almacén de certificados de
Firefox en Mac OS X.</p></li>
<li><p>Se solventa el problema que impedía firmar textos planos con el
formato de firma XAdES.</p></li>
<li><p>Mejora de la compatibilidad de Firefox cuando el nombre de
usuario de Windows contiene caracteres especiales.</p></li>
</ul></td>
</tr>
</tbody>
</table>

### Cliente v3.3.1

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>3.3.1</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>17/08/2012</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Actualización a las nuevas versiones de navegadores, resolución de
errores y nuevas características.</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Características Incluidas</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Se actualiza el mensaje del diálogo de licencia.</p></li>
<li><p>Se agrega la compatibilidad con Mozilla Firefox 11 y
superiores.</p></li>
<li><p>Se reconoce el tipo de fichero RAR para su identificación en
firmas.</p></li>
<li><p>Las firmas CAdES generadas con un algoritmo SHA-2 siempre
incluirán el atributo SigningCertificateV2.</p></li>
<li><p>Se agrega la propiedad "includeOnlySignningCertificate" mediante
el cual se puede evitar que se incluya toda la cadena de certificación
en las firmas/multifirmas XAdES/XMLdSig (necesario para compatibilidad
con versiones de la Plataforma @firma anteriores a la v5.5)</p></li>
<li><p>Cuando no se puede acceder al almacén del sistema, se configura
el tipo de almacén PKCS#12 para su uso.</p></li>
<li><p>Los nombres generados durante los proceso de firma masiva de
directorios ahora incluyen la partícula ".sign" o ".cosign" según se
haya firmado o cofirmado el fichero.</p></li>
<li><p>Ahora se permite el cambio de formato de firma en las operaciones
de firma masiva programática (no aplica a cofirmas y
contrafirmas).</p></li>
<li><p>Se incluye la firma de factura electrónica.</p></li>
</ul></td>
</tr>
</tbody>
</table>

### Cliente v3.4

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Emisión de Versión</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Desarrollo</strong></td>
<td><strong>ClienteFirma</strong></td>
</tr>
<tr class="even">
<td><strong>Nº Versión</strong></td>
<td><strong>3.4</strong></td>
</tr>
<tr class="odd">
<td><strong>Fecha</strong></td>
<td><strong>28/04/2015</strong></td>
</tr>
<tr class="even">
<td><strong>Motivo Generación</strong></td>
<td>Se abandonan entornos antiguos e incorporan otros nuevos, resolución
de errores y nuevas características.</td>
</tr>
<tr class="odd">
<td colspan="2"><strong>Cambios realizados</strong></td>
</tr>
<tr class="even">
<td colspan="2"><ul>
<li><p>Se incorpora la compatibilidad con Java 8 y se abandona la
compatibilidad con Java 5.</p></li>
<li><p>Se amplía la compatibilidad hasta su versión 37 de Mozilla
Firefox.</p></li>
<li><p>Se agrega la compatibilidad con Oracle Java en MacOS X.</p></li>
<li><p>Se agrega la posibilidad de recargar los certificados del diálogo
de selección y el cargar un PKCS#12 en lugar de usar uno de los
certificados del almacén.</p></li>
<li><p>Se hace posible agregar una rúbrica a las firmas PAdES.</p></li>
<li><p>Se habilita la función de firmar mediante <em>manifest</em> en
las firmas XAdES.</p></li>
<li><p>Se eliminan advertencias innecesarias de cara al
usuario.</p></li>
<li><p>Se eliminan funcionales residuales y desaconsejadas de versiones
antiguas del Cliente @firma:</p>
<ul>
<li><p>La firma de múltiples hashes.</p></li>
<li><p>La función de firma Web.</p></li>
<li><p>Los filtros de certificados compatibles con el Cliente
2.4.</p></li>
<li><p>El diálogo de confirmación con el hash de los datos que se va a
firmar</p></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

<span id="_Toc417992902" class="anchor"></span>Creative Commons

**Reconocimiento-NoComercial-CompartirIgual 3.0 Unported**

**Usted es libre de:**

| <img src="media/image5.png" style="width:0.52083in;height:0.52083in" 
 alt="share" />                                                        | Compartir - copiar, distribuir, ejecutar y comunicar públicamente la obra |
|----------------------------------------------------------------------|---------------------------------------------------------------------------|
| <img src="media/image6.png" style="width:0.52083in;height:0.52083in" 
 alt="remix" />                                                        | hacer obras derivadas                                                     |

**Bajo las condiciones siguientes:**

| <img src="media/image7.png" style="width:0.52083in;height:0.52083in" 
 alt="by" />                                                           | **Atribución** — Debe reconocer los créditos de la obra de la manera especificada por el autor o el licenciante (pero no de una manera que sugiera que tiene su apoyo o que apoyan el uso que hace de su obra). |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <img src="media/image8.png" style="width:0.52083in;height:0.52083in" 
 alt="nc" />                                                           | **No Comercial** — No puede utilizar esta obra para fines comerciales.                                                                                                                                          |
| <img src="media/image9.png" style="width:0.52083in;height:0.52083in" 
 alt="sa" />                                                           | **Compartir bajo la Misma Licencia** — Si altera o transforma esta obra, o genera una obra derivada, sólo puede distribuir la obra generada bajo una licencia idéntica a ésta.                                  |

**Entendiendo que:**

**Renuncia** — Alguna de estas condiciones puede no aplicarse si se
obtiene el permiso del titular de los derechos de autor

**Dominio Público** — Cuando la obra o alguno de sus elementos se halle
en el dominio público según la ley vigente aplicable, esta situación no
quedará afectada por la licencia.

**Otros derechos** — Los derechos siguientes no quedan afectados por la
licencia de ninguna manera:

- Los derechos derivados de usos legítimos u otras limitaciones
  > reconocidas por ley no se ven afectados por lo anterior.

- Los derechos morales del auto;

- Derechos que pueden ostentar otras personas sobre la propia obra o su
  > uso, como por ejemplo derechos de imagen o de privacidad.

  **Aviso** — Al reutilizar o distribuir la obra, tiene que dejar muy en
  claro los términos de la licencia de esta obra. La mejor forma de
  hacerlo es enlazar a esta página.

***Licencia***

LA OBRA O LA PRESTACIÓN (SEGÚN SE DEFINEN MÁS ADELANTE) SE PROPORCIONA
BAJO LOS TÉRMINOS DE ESTA LICENCIA PÚBLICA DE CREATIVE COMMONS (CCPL O
LICENCIA). LA OBRA O LA PRESTACIÓN SE ENCUENTRA PROTEGIDA POR LA LEY
ESPAÑOLA DE PROPIEDAD INTELECTUAL Y/O CUALESQUIERA OTRAS NORMAS QUE
RESULTEN DE APLICACIÓN. QUEDA PROHIBIDO CUALQUIER USO DE LA OBRA O
PRESTACIÓN DIFERENTE A LO AUTORIZADO BAJO ESTA LICENCIA O LO DISPUESTO
EN LA LEY DE PROPIEDAD INTELECTUAL.

MEDIANTE EL EJERCICIO DE CUALQUIER DERECHO SOBRE LA OBRA O LA
PRESTACIÓN, USTED ACEPTA Y CONSIENTE LAS LIMITACIONES Y OBLIGACIONES DE
ESTA LICENCIA, SIN PERJUICIO DE LA NECESIDAD DE CONSENTIMIENTO EXPRESO
EN CASO DE VIOLACIÓN PREVIA DE LOS TÉRMINOS DE LA MISMA. EL LICENCIADOR
LE CONCEDE LOS DERECHOS CONTENIDOS EN ESTA LICENCIA, SIEMPRE QUE USTED
ACEPTE LOS PRESENTES TÉRMINOS Y CONDICIONES.

**1. Definiciones**

1.  La **obra** es la creación literaria, artística o científica
    ofrecida bajo los términos de esta licencia.

<!-- -->

1.  En esta licencia se considera una **prestación** cualquier
    interpretación, ejecución, fonograma, grabación audiovisual, emisión
    o transmisión, mera fotografía u otros objetos protegidos por la
    legislación de propiedad intelectual vigente aplicable.

2.  La aplicación de esta licencia a una **colección** (definida más
    adelante) afectará únicamente a su estructura en cuanto forma de
    expresión de la selección o disposición de sus contenidos, no siendo
    extensiva a éstos. En este caso la colección tendrá la consideración
    de obra a efectos de esta licencia.

3.  El **titular originario** es:

<!-- -->

1.  En el caso de una obra literaria, artística o científica, la persona
    > natural o grupo de personas que creó la obra.

2.  En el caso de una obra colectiva, la persona que la edite y divulgue
    > bajo su nombre, salvo pacto contrario.

3.  En el caso de una interpretación o ejecución, el actor, cantante,
    > músico, o cualquier otra persona que represente, cante, lea,
    > recite, interprete o ejecute en cualquier forma una obra.

4.  En el caso de un fonograma, el productor fonográfico, es decir, la
    > persona natural o jurídica bajo cuya iniciativa y responsabilidad
    > se realiza por primera vez una fijación exclusivamente sonora de
    > la ejecución de una obra o de otros sonidos.

5.  En el caso de una grabación audiovisual, el productor de la
    > grabación, es decir, la persona natural o jurídica que tenga la
    > iniciativa y asuma la responsabilidad de las fijaciones de un
    > plano o secuencia de imágenes, con o sin sonido.

6.  En el caso de una emisión o una transmisión, la entidad de
    > radiodifusión.

7.  En el caso de una mera fotografía, aquella persona que la haya
    > realizado.

8.  En el caso de otros objetos protegidos por la legislación de
    > propiedad intelectual vigente, la persona que ésta señale.

<!-- -->

4.  Se considerarán **obras derivadas** aquellas obras creadas a partir
    de la licenciada, como por ejemplo: las traducciones y adaptaciones;
    las revisiones, actualizaciones y anotaciones; los compendios,
    resúmenes y extractos; los arreglos musicales y, en general,
    cualesquiera transformaciones de una obra literaria, artística o
    científica. Para evitar la duda, si la obra consiste en una
    composición musical o grabación de sonidos, la sincronización
    temporal de la obra con una imagen en movimiento (synching) será
    considerada como una obra derivada a efectos de esta licencia.

5.  Tendrán la consideración de **colecciones** la recopilación de obras
    ajenas, de datos o de otros elementos independientes como las
    antologías y las bases de datos que por la selección o disposición
    de sus contenidos constituyan creaciones intelectuales. La mera
    incorporación de una obra en una colección no dará lugar a una
    derivada a efectos de esta licencia.

6.  El **licenciador** es la persona o la entidad que ofrece la obra o
    prestación bajo los términos de esta licencia y le concede los
    derechos de explotación de la misma conforme a lo dispuesto en ella.

7.  **Usted** es la persona o la entidad que ejercita los derechos
    concedidos mediante esta licencia y que no ha violado previamente
    los términos de la misma con respecto a la obra o la prestación, o
    que ha recibido el permiso expreso del licenciador de ejercitar los
    derechos concedidos mediante esta licencia a pesar de una violación
    anterior.

8.  La **transformación** de una obra comprende su traducción,
    adaptación y cualquier otra modificación en su forma de la que se
    derive una obra diferente. La creación resultante de la
    transformación de una obra tendrá la consideración de obra derivada.

9.  Se entiende por **reproducción** la fijación directa o indirecta,
    provisional o permanente, por cualquier medio y en cualquier forma,
    de toda la obra o la prestación o de parte de ella, que permita su
    comunicación o la obtención de copias.

10. Se entiende por **distribución** la puesta a disposición del público
    del original o de las copias de la obra o la prestación, en un
    soporte tangible, mediante su venta, alquiler, préstamo o de
    cualquier otra forma.

11. Se entiende por **comunicación pública** todo acto por el cual una
    pluralidad de personas, que no pertenezcan al ámbito doméstico de
    quien la lleva a cabo, pueda tener acceso a la obra o la prestación
    sin previa distribución de ejemplares a cada una de ellas. Se
    considera comunicación pública la puesta a disposición del público
    de obras o prestaciones por procedimientos alámbricos o
    inalámbricos, de tal forma que cualquier persona pueda acceder a
    ellas desde el lugar y en el momento que elija.

12. La **explotación** de la obra o la prestación comprende la
    reproducción, la distribución, la comunicación pública y, en su
    caso, la transformación.

**2. Límites de los derechos.** Nada en esta licencia pretende reducir o
restringir cualesquiera límites legales de los derechos exclusivos del
titular de los derechos de propiedad intelectual de acuerdo con la Ley
de propiedad intelectual o cualesquiera otras leyes aplicables, ya sean
derivados de usos legítimos, tales como la copia privada o la cita, u
otras limitaciones como la resultante de la primera venta de ejemplares
(agotamiento).

**3. Concesión de licencia.** Conforme a los términos y a las
condiciones de esta licencia, el licenciador concede, por el plazo de
protección de los derechos de propiedad intelectual y a título gratuito,
una licencia de ámbito mundial no exclusiva que incluye los derechos
siguientes:

1.  Derecho de reproducción, distribución y comunicación pública de la
    obra o la prestación.

<!-- -->

13. Derecho a incorporar la obra o la prestación en una o más
    colecciones.

14. Derecho de reproducción, distribución y comunicación pública de la
    obra o la prestación lícitamente incorporada en una colección.

15. Derecho de transformación de la obra para crear una obra derivada
    siempre y cuando se incluya en ésta una indicación de la
    transformación o modificación efectuada.

16. Derecho de reproducción, distribución y comunicación pública de
    obras derivadas creadas a partir de la obra licenciada.

17. Derecho a extraer y reutilizar la obra o la prestación de una base
    de datos.

18. Para evitar cualquier duda, el titular originario:

<!-- -->

1.  Conserva el derecho a percibir las remuneraciones o compensaciones
    previstas por actos de explotación de la obra o prestación,
    calificadas por la ley como irrenunciables e inalienables, y sujetas
    a gestión colectiva obligatoria.

2.  Renuncia al derecho exclusivo a percibir, tanto individualmente como
    mediante una entidad de gestión colectiva de derechos, cualquier
    remuneración derivada de actos de explotación de la obra o
    prestación que usted realice.

Estos derechos se pueden ejercitar en todos los medios y formatos,
tangibles o intangibles, conocidos en el momento de la concesión de esta
licencia. Los derechos mencionados incluyen el derecho a efectuar las
modificaciones que sean precisas técnicamente para el ejercicio de los
derechos en otros medios y formatos. Todos los derechos no concedidos
expresamente por el licenciador quedan reservados, incluyendo, a título
enunciativo pero no limitativo, los derechos morales irrenunciables
reconocidos por la ley aplicable. En la medida en que el licenciador
ostente derechos exclusivos previstos por la ley nacional vigente que
implementa la directiva europea en materia de derecho sui generis sobre
bases de datos, renuncia expresamente a dichos derechos exclusivos.

**4. Restricciones.** La concesión de derechos que supone esta licencia
se encuentra sujeta y limitada a las restricciones siguientes:

1.  Usted puede reproducir, distribuir o comunicar públicamente la obra
    o prestación solamente bajo los términos de esta licencia y debe
    incluir una copia de la misma, o su Identificador Uniforme de
    Recurso (URI). Usted no puede ofrecer o imponer ninguna condición
    sobre la obra o prestación que altere o restrinja los términos de
    esta licencia o el ejercicio de sus derechos por parte de los
    concesionarios de la misma. Usted no puede sublicenciar la obra o
    prestación. Usted debe mantener intactos todos los avisos que se
    refieran a esta licencia y a la ausencia de garantías. Usted no
    puede reproducir, distribuir o comunicar públicamente la obra o
    prestación con medidas tecnológicas que controlen el acceso o el uso
    de una manera contraria a los términos de esta licencia. Esta
    sección 4.a también afecta a la obra o prestación incorporada en una
    colección, pero ello no implica que ésta en su conjunto quede
    automáticamente o deba quedar sujeta a los términos de la misma. En
    el caso que le sea requerido, previa comunicación del licenciador,
    si usted incorpora la obra en una colección y/o crea una obra
    derivada, deberá quitar cualquier crédito requerido en el apartado
    4.b, en la medida de lo posible.

<!-- -->

19. Si usted reproduce, distribuye o comunica públicamente la obra o la
    prestación, una colección que la incorpore o cualquier obra
    derivada, debe mantener intactos todos los avisos sobre la propiedad
    intelectual e indicar, de manera razonable conforme al medio o a los
    medios que usted esté utilizando:

<!-- -->

1.  El nombre del autor original, o el seudónimo si es el caso, así como
    el del titular originario, si le es facilitado.

2.  El nombre de aquellas partes (por ejemplo: institución, publicación,
    revista) que el titular originario y/o el licenciador designen para
    ser reconocidos en el aviso legal, las condiciones de uso, o de
    cualquier otra manera razonable.

3.  El título de la obra o la prestación si le es facilitado.

4.  El URI, si existe, que el licenciador especifique para ser vinculado
    a la obra o la prestación, a menos que tal URI no se refiera al
    aviso legal o a la información sobre la licencia de la obra o la
    prestación.

5.  En el caso de una obra derivada, un aviso que identifique la
    transformación de la obra en la obra derivada (p. ej., "traducción
    castellana de la obra de Autor Original," o "guión basado en obra
    original de Autor Original").

    Este reconocimiento debe hacerse de manera razonable. En el caso de
    una obra derivada o incorporación en una colección estos créditos
    deberán aparecer como mínimo en el mismo lugar donde se hallen los
    correspondientes a otros autores o titulares y de forma comparable a
    los mismos. Para evitar la duda, los créditos requeridos en esta
    sección sólo serán utilizados a efectos de atribución de la obra o
    la prestación en la manera especificada anteriormente. Sin un
    permiso previo por escrito, usted no puede afirmar ni dar a entender
    implícitamente ni explícitamente ninguna conexión, patrocinio o
    aprobación por parte del titular originario, el licenciador y/o las
    partes reconocidas hacia usted o hacia el uso que hace de la obra o
    la prestación.

<!-- -->

20. Para evitar cualquier duda, debe hacerse notar que las restricciones
    anteriores (párrafos 4.a y 4.b) no son de aplicación a aquellas
    partes de la obra o la prestación objeto de esta licencia que
    únicamente puedan ser protegidas mediante el derecho sui generis
    sobre bases de datos recogido por la ley nacional vigente
    implementando la directiva europea de bases de datos

**5. Exoneración de responsabilidad**

A MENOS QUE SE ACUERDE MUTUAMENTE ENTRE LAS PARTES, EL LICENCIADOR
OFRECE LA OBRA O LA PRESTACIÓN TAL CUAL (ON AN "AS-IS" BASIS) Y NO
CONFIERE NINGUNA GARANTÍA DE CUALQUIER TIPO RESPECTO DE LA OBRA O LA
PRESTACIÓN O DE LA PRESENCIA O AUSENCIA DE ERRORES QUE PUEDAN O NO SER
DESCUBIERTOS. ALGUNAS JURISDICCIONES NO PERMITEN LA EXCLUSIÓN DE TALES
GARANTÍAS, POR LO QUE TAL EXCLUSIÓN PUEDE NO SER DE APLICACIÓN A USTED.

**6. Limitación de responsabilidad.** SALVO QUE LO DISPONGA EXPRESA E
IMPERATIVAMENTE LA LEY APLICABLE, EN NINGÚN CASO EL LICENCIADOR SERÁ
RESPONSABLE ANTE USTED POR CUALESQUIERA DAÑOS RESULTANTES, GENERALES O
ESPECIALES (INCLUIDO EL DAÑO EMERGENTE Y EL LUCRO CESANTE), FORTUITOS O
CAUSALES, DIRECTOS O INDIRECTOS, PRODUCIDOS EN CONEXIÓN CON ESTA
LICENCIA O EL USO DE LA OBRA O LA PRESTACIÓN, INCLUSO SI EL LICENCIADOR
HUBIERA SIDO INFORMADO DE LA POSIBILIDAD DE TALES DAÑOS.

**7. Finalización de la licencia**

1.  Esta licencia y la concesión de los derechos que contiene terminarán
    automáticamente en caso de cualquier incumplimiento de los términos
    de la misma. Las personas o entidades que hayan recibido de usted
    obras derivadas o colecciones bajo esta licencia, sin embargo, no
    verán sus licencias finalizadas, siempre que tales personas o
    entidades se mantengan en el cumplimiento íntegro de esta licencia.
    Las secciones 1, 2, 5, 6, 7 y 8 permanecerán vigentes pese a
    cualquier finalización de esta licencia.

<!-- -->

21. Conforme a las condiciones y términos anteriores, la concesión de
    derechos de esta licencia es vigente por todo el plazo de protección
    de los derechos de propiedad intelectual según la ley aplicable. A
    pesar de lo anterior, el licenciador se reserva el derecho a
    divulgar o publicar la obra o la prestación en condiciones distintas
    a las presentes, o de retirar la obra o la prestación en cualquier
    momento. No obstante, ello no supondrá dar por concluida esta
    licencia (o cualquier otra licencia que haya sido concedida, o sea
    necesario ser concedida, bajo los términos de esta licencia), que
    continuará vigente y con efectos completos a no ser que haya
    finalizado conforme a lo establecido anteriormente, sin perjuicio
    del derecho moral de arrepentimiento en los términos reconocidos por
    la ley de propiedad intelectual aplicable.

**8. Miscelánea**

1.  Cada vez que usted realice cualquier tipo de explotación de la obra
    o la prestación, o de una colección que la incorpore, el licenciador
    ofrece a los terceros y sucesivos licenciatarios la concesión de
    derechos sobre la obra o la prestación en las mismas condiciones y
    términos que la licencia concedida a usted.

<!-- -->

22. Cada vez que usted realice cualquier tipo de explotación de una obra
    derivada, el licenciador ofrece a los terceros y sucesivos
    licenciatarios la concesión de derechos sobre la obra objeto de esta
    licencia en las mismas condiciones y términos que la licencia
    concedida a usted.

23. Si alguna disposición de esta licencia resulta inválida o
    inaplicable según la Ley vigente, ello no afectará la validez o
    aplicabilidad del resto de los términos de esta licencia y, sin
    ninguna acción adicional por cualquiera las partes de este acuerdo,
    tal disposición se entenderá reformada en lo estrictamente necesario
    para hacer que tal disposición sea válida y ejecutiva.

24. No se entenderá que existe renuncia respecto de algún término o
    disposición de esta licencia, ni que se consiente violación alguna
    de la misma, a menos que tal renuncia o consentimiento figure por
    escrito y lleve la firma de la parte que renuncie o consienta.

25. Esta licencia constituye el acuerdo pleno entre las partes con
    respecto a la obra o la prestación objeto de la licencia. No caben
    interpretaciones, acuerdos o condiciones con respecto a la obra o la
    prestación que no se encuentren expresamente especificados en la
    presente licencia. El licenciador no estará obligado por ninguna
    disposición complementaria que pueda aparecer en cualquier
    comunicación que le haga llegar usted. Esta licencia no se puede
    modificar sin el mutuo acuerdo por escrito entre el licenciador y
    usted.
