---
title: Arquitectura del Cliente @firma
---

Índice de contenidos

[1 Arquitectura de Módulos del proyecto Cliente @firma
[4](#arquitectura-de-módulos-del-proyecto-cliente-firma)](#arquitectura-de-módulos-del-proyecto-cliente-firma)

[1.1 Descripción general
[4](#descripción-general)](#descripción-general)

[1.2 Núcleo [5](#núcleo)](#núcleo)

[1.2.1 Módulo afirma-core [5](#módulo-afirma-core)](#módulo-afirma-core)

[1.2.2 Módulo afirma-ui-core-jse
[5](#módulo-afirma-ui-core-jse)](#módulo-afirma-ui-core-jse)

[1.3 Gestión de almacenes de claves y certificados
[6](#gestión-de-almacenes-de-claves-y-certificados)](#gestión-de-almacenes-de-claves-y-certificados)

[1.3.1 Módulo afirma-core-keystores
[6](#módulo-afirma-core-keystores)](#módulo-afirma-core-keystores)

[1.3.2 Módulo afirma-keystores-mozilla
[7](#módulo-afirma-keystores-mozilla)](#módulo-afirma-keystores-mozilla)

[1.3.3 Módulo afirma-keystores-single
[8](#módulo-afirma-keystores-single)](#módulo-afirma-keystores-single)

[1.3.4 Módulo afirma-keystores-capiaddressbook
[9](#módulo-afirma-keystores-capiaddressbook)](#módulo-afirma-keystores-capiaddressbook)

[1.4 Realización de firmas binarias
[9](#realización-de-firmas-binarias)](#realización-de-firmas-binarias)

[1.4.1 Módulo afirma-crypto-core-pkcs7
[10](#módulo-afirma-crypto-core-pkcs7)](#módulo-afirma-crypto-core-pkcs7)

[1.4.2 Módulo afirma-crypto-cades
[11](#módulo-afirma-crypto-cades)](#módulo-afirma-crypto-cades)

[1.4.3 Módulo afirma-crypto-cades-multi
[12](#módulo-afirma-crypto-cades-multi)](#módulo-afirma-crypto-cades-multi)

[1.4.4 Módulo afirma-crypto-cades-enveloper
[13](#módulo-afirma-crypto-cades-enveloper)](#módulo-afirma-crypto-cades-enveloper)

[1.4.5 Módulo afirma-crypto-pades
[14](#módulo-afirma-crypto-pades)](#módulo-afirma-crypto-pades)

[1.4.6 Módulo afirma-crypto-cms
[15](#módulo-afirma-crypto-cms)](#módulo-afirma-crypto-cms)

[1.4.7 Módulo afirma-crypto-cms-enveloper
[16](#módulo-afirma-crypto-cms-enveloper)](#módulo-afirma-crypto-cms-enveloper)

[1.5 Realización de firmas XML
[17](#realización-de-firmas-xml)](#realización-de-firmas-xml)

[1.5.1 Módulo afirma-crypto-core-xml
[17](#módulo-afirma-crypto-core-xml)](#módulo-afirma-crypto-core-xml)

[1.5.2 Módulo afirma-crypto-xades
[18](#módulo-afirma-crypto-xades)](#módulo-afirma-crypto-xades)

[1.5.3 Módulo afirma-crypto-xmlsignature
[19](#módulo-afirma-crypto-xmlsignature)](#módulo-afirma-crypto-xmlsignature)

[1.5.4 Módulo afirma-crypto-odf
[20](#módulo-afirma-crypto-odf)](#módulo-afirma-crypto-odf)

[1.5.5 Módulo afirma-crypto-ooxml
[20](#módulo-afirma-crypto-ooxml)](#módulo-afirma-crypto-ooxml)

[1.6 Realización de cifrados simétricos
[22](#realización-de-cifrados-simétricos)](#realización-de-cifrados-simétricos)

[1.6.1 Módulo afirma-crypto-cipher
[22](#módulo-afirma-crypto-cipher)](#módulo-afirma-crypto-cipher)

[1.7 Realización de firmas / multifirmas masivas
[23](#realización-de-firmas-multifirmas-masivas)](#realización-de-firmas-multifirmas-masivas)

[1.7.1 Módulo afirma-core-massive
[23](#módulo-afirma-core-massive)](#módulo-afirma-core-massive)

[2 Dependencias del Applet @firma respecto a los módulos
[25](#dependencias-del-applet-firma-respecto-a-los-módulos)](#dependencias-del-applet-firma-respecto-a-los-módulos)

[2.1 Descripción general
[25](#descripción-general-1)](#descripción-general-1)

[3 Dependencias del MiniApplet @firma respecto a los módulos
[26](#dependencias-del-miniapplet-firma-respecto-a-los-módulos)](#dependencias-del-miniapplet-firma-respecto-a-los-módulos)

[3.1 Descripción general
[26](#descripción-general-2)](#descripción-general-2)

[4 Dependencias del interfaz Standalone respecto a los módulos
[27](#dependencias-del-interfaz-standalone-respecto-a-los-módulos)](#dependencias-del-interfaz-standalone-respecto-a-los-módulos)

[4.1 Descripción general
[27](#descripción-general-3)](#descripción-general-3)

[5 Dependencias de SimpleAfirma respecto a los módulos
[28](#dependencias-de-simpleafirma-respecto-a-los-módulos)](#dependencias-de-simpleafirma-respecto-a-los-módulos)

[5.1 Descripción general
[28](#descripción-general-4)](#descripción-general-4)

# Arquitectura de Módulos del proyecto Cliente @firma

![](media/image1.emf)

## Descripción general

El proyecto @firma se compone de una serie de módulos funcionales con
ciertas dependencias de cohesión y un mínimo acoplamiento que forman un
árbol de sub-proyectos.

Esta separación en módulos funcionales permite a los desarrolladores
crear nuevos productos reutilizando partes de @firma de forma sencilla,
a la vez que facilita la evolución, el mantenimiento y la evolución de
las propias aplicaciones del proyecto Cliente @firma.

## Núcleo

<img src="media/image2.png" style="width:1.24419in;height:0.95526in"
alt="C:\Users\Tomas\workspace\afirma-core\src\main\java\es\gob\afirma\core\doc-files\package-info-1.png" />

1.  1.  
    2.  

### Módulo afirma-core

El módulo central del proyecto (afirma-core) es la base para el resto de
los módulos, y contiene tanto los interfaces que definen las
funcionalidades clave del proyecto (firma electrónica, cifrado, etc.)
como una serie de clases de utilidad (incluyendo excepciones básicas)
que son de uso generalizado para el resto de los módulos.

El módulo afirma-core es compatible con JSE 1.5 (y superiores) y con
Apache Batik (lo que le proporciona compatibilidad con Google Android
2.2 y superiores).

El módulo, presenta a su vez dos dependencias:

- Dependencia dinámica con la biblioteca “Java Mime Magic Library 0.1.0”
  (que a su vez puede tener dependencias con “Apache Jakarta ORO
  2.0.8”), utilizada por la clase es.gob.afirma.core.misc.MimeHelper
  para la detección de tipos de contenido.

  - Al ser dinámica, el módulo afirma-core es funcional (no presenta
    errores ni en tiempo de ejecución ni en tiempo de compilación)
    incluso si esta biblioteca no se encuentra en el CLASSPATH, pero en
    este caso no se realizará detección de tipo de contenido y siempre
    se devolverá el valor por defecto (contenido binario genérico).

- Dependencia dinámica con el módulo afirma-ui-core-jse.

  - Al ser dinámica, el módulo afirma-core no presenta errores en tiempo
    de compilación) incluso si este módulo no se encuentra en el
    CLASSPATH, pero en este caso cualquier operación que requiera un
    interfaz gráfico resultará en error.

#### Bibliotecas o código de terceros

- Bibliotecas externas:

  - Java Mime Magic Library 0.1.0

  - Apache Jakarta ORO 2.0.8

  - Apache Commons Logging 1.1.1

- Código incluido:

  - com.sun.deploy.util.WinRegistry basado en la clase de igual nombre
    de OpenJDK.

  - es.gob.afirma.core.misc.Base64 basado en código de Mikael Grev con
    licencia BSD.

### Módulo afirma-ui-core-jse

Para mejorar la portabilidad del núcleo a plataformas que no cuenten con
Swing o AWT para la creación y gestión de interfaces gráficos, todas las
operaciones relacionadas con estos interfaces gráficas se separan en un
sub-proyecto diferente.

Aunque las funcionalidades principales de este módulo se declaran en el
interfaz es.gob.afirma.core.ui.AOUIManager, se incluyen también otras
clases y métodos de utilidad adicionales.

Este módulo es compatible con JSE 1.5, y debe ser sustituido por
implementaciones alternativas cuando se desee usar el Cliente @firma
haciendo uso de las capacidades gráficas predefinidas en Google Android
u otras plataformas distintas a JSE 1.5 (y superiores). Igualmente, es
conveniente su sustitución cuando se use el Cliente @firma en sistemas
servidores sin entorno gráfico.

## Gestión de almacenes de claves y certificados

![](media/image3.emf)

Una de las funcionalidades más importante en cualquier aplicación de
firma electrónica es el acceso a las funcionalidades de gestión de
certificados y claves privadas con las que se van a realizar las firmas
(u otras operaciones criptográficas).

Se soportan múltiples tipos de almacenes (PKCS#12, Windows CAPI, Mac OS
X Keychain, Java, etc.), con la peculiaridad de que mediante dos únicas
clases (es.gob.afirma.keystores.main.common.AOKeyStoreManager y
es.gob.afirma.keystores.main.common.AOKeyStoreManagerFactory) se
gestionan tanto almacenes de tipo KeyStore como de tipo CertStore.

### Módulo afirma-core-keystores

<img src="media/image4.png" style="width:1.43282in;height:1.2093in"
alt="C:\Users\Tomas\workspace\afirma-core-keystores\src\main\java\es\gob\afirma\keystores\main\doc-files\package-info-1.png" />

Este módulo incorpora el soporte de la mayoría de tipos de almacén,
además de las implementaciones de los interfaces del núcleo relacionados
con almacenes de claves y certificados.

Los tipos soportados son:

- PKCS#12

- Java KeyStore (todas las variantes).

- PKCS#11

  - Incluyendo DNIe vía PKCS#11

- Windows CAPI

  - Certificados personales

  - Certificados raíz

- Llavero de Mac OS X

El módulo hace uso de interfaces gráficas (solicitud de contraseñas o
PIN), por lo que necesita que el núcleo cuente con el módulo
afirma-core-ui-jse (o una re-implementación del mismo).

El módulo afirma-core-keystores es compatible con JSE 1.5 (y superiores)
y con Apache Batik (lo que le proporciona compatibilidad con Google
Android 2.2 y superiores), con la precaución de que en entornos
distintos a JSE 1.5 o superiores es necesaria una re-implementación
compatible del módulo afirma-core-ui-jse si se usan funcionalidades que
necesiten interfaz gráfico.

### Módulo afirma-keystores-mozilla

<img src="media/image5.png" style="width:1.5814in;height:2.02743in"
alt="C:\Users\Tomas\workspace\afirma-keystores-mozilla\doc\es\gob\afirma\keystores\mozilla\doc-files\package-info-1.png" />

La gestión de almacenes NSS (*Netscape Security Services*), usados por
los productos Mozilla (Firefox, ThunderBird, SeaMonkey, etc.) presenta
numerosas diferencias respecto a los otros tipos soportados por
afirma-core-keystores, por lo que se encuentra separado en un módulo
independiente. Pese a esta separación, la factoría principal
(es.gob.afirma.keystores.main.common.AOKeyStoreManagerFactory) será
capaz de trabajar con estos almacenes cuando afirma-keystores-mozilla
esté en el CLASSPATH.

Este módulo soporta únicamente el almacén de certificados personales (no
raíz o autoridades intermedias), y necesita que el sistema cuente con
las bibliotecas NSS (Netscape Security Services) correctamente
instaladas y de la misma arquitectura que el JRE.

El módulo afirma-keystores-mozilla es compatible con JSE 1.5 (y
superiores), con la precaución de que en entornos distintos a JSE 1.5 o
superiores es necesaria una re-implementación compatible del módulo
afirma-core-ui-jse si se usan funcionalidades que necesiten interfaz
gráfico.

Ha sido probado con NSS de 32 y 64 bits en Windows, Linux, Mac OS X y
Solaris. En Mac OS X puede requerir la realización de cambios
persistentes en el sistema, para lo cual solicitará la contraseña de
administración la primera vez que se ejecute.

#### Bibliotecas o código de terceros

- Código incluido:

  - es.gob.afirma.keystores.mozilla.MozillaKeyStoreUtilities contiene
    porciones inspiradas en clases de OpenJDK.

### Módulo afirma-keystores-single

<img src="media/image6.png" style="width:0.61529in;height:1.32558in"
alt="C:\Users\Tomas\workspace\afirma-keystores-single\doc\es\gob\afirma\keystores\single\doc-files\package-info-1.png" />

El módulo afirma-keystores-single es directamente un proveedor
criptográfico JCA/JCE que implementa el SPI (*Service Provider
Interface*) KeyStore añadiendo un almacén llamado PKCS7 que permite
tratar como KeyStore certificados en disco en formato PKCS#7 o
directamente X.509 (tanto binarios como Base64).

Para usar este módulo es necesario instalarlo en Java como proveedor
criptográfico JCE/JCA y obtener el KeyStore de nombre PKCS7. No se
implementa el SPI CertStore.

El módulo afirma-keystores-single es compatible con JSE 1.5 (y
superiores) y con Apache Batik (lo que le proporciona compatibilidad con
Google Android 2.2 y superiores), con la precaución de que en entornos
distintos a JSE 1.5 o superiores es necesaria una re-implementación
compatible del módulo afirma-core-ui-jse si se usan funcionalidades que
necesiten interfaz gráfico.

### Módulo afirma-keystores-capiaddressbook

Este módulo no tiene ninguna dependencia externa, ni con bibliotecas ni
con otros módulos del Cliente @firma.

El módulo afirma-keystores-capiaddressbook es directamente un proveedor
criptográfico JCA/JCE que implementa el SPI (*Service Provider
Interface*) KeyStore añadiendo dos almacenes (llamados
Windows-ADDESSBOOK y Windows-CA) permite tratar como KeyStore
certificados en loa almacenes de Windows “Libreta de Direcciones” y
“Autoridades de Certificación” respectivamente.

Para usar este módulo es necesario instalarlo en Java como proveedor
criptográfico JCE/JCA y obtener el KeyStore de nombre PKCS7. No se
implementa el SPI CertStore.

El módulo afirma-core-addressbook es compatible con JSE 1.6 (y
superiores) únicamente en entornos MS-Windows. En JRE 64 bits es
necesario que este incluya el proveedor SunMSCAPI. No se soporta la
arquitectura IA64.

#### Bibliotecas o código de terceros

- Código incluido:

  - sun.security.mscapi contiene porciones del proveedor de seguridad
    SunMSCAPI de OpenJDK.

## Realización de firmas binarias

![](media/image7.emf)

Los módulos de realización de firmas binarias contienen las
funcionalidades necesarias para la creación y gestión de firmas
electrónicas y sobres digitales en formatos PKCS#7 y derivados, donde
encontramos los siguientes formatos:

- Firmas electrónicas

  - CMS

  - CAdES

  - PAdES

- Sobres digitales

  - CMS

  - CAdES

### Módulo afirma-crypto-core-pkcs7

<img src="media/image8.png" style="width:1.4186in;height:1.48559in"
alt="C:\Users\Tomas\workspace\afirma-crypto-core-pkcs7\src\main\java\es\gob\afirma\signers\pkcs7\doc-files\package-info-1.png" />

El módulo afirma-crypto-core-pkcs7 contiene métodos de utilidad para la
creación de firmas electrónicas en formatos derivados de PKCS#7, pero no
provee ninguna funcionalidad directa a los usuarios (ni siquiera genera
firmas en formato PKCS#7), es un módulo de uso interno por parte de
otros módulos.

Por motivos organizativos, este módulo presenta a su vez un sub-módulo
llamado afirma-crypto-core-pkcs7-tsp, que por simplicidad no se trata de
forma separada ni se muestra en los diagramas, considerándose que ambos
forman un único módulo integral.

El módulo presenta dependencia directa únicamente con el núcleo (módulo
afirma-core) y con las bibliotecas externas BouncyCastle (proveedor,
correo y TSP).

El módulo no realiza ninguna llamada a interfaces gráficos y es
compatible con JSE 1.5 y superiores y con Apache Batik (Android) 3 y
superiores. Para compatibilidad con Android 2.x es necesario
refactorizar el proyecto sustituyendo BouncyCastle por SpongyCastle.

#### Bibliotecas o código de terceros

- Bibliotecas externas:

  - BouncyCastle 1.46.

### Módulo afirma-crypto-cades

<img src="media/image9.png" style="width:2.30315in;height:2.0748in" />

El módulo afirma-crypto-cades contiene la funcionalidad para la
generación de firmas electrónicas binaria acordes al estándar CAdES.
Además de la propia funcionalidad de firma, contiene los métodos
necesarios para la generación de multifirmas CAdES.

El módulo presenta dependencia directa con el núcleo (módulo
afirma-core), con el módulo de firma binaria (afirma-crypto-core-pkcs7)
y con las bibliotecas externas BouncyCastle (proveedor y correo). Para
la generación de multifirmas CAdES debe cubrirse también una dependencia
dinámica con el módulo afirma-crypto-cades-multi.

El módulo no realiza ninguna llamada a interfaces gráficos y es
compatible con JSE 1.5 y superiores y con Apache Batik (Android) 3 y
superiores. Para compatibilidad con Android 2.x es necesario
refactorizar el proyecto sustituyendo BouncyCastle por SpongyCastle.

#### Bibliotecas o código de terceros

- Bibliotecas externas:

  - BouncyCastle 1.46.

### Módulo afirma-crypto-cades-multi

<img src="media/image10.png" style="width:1.90551in;height:2.38976in" />

El módulo afirma-crypto-cades-multi contiene los métodos para la
generación de multifirmas cades: cofirmas (firmas paralelas) y
contrafirmas (firmas en cascada). Los usuarios no utilizarán estos
métodos de forma directa, sino a través del manejador de firma CAdES
(es.gob.afirma.crypto.cades.AOCAdESSigner) existente en el módulo
afirma-crypto-cades.

El módulo presenta dependencia directa con el módulo de firma CAdES
(afirma-crypto-cades), con las funcionalidades de firma binaria
(afirma-crypto-core-pkcs7), así como del propio de núcleo (módulo
afirma-core) y con las bibliotecas externas BouncyCastle (proveedor y
correo).

El módulo no realiza ninguna llamada a interfaces gráficos y es
compatible con JSE 1.5 y superiores y con Apache Batik (Android) 3 y
superiores. Para compatibilidad con Android 2.x es necesario
refactorizar el proyecto sustituyendo BouncyCastle por SpongyCastle.

#### Bibliotecas o código de terceros

- Bibliotecas externas:

  - BouncyCastle 1.46.

### Módulo afirma-crypto-cades-enveloper

<img src="media/image11.png" style="width:2.43701in;height:3.05906in" />

El módulo afirma-crypto-cades-enveloper contiene los métodos para la
generación de las siguientes estructuras CAdES:

- Data

- DigestedData

- EncryptedData

- EnvelopedData

- SignedAndEnvelopedData

El módulo presenta dependencia directa con el núcleo (módulo
afirma-core), el módulo CAdES (afirma-crypto-cades) , a través del que
realiza las firmas de los empaquetados que la requieren y con las
bibliotecas externas BouncyCastle (proveedor y correo). Adicionalmente,
existe una dependencia indirecta con el módulo PKCS#7
(afirma-crypto-core-pkcs7), necesario para el tratamiento de las firmas
binarias.

El módulo no realiza ninguna llamada a interfaces gráficos y es
compatible con JSE 1.5 y superiores y con Apache Batik (Android) 3 y
superiores. Para compatibilidad con Android 2.x es necesario
refactorizar el proyecto sustituyendo BouncyCastle por SpongyCastle.

#### Bibliotecas o código de terceros

- Bibliotecas externas:

  - BouncyCastle 1.46.

### Módulo afirma-crypto-pades

<img src="media/image12.png" style="width:2.80709in;height:2.27953in" />

El módulo afirma-crypto-pades contiene los métodos para firmar
electrónicamente documentos PDF. La firma PAdES es una firma derivada de
CAdES que se inserta dentro de un documento PDF y se registra de forma
concreta en su diccionario interno.

El módulo depende directamente del módulo de firma CAdES
(afirma-crypto-cades), del núcleo (módulo afirma-core) y de la
biblioteca externa iText, para el manejo de documentos PDF. A su vez,
depende indirectamente de las bibliotecas externas BouncyCastle
(proveedor, correo y TSP) y del núcleo de firma binaria (módulo
afirma-crypto-core-pkcs7). Para su ejecución desde entornos JSE, será
necesario cubrir la dependencia del núcleo con el módulo
afirma-core-ui-jse.

El módulo es compatible con JSE 1.5 y superiores y con Apache Batik
(Android) 3 y superiores. Para compatibilidad con Android 2.x es
necesario refactorizar el proyecto sustituyendo BouncyCastle por
SpongyCastle. En sistemas Android, será necesario remplazar el módulo
afirma-core-ui-jse por otro que maneje correctamente los interfaces
gráficos del entorno.

#### Bibliotecas o código de terceros

- Bibliotecas externas:

  - BouncyCastle 1.46.

  - iText 2.1.7.

### Módulo afirma-crypto-cms

<img src="media/image13.png" style="width:2.43701in;height:2.41732in" />

El módulo afirma-crypto-cms contiene los métodos para la firma y
multifirma electrónica binaria en formato CMS, variante evolucionada de
PKCS#7. El único *contentType* CMS soportado por este módulo es
*signedData*, el correspondiente a las firmas electrónicas CMS.

El módulo presenta dependencia directa con el núcleo (módulo
afirma-core), con el módulo PKCS#7 (afirma-crypto-core-pkcs7) y con las
bibliotecas externas BouncyCastle (proveedor y correo).

El módulo no realiza ninguna llamada a interfaces gráficos y es
compatible con JSE 1.5 y superiores y con Apache Batik (Android) 3 y
superiores. Para compatibilidad con Android 2.x es necesario
refactorizar el proyecto sustituyendo BouncyCastle por SpongyCastle.

#### Bibliotecas o código de terceros

- Bibliotecas externas:

  - BouncyCastle 1.46.

### Módulo afirma-crypto-cms-enveloper

<img src="media/image14.png" style="width:2.43701in;height:3.05906in" />

El módulo afirma-crypto-cms-enveloper contiene los métodos para la
generación de las siguientes estructuras CMS:

- AuthenticatedData

- AuthenticatedAndEnvelopedData

- CompressedData

- Data

- DigestedData

- EncryptedData

- EnvelopedData

- SignedAndEnvelopedData

El módulo presenta dependencia directa con el núcleo (módulo
afirma-core), el módulo CMS (afirma-crypto-cms) , a través del que
realiza las firmas de los empaquetados que la requieren y con las
bibliotecas externas BouncyCastle (proveedor y correo). Adicionalmente,
existe una dependencia indirecta con el módulo PKCS#7
(afirma-crypto-core-pkcs7), necesario para el tratamiento de las firmas
binarias.

El módulo no realiza ninguna llamada a interfaces gráficos y es
compatible con JSE 1.5 y superiores y con Apache Batik (Android) 3 y
superiores. Para compatibilidad con Android 2.x es necesario
refactorizar el proyecto sustituyendo BouncyCastle por SpongyCastle.

#### Bibliotecas o código de terceros

- Bibliotecas externas:

  - BouncyCastle 1.46.

## Realización de firmas XML

![](media/image15.emf)

Los módulos de realización de firmas XML contienen las funcionalidades
necesarias para la creación y gestión de firmas electrónicas XML. Los
formatos de firma que se ajustan a esta categoría son:

- XAdES

- XMLDSig

- ODF

- OOXML

### Módulo afirma-crypto-core-xml

<img src="media/image16.png" style="width:0.64961in;height:1.37795in" />

El módulo afirma-crypto-core-xml contiene métodos de utilidad necesarios
para el tratamiento de firmas XML, independientemente de su formato
concreto. Este módulo no provee ninguna funcionalidad directa a los
usuarios, es un módulo de utilidad para su uso por otros módulos.

El módulo presenta dependencia directa únicamente con el núcleo del
proyecto (módulo afirma-core).

Desde este módulo no se realiza ninguna llamada a interfaces gráficos y
es compatible con JSE 1.6 y superiores.

### Módulo afirma-crypto-xades

<img src="media/image17.png" style="width:3.42126in;height:2.28346in" />

El módulo afirma-crypto-xades contiene la funcionalidad para la
generación de firmas electrónicas XML avanzadas acordes al estándar
XAdES. El módulo está preparado para la generación de este tipo de
firmas en sus variantes Internally Detached, Enveloping y Enveloped.
También permite la multifirma en este formato.

Existe dependencia directa de este módulo con el núcleo del Cliente
(módulo afirma-core), el módulo de firmas XML (afirma-crypto-core-xml) y
la biblioteca externa JXAdES. Para tener acceso a la funcionalidad
completa del módulo es necesario cubrir dos dependencias adicionales, la
biblioteca externa JMimeMagic, que permite identificar el tipo de
contenido firmado, y el módulo de interfaces gráficos correspondiente al
entorno en cuestión, por defecto, JSE (afirma-core-ui-jse), que permite
mostrar un diálogo auxiliar para localizar las hojas de estilo
declaradas cuando es necesario.

La biblioteca externa JMimeMagic tiene a su vez dependencias con las
bibliotecas Apache Log4Java y Apache Oro. Debido a que estas son
dependencias externas se omitirán para simplificar el diagrama de
arquitectura.

El módulo es compatible con JSE 1.6 y superiores.

#### Bibliotecas o código de terceros

- Bibliotecas externas:

  - JXAdES (Build 5705)

  - JMimeMagic 0.1.0

### Módulo afirma-crypto-xmlsignature

<img src="media/image18.png" style="width:2.58661in;height:2.28346in" />

El módulo afirma-crypto-xmlsignature contiene la funcionalidad para la
generación de firmas electrónicas XML acordes al estándar XMLdSig. El
módulo está preparado para la generación de este tipo de firmas en sus
variantes Internally Detached, Enveloping y Enveloped. También permite
la multifirma en este formato, completando las deficiencias en la
declaración de este estándar con estructuras propias de XAdES (firma
avanzada).

Este módulo presenta dependencias directas con el núcleo del Cliente
(módulo afirma-core) y el módulo de firmas XML (afirma-crypto-core-xml).
Adicionalmente, para tener acceso a la funcionalidad completa del módulo
es necesario cubrir dos dependencias adicionales, la biblioteca externa
JMimeMagic, que permite identificar el tipo de contenido firmado, y el
módulo de interfaces gráficos correspondiente al entorno en cuestión,
por defecto, JSE (afirma-core-ui-jse), que permite mostrar un diálogo
auxiliar para localizar las hojas de estilo declaradas cuando es
necesario.

La biblioteca externa JMimeMagic tiene a su vez dependencias con las
bibliotecas Apache Log4Java y Apache Oro. Debido a que estas son
dependencias externas se omitirán para simplificar el diagrama de
arquitectura.

El módulo es compatible con JSE 1.6 y superiores.

#### Bibliotecas o código de terceros

- Bibliotecas externas:

  - JMimeMagic 0.1.0

### Módulo afirma-crypto-odf

<img src="media/image19.png" style="width:1.83071in;height:1.51969in" />

El módulo afirma-crypto-odf contiene la funcionalidad necesaria para
agregar firmas a un documento ODF (*Open Document File*). Las firmas
generadas son variantes de XMLdSig que se insertan y declaran en los
documentos ODF. Las firmas generadas por el módulo son compatibles con
LibreOffice y OpenOffice.org 3.2 y superiores. El módulo permite la
creación de firmas compatibles con OpenOffice.org 3.1, pero estas
dejarán de ser compatibles con versiones superiores de esta herramienta.

Este módulo presenta dependencias directas con el núcleo del Cliente
(módulo afirma-core) y el módulo de firmas XML (afirma-crypto-core-xml).

El módulo es compatible con JSE 1.6 y superiores.

### Módulo afirma-crypto-ooxml

<img src="media/image20.png" style="width:2.64961in;height:3.26378in" />

El módulo afirma-crypto-ooxml contiene la funcionalidad necesaria para
agregar firmas electrónicas a un documento OOXML (*Office Open XML*).
Las firmas generadas son variantes de XMLdSig que se insertan y declaran
en los documentos OOXML.

Este módulo presenta dependencias directas con el núcleo del Cliente
(módulo afirma-core), el módulo de firma XMLdSig
(afirma-crypto-xmlsignature, que a su vez depende de
afirma-crypto-core-xml) y la biblioteca externa Apache Commons-IO.

El módulo es compatible con JSE 1.6 y superiores.

## Realización de cifrados simétricos

![](media/image21.emf)

Los cifrados simétricos no hacen uso de certificados ni algoritmos RSA o
DSA, sino que usan o claves adaptadas para los distintos algoritmos de
cifrado o contraseñas que los usuarios pueden recordar e introducir
directamente.

### Módulo afirma-crypto-cipher

<img src="media/image22.png" style="width:1.62598in;height:1.44882in" />

El módulo de cifrado (afirma-crypto-cipher) hace uso del proveedor Sun
JCE para la realización de cifrados simétricos en base a claves y
contraseñas. Los algoritmos de cifrado soportados son:

- Mediante clave

  - AES

  - ARCFOUR

  - BLOWFISH

  - DES

  - TripleDES

  - RC2

- Mediante contraseña

  - PBE con SHA1 y TripleDES

  - PBE con SHA1 y RC2.40

  - PBE con MD5 y DDES

Este módulo depende directamente del núcleo (módulo afirma-core) y, de
forma indirecta, de un módulo de interfaces gráficos, por defecto, el de
JSE (afirma-core-ui-jse).

El módulo es compatible con JSE 1.5 y superiores.

## Realización de firmas / multifirmas masivas

![](media/image23.emf)

Se llaman firmas masivas a los procesos en los que se firman
consecutivamente varios ficheros. Estas firmas consecutivas pueden
realizarse sin interacción intermedia del usuario y las listas de
ficheros a firmas pueden establecerse por varios medios, externamente de
forma programática o con una lógica interna basada en directorios y
carpetas del sistema de ficheros.

### Módulo afirma-core-massive

<img src="media/image24.png" style="width:5.51042in;height:3.87649in" />

El módulo afirma-core-massive proporciona dos mecanismos para la firma
masiva de datos. Estos son:

- Firma/Multifirma de directorios: Proporciona los métodos para firmar y
  multifirmar los ficheros de un directorio. Admite configurar el
  comportamiento de las operaciones individuales, las opciones de firma,
  filtrar ficheros por extensión …

- Firma/Multifirma programática: Proporciona los métodos necesarios para
  firmar o multifirmar datos, proporcionando estos, un fichero o su
  huella digital.

Este módulo depende directamente del núcleo (módulo afirma-core) del
proyecto. A su vez, enlaza dinámicamente con cualquier módulo de firma
que agregue al proyecto, heredando todas sus dependencias.

El módulo es compatible con JSE 1.5 y superiores.

## Utilidades

### Módulo afirma-util

El módulo afirma-util contiene clases de utilidad para la gestión de
validez de certificados.

Es compatible con Java 1.5 y superiores, depende únicamente del núcleo y
no usa bibliotecas externas ni contiene código de terceros.

# Dependencias del Applet @firma respecto a los módulos

## Descripción general

El Applet @firma es un Applet para la realización de firmas y
multifirmas electrónicas, cifrados simétricos y sobre digitales. También
permite la operación de masiva de firmas electrónicas.

El applet @firma tiene como dependencias los módulos del Cliente del
siguiente listado:

- afirma-core

- afirma-ui-core-jse

- afirma-core-keystores

- afirma-keystores-mozilla

- afirma-keystores-single

- afirma-keystores-capiaddressbook

- afirma-crypto-core-pkcs7

- afirma-crypto-cades

- afirma-crypto-cades-multi

- afirma-crypto-pades

- afirma-crypto-cms

- afirma-crypto-cms-enveloper

- afirma-crypto-core-xml

- afirma-crypto-xades

- afirma-crypto-xmlsignature

- afirma-crypto-odf

- afirma-crypto-ooxml

- afirma-crypto-cipher

- afirma-core-massive

- afirma-util

# Dependencias del MiniApplet @firma respecto a los módulos

## Descripción general

El MiniApplet @firma es un frontal de firma electrónica en forma de
Applet para su ejecución en entorno Web. Este aplicativo permite su
ejecución desde cualquier navegador Web soportado por el Cliente y la
generación de firma en formatos CAdES, PAdES, XAdES y ODF.

Los módulos del Cliente de los que depende el MiniApplet @firma son:

- afirma-core

- afirma-ui-core-jse

- afirma-core-keystores

- afirma-keystores-mozilla

- afirma-crypto-core-pkcs7

- afirma-crypto-cades

- afirma-crypto-cades-multi

- afirma-crypto-pdf

- afirma-crypto-core-xml

- afirma-crypto-xades

# Dependencias del interfaz Standalone respecto a los módulos

## Descripción general

El interfaz Standalone es un aplicativo de escritorio que permite la
generación de firmas electrónicas, cifrados simétricos y sobre
digitales, además de permitir operaciones de firma masiva y la
validación y extracción de datos de firma.

Los módulos del Cliente de los que depende el interfaz Standalone son:

- afirma-core

- afirma-ui-core-jse

- afirma-core-keystores

- afirma-keystores-mozilla

- afirma-keystores-single

- afirma-keystores-capiaddressbook

- afirma-crypto-core-pkcs7

- afirma-crypto-cades

- afirma-crypto-cades-multi

- afirma-crypto-pdf

- afirma-crypto-cms

- afirma-crypto-cms-enveloper

- afirma-crypto-core-xml

- afirma-crypto-xades

- afirma-crypto-xmlsignature

- afirma-crypto-odf

- afirma-crypto-ooxml

- afirma-crypto-cipher

- afirma-core-massive

- afirma-util

# Dependencias de SimpleAfirma respecto a los módulos

## Descripción general

El interfaz SimpleAfirma es un aplicativo de escritorio que permite la
generación sencilla de firmas electrónicas.

Los módulos del Cliente de los que depende el interfaz SimpleAfirma son:

- afirma-core

- afirma-ui-core-jse

- afirma-core-keystores

- afirma-keystores-mozilla

- afirma-crypto-core-pkcs7

- afirma-crypto-cades

- afirma-crypto-cades-multi

- afirma-crypto-pdf

- afirma-crypto-core-xml

- afirma-crypto-xades

- afirma-util

# Tabla resumen de dependencias de las aplicaciones @firma respecto a los módulos

<table>
<colgroup>
<col style="width: 43%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Módulos</th>
<th><strong>Applet</strong></th>
<th><strong>MiniApplet</strong></th>
<th><strong>StandAlone</strong></th>
<th><strong>Simple</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p>afirma-core</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>afirma-ui-core-jse</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>afirma-core-keystores</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>afirma-keystores-mozilla</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>afirma-keystores-single</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>afirma-keystores-capiaddressbook</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>afirma-crypto-core-pkcs7</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>afirma-crypto-cades</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>afirma-crypto-cades-multi</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>afirma-crypto-pdf</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>afirma-crypto-cms</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>afirma-crypto-cms-enveloper</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>afirma-crypto-core-xml</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>afirma-crypto-xades</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>afirma-crypto-xmlsignature</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>afirma-crypto-odf</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>afirma-crypto-ooxml</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>afirma-crypto-cipher</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>afirma-core-massive</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>afirma-util</p>
</blockquote></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

Leyenda: Verde: Utiliza el módulo. Blanco: No utiliza el módulo
