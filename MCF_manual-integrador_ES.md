---
title: |
  Manual del integrador del  
  Cliente @firma v1.8.2
---

# Índice de contenidos

[1 Objeto del documento
[7](#objeto-del-documento)](#objeto-del-documento)

[2 Introducción [8](#introducción)](#introducción)

[2.1 Licencia [8](#licencia)](#licencia)

[2.1.1 Licencias Java [9](#licencias-java)](#licencias-java)

[2.2 Recursos [9](#recursos)](#recursos)

[2.3 Adecuación al Esquema Nacional de Seguridad
[9](#adecuación-al-esquema-nacional-de-seguridad)](#adecuación-al-esquema-nacional-de-seguridad)

[3 Requisitos mínimos [11](#requisitos-mínimos)](#requisitos-mínimos)

[3.1 Entorno Cliente [11](#entorno-cliente)](#entorno-cliente)

[3.1.1 AutoFirma [11](#autofirma)](#autofirma)

[3.1.2 Cliente móvil Android
[12](#cliente-móvil-android)](#cliente-móvil-android)

[3.1.3 Cliente móvil iOS [12](#cliente-móvil-ios)](#cliente-móvil-ios)

[3.2 Entorno Servidor [12](#entorno-servidor)](#entorno-servidor)

[4 Operaciones soportadas
[13](#operaciones-soportadas)](#operaciones-soportadas)

[5 Despliegue del Cliente @firma
[14](#despliegue-del-cliente-firma)](#despliegue-del-cliente-firma)

[5.1 Información preliminar
[14](#información-preliminar)](#información-preliminar)

[5.2 Importación del JavaScript de despliegue
[15](#importación-del-javascript-de-despliegue)](#importación-del-javascript-de-despliegue)

[5.2.1 Importación en páginas Web generadas dinámicamente
[16](#importación-en-páginas-web-generadas-dinámicamente)](#importación-en-páginas-web-generadas-dinámicamente)

[5.3 Servicios del Cliente @firma
[16](#servicios-del-cliente-firma)](#servicios-del-cliente-firma)

[5.3.1 Servicios auxiliares de comunicación
[17](#servicios-auxiliares-de-comunicación)](#servicios-auxiliares-de-comunicación)

[5.3.2 Servicios de firma trifásica y firma de lotes
[19](#servicios-de-firma-trifásica-y-firma-de-lotes)](#servicios-de-firma-trifásica-y-firma-de-lotes)

[5.3.3 Configuración de los servicios
[24](#configuración-de-los-servicios)](#configuración-de-los-servicios)

[5.4 Configuración del *Content Security Policy*
[26](#configuración-del-content-security-policy)](#configuración-del-content-security-policy)

[6 Integración del Cliente @firma en un trámite web
[27](#integración-del-cliente-firma-en-un-trámite-web)](#integración-del-cliente-firma-en-un-trámite-web)

[6.1 Carga de la aplicación
[28](#carga-de-la-aplicación)](#carga-de-la-aplicación)

[6.1.1 Configuración de los puertos de comunicación
[28](#configuración-de-los-puertos-de-comunicación)](#configuración-de-los-puertos-de-comunicación)

[6.1.2 Configuración de los servicios auxiliares de comunicación
[29](#configuración-de-los-servicios-auxiliares-de-comunicación)](#configuración-de-los-servicios-auxiliares-de-comunicación)

[6.1.3 Forzado de la comunicación a través de los servicios auxiliares
[30](#forzado-de-la-comunicación-a-través-de-los-servicios-auxiliares)](#forzado-de-la-comunicación-a-través-de-los-servicios-auxiliares)

[6.1.4 Restricción según desfase horario con el servidor
[31](#restricción-según-desfase-horario-con-el-servidor)](#restricción-según-desfase-horario-con-el-servidor)

[6.1.5 Selección del almacén de claves
[32](#selección-del-almacén-de-claves)](#selección-del-almacén-de-claves)

[6.2 Firma electrónica [38](#firma-electrónica)](#firma-electrónica)

[6.2.1 Firma de múltiples documentos (firma masiva)
[40](#firma-de-múltiples-documentos-firma-masiva)](#firma-de-múltiples-documentos-firma-masiva)

[6.2.2 Firma trifásica [42](#firma-trifásica)](#firma-trifásica)

[6.3 Cofirma electrónica
[44](#cofirma-electrónica)](#cofirma-electrónica)

[6.4 Contrafirma electrónica
[46](#contrafirma-electrónica)](#contrafirma-electrónica)

[6.4.1 Selección de nodos
[48](#selección-de-nodos)](#selección-de-nodos)

[6.5 Firma de lotes predefinidos
[50](#firma-de-lotes-predefinidos)](#firma-de-lotes-predefinidos)

[6.5.1 Creación del lote [51](#creación-del-lote)](#creación-del-lote)

[6.5.2 Agregar documentos al lote
[52](#agregar-documentos-al-lote)](#agregar-documentos-al-lote)

[6.5.3 Firma del lote [54](#firma-del-lote)](#firma-del-lote)

[*6.5.4* *Ejemplo de operación de firma de lote*
[58](#ejemplo-de-operación-de-firma-de-lote)](#ejemplo-de-operación-de-firma-de-lote)

[6.5.5 Firma de lotes sin servidor (monofásica)
[58](#firma-de-lotes-sin-servidor-monofásica)](#firma-de-lotes-sin-servidor-monofásica)

[6.5.6 Antiguo mecanismo de firma de lotes
[62](#antiguo-mecanismo-de-firma-de-lotes)](#antiguo-mecanismo-de-firma-de-lotes)

[6.6 Selección de certificado
[62](#selección-de-certificado)](#selección-de-certificado)

[6.7 Recuperación de log
[64](#recuperación-de-log)](#recuperación-de-log)

[6.8 Operaciones de gestión de ficheros
[65](#operaciones-de-gestión-de-ficheros)](#operaciones-de-gestión-de-ficheros)

[6.8.1 Guardado de datos en disco
[66](#guardado-de-datos-en-disco)](#guardado-de-datos-en-disco)

[6.8.2 Selección y recuperación de un fichero por parte del usuario
[68](#selección-y-recuperación-de-un-fichero-por-parte-del-usuario)](#selección-y-recuperación-de-un-fichero-por-parte-del-usuario)

[6.8.3 Selección y recuperación de múltiples ficheros por parte del
usuario
[70](#selección-y-recuperación-de-múltiples-ficheros-por-parte-del-usuario)](#selección-y-recuperación-de-múltiples-ficheros-por-parte-del-usuario)

[6.9 Métodos de utilidad JavaScript
[71](#métodos-de-utilidad-javascript)](#métodos-de-utilidad-javascript)

[6.9.1 Conversión de una cadena Base64 a texto
[72](#conversión-de-una-cadena-base64-a-texto)](#conversión-de-una-cadena-base64-a-texto)

[6.9.2 Conversión de un texto a cadena Base64
[72](#conversión-de-un-texto-a-cadena-base64)](#conversión-de-un-texto-a-cadena-base64)

[6.9.3 Descarga de datos remotos
[73](#descarga-de-datos-remotos)](#descarga-de-datos-remotos)

[7 Configuración de las operaciones
[75](#configuración-de-las-operaciones)](#configuración-de-las-operaciones)

[7.1 Paso de parámetros adicionales
[75](#paso-de-parámetros-adicionales)](#paso-de-parámetros-adicionales)

[7.2 Configuración de los filtros de certificados
[76](#configuración-de-los-filtros-de-certificados)](#configuración-de-los-filtros-de-certificados)

[7.3 Selección automática de certificados
[83](#selección-automática-de-certificados)](#selección-automática-de-certificados)

[7.4 Configuración de la política de firma
[83](#configuración-de-la-política-de-firma)](#configuración-de-la-política-de-firma)

[7.4.1 Política de firma de la AGE v1.9
[83](#política-de-firma-de-la-age-v1.9)](#política-de-firma-de-la-age-v1.9)

[7.4.2 Política de firma de Factura electrónica (Facturae)
[85](#política-de-firma-de-factura-electrónica-facturae)](#política-de-firma-de-factura-electrónica-facturae)

[7.5 Validación de firmas previas
[85](#validación-de-firmas-previas)](#validación-de-firmas-previas)

[8 Formatos de firma [87](#formatos-de-firma)](#formatos-de-firma)

[8.1 Configuración de firmas CAdES
[88](#configuración-de-firmas-cades)](#configuración-de-firmas-cades)

[8.1.1 Algoritmos de firma
[89](#algoritmos-de-firma)](#algoritmos-de-firma)

[8.1.2 Firmas CAdES implícitas o explícitas
[89](#firmas-cades-implícitas-o-explícitas)](#firmas-cades-implícitas-o-explícitas)

[8.1.3 Parámetros adicionales
[89](#parámetros-adicionales)](#parámetros-adicionales)

[8.2 Configuración de firmas XAdES
[94](#configuración-de-firmas-xades)](#configuración-de-firmas-xades)

[8.2.1 Algoritmos de firma
[95](#algoritmos-de-firma-1)](#algoritmos-de-firma-1)

[8.2.2 Algoritmos de huella digital para las referencias
[95](#algoritmos-de-huella-digital-para-las-referencias)](#algoritmos-de-huella-digital-para-las-referencias)

[8.2.3 Situación del nodo de firma en XAdES Enveloped
[96](#situación-del-nodo-de-firma-en-xades-enveloped)](#situación-del-nodo-de-firma-en-xades-enveloped)

[8.2.4 Transformaciones sobre el contenido a firmar
[97](#transformaciones-sobre-el-contenido-a-firmar)](#transformaciones-sobre-el-contenido-a-firmar)

[8.2.5 Uso de estructuras *Manifest* en firmas XAdES
[98](#uso-de-estructuras-manifest-en-firmas-xades)](#uso-de-estructuras-manifest-en-firmas-xades)

[8.2.6 Tratamiento de las hojas de estilo XSL de los XML a firmar
[101](#tratamiento-de-las-hojas-de-estilo-xsl-de-los-xml-a-firmar)](#tratamiento-de-las-hojas-de-estilo-xsl-de-los-xml-a-firmar)

[8.2.7 Parámetros adicionales
[101](#parámetros-adicionales-1)](#parámetros-adicionales-1)

[8.3 Configuración de firmas PAdES
[112](#configuración-de-firmas-pades)](#configuración-de-firmas-pades)

[8.3.1 Algoritmos de firma
[113](#algoritmos-de-firma-2)](#algoritmos-de-firma-2)

[8.3.2 Operaciones no soportadas y notas de interés
[113](#operaciones-no-soportadas-y-notas-de-interés)](#operaciones-no-soportadas-y-notas-de-interés)

[8.3.3 Creación de una firma visible
[113](#creación-de-una-firma-visible)](#creación-de-una-firma-visible)

[8.3.4 Inserción de una imagen en un documento PDF antes de ser firmado
[119](#inserción-de-una-imagen-en-un-documento-pdf-antes-de-ser-firmado)](#inserción-de-una-imagen-en-un-documento-pdf-antes-de-ser-firmado)

[8.3.5 Firma de documentos PDF cifrados o protegidos con contraseña
[120](#firma-de-documentos-pdf-cifrados-o-protegidos-con-contraseña)](#firma-de-documentos-pdf-cifrados-o-protegidos-con-contraseña)

[8.3.6 Documentos certificados
[121](#documentos-certificados)](#documentos-certificados)

[8.3.7 Comprobación de *PDF Shadow Attack*
[122](#comprobación-de-pdf-shadow-attack)](#comprobación-de-pdf-shadow-attack)

[8.3.8 Parámetros adicionales
[123](#parámetros-adicionales-2)](#parámetros-adicionales-2)

[8.4 Configuración de firmas de factura electrónica
[129](#configuración-de-firmas-de-factura-electrónica)](#configuración-de-firmas-de-factura-electrónica)

[8.4.1 Operaciones no soportadas y notas de interés
[129](#operaciones-no-soportadas-y-notas-de-interés-1)](#operaciones-no-soportadas-y-notas-de-interés-1)

[8.4.2 Algoritmos de firma
[129](#algoritmos-de-firma-3)](#algoritmos-de-firma-3)

[8.4.3 Parámetros adicionales
[129](#parámetros-adicionales-3)](#parámetros-adicionales-3)

[9 Compatibilidad con dispositivos móviles y AutoFirma
[132](#compatibilidad-con-dispositivos-móviles-y-autofirma)](#compatibilidad-con-dispositivos-móviles-y-autofirma)

[9.1 Requisitos de despliegue
[132](#requisitos-de-despliegue)](#requisitos-de-despliegue)

[9.2 Limitaciones [132](#limitaciones)](#limitaciones)

[9.2.1 Limitaciones de formato
[133](#limitaciones-de-formato)](#limitaciones-de-formato)

[9.2.2 Limitaciones funcionales
[133](#limitaciones-funcionales)](#limitaciones-funcionales)

[9.2.3 Limitaciones de entono
[134](#limitaciones-de-entono)](#limitaciones-de-entono)

[9.3 Recomendaciones de despliegue
[134](#recomendaciones-de-despliegue)](#recomendaciones-de-despliegue)

[9.4 Notificaciones al usuario
[136](#notificaciones-al-usuario)](#notificaciones-al-usuario)

[10 Problemas conocidos
[138](#problemas-conocidos)](#problemas-conocidos)

[10.1 No se puede acceder al almacén de claves de Firefox 49.0 y
superiores
[138](#no-se-puede-acceder-al-almacén-de-claves-de-firefox-49.0-y-superiores)](#no-se-puede-acceder-al-almacén-de-claves-de-firefox-49.0-y-superiores)

[10.2 No se puede acceder al almacén de claves de Firefox 58
[138](#no-se-puede-acceder-al-almacén-de-claves-de-firefox-58)](#no-se-puede-acceder-al-almacén-de-claves-de-firefox-58)

[10.3 No se detecta la inserción/extracción del DNIe en el lector (u
otra tarjeta inteligente)
[139](#no-se-detecta-la-inserciónextracción-del-dnie-en-el-lector-u-otra-tarjeta-inteligente)](#no-se-detecta-la-inserciónextracción-del-dnie-en-el-lector-u-otra-tarjeta-inteligente)

[10.4 Falla la operación de firma con DNIe o una tarjeta de la FNMT
[139](#falla-la-operación-de-firma-con-dnie-o-una-tarjeta-de-la-fnmt)](#falla-la-operación-de-firma-con-dnie-o-una-tarjeta-de-la-fnmt)

[10.5 No se permite la firma de PDF con ciertos certificados
[140](#no-se-permite-la-firma-de-pdf-con-ciertos-certificados)](#no-se-permite-la-firma-de-pdf-con-ciertos-certificados)

[10.6 El servicio de firma trifásica genera un error al realizar firmas
XAdES en servidores JBoss
[140](#el-servicio-de-firma-trifásica-genera-un-error-al-realizar-firmas-xades-en-servidores-jboss)](#el-servicio-de-firma-trifásica-genera-un-error-al-realizar-firmas-xades-en-servidores-jboss)

[10.7 Las firmas con DNIe requieren que se introduzca el PIN del DNIe
por cada operación de firma
[140](#las-firmas-con-dnie-requieren-que-se-introduzca-el-pin-del-dnie-por-cada-operación-de-firma)](#las-firmas-con-dnie-requieren-que-se-introduzca-el-pin-del-dnie-por-cada-operación-de-firma)

[10.8 Error al cargar el listado de certificados después del cambio en
caliente del almacén por defecto
[141](#error-al-cargar-el-listado-de-certificados-después-del-cambio-en-caliente-del-almacén-por-defecto)](#error-al-cargar-el-listado-de-certificados-después-del-cambio-en-caliente-del-almacén-por-defecto)

[10.9 AutoFirma no puede comunicarse con el navegador en macOS
[141](#autofirma-no-puede-comunicarse-con-el-navegador-en-macos)](#autofirma-no-puede-comunicarse-con-el-navegador-en-macos)

[10.10 Sólo se realiza la firma del primer documento de una serie cuando
se realizan las firmas desde Google Chrome
[142](#sólo-se-realiza-la-firma-del-primer-documento-de-una-serie-cuando-se-realizan-las-firmas-desde-google-chrome)](#sólo-se-realiza-la-firma-del-primer-documento-de-una-serie-cuando-se-realizan-las-firmas-desde-google-chrome)

[10.11 No se abre la aplicación de firma al realizar la firma desde
Google Chrome
[143](#no-se-abre-la-aplicación-de-firma-al-realizar-la-firma-desde-google-chrome)](#no-se-abre-la-aplicación-de-firma-al-realizar-la-firma-desde-google-chrome)

[10.12 No se abre la aplicación de firma con Edge Legacy (EdgeHTML)
[143](#no-se-abre-la-aplicación-de-firma-con-edge-legacy-edgehtml)](#no-se-abre-la-aplicación-de-firma-con-edge-legacy-edgehtml)

[10.13 No se abre la aplicación de firma con Firefox cuando el servidor
declara una política de seguridad (CSP)
[144](#no-se-abre-la-aplicación-de-firma-con-firefox-cuando-el-servidor-declara-una-política-de-seguridad-csp)](#no-se-abre-la-aplicación-de-firma-con-firefox-cuando-el-servidor-declara-una-política-de-seguridad-csp)

[ANEXO I. Comunicación JavaScript de despliegue – Cliente @firma
[145](#comunicación-javascript-de-despliegue-cliente-firma)](#comunicación-javascript-de-despliegue-cliente-firma)

[I.1. Comunicación por sockets
[145](#comunicación-por-sockets)](#comunicación-por-sockets)

[I.2. Comunicación por servidor intermedio
[146](#comunicación-por-servidor-intermedio)](#comunicación-por-servidor-intermedio)

[ANEXO II. Firma trifásica
[148](#firma-trifásica-1)](#firma-trifásica-1)

[II.1. Servicios de firma trifásica y de lotes
[149](#servicios-de-firma-trifásica-y-de-lotes)](#servicios-de-firma-trifásica-y-de-lotes)

[II.1.1. Gestor de documentos del servicio
[149](#gestor-de-documentos-del-servicio)](#gestor-de-documentos-del-servicio)

[II.1.2. Gestores de documentos personalizados
[152](#gestores-de-documentos-personalizados)](#gestores-de-documentos-personalizados)

[II.1.2.1. Desarrollo de un gestor de documentos personalizado
[152](#desarrollo-de-un-gestor-de-documentos-personalizado)](#desarrollo-de-un-gestor-de-documentos-personalizado)

[II.1.2.2. Configuración de un gestor de documentos personalizado
[155](#configuración-de-un-gestor-de-documentos-personalizado)](#configuración-de-un-gestor-de-documentos-personalizado)

[II.2. Uso de la firma trifásica con los gestores de documentos
[155](#uso-de-la-firma-trifásica-con-los-gestores-de-documentos)](#uso-de-la-firma-trifásica-con-los-gestores-de-documentos)

[II.2.1. Gestor de documentos “FileSystemDocumentManager”
[156](#gestor-de-documentos-filesystemdocumentmanager)](#gestor-de-documentos-filesystemdocumentmanager)

[II.2.1.1. Parámetros de uso y descripción del funcionamiento
[156](#parámetros-de-uso-y-descripción-del-funcionamiento)](#parámetros-de-uso-y-descripción-del-funcionamiento)

[II.2.1.2. Configuración en alta disponibilidad con varios nodos
[157](#configuración-en-alta-disponibilidad-con-varios-nodos)](#configuración-en-alta-disponibilidad-con-varios-nodos)

[II.2.2. Gestor de documentos “LegacyBatchDocumentManager”
[158](#gestor-de-documentos-legacybatchdocumentmanager)](#gestor-de-documentos-legacybatchdocumentmanager)

[II.2.2.1. Parámetros de uso y descripción del funcionamiento
[158](#parámetros-de-uso-y-descripción-del-funcionamiento-1)](#parámetros-de-uso-y-descripción-del-funcionamiento-1)

# Objeto del documento

En el presente documento se detalla el proceso de integración y
configuración del Cliente @firma para la generación de firmas de usuario
en trámites web.

# Introducción

El Cliente @firma es una solución de firma electrónica que permite a sus
usuarios generar firmas con sus certificados locales. El Cliente está
especialmente orientado a ser integrado dentro de trámites web de tal
forma que una aplicación web pueda solicitar al usuario la firma de unos
datos a través del Cliente y obtener como respuesta la firma de esos
datos.

El Cliente @firma está formado principalmente por dos componentes:

- Una aplicación nativa (AutoFirma, para equipos es de sobremesa; el
  Cliente móvil Android, para dispositivos Android; o el Cliente móvil
  iOS, para dispositivos iOS). Esta aplicación debe estar instalada en
  el dispositivo del usuario antes de iniciar el proceso de firma.

- Un JavaScript de despliegue para la integración del proceso de firma
  dentro del trámite web.

Además de los componentes mencionados, el uso de determinadas funciones
del Cliente @firma o su compatibilidad con determinados entornos puede
requerir el despliegue de diversos servicios auxiliares a los que deberá
conectar la aplicación cliente.

El Cliente @firma hace uso de los certificados digitales X.509v3 y de
las claves privadas asociadas a estos que estén instalados en el
repositorio o almacén de claves y certificados (*KeyStore*) del sistema
operativo o del navegador Web (Internet Explorer, Mozilla Firefox, etc.)
del usuario. También se permite el uso de certificados en dispositivos
criptográficos (tarjetas inteligentes, dispositivos USB) instalados en
el sistema y con controlador CSP/PKCS#11 compatible (como, por ejemplo,
el DNI Electrónico o DNIe) y certificados en almacenes software
(PKCS#12/PFX). La clave privada del usuario no abandona en ningún caso
el almacén de claves ni sale del equipo del usuario.

El Cliente @firma no almacena ningún tipo de información personal del
usuario, ni hace uso de cookies ni ningún otro mecanismo para la gestión
de datos de sesión. AutoFirma sí almacena el log de su última ejecución
a efectos de ofrecer soporte al usuario si se encontrase algún error
durante su ejecución.

El Cliente @firma forma parte de la *suite* de productos de @firma, pero
no interacciona con ninguno de los servicios del resto de productos. El
Cliente @firma sólo generar firmas electrónicas con los certificados de
usuario. La validación de estas firmas y su promoción a firmas longevas,
por ejemplo, son operaciones que deberán realizarse de forma
independiente con otros productos de la *suite* (@firma, VALIDe,
Integr@...)

## Licencia

El Cliente @firma es software libre y puede usarse, según se desee, bajo
licencia *GNU General Public License* versión 2 (GPLv2) o bajo licencia
*European Software License* 1.1 (EUPL 1.1) o superior.

El Cliente @firma incluye, entre otros, los siguientes productos de
terceros con licencias compatibles:

- JXAdES (<https://github.com/universitatjaumei/jxades>)

- SpongyCastle (<https://rtyley.github.io/spongycastle/>)

- Código derivado de iText v2.1.7 (<http://itextpdf.com/>)

- Código derivado de Java Mime Magic Library
  (<http://jmimemagic.sourceforge.net/>)

- Apache Santuario (<https://santuario.apache.org/>)

- Proxy Vole (<https://github.com/MarkusBernhardt/proxy-vole>)

- Java WebSocket (<https://github.com/TooTallNate/Java-WebSocket>)

### Licencias Java

AutoFirma, en sus versiones para Windows y macOS, incluye una máquina
virtual de Java (JVM) para la ejecución de la aplicación.

- Microsoft Windows (64bits):

  - OpenJDK JRE 17.0.2 (licencia GPL v2)

- macOS

  - OpenJDK JRE 17.0.2 (licencia GPL v2)

Las licencias de las JVM incluidas en AutoFirma permiten su uso sin
coste de licencia.

En caso de utilizar el antiguo MiniApplet (disponible hasta el Cliente
@firma 1.6.5), la entidad encargada de la implantación de la solución
será la responsable de la proporcionar la JVM necesaria a sus empleados
y las licencias que esta pueda requerir. En el caso de los ciudadanos o
usuarios que no lo utilicen en el desempeño de su actividad laboral, no
se requerirá el pago de licencias independientemente de que se utilice
OpenJDK u Oracle Java.

Los Clientes móviles para Android e iOS utilizan únicamente el entorno
de ejecución proporcionado por el del sistema y no requieren licencia.

## Recursos

Puede consultar la información relativa al proyecto Cliente @firma y
descargar el código fuente y los binarios de la aplicación en la
siguiente dirección Web:

<http://administracionelectronica.gob.es/ctt/clienteafirma>

Así mismo, el código del Cliente se encuentra disponible en GitHub y sus
distintos módulos se encuentran disponibles en el repositorio central de
Maven:

- Fuentes: <https://github.com/ctt-gob-es/clienteafirma>

- Binarios: <https://search.maven.org/search?q=es.gob.afirma>

## Adecuación al Esquema Nacional de Seguridad

Los productos de la Suite @firma pueden permitir el uso de algoritmos no
recomendados por la Guía 807 del Esquema Nacional de Seguridad (ENS;
editada por el Centro Criptológico Nacional, CCN) vigente en el momento
de publicación de este documento. Queda bajo la responsabilidad de las
aplicaciones que hacen uso de estos productos el configurar
adecuadamente las llamadas a los mismos para generar el resultado
esperado, válido y adecuado para ese momento y el nivel de seguridad
deseado, utilizando para ello algoritmos de la familia SHA-2 tal y como
especifica dicha norma para la generación de firmas electrónicas.

Puede consultar la norma vigente desde el siguiente enlace:

<https://www.ccn-cert.cni.es/series-ccn-stic/800-guia-esquema-nacional-de-seguridad/513-ccn-stic-807-criptologia-de-empleo-en-el-ens/file.html>

# Requisitos mínimos

## Entorno Cliente

Los requisitos mínimos del entorno cliente dependerá de la aplicación
nativa utilizada para firmar. Debido a la amplia variedad de navegadores
del mercado, sólo se citarán para cada aplicación cliente aquellos
navegadores para los que se han realizado pruebas específicas. No
excluye esto que pueda funcionar correctamente con otros entornos.

### AutoFirma

El uso de AutoFirma como herramienta de firma integrada dentro del
proceso de firma de trámites web tiene los siguientes requerimientos en
cuanto a entorno operativo:

- Sistema Operativo

  - Microsoft Windows 7 o superior.

    - Soportado directamente en 7, 8, 8.1, 10 y 11.

    - En 32 o 64 bits.

  - Linux.

    - Soportado directamente en Ubuntu 20.04 LTS, Fedora 35 y OpenSUSE
      15.3.

  - macOS Catalina o superior.

    - Soportado directamente en Catalina, Big Sur y Monterrey.

- Navegadores Web (Cuando es invocada desde una aplicación web)

  - Microsoft Windows

    - Google Chrome 46 o superior.

    - Mozilla Firefox 41.0.1 o superior.

    - Microsoft Internet Explorer 8 o superior.

    - Microsoft Edge Legacy v20 o superior (EdgeHTML).

    - Microsoft Edge (Edge Chromium).

  - Linux

    - Mozilla Firefox 41.0.1 o superior.

  - macOS

    - Apple Safari 9.0 o superior.

    - Google Chrome 46 o superior.

    - Mozilla Firefox 41.0.1 o superior.

En entornos macOS y Windows no es necesario que el usuario tenga
instalado un entorno de ejecución de Java, ya que viene incluido en la
propia aplicación. En Linux se necesita un entorno de ejecución de Java
OpenJDK (marcado como recomendacíon en el instalador de AutoFirma para
permitir el uso de la compilación preferida del usuario de la JRE
(versión 8 o superior).

Para el acceso al almacén de Firefox en algunas versiones de Windows
puede ser necesario instalar los entornos de ejecución redistribuibles
de Microsoft Visual C++ 2015. Si AutoFirma no puede cargar los
certificados de su almacén de claves, siga las instrucciones descritas
en el apartado de errores conocidos <u>No se puede acceder al almacén de
claves de Firefox 49.0 y superiores</u>.

### Cliente móvil Android

El uso de Cliente móvil Android como herramienta de firma integrada
dentro del proceso de firma de trámites web tiene los siguientes
requerimientos en cuanto a entorno operativo:

- Sistema Operativo

  - Android 4.3 o superior.

- Navegadores Web (para la invocación por protocolo)

  - Google Chrome.

  - Navegador webkit.

### Cliente móvil iOS

El uso de Cliente móvil iOS como herramienta de firma integrada dentro
del proceso de firma de trámites web tiene los siguientes requerimientos
en cuanto a entorno operativo:

- Sistema Operativo

  - iOS 13 o superior.

- Navegadores Web (para la invocación por protocolo)

  - Apple Safari.

## Entorno Servidor

El Cliente @firma requiere de una serie de servicios auxiliares para el
uso de ciertas funcionalidades y la compatibilidad con determinados
entornos. Los requisitos de estos servicios son los siguientes:

- Servidor de aplicaciones JEE compatible con Servlets de Java.

  - Apache Tomcat, WildFly, RedHat JBoss, IBM WebSphere, Oracle
    GlassFish, Oracle Application Server, etc.

- JRE 1.7 o superior.

Puede saber más acerca de los servicios auxiliares del Cliente @firma,
consulte el apartado <u>5.3 Servicios del Cliente @firma</u>.

# Operaciones soportadas

El Cliente @firma proporciona funcionalidades de firma electrónica
(incluyendo firmas múltiples) con certificados locales, pero no otras
operaciones de firma o criptografía como validación de firmas, promoción
a formatos longevos, sellado de tiempo, creación de sobres digitales o
cifrado. Adicionalmente, el Cliente @firma proporciona un conjunto de
métodos de utilidad y opciones de operación.

Las operaciones soportadas por el Cliente @firma son:

- Firma electrónica.

- Firmas electrónicas múltiples (más de un firmante por documento).

  - Cofirma.

  - Contrafirma.

- Firma de lotes de documentos.

- Selección de certificado.

- Funciones de utilidad:

  - Conversión de una cadena Base64 a texto.

  - Conversión de un texto a una cadena Base64.

  - Guardado de datos en disco.

  - Carga de fichero local.

  - Carga de multiples ficheros.

Si su aplicación requiere una funcionalidad de firma no soportada por el
Cliente @firma, consulte el catálogo de aplicaciones de @firma para
determinar cuál es la más apropiada para sus necesidades.

# Despliegue del Cliente @firma

Para integrar el Cliente @firma en su aplicación web se debe publicar
junto a la misma el fichero “autoscript.js”. En este fichero se
encuentra el objeto JavaScript que deberemos utilizar para invocar a las
distintas operaciones del Cliente y obtener su resultado.

Adicionalmente y según el entorno de ejecución del usuario, es posible
que para la comunicación entre el JavaScript de despliegue y el Cliente
@firma sea necesario el uso de dos servicios de comunicación. Estos dos
servicios, se distribuyen junto al JavaScript de despliegue en forma de
archivos WAR (“afirma-signature-retriever.war” y
“afirma-signature-storage.war”) y deberían desplegarse en el mismo
dominio que la página web desde la que se use el Cliente. Las
funcionalidades de firma trifásica y firma de lotes también requieren el
despliegue de un servicio adicional
(“afirma-server-triphase-signer.war”).

Consulte en el apartado <u>5.3 Servicios del Cliente @firma</u> en qué
casos son necesarios estos servicios y así determinar si debe realizar
su despliegue.

## Información preliminar

En este apartado se presentan distintos aspectos que el integrador del
Cliente @firma debe tener en cuenta antes del despliegue del Cliente
@firma:

- Como medida de seguridad, AutoFirma no permite el despliegue en
  páginas a las que se acceda mediante “127.0.0.1” o “localhost”. Si va
  a realizar pruebas en su equipo local, deberá tomar alguna de las
  siguientes alternativas:

  - Acceda a su página y a los servicios del cliente a través de la IP
    de red que tenga asignada su equipo.

  - Configure en el fichero hosts de su equipo un alias para “127.0.0.1”
    y utilícelo como nombre de dominio. La localización del fichero
    hosts según el sistema operativo es:

    - En Windows: UNIDAD:\\\Windows\System32\drivers\etc\\

    - En Linux y macOS: /etc/hosts

- La página web, el JavaScript de despliegue y los servicios del Cliente
  @firma deben ser accesibles desde el mismo dominio. De esta forma se
  evitarán errores debido a los mecanismos de seguridad del navegador
  para bloquear ataques de *Cross-Site Scripting* (XSS). Esto es
  especialmente importante cuando se hace uso de los servicos auxiliares
  de comunicación (StorageService y RetrieveService).

  - Despliegue una instancia de los servicios auxiliares de comunicación
    > por cada aplicación en la que integre el cliente o, al menos, por
    > cada dominio.

- Siempre que se utilice el Cliente @firma ha de tenerse en cuenta que
  la aplicación nativa debe poder confiar en los certificos SSL
  utilizados por cualquier servicio externo al que se deda conectar. En
  caso contrario, fallaría la conexión. Esto es crítico cuando se hace
  uso de la comunicación por servidor intermedio o se utiliza la
  operación de firma trifásica.

  - En el caso de usar AutoFirma, puede evitar problemas durante el
    desarrollo y pruebas desactivando la comprobación de los
    certificados SSL o agregando su dominio a la lista de dominios
    seguros. Puede hacer esto desde el panel de preferencias, en la
    pestaña “General”, desactivando la casilla de verificación “Aceptar
    sólo conexiones con sitios seguros (Recomendado)” o accediento al
    apartado “Dominios seguros”.

  - En el caso de aplicaciones de firma móvil Android, puede desactivar
    > la validación de certicados o agregar el dominio a la lista de
    > dominios seguros desde el menú “Configuración”.

- Codificación UTF-8 de las páginas cuando se proporcionen o recojan
  textos del cliente.

  - El Cliente @firma interpreta todos los textos, tanto los recibidos
    como los devueltos en las respuestas, usando el juego de caracteres
    UTF-8. Para poder transmitirlos y mostrarlos correctamente desde una
    página web es necesario que esta se encuentre codificada en UTF-8 y
    lo declare como tal.

  - En caso de no ser posible, se recomienda:

    - Que el Base64 de los textos a proporcionar al Cliente se hayan
      obtenido desde un entorno en el que se pueda gantizar que
      originalmente estaban codificados en UTF-8. Por ejemplo, que el
      texto ya estuviese previamente codificado o que se codifique a
      través de un servicio.

    - No mostrar directamente al usuario los mensajes devueltos por el
      propio Cliente.

## Importación del JavaScript de despliegue

Para integrar el Cliente @firma en su página Web debe importar en ella
la biblioteca JavaScript “autoscript.js”. Puede hacer referencia a la
misma mediante una URL absoluta o mediante una URL relativa a partir de
la dirección de publicación de su página Web.

Por ejemplo, se puede introducir la carga de la biblioteca en la sección
head del HTML, tal y como se muestra en el siguiente ejemplo:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>&lt;head&gt;</p>
<p>&lt;script
src=<em>"https://miweb.com/afirma/js/autoscript.js"</em>&gt;&lt;/script&gt;</p>
<p><u>…</u></p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Si la página Web en la que deseamos cargar el Cliente @firma estuviese
también en la ruta “<https://miweb.com/afirma>” se podría hacer
referencia a la biblioteca “autoscript.js” de forma relativa indicando:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>&lt;head&gt;</p>
<p>&lt;script src=<em>"js/autoscript.js"</em>&gt;&lt;/script&gt;</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Cualquier página Web con esta biblioteca JavaScript importada está lista
para utilizar el Cliente @firma.

### Importación en páginas Web generadas dinámicamente

En un sistema Web actual, lo habitual es que las páginas Web no residan
pre-construidas en directorios Web, sino que estas se generen
dinámicamente mediante alguna de las muchas tecnologías disponibles de
aplicaciones Web (JSP, ASP, PHP, etc.).

En estos casos es necesario tener en cuenta que la dirección de la
biblioteca JavaScript debería establecerse en base a la URL de
despliegue de la página si se hace de forma relativa. En caso de duda,
utilice la URL absoluta.

## Servicios del Cliente @firma

La compatibilidad del Cliente @firma con determinados entornos y
funciones puede requerir el despliegue de una serie de servicios
auxiliares. Estos servicios se distribuyen en forma de archivos WAR
junto al JavaScript de espliegue del Cliente @firma y deberían
desplegarse por cada aplicación o sistema que desee utilizarlos.

Los archivos WAR en los que se distribuyen estos servicios no requieren
el uso de un software servidor de aplicaciones concreto. Consulte el
apartado <u>3.2 Entorno Servidor</u> para saber más de los requisitos de
despliegue y la documentación de su servidor de aplicaciones para saber
cómo desplegarlos.

En caso de que su aplicación no tenga que ser compatible con los
entornos o las funcionalidades listadas a continuación, no será
necesario el despliegue de ningún servicio. Esto es, que no tendrá que
desplegarlos en los siguientes casos:

- Si no se requiere compatibilidad con Internet Explorer 10 ni con
  Safari 10 ni versiones anteriores de ambas aplicaciones.

- Si no se requiere compatibilidad con dispositivos móviles.

- Si no se utilizan operaciones de firma trifásica o firma de lotes.

Cada uno de estos servicios requiere un fichero de configuración, pero
la lógica para definir la ubicación de estos ficheros es la misma para
todos ellos. Este aspecto de la configuración se detalla en el apartado
<u>5.3.3 Configuración de los servicios</u>.

### Servicios auxiliares de comunicación

Para la comunicación entre el JavaScript de despliegue del Cliente
@firma y la propia aplicación de firma se utilizan diversos mecanismos.
Uno de estos requiere del uso de dos servicos auxiliares de
comunicación. Deberá utilizar estos servicios cuando:

- Desee que su despliegue sea compatible con entornos móviles.

- Desee que su despliegue sea compatible con Internet Explorer 10 y
  anteriores (o una versión superior en modo compatibilidad con estas
  versiones).

- Cuando la aplicación fuerce intencionadamente la comunicación a través
  de estos servicios.

Estos servicios se distribuyen junto con el JavaScript de despliegue del
Cliente @firma y son los siguientes:

- **StorageService**

  - Este Servlet permite almacenar datos en un directorio temporal del
    servidor.

  - Este servicio se despliega por medio del WAR
    “afirma-signature-storage.war”.

- **RetrieveService**

  - Este Servlet permite recuperar datos de un servidor. Los datos
    devueltos deben estar almacenados en un directorio temporal
    predefinido y, tras devolver los datos, el servicio borrará el
    fichero temporal en donde se almacenaban. Este servicio nunca
    devolverá datos que se guardasen hace más de un tiempo máximo
    configurado, devolviendo error tal como si no hubiese encontrado el
    fichero de datos. Igualmente, borrará todos aquellos ficheros del
    directorio temporal que hayan sobrepasado este tiempo máximo desde
    su creación.

  - Este servicio se despliega por medio del WAR “afirma-signature-
    retriever.war”.

En cualquier el resto de los casos, el JavaScript de despliegue y
AutoFirma se comunicarán a través de Sockets. Consulte el apartado
<u>ANEXO I Comunicación JavaScript de despliegue – Cliente @firma</u>
para saber más sobre los mecanismos de comunicación entre el JavaScript
de despliegue y el Cliente @firma.

| **Importante:** Los servicios de almacenamiento y guardado en servidor deben ser accesibles desde el mismo dominio en el que se encuentre la página de firma. Si no se hiciese así, el navegador web puede bloquear la conexión con ellos interpretando que se trata de un ataque de *cross-site scripting (XSS)*. |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

##### Configuración de los servicios de almacenaje y recuperación

Los servicios de almacenaje y recuperación sirven para comunicar el
JavaScript de despliegue y el Cliente @firma mediante el guardado
temporal de los datos en un directorio concreto del servidor.

Este directorio temporal debe ser visible y accesible por todas las
instancias en ejecución de los servicios. Este aspecto es especialmente
importante en configuraciones de servidores de aplicaciones en alta
disponibilidad, donde puede haber varios nodos que presten el servicio,
cada uno de ellos en un sistema de ficheros diferente.

El que todos los nodos accedan al mismo directorio referenciado en la
configuración se puede lograr fácilmente usando un almacenamiento
compartido entre todos ellos (con el mismo punto de montaje), mediante
enlaces simbólicos, etc. Es importante también asegurarse de que todos
los nodos tienen los permisos adecuados sobre los directorios
configurados.

Los servicios de almacenaje y recuperación de datos para la comunicación
entre el JavaScript de despliegue y el Cliente @firma (StorageService y
RetrieveService, respectivamente), utilizan el mismo fichero de
configuración. Este fichero es “intermediate_config.properties”, que
debe encontrarse en un directorio indetificado por la ruta absoluta
transmitida a través de un parámetro “-Dclienteafirma.config.path”.

Las propiedades disponibles en este fichero de configuración son las
siguientes:

- **tmpDir**: Es el directorio del servidor en donde se almacenarán los
  datos temporales.

  - Debe contener el mismo valor en los servicios de guardado y recogida
    de datos si estos se desplegasen por separado.

  - A este directorio sólo necesitan acceder los servicios de guardado y
    recuperación de datos, por lo que el administrador del sistema puede
    determinar que sólo estos servicios pueden acceder a dicho
    directorio.

  - En caso de realizarse un despliegue en múltiples nodos, el
    directorio debería encontrarse en una unidad compartida por todos
    ellos.

  - Si no se configura esta propiedad, se usará el directorio temporal
    del servidor.

- **expTime**: Es el tiempo de caducidad en milisegundos de los ficheros
  del directorio. Una vez superado ese tiempo desde la creación del
  fichero, el servicio de recuperación se negará a devolverlo y lo
  eliminará.

  - Si no se configura esta propiedad, se usará por defecto el valor
    “60000” (1 minuto)

- **maxFileSize**: Es el tamaño máximo de fichero permitido expresado en
  bytes. Su utilidad responde principalmente a motivos de seguridad,
  para evitar que el directorio del servidor se quede sin espacio si
  comienzan a subirse datos de gran tamaño.

  - Si no se configura esta propiedad, se usará por defecto el valor
    “0”, que indica que no hay límite de tamaño de fichero.

- **debug**: Habilita el modo debug cuando se configura el valor “true”.
  El modo debug sólo debería habilitarse durante la fase de integración
  y nunca en entornos productivos. En este modo:

  - Se muestran traza de log adicionales.

  - No se eliminan los ficheros recuperados del servicior intermedio.

  - No se eliminan los ficheros caducados del directorio temporal del
    servidor intermedio.

  - No se limita el tamaño máximo de los ficheros a guardar.

Un ejemplo de fichero de configuración podría ser:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p># Directorio para el guardado de los ficheros. Por defecto:
Directorio temporal</p>
<p>tmpdir=C:/clienteafirma/temp</p>
<p># Tiempo de caducidad de los mensajes. Por defecto: 60000 (1
minuto)</p>
<p>expTime=60000</p>
<blockquote>
<p># Tamano maximo de fichero en bytes. Por defecto: 0 (Sin limite)</p>
</blockquote>
<p>maxFileSize=1048576</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

###### Consideraciones de seguridad

Un posible ataque de denegación de servicio sobre este sistema de
almacenaje temporal es simplemente hacer muchas peticiones de almacenaje
hasta que se alcance la capacidad total del sistema de ficheros.

Los servicios proporcionados no incorporan ninguna medida contra estos
ataques más que la limitación del tamaño de fichero, por lo que debe ser
el integrador el que las implemente. Algunas de estas medidas podrían
ser:

- Establecer cuotas de disco para el directorio configurado en
  **tmpDir**.

- Detectar (y prevenir) múltiples llamadas al servicio de almacenamiento
  desde una misma dirección sin estar acompañadas de las respectivas
  llamadas de recuperación.

- Detectar (y prevenir) múltiples llamadas al servicio de almacenamiento
  en una frecuencia inusualmente alta.

### Servicios de firma trifásica y firma de lotes

Estos servicios se distribuyen en el archivo desplegable
“afirma-server-triphase-signer.war” y deberán desplegarse cuando:

- Desee que su despliegue sea compatible con entornos móviles.

  - Para más información, consulte el apartado <u>9 Compatibilidad con
    dispositivos móviles y AutoFirma</u>.

- Desee utilizar las funciones de firma trifásica del cliente @firma.

  - Para más información, consulte el apartado <u>6.2.2 Firma
    trifásica</u>.

- Desee utilizar las funciones de firma de lotes.

  - Para más información, consulte el apartado <u>6.5 Firma de lotes
    predefinidos</u>.

Los servicios en cuestión son los siguientes:

- **SignatureService**

  - Servicio para la ejecución de operaciones de firma trifásica.

  - Requerido cuando deseamos utilizar este tipo de operación y cuando
    se realizan firmas desde las aplicaciones cliente móvil.

- **presign**

  - Servicio para la carga de documentos y prefirma en los procesos de
    firma de lotes.

- **postsign**

  - Servicio para la postfirma en los procesos de firma de lotes y
    guardado de las firmas.

| **Advertencia:** AutoFirma 1.7 y anteriores hacían uso de un mecanismo de firma de lotes distinto al actual, que usaba sus propios servicios y se configuraban de forma separada. Estos servicios siguen incluyéndose en el “afirma-server-triphase-signer.war”, pero se consideran obsoletos y sólo deberían seguir usándose para dar soporte a los antiguos despliegues de firma trifásica, también soportados por AutoFirma 1.8 y superiores. Si desea utilizar el antiguo sistema de firma de lotes, consulte la documentación de AutoFirma 1.7. |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

#### Configuración del servicio trifásico

Los servicios de firma trifásica y de lotes se configuran a través del
fichero “tps_config.properties”, que debe encontrarse en un directorio
identificado por la ruta absoluta transmitida al servidor de
aplicaciones a través de un parámetro “-Dclienteafirma.config.path”. Se
puede proporcionar este parámetro en el arranque del servidor de
aplicaciones.

Las propiedades que pueden establecerse en este fichero son:

- **Access-Control-Allow-Origin**

  - Permite establecer el origen permitido de las peticiones. Los
    servicios agregarán el valor de esta propiedad en las respuestas del
    servicio.

  - Si se establece como valor un asterisco (‘\*’), se indica que se
    pueden realizar peticiones desde cualquier dominio.

  - Valor por defecto: \*

- **xml.provider.apache**

  - Permite forzar el proveedor de firma XML que se debe utilizar. Si se
    indica false, se forzará el proveedor de Sun. Cualquier otro valor,
    hará que se utilice el proveedor de Apache. Esto puede ser útil para
    evitar problemas de compatibilidad con bibliotecas de procesado de
    XML (como XERCES y XALAN) que puedan encontrarse en el *classpath*
    del servidor de aplicaciones. Este tipo de bibliotecas pueden
    interferir con las que incluye el propio Oracle Java e impedir
    realizar firmas XAdES.

  - Valor por defecto: true

- **document.manager**

  - Clase que se encargará de gestionar los documentos que se deben
    firmar y las firmas generadas en los procesos de firma trifásica y
    de lote.

  - Valor por defecto:

    - es.gob.afirma.triphase.server.document.SelfishDocumentManager

      - El gestor de documentos (*Document Manager)* por defecto imita
        un proceso de firma monofásica, lo cual quiere decir que se
        deberán proporcionar los datos a firmar en las llamadas a las
        operaciones de firma y de lote.

  - Para saber más de la firma trifásica y las ventajas que ofrece
    consulte el apartado <u>ANEXO II Firma trifásica</u>.

- **verification.key**

  - Clave utilizada para generar el código de verificación de las
    firmas.

  - Si se configura aquí un valor (puede ser cualquiera), se utilizará
    este para generar un código de verificación de los datos enviados a
    firmar. Este código se genera en la prefirma en base a los datos y
    se comprueba en la postfirma para garantizar que la firma generada
    se realizó sobre los datos originalmente prefirmados.

  - Por defecto, no se configura ningún valor y no se realizará está
    validación.

- **cacheEnabled**

  - Establece si se deben guardar en caché los documentos durante la
    firma. Se habilita con el valor “true” y se mantiene deshabilitada
    con cualquier otro valor.

  - Por regla general, el documento a firmar es necesario tanto en la
    prefirma como en la postfirma. Esto quiere decir que se deberá
    recuperar en dos ocasiones mediante el gestor de documentos
    configurado. Si recuperarlo del entorno en el que se encuentre es un
    proceso pesado, se puede configurar que guardé en caché el documento
    durante la prefirma para no tener que volverlo a recuperar durante
    la posfirma.

  - Valor por defecto: false

  - La implementación de la caché se determina mediante la propiedad
    “document.cache.manager” de este mismo fichero.

  - Téngase en cuenta que según el gestor de documentos y la
    implementación de caché puede o no ser conveniente habilitar el uso
    de la caché. Por regla general, sólo se debería habilitar la caché
    cuando se implemente un gestor de documentos personalizado, no los
    incluidos por defecto en el servicio de firma trifásica, y cuando la
    recuperación de este documento del gestor de documentos sea más
    costosa que la recuperación de los datos de la caché, lo cual
    dependerá de la implementación de caché utilizada.

- **document.cache.manager**

  - Clase que se encargará de guardar y recuperar datos de la caché.

  - La implementación por defecto usa el disco cómo caché, ya que el
    guardado en memoria puede sobrepasar los límites establecidos para
    el servicio cuando se procesen varias peticiones simultáneamente.

  - Valor por defecto:

    - es.gob.afirma.triphase.server.cache.FileSystemCacheManager

  - Este propiedad solo se tendrá en cuenta si se activase la caché
    mediante la propiedad “cacheEnabled”.

<!-- -->

- **maxPagesToCheckShadowAttack**

  - Número máximo de páginas sobre las que comprobar el PDF Shadow
    Attack. Se puede omitir la comprobación indicando "0" paginas o
    permitir que se haga sobre todo el documento indicando el valor
    "all". Por defecto, 10.

  - Se puede consultar más información sobre la validación de PDF Shadow
    Attack en el apartado <u>8.3.7 Comprobación de *PDF Shadow
    Attack*</u>.

- **tmpdir**

  - Directorio para el guardado de los ficheros temporales. Si no se
    indica, se usará el del usuario, aunque es recomendable el uso de un
    directorio específico para este fin.

- **concurrent.enable**

  - Determina como procesar las firmas en las operaciones de firma de
    lotes. Puede tener dos valores:

    - true

      - Indica que se permite el proceso en paralelo de las entradas del
        lote.

    - false

      - Las firmas del lote se procesarán secuencialmente. Este es el
        valor por defecto.

- **concurrent.timeout**

  - Numero de segundos que debera durar como maximo cada fase de una
    operacion de firma en modo concurrente. Si se excediese este tiempo,
    se detendria y se consideraria que se produjo un error.

  - Valor por defecto: 30

- **concurrent.maxsigns**

  - Número máximo de firmas que se procesaran concurrentemente en caso
    de estar activo el modo concurrente.

  - Valor por defecto: 10

- **batch.maxDocuments**

  - Indica el numero máximo de documentos que se pueden enviar en una
    petición.

  - Valor por defecto: 15

- **batch.maxSize**

  - Indica el tamaño máximo global en bytes que puede tener la petición
    en bytes.

  - Valor por defecto: 100000

- **batch.maxReferenceSize**

  - Indica el tamaño máximo en bytes que puede tener la referencia a los
    ficheros dentro de la petició.

  - Valor por defecto: 50000

- **batch.maxDocSize**

  - Indica el tamaño máximo en bytes que puede tener un fichero que se
    esté procesando a través del mecanismo antiguo de firma por lotes.

  - Valor por defecto: 100000

El fichero de configuración básico por defecto será:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p># Orígenes permitidos</p>
<p>Access-Control-Allow-Origin=*</p>
<p># Permite indicar si se debe usar el proveedor de firma XML de
Apache.</p>
<p>xml.provider.apache=true</p>
<p># Clase del gestor de documentos a utilizar (debe implementar
DocumentManager)</p>
<blockquote>
<p>document.manager=es.gob.afirma.triphase.server.document.SelfishDocumentManager</p>
</blockquote>
<p># Clave de verificacion</p>
<blockquote>
<p>verification.key=</p>
</blockquote>
<p># Habilitar caché</p>
<blockquote>
<p>cacheEnabled=false</p>
</blockquote>
<p># Clase de implementacion de cache a utilizar (debe implementar
DocumentCacheManager)</p>
<blockquote>
<p>document.cache.manager=es.gob.afirma.triphase.server.cache.FileSystemCacheManager</p>
</blockquote>
<p># Numero maximo de paginas sobre las que comprobar el PDF Shadow
Attack.</p>
<p>maxPagesToCheckShadowAttack=10</p>
<p># Directorio para el guardado de temporales</p>
<p>tmpdir=</p>
<p># Operacion concurrente (true) o en serie (false)</p>
<p>concurrent.enable=false</p>
<p># Numero de segundos maximos para cada operacion de firma</p>
<p>concurrent.timeout=30</p>
<p># Numero maximo de firmas procesadas concurrentemente</p>
<blockquote>
<p>concurrent.maxsigns=10</p>
</blockquote>
<p># Limite del tamano del documento en bytes en antiguo mecanismo de
firma de lotes</p>
<blockquote>
<p>batch.maxDocSize=50000</p>
</blockquote></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Adicionalmente, en este fichero se podrán configurar todas aquellas
propiedades que se deseen establecer para el gestor de documentos y la
implementación de caché configurados. Así, por ejemplo, en el gestor de
documentos a través de sistema de ficheros (“FileSystemDocumentManager”)
que se proporciona junto al servicio como muestra, se puede configurar
un directorio de entrada de los datos y uno de salida para las firmas,
así como si se desean sobreescribir los datos en el directorio de
salida. También se incluye junto al servicio el gestor
“LegacyBatchDocumentManager”, orientado a proporcionar al sistema de
firma de lotes actual la misma funcionalidad que proporcionaba el
sistema de firma de lotes de AutoFirma 1.7 y anteriores.

Consulte el apartado <u>II.1.1 Gestor de documentos del servicio</u>
para saber más acerca de los gestores de documentos y sobre el gestor de
documentos a través de sistema de ficheros.

Si se activase el uso de la caché y se configurase la implementación por
defecto (es.gob.afirma.triphase.server.cache.FileSystemCacheManager), se
usarían las siguientes propiedades adicionales del fichero de
configuración:

- cache.tmpDir: Ruta absoluta del directorio del servidor donde se
  almacenarán temporalmente los documentos guardados en caché.

- cache.expTime: Tiempo de caducidad en milisegundos de los archivos
  cacheados. Debe ser un número entero y positivo. Valor por defecto:
  60000.

- cache.maxUseToCleaning: Configura cada cuántos usos se limpiará la
  caché. Durante el proceso de limpieza, se eliminará un fichero de la
  caché si ha excedido el tiempo de caducidad. Valor por defecto: 300.

Un desarrollador Java podría crear nuevos sistemas de caché e
integrarlos en el servicio. Esto le permitiría a crear procesos optimos
que redujesen las transferencias de datos por red.

Para implementar un sistema de caché, se deberá implementar la interfaz
es.gob.afirma.triphase.server.cache.DocumentCacheManager, disponible en
el módulo “afirma-server-triphase-signer-document” del proyecto. Puede
importar este módulo a su proyecto Maven mediante la referencia:

\<dependency\>

\<groupId\>es.gob.afirma\</groupId\>

\<artifactId\>afirma-server-triphase-signer-document\</artifactId\>

\<version\>1.8\</version\>

\</dependency\>

### Configuración de los servicios

Independientemente de su función, todos los servicios que acompañan al
Cliente @firma siguen la misma lógica para localizar su fichero de
configuración y el uso de variables de entorno. En este apartado se
explica cómo configurar estos aspectos comunes a todos ellos.

Los servicios del Cliente utilizan uno o varios ficheros de propiedades
para su configuración. Estos ficheros tienen nombres prefijados, pero el
integrador puede definir su ubicación mediante la variable de entorno
“clienteafirma.config.path”. El valor asignado a esta variable debe ser
la ruta del directorio en el que se encontrarán esos ficheros. La
variable puede establecerse, por ejemplo, por medio de la variable
\$JAVA_OPTS al levantar el servidor de aplicaciones. Por ejemplo:

| JAVA_OPTS=“%JAVA_OPTS% -Dclienteafirma.config.path=/opt/usuarios/cliente/conf” |
|--------------------------------------------------------------------------------|

También se puede hacer uso de otras variables declaradas por uno mismo o
por el propio servidor de aplicaciones. Por ejemplo:

| JAVA_OPTS=“%JAVA_OPTS% -Dclienteafirma.config.path=%CATALINA_HOME%/conf/afirma” |
|---------------------------------------------------------------------------------|

En caso de no declararse la variable de entorno, se buscarán los
ficheros en el *classpath* de la aplicación, por lo que podría
introducirse el fichero de configuración dentro de los WAR de los
servicios.

Cada uno de los ficheros de configuración de los servicios del Cliente
@firma está compuesto por una serie de propiedades con valores
asignados. El valor establecido en esas propiedades será el utilizado
por los servicios, pero también es posible heredar parte de la
configuración mediante variables de entorno. Para utilizar el valor de
una variable de entorno como parte o todo el valor de una de las
propiedades de configuración, estableceremos en el fichero el nombre de
la variable en cuestión delimitado por las partículas “\${” y “}”. Por
ejemplo:

Se podría establecer una propiedad en el arranque del servidor de
aplicaciones:

JAVA_OPTS=“%JAVA_OPTS%
-Dclienteafirma.config.path=%CATALINA_HOME%/conf/afirma
–DtempDir=%CATALINA_HOME%/temp/afirma”

Mientras, en nuestro fichero de configuración podríamos establecer el
valor de una propiedad valiéndonos de esa propiedad del sistema que
hemos establecido:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p># Se usará como directorio temporal, el subdirectorio "temp",
localizado</p>
<p># en el directorio configurado por medio de la propiedad de sistema
"tempDir".</p>
<p>tmpdir=${tempDir}/temp</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Los ficheros de configuración se leen una única vez durante la carga de
los servicios por lo que, tras realizar un cambio en ellos, será
necesario reiniciar el servidor de aplicaciones para que los servicios
los apliquen.

## Configuración del *Content Security Policy*

AutoFirma y los clientes móviles atienden las peticiones realizadas
desde el JavaScript de despliegue por medio del protocolo “afirma”. Si
su servidor web utiliza cabeceras CSP (Content Security Policy) para
limitar las fuentes de las que cargar los recursos de sus páginas web,
es probable que algunos navegadores Web (se ha identificado el caso
concreto de Mozilla Firefox) rechacen la llamada a estas URL externas.

En caso de que el servidor no utilice cabeceras CSP, no será necesario
hacer nada para el funcionamiento del Cliente @firma. Si, en cambio, sí
se utilizan, será necesario agregar a esta cabecera el esquema
“afirma://” para garantizar que el navegador permite el acceso a este
tipo de URL. Para hacer esto, se agregará la partícula “afirma://\*” en
la fuente por defecto de la política de seguridad.

Por ejemplo, si la cabecera con la política de seguridad fuese:

| Content-Security-Policy: default-src 'self' \*.site.com; img-src \* |
|---------------------------------------------------------------------|

Se modificaría para convertirlo en:

| Content-Security-Policy: default-src 'self' \*.site.com afirma://\*; img-src \* |
|---------------------------------------------------------------------------------|

# Integración del Cliente @firma en un trámite web

El API del Cliente @firma se expone automáticamente al entorno
JavaScript al importar en la página web la biblioteca “autoscript.js”.
En esta biblioteca está definido el objeto “AutoScript” y a partir de él
se podrá invocar a todas las operaciones del Cliente. Por ejemplo, para
inicializar el Cliente:

| AutoScript.cargarAppAfirma(); |
|-------------------------------|

O, para firmar:

| AutoScript.sign(…); |
|---------------------|

La operación de inicialización del cliente no implica una llamada al
Cliente @firma, únicamente inicializa el objeto JavaScript, por lo que
puede realizarse durante la carga de la página. El resto de las
llamadas, sin embargo, pueden implicar la invocación a una aplicación
externa como es el Cliente @firma.

La comunicación con el Cliente @firma se realiza de forma asíncrona.
Para poder gestionar esto, todas las funciones que implican llamar al
Cliente permiten que se les proporcione una función *callback* a través
de la cual obtener el resultado.

Para el correcto uso del Cliente @firma deben seguirse siempre las
siguientes normas:

- No lanzar operaciones de forma automática. Todas las operaciones
  deberían desencadenarse a raíz de una acción del usuario. Por ejemplo,
  no se debe llamar al método de firma durante la carga de la página
  web. En su lugar, por ejemplo, se debería mostrar un botón “Firmar” y,
  cuando el usuario pulse dicho botón, llamar a la operación de firma.

- No se deben lanzar simultáneamente varias operaciones del Cliente.
  Hasta que no se obtenga el resultado de una operación a través de su
  función *callback*, no se debería llamar a la siguiente. Así, por
  ejemplo, no se permitiría hacer lo siguiente:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>AutoScript.sign(…); // ERROR: La segunda función se llamará antes
de</p>
<p>AutoScript.sign(…); // terminar la anterior</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

En su lugar, se debería usar:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>// Funcion callback ejecutada al procesar el resultado de la
Firma 1</p>
<p>function callbackFirma1(…) {</p>
<p>AutoScript.sign(…); // Firma 2</p>
<p>}</p>
<p>…</p>
<p>AutoScript.sign(…, callbackFirma1, …); // Firma 1</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

## Carga de la aplicación

Una vez importado el JavaScript en la página Web, deberemos inicializar
el objeto de comunicación con el cliente mediante el método:

cargarAppAfirma()

Es necesario haber llamado al método de carga del Cliente antes de
realizar cualquier otra de las operaciones soportadas por la aplicación.

A continuación, se muestran diferentes ejemplos de carga del Cliente:

- Carga directa desde el código HTML:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>&lt;body&gt;</p>
<p>&lt;script type=<em>"text/javascript"</em>&gt;</p>
<p>AutoScript.cargarAppAfirma();</p>
<p>&lt;/script&gt;</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

- Carga desde una función invocada en el momento de firmar:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>function</strong> firmar() {</p>
<p>AutoScript.cargarAppAfirma();</p>
<p>AutoScript.sign(</p>
<p>dataB64,</p>
<p><em>"</em>SHA512withRSA<em>"</em>,</p>
<p><em>"</em>PAdES<em>"</em>,</p>
<p><strong>null</strong>,</p>
<p>firmaCorrectaCallback,</p>
<p>firmaErrorCallback);</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

La función de carga del Cliente sólo se debería invocar una única vez
por página web. Así, no se debe utilizar este último ejemplo si se va a
llamar varias veces al método de firma.

### Configuración de los puertos de comunicación

El trámite web y AutoFirma se comunicarán comúnmente a través de un
socket abierto en el equipo. Por defecto, es el propio JavaScript de
despliegue el que gestiona qué número de puerto debe usar para la
apertura del socket, pero el propio trámite web puede establecer una
configuración específica si conoce el entorno de sus usuarios y lo
considera conveniente.

La aplicación puede configurar los puertos a utilizar mediante el
método:

setPortRange (port1, port2)

La llamada a este método configura que para la comunicación debe
seleccionarse un puerto aleatorio de entre los determinados por el rango
port1-port2, ambos inclusive. Si sólo se indicase un parámetro en el
método o si ambos fuesen el mismo número de puerto, se utilizaría
siempre ese puerto para la comunicación.

Por defecto, el javascript escogerá un puerto en el rango 49152-65535.
Sin embargo, al utilizar este método, se puede establecer cualquier
subrango de entre los puertos 2014 y 65535.

Este método puede ser llamado antes o después del método de carga, pero
debe llamarse antes de invocar a la primera operación que requiera la
apertura de la aplicación. Una vez invocada una operación el puerto no
se puede establecer ni cambiar.

Ejemplos de uso de este método serían:

- Configuración de un rango de puertos específico:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>&lt;body&gt;</p>
<p>&lt;script type=<em>"text/javascript"</em>&gt;</p>
<p>AutoScript.setPortRange(61000, 62000);</p>
<p>AutoScript.cargarAppAfirma();</p>
<p>&lt;/script&gt;</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

- Configuración de un puerto concreto:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>&lt;body&gt;</p>
<p>&lt;script type=<em>"text/javascript"</em>&gt;</p>
<p>AutoScript.setPortRange(63117);</p>
<p>AutoScript.cargarAppAfirma();</p>
<p>&lt;/script&gt;</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

### Configuración de los servicios auxiliares de comunicación

La comunicación entre la página del trámite web y los clientes de firma
móviles se realizará a través de los servicios auxiliares de
almacenamiento y recuperación que habrá que desplegar junto a la página
de firma. También se utilizan estos con AutoFirma cuando la aplicación
lo indica expresamente.

Por regla general, es buena práctica desplegar siempre estos servicios y
configurarlos en nuestra aplicación, ya que posibilitan que el trámite
de firma sea compatible con diversos entornos de usuario, como con
dispositivos móviles y versiones antiguas de Internet Explorer y
Microsoft Edge Legacy.

Para la configuración de los servicios de comunicación se usará el
método:

setServlets (storageServiceUrl, retrieveServiceUrl)

Un ejemplo de configuración de los servicios auxiliares es:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>&lt;body&gt;</p>
<p>&lt;script type=<em>"text/javascript"</em>&gt;</p>
<p>AutoScript.setServlets(</p>
<p><em>"</em>https://gobierno.es/afirma-signature-storage/StorageService<em>",</em></p>
<p><em>"</em>https://gobierno.es/afirma-signature-retriever/RetrieveService<em>"</em>);</p>
<p>AutoScript.cargarAppAfirma();</p>
<p>&lt;/script&gt;</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Recuerde que, para evitar que se produzcan errores de *cross-site
scripting (XSS),* los servicios auxiliares de comunicación deben estar
disponibles desde el mismo dominio que la página web desde la que se
realiza la firma.

Consulte el apartado <u>5.3.1 Servicios auxiliares de comunicación</u>
para saber más acerca de los servicios auxiliares de comunicación y los
entornos de usuario para los que son necesarios.

### Forzado de la comunicación a través de los servicios auxiliares

Una aplicación puede forzar a que siempre se utilice la comunicación a
través de los servicios auxiliares, ya sea para mantener un
comportamiento homogéneo en todos los entornos, para evitar problemas
específicos con algún entorno o para optimizar algún proceso de firma
concreto. Esto, sin embargo, debería evitarse en la medida de lo
posible.

Se puede forzar la comunicación a través de los servicios auxiliares
invocando al método:

setForceWSMode(force)

Al invocar a este método con el parámetro true **antes de invocar al
método de carga**, el mecanismo de comunicación quedará prefijado al de
servicios auxiliares. Sin embargo, no se recomienda usar este método
salvo en casos muy específicos, como cuando se utilizan operaciones de
firma trifásica con un gestor de documentos a medida.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>Advertencia:</strong> Diversas características y medidas
de seguridad de los navegadores Firefox, Chrome y Edge afectan al uso de
AutoFirma cuando se comunican a través de los servicios auxiliares. Si
se forzarse al uso de estos servicios, debe evitarse realizar dos o más
llamadas a las funciones que invoquen al Cliente a raíz de una única
interacción del usuario. Por ejemplo, no se podría invocar una llamada a
una operación del Cliente desde la función <em>callback</em> de una
operación anterior.</p>
<p>Google Chrome y Microsoft Edge imponen restricciones adicionales que
también afectan a la compatibilidad del despliegue con dispositivos
móviles. Para saber más acerca de estas restricciones y la comunicación
con servidor intermedio, consulte el apartado <u><strong>¡Error! No se
encuentra el origen de la referencia.</strong> <strong>¡Error! No se
encuentra el origen de la referencia.</strong></u>.</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Un ejemplo de forzado de la comunicación a través de los servicios
auxiliares es:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>&lt;body&gt;</p>
<p>&lt;script type=<em>"text/javascript"</em>&gt;</p>
<p>AutoScript.setForceWSMode(<strong>true</strong>);</p>
<p>AutoScript.setServlets(</p>
<p><em>"</em>https://gobierno.es/afirma-signature-storage/StorageService<em>",</em></p>
<p><em>"</em>https://gobierno.es/afirma-signature-retriever/RetrieveService<em>"</em>);</p>
<p>AutoScript.cargarAppAfirma();</p>
<p>&lt;/script&gt;</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

### Restricción según desfase horario con el servidor

Al realizar una firma en el equipo del usuario, se registra en la propia
firma la hora del propio equipo (esto no aplica a las operaciones de
firma trifásicas). En caso de que la hora y/o fecha del equipo se
encuentren mal configuradas, es posible que una validación posterior de
la firma provoque errores, sobre todo si se trabaja también con sellos
de tiempo. Por norma general, esto sólo ocurre en casos extremos y no
suele ser necesario aplicar ninguna medida para evitar esto.

El JavaScript de despliegue del Cliente @firma incluye una función que
compara la hora del equipo del usuario con la del servidor web para así
detectar el desfase horario que hay entre ambos. En caso de detectar un
desfase se puede advertir al usuario o incluso bloquear la operación de
firma.

Para hacer la comprobación de desfase horario puede utilizar el método
JavaScript:

checkTime(checkType, maxMillis, checkURL)

Este método debe invocarse antes del método de carga del Cliente y puede
recibir como parámetros:

- checkType

  - Tipo de verificación que se desea realizar. Admite los valores:

    - AutoScript.CHECKTIME_NO: No realiza ningún tipo de comprobación.
      Este es el valor por defecto.

    - AutoScript.CHECKTIME_RECOMMENDED: Realiza la comprobación horaria
      y, en caso de encontrar un desfase, pedirá al usuario que lo
      corrija antes de continuar.

    - AutoScript.CHECKTIME_OBLIGATORY: Realiza la comprobación horaria
      y, en caso de encontrar un desfase, pedirá al usuario que lo
      corrija y evitará que el Cliente se ejecute en cualquier llamada
      posterior.

- maxMillis

  - Milisegundos máximos que se permiten de desfase. Se recomienda que
    se indique un periodo mínimo de 1 minuto (60.000 milisegundos) para
    facilitar la corrección de la hora en el equipo del usuario.

  - El valor por defecto son 5 minutos (300.000 milisegundos).

- checkURL

  - URL contra la que se realizara la petición para obtener la hora del
    servidor.

  - Por defecto, se usará la URL de la página cargada en el navegador.
    Si cree que es posible que esto ocasione un mal funcionamiento por
    parte de su aplicación, indique otra URL dentro de su dominio.

Un ejemplo de uso sería:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>&lt;body&gt;</p>
<p>&lt;script type=<em>"text/javascript"</em>&gt;</p>
<p>AutoScript.checkTime(AutoScript.CHECKTIME_RECOMMENDED, 300000);</p>
<p>AutoScript.cargarAppAfirma();</p>
<p>&lt;/script&gt;</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Debe notarse que, según la configuración del servidor web, es posible
que no se pueda determinar la hora a través de la información que este
proporciona. De ser así, no se mostrará ninguna advertencia al usuario
para no perjudicar la realización del trámite. También es posible que un
servidor sólo transmita la hora en la primera carga de la página y no
cuando esta se refresca. Si ese fuese el caso, sólo se advertiría de la
diferencia horaria en la primera carga de la página y no si el usuario
refrescase la página desde su navegador.

Téngase en cuenta también que el desfase horario se calcula en el
momento de invocar al método checkTime. Así pues, si el usuario
modificase la hora de su sistema después de la comprobación, podría
realizar operaciones de firma sin que se le mostrasen advertencias.

En caso de que desee bloquear de forma completa la firma de datos cuando
se detecte una hora incorrecta en el sistema, asegúrese de que el
servidor de la página web de comprobación de hora siempre envía la hora
en las respuestas de sus peticiones y llame al método checkTime antes de
cada operación de firma.

### Selección del almacén de claves

El Cliente @firma accede al almacén de claves del navegador web o el
sistema operativo del usuario para ofrecer sus certificados en las
operaciones de firma. Los almacenes utilizados por defecto por cada una
de las aplicaciones son:

- **AutoFirma**:

  - Si se utiliza Firefox, se accederá al almacén de claves interno del
    navegador y se buscarán las tarjetas inteligentes configuradas como
    dispositivos de seguridad en este.

  - En cualquier otro caso, se usará el del sistema operativo.

    - Windows: CAPI (*Cryptography Application Programming Interface*)

    - macOS: Llavero de macOS

    - Linux: Almacén compartido NSS

  - Cuando se detecte un DNIe o una tarjeta CERES conectada al equipo,
    AutoFirma accederá a ella y dará la posibilidad de firmar con sus
    certificados, independendientemente de que también se muestren los
    certificados del navegador o del sistema operativo.

- **Cliente móvil Android**:

  - Utiliza el almacén de claves de Android.

- **Cliente móvil iOS**:

  - Utiliza el almacén de la propia aplicación.

Aunque **se recomienda no seleccionar el uso de un almacén de claves
distinto al por defecto**, AutoFirma permite que se configure otro de
los almacenes soportados. Los Cliente móviles, en cambio, sólo admiten
el almacén por defecto.

Para establecer el almacén de claves al que debe acceder AutoFirma, se
deberá utilizar el siguiente método antes de invocar a cualquier
operación de firma o selección de certificado:

setKeyStore (keystore);

En esta función:

- keystore

  - Tipo de almacén al que se debe URL de acceso a los datos a
    descargar.

  - En el objeto AutoScript se han definido las siguientes claves para
    configurar almacenes de claves:

    - KEYSTORE_WINDOWS

      - Almacén de certificados CAPI. Compatible únicamente con sistemas
        Microsoft Windows.

    - KEYSTORE_APPLE

      - Llavero de macOS. Compatible únicamente con sistemas Apple
        macOS.

    - KEYSTORE_SHARED_NSS

      - Almacén NSS del sistema. Compatible únicamente con sistemas
        Linux.

    - KEYSTORE_MOZILLA

      - Almacén NSS de Mozilla (Mozilla Firefox, Mozilla Thunderbird,
        etc.).

    - KEYSTORE_PKCS12

      - Almacén en fichero PKCS#12 / PFX (Personal File Exchange).

    - KEYSTORE_JAVA

      - Almacén en fichero JKS (Java KeyStore).

    - KEYSTORE_JCEKS

      - Almacén en fichero JCEKS (Java Cryptography Extension KeyStore).

    - KEYSTORE_JAVACE

      - Almacén en fichero de tipo CaseExactJKS (Case Exact Java
        KeyStore).

    - KEYSTORE_PKCS11

      - Almacén de claves compatible PKCS#11 (tarjetas inteligentes,
        aceleradora criptográfica…).

Si se selecciona un almacén no disponible en el entorno del usuario,
AutoFirma dará error al intentar acceder al almacén de claves. Los
clientes móviles únicamente ignorarán esta opción de la configuración.

Determinados tipos de almacén permiten indicar el fichero o biblioteca
en disco asociado al almacén. Este fichero o biblioteca debe indicarse
mediante su ruta absoluta en el sistema del usuario, como parte del
mismo parámetro, a continuación del tipo de almacén y separados por
signo dos puntos (‘:’), siguiendo el patrón:

> TIPO_ALMACEN:RUTA_ALMACEN

Los almacenes que permiten indicar el fichero o biblioteca que se debe
utilizar son:

- KEYSTORE_APPLE

  - Permite indicar un fichero de tipo llavero en el que se encuentran
    los certificados de firma.

  - Si no se indica ningún fichero se usa el llavero general del
    sistema.

- KEYSTORE_PKCS12

  - Permite indicar el almacén en fichero de tipo PKCS#12/PFX
    (normalmente con extensiones “p12” o “pfx”) en el que se encuentran
    los certificados de firma.

  - Si no se indica ningún fichero AutoFirma solicitará al usuario que
    seleccione uno mediante un diálogo gráfico.

- KEYSTORE_PKCS11

  - Permite indicar la biblioteca que se debe utilizar para acceder al
    dispositivo que almacena los certificados de firma.

  - Si no se indica ningún fichero, el Cliente @firma solicitará al
    usuario que seleccione uno mediante un diálogo gráfico.

  - Es importante reseñar que la biblioteca PKCS#11 es dependiente del
    sistema operativo y de su arquitectura, por lo que, si se indica,
    por ejemplo, una biblioteca PKCS#11 como una DLL (Dynamic Link
    Library) de 32 bits, no funcionará ni en Linux ni en macOS, pero
    tampoco en Windows si se utiliza AutoFirma 64 bits.

| **Advertencia**: Los almacenes que hacen uso de un fichero o biblioteca requieren una contraseña de acceso. Esta contraseña se preguntará directamente al usuario cuando se requiera el acceso al almacén. |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

A continuación, se muestran ejemplos de selección del almacén de claves:

- Configuración del almacén de Windows:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>AutoScript.cargarAppAfirma();</p>
<p>AutoScript.setKeyStore(AutoScript.KEYSTORE_WINDOWS);</p>
<p>…</p>
<p>AutoFirma.sign (dataB64, "SHA512withRSA", "CAdES",
<strong>null</strong>, successCallback, errorCallback);</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

- Configuración de un almacén PKCS#12 en una ruta conocida:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>AutoScript.cargarAppAfirma();</p>
<p>AutoScript.setKeyStore(AutoScript.KEYSTORE_PKCS12 +
":/usr/home/usuario/almacen.p12");</p>
<p>…</p>
<p>AutoFirma.sign (dataB64, "SHA512withRSA", "CAdES", null,
successCallback, errorCallback);</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

- Configuración de un controlador PKCS#11 para el acceso de dispositivo
  critprográfico:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>AutoScript.cargarAppAfirma();</p>
<p>AutoScript.setKeyStore(AutoScript.KEYSTORE_PKCS11 +
":C:\\Windows\\System32\\PkcsV2GK.dll");</p>
<p>…</p>
<p>AutoFirma.sign (dataB64, "SHA512withRSA", "CAdES", null,
successCallback, errorCallback);</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

En sistemas Windows, puede darse el caso de que el usuario utilice un
perfil temporal, con lo que el usuario no contará con certificados ni
tarjetas instaladas en el almacén de Windows. Cuando el Cliente @firma
detecte este caso, hará uso del controlador de tarjetas integrado en la
aplicación (JMulticard) para acceder a un DNIe o tarjeta CERES insertada
en un lector del equipo. Además, buscará en el sistema una serie
predeterminada de bibliotecas PKCS#11 y tratará de utilizar las tarjetas
inteligentes insertadas y asociadas a estas bibliotecas.

#### Uso de tarjetas inteligentes

AutoFirma tiene acceso a las claves de las tarjetas inteligentes a
partir de sus controladores cuando están instalados en el sistema. Para
utilizar los certificados en tarjeta en las operaciones de firma, se
puede acceder a ellos desde un almacén PKCS#11 configurado o desde
cualquiera de los almacenes de sistema disponibles:

- KEYSTORE_WINDOWS: El almacén de Windows carga automáticamente todas
  las tarjetas insertadas para las que se haya instalado su controlador
  CSP o el MiniDriver correspondiente de Windows Update. En caso de
  detectarse un DNIe insertado o una tarjeta CERES, se hará uso de los
  mismos a partir de un controlador interno de la aplicación para
  corregir problemas detectados con Java en los controladores oficiales.

- KEYSTORE_MOZILLA/ KEYSTORE_SHARED_NSS: Los almacenes de Mozilla se
  componen de un almacén interno y el conjunto de controladores PKCS#11
  de las tarjetas instaladas en el sistema. AutoFirma cargará
  automáticamente el almacén interno y todos los dispositivos
  detectados. Debido a problemas de incompatibilidad detectados entre
  Java y los controladores oficiales de DNIe y tarjetas CERES, en caso
  de detectarse insertada cualquiera de estas tarjetas se utilizará un
  controlador interno de la aplicación, ignorándose los PKCS#11
  configurados en el almacén de Mozilla. En caso de detectar alguna de
  estas tarjetas también se ignorarán el resto de los dispositivos
  insertados para evitar problemas entre los distintos controladores.

- KEYSTORE_APPLE: El llavero de macOS se compone de un almacén internos
  y el conjunto de controladores de las tarjetas insertadas. Debido a
  problemas detectados con Java y los controladores oficiales de DNIe y
  tarjetas CERES, en caso de detectarse insertada cualquiera de estas
  tarjetas se utilizará un controlador interno de la aplicación.

Por regla general, se considera que sólo debería haber una tarjeta
inteligente insertada en el momento de firmar. En caso de encontrarse
varias, se dará prioridad al DNIe y las tarjetas CERES. En dichos casos,
es posible que los certificados del resto de tarjetas no aparezcan
disponibles para firmar o den error durante la firma.

El uso de las tarjetas CERES de la FNMT y del DNIe se realiza a través
de las bibliotecas de JMulticard, por lo que no es necesario tener
instalados sus controladores en el equipo para poder firmar con ellas.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>Advertencia</strong>: Existen controladores de tarjetas
inteligentes que, tras la inserción de la tarjeta, registran en el
almacén de Windows los certificados que contiene. A partir de entonces,
los certificados se muestran en el almacén incluso sin tener la tarjeta
insertada. Se ha encontrado que en Windows 10 21H1 y superiores este
comportamiento produce problemas con Java y AutoFirma, ya que al
intentar cargar el almacén de claves se intentan cargar esos
certificados que en realidad no se encuentran en el almacén. El
resultado es que el proceso de carga puede llevar varios minutos, lo que
se traduce en que se tarda ese tiempo en mostrarse el diálogo de
selección de certificados o realizar la firma si el certificado se
seleccionaba directamente. Subsiguientes firmas no conllevan esperar
este tiempo, ya que para entonces el almacén ya está cargado, pero
volverá a suceder si se recarga el almacén.</p>
<p>Para solventar esta situación es necesario eliminar esos certificados
del almacén de Windows cuando la tarjeta no se encuentra
insertada.</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

| **Advertencia:** A partir de cierta versión del controlador de la tarjeta CERES se ha apreciado que, si se tiene en el almacén de Windows instalado un certificado que también se encuentra en el almacén de la tarjeta inteligente, el certificado local se elimina tras el uso de la tarjeta. Este comportamiento no está relacionado con el uso de AutoFirma. |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

#### Uso del DNIe

AutoFirma utiliza la biblioteca JMulticard para permitir firmar con DNIe
sin necesidad de que los usuarios tengan instalados los controladores de
la tarjeta. Esta biblioteca se utilizará siempre que se encuentre un
DNIe insertado en un lector del equipo y se inserte su PIN en el diálogo
de JMulticard.

La aplicación solicita el PIN del DNIe antes de listar los certificados
del almacén y de que el usuario indique qué certificado desea utilizarla
para firmar. Este comportamiento emula el de los controladores PKCS#11
de las tarjetas en donde el PIN es necesario para listar los
certificados contenidos por la tarjeta y sigue la lógica de que si un
usuario ha insertado el DNIe en el lector es porque lo desea utilizar.
Cuando el usuario inserta el PIN, se listan sus certificados y se abre
el canal seguro con la tarjeta y, en el momento de firmar, se utiliza
este canal seguro para realizar la operación de firma. A continuación,
se cierra el canal seguro.

Las operaciones de firma realizadas posteriormente desde la misma
instancia del AutoFirma, solicitarán el PIN de la tarjeta sólo en el
momento de realizar la firma, momento en el cual se volverá a abrir el
canal seguro con la tarjeta.

Si se recargase el almacén por medio de la opción correspondiente del
diálogo de selección de certificados, el controlador se reiniciaría y
volvería a pedir el PIN de la tarjeta para listar los certificados.

El diálogo de solicitud de PIN de JMulticard mostrará una casilla para
indicar que se desea recordar la contraseña de la tarjeta durante el
resto de la sesión. Esta casilla funciona cuando las firmas se realizan
dentro de la misma operación (firma de lotes, contrafirmas de varios
nodos…). Para que se recuerde la contraseña a lo largo de distintas
operaciones es necesario que se utilice simultáneamente la función
“setStickySignatory()”, descrita en el apartado <u>6.2.1 Firma de
múltiples documentos (firma masiva)</u>. En el momento en el que se
cierra la instancia de AutoFirma (se cambia de página, se utiliza
comunicación por servidor intermedio, se cumple el tiempo máximo de
inactividad en la comunicación por sockets, etc.), dejará de surtir
efecto la configuración de “setStickySignatory()” y se volverá a pedir
el PIN de la tarjeta.

En el caso de ejecutar Autofirma usando el almacén de Windows y cancelar
el diálogo de PIN del DNIe de JMulticard, se cargará el almacén del
sistema normalmente. Si se tiene instalado el controlador oficial del
DNIe en el equipo esto puede implicar que los certificados del DNIe se
listen también en el diálogo de selección de certificados ya que será el
controlador oficial el que los cargue. En estos casos, también se usará
el controlador oficial para realizar la firma.

## Firma electrónica

La operación de firma electrónica nos permite generar la firma
electrónica de unos datos, que pueden haber sido proporcionados por la
aplicación o seleccionados por el usuario.

Para ejecutar la operación de firma se utiliza la función JavaScript:

sign(dataB64, algorithm, format, params, successCb, errorCb);

En esta función:

- dataB64

  - Datos que se desean firmar codificados en Base64.

    - Si los datos que necesita firmar son un texto (texto plano, XML,
      JSON, etc), puede convertirlos a Base64 por medio de las funciones
      de utilidad proporcionadas en el JavaScript de despliegue,
      descritas en el apartado <u>6.9.2 Conversión de un texto a cadena
      Base64</u>.

  - Si no se proporciona este parámetro (se usa null) o si se pasa una
    cadena vacía, el Cliente @firma mostrará al usuario un diálogo de
    selección de fichero para que seleccione el documento que desea
    firmar.

    - Salvo en casos concretos, no se recomienda dejar en manos del
      usuario la selección del fichero a firmar. Incluso si es necesario
      hacerlo, se recomienda hacer que el usuario cargue los datos
      previamente en servidor mediante un componente HTML y seguidamente
      se realice una operación de firma trifásica.

    - Para la compatibilidad con dispositivos móviles, nunca se deben
      proporcionar nulos o cadena vacía.

<!-- -->

- algorithm

  - Algoritmo de firma. Consulte el apartado dedicado a los algorirmos
    de firma soportados para el formato de firma que desee utilizar.

<!-- -->

- format

  - Formato de firma. Consulte el apartado <u>8 Formatos de firma</u>
    para consultar aquellos disponibles.

<!-- -->

- params

  - Parámetros adicionales para la configuración de la operación de
    firma y características particulares del formato de firma
    seleccionado.

    - Si se introduce un nulo, se usará la configuración por defecto
      para el formato de firma establecido.

    - Consulte el apartado <u>7.1 Paso de parámetros adicionales</u>
      para saber cómo realizar el paso de parámetros y el apartado de
      información específica del formato de firma que desee realizar
      para saber los parámetros soportados por el formato en cuestión.

<!-- -->

- successCb

  - Función *callback* JavaScript que se ejecutará una vez se obtenga el
    resultado de la operación de firma. Esta función recibirá hasta tres
    parámetros:

    1.  En el primer parámero se recibe la firma resultante codificada
        en Base64.

    2.  En el segundo parámetro se recibe el certificado usado para
        firmar codificado en Base64.

    3.  En el tercer parámetro, opcionalmente, se recibirá un objeto
        JSON con el nombre del fichero firmado (en caso de que lo haya
        seleccionado el usuario).

<!-- -->

- errorCb

  - Función *callback* JavaScript que se ejecutará cuando ocurra un
    error durante la operación de firma. Esta función recibirá hasta dos
    parámetros:

    1.  En el primer parámetro se recibe un texto con el tipo del error.

    2.  En el segundo parámetro se recibe un texto con el mensaje de
        error.

A continuación, se muestran distintos ejemplos de firma electrónica:

- Firma electrónica de datos:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>var</strong> dataB64 = "SG9sYSBNdW5kbyE="; // Datos a
firmar</p>
<p>AutoScript.sign (dataB64, "SHA512withRSA", "CAdES",
"mode=implicit\nexpPolicy=FirmaAGE", successCallback,
errorCallback);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

- Firma electrónica de un texto:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>var</strong> dataB64 = AutoScript.getBase64FromText("Hola
Mundo!!");</p>
<blockquote>
<p>AutoScript.sign (dataB64, "SHA512withRSA", "XAdES",
<strong>null</strong>, successCallback, errorCallback);</p>
</blockquote>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

- Firma electrónica cargando datos desde un fichero:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>// Función que se ejecutará cuando la firma termine
correctamente.</p>
<p>// Almacenara la firma, el certificado y el nombre del fichero
firmado en</p>
<p>// campos de un formulario y lo enviará a servidor</p>
<p><strong>function</strong> sendSignatureCallback (signatureB64,
certificateB64, extraData) {</p>
<p>// Obtenemos el nombre del fichero cargado para</p>
<p><strong>var</strong> filename = !!extraData ? extraData.filename :
<strong>null</strong>;</p>
<p>document.getElementByName("signatureField").value = signatureB64;</p>
<p>document.getElementByName("certificateField").value =
certificadteB64;</p>
<p><strong>if</strong> (filename) {</p>
<p>document.getElementByName("filenameField").value = filename;</p>
<p>}</p>
<p>document.getElementByName("formulario").submit();</p>
<p>}</p>
<p>// Funcion que se ejecutara cuando el proceso de firma falle</p>
<p><strong>function</strong> showErrorCallback (type, message) {</p>
<p>showError(message); // Funcion de la aplicación para mostrar
errores</p>
<p>}</p>
<p>…</p>
<p>// Llamamos a la operacion de firma</p>
<p>AutoScript.sign (<strong>null</strong>, "SHA512withRSA", "CAdES",
<strong>null</strong>, sendSignatureCallback, showErrorCallback);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Es importante recalcar que la aplicación que solicita la firma no sabrá
del resultado de la operación hasta que el JavaScript de despliegue
invoque a la función *callback* de éxito o de error. Es probable que no
se desee que el usuario interaccione de ninguna manera con la aplicación
hasta haber finalizado la firma, por lo que se recomienda que se le
muestre un mensaje de espera justo antes de llamar a la operación de
firma (pudiendo incluso bloquear la posibilidad de interaccionar con la
interfaz de la aplicación). Este mensaje no debería retirarse hasta
recibir una respuesta de la aplicación, por lo que se eliminaría en las
funciones *callback* de éxito y de error. A partir de entonces, el
usuario podría navegar de nuevo libremente.

La espera de la aplicación a la respuesta del cliente de firma debería
aplicarse a cualquier operación de firma, cofirma, contrafirma o firma
de lote y es especialmente importante cuando se fueza el modo de
comunicación entre la aplicación y el cliente sea a través de servidor
intermedio o cuando se desea que nuestra aplicación sea compatible con
los Clientes móviles.

### Firma de múltiples documentos (firma masiva)

Cuando se deseen firmar multiples datos a través del Cliente @firma debe
tenerse en cuenta un aspecto importante: el envío de datos a firmar debe
realizarse siempre secuencialmente, nunca en paralelo. Es decir, no
enviaremos a firmar un dato hasta no haber recibido el resultado de una
operación anterior.

El modo común y recomendado de realizar la firma secuencial de múltiples
documentos es solicitar la firma de un documento en la función
*callback* en la que se recibe el resultado de la operación anterior.

Un ejemplo de uso es:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>// Posicion del elemento que se esta procesando</p>
<p><strong>var</strong> idx = 0;</p>
<p>// Array con los valores a firmar</p>
<p><strong>var</strong> dataArray = [
"UHJpbWVyIGRhdG8gZGUgcHJ1ZWJh",</p>
<p>"U2VndW5kbyBkYXRvIGRlIHBydWViYQ==",</p>
<p>"VGVyY2VyIGRhdG8gZGUgcHJ1ZWJh",</p>
<p>"Q3VhcnRvIGRhdG8gZGUgcHJ1ZWJh"</p>
<p>];</p>
<p>// Iniciamos la firma del primer dato a firmar</p>
<p>AutoScript.setStickySignatory(<strong>true</strong>);</p>
<p>AutoScript.sign( dataArray[idx],</p>
<p>"SHA512withRSA",</p>
<p>"CAdES",</p>
<p>paramsParam,</p>
<p>successCallback,</p>
<p>showErrorCallback);</p>
<p>…</p>
<p>// Función callback a ejecutar cuando termine correctamente una
firma</p>
<p><strong>function</strong> successCallback (signatureB64) {</p>
<p>// Procesamos la firma</p>
<p>…</p>
<p>// Mandamos a firmar el siguiente dato (si quedase alguno)</p>
<p>++idx;</p>
<p><strong>if</strong> (idx &lt; dataArray.length) {</p>
<p>AutoScript.sign( dataArray[idx],</p>
<p>"SHA512withRSA",</p>
<p>"CAdES",</p>
<p>paramsParam,</p>
<p>successCallback,</p>
<p>showErrorCallback);</p>
<p>}</p>
<p><strong>else</strong> {</p>
<p>// Ya se han generado todas las firmas</p>
<p>…</p>
<p>}</p>
<p>}</p>
<p>// Función callback a ejecutar cuando falle la firma</p>
<p><strong>function</strong> showErrorCallback (errorType, errorMsg)
{</p>
<p>// Mostramos el error</p>
<p>alert(“Error durante la firma de un documento. Se interrumpirá el
proceso de firma.”);</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Para posibilitar que el usuario sólo deba seleccionar el certificado de
firma en una ocasión y no para operación individual, se deberá dejar
prefijado este certificado mediante el método:

setStickySignatory (sticky);

En esta función:

- *sticky*

  - Indica si se debe fijar el siguiente certificado que se utilice.

    - Si se indica el valor “true”, el próximo certificado que
      seleccione mediante un filtro o que seleccione directamente el
      usuario (en una operación de firma o selección de certificado)
      quedará fijado y se utilizará para todas las operaciones
      posteriores.

    - Si se indica el valor false, se libera el certificado y se volverá
      a solicitar al usuario en cada una de las siguientes operaciones.

Esta función no devuelve nada y sólo es compatible con AutoFirma. En una
operación de firma con los clientes móviles, el usuario deberá
seleccionar el certificado por cada operación de firma individual.

Al realizar múltiples firmas con tarjetas inteligentes, es posible que
se pida el PIN de la tarjeta por cada operación individual, según sea el
comportamiento definido por el controlador de la propia tarjeta. En caso
de usarse una tarjeta CERES o el DNIe, el controlador será JMulticard y
este mostrará en el diálogo de selección de PIN una casilla que podrá
seleccionarse para que la aplicación recuerde el PIN y no lo vuelva a
solicitar si se ha llamado a la función “setStickySignatory()” con el
valor “true”.

Adicionalmente, para la generación de multifirmas dentro de un
procedimiento masivo es interesante indicar el valor “AUTO” como formato
de firma. Al hacerlo, las cofirmas y contrafirmas se realizarán en el
mismo formato que la firma sobre la que se opera. El valor “AUTO” no es
válido para firmas simples. Puede saber más sobre esta opción en el
apartado <u>8 Formatos de firma</u>.

Otra alternativa para firmar múltiples documentos es la operación de
<u>6.5 Firma de lotes predefinidos</u>.

### Firma trifásica

Una operación de firma requiere preparar la estructura de la firma
conforme el formato de firma seleccionado, cifrar con la clave privada
del certificado del usuario parte de esa estructura e introducir esos
datos cifrados dentro de la misma estructura. Habitualmente, estos tres
pasos se ejecutan de forma conjunta en el cliente y por eso decimos que
la firma se ha ejecutado en una única fase (monofásica).

Una alternativa a lo anterior sería separar estos tres pasos y delegar
en un servidor aquello que no requiera datos del usuario. Así, preparar
la estructura e introducir los datos cifrados en ella (fases 1 y 3) se
puede realizar en servidor, mientras que el cifrado de los datos con la
clave privada del certificado del usuario se realizaría en local (la
clave del certificado nunca sale del equipo del usuario). Este mecanismo
en tres pasos es lo que se denomina firma trifásica.

Las firmas realizadas por AutoFirma se realizan, por defecto, de forma
monofásica. Sin embargo, el AutoFirma también permite realizar las
firmas de forma trifásica y los clientes móviles las realizarán casi en
todos los casos de este modo.

Las operaciones de firma trifásicas ayudan a reducir el envío de
información entre el Cliente y el servidor cuando los datos a firmar se
encuentran en servidor y/o cuando la firma generada por el usuario va a
enviarse a ese servidor. Sin embargo, ya que parte de la operación
trifásica se realiza en servidor, puede suponer un problema si se recibe
un volumen de peticiones mayor al que puede procesar, ya que aumentan
sus necesidades de memoría y procesador.

La realización de firmas trifásicas requiere el despliegue del servicio
de firma trifásica descrito en el apartado <u>5.3.2 Servicios de firma
trifásica y firma de lotes</u>. Así mismo, se deberán cumplir las
siguientes condiciones en la operación de firma:

- Se podrá proporcionar una referencia a los datos a firmar en lugar de
  los propios datos. El tipo de referencia variará según la clase
  gestora de documentos configurada en el servicio de firma trifásica.
  Con la clase gestora por defecto se seguirán requiriendo los propios
  datos.

- Se usará el nombre del formato de firma trifásica en lugar del nombre
  de formato tradicional:

  - Para firmas CAdES: CAdEStri

  - Para firmas XAdES: XAdEStri

  - Para firmas PAdES: PAdEStri

  - Para firmas de factura electrónica: FacturaEtri

**NOTA:** En los clientes móviles se realizará firma trifásica
indepedencientemente de que se use el nombre monofásico del formato
cuando la aplicación cliente no soporte su generación monofásica.

- Se configurará el parámetro adicional “serverUrl” con la URL del
  servicio de firma trifásica. Para saber más de los parámetros
  adicionales de configuración consulte el apartado <u>7.1 Paso de
  parámetros adicionales</u>.

Un ejemplo de operación de firma trifásica sería:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>// Configuramos una firma CAdES trifásica implicita</p>
<p><strong>var</strong> params =
"mode=implicit\nserverUrl=https://servidor.com/afirma/afirma-server-triphase-signer/SignatureService";</p>
<p>AutoScript.sign (dataRefB64, "SHA512withRSA", "CAdEStri", params,
showSignResultCallback, showErrorCallback);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

El proceso trifásico de firma se encuentra disponible para las
operaciones de firma, cofirma y contrafirma.

Consulte más información sobre la operativa interna del proceso de firma
trifásica en el apartado <u>ANEXO II Firma trifásica</u>.

## Cofirma electrónica

La cofirma es la operación mediante la cual se agrega una nueva firma a
una firma previa. La firma generada está al mismo nivel que la firma
original. Esta sería la operación mediante la cual dos o más firmantes
muestran su acuerdo con un documento.

La cofirma consiste en agregar la información de firma de un firmante a
una firma ya existente. Así, será necesario que una persona firme el
documento generando así la información de firma. El segundo firmante
deberá cofirmar la firma generada por el primer firmante, el tercero
cofirmará la firma generada por el segundo y así sucesivamente. Esta
operación se puede realizar por entero en el lado cliente o a través del
proceso de firma trifásica descrito en el <u>ANEXO II Firma
trifásica</u>.

La función JavaScript mediante la cual se realizan las cofirmas es:

> cosign(signB64, algorithm, format, params, successCb, errorCb);

En esta función:

- signB64

  - Firma electrónica que se desea cofirmar codificada en Base64.

    - Una firma en Base64 puede ser el resultado obtenido por cualquier
      operación de firma, cofirma o contrafirma previa.

  - Si no se proporciona este parámetro (se usa null) o si se pasa una
    cadena vacía, el Cliente @firma mostrará al usuario un diálogo de
    selección de fichero para que seleccione el fichero de firma que
    desea cofirmar.

    - Salvo en casos concretos, no se recomienda dejar en manos del
      usuario la selección del fichero de firma. Incluso si es necesario
      hacerlo, se recomienda hacer que el usuario cargue la firma
      previamente en servidor mediante un componente HTML y seguidamente
      se realice una operación de cofirma trifásica.

    - Para la compatibilidad con dispositivos móviles, nunca se deben
      proporcionar nulos o cadena vacía.

- algorithm

  - Algoritmo de firma. Consulte el apartado dedicado a los algorirmos
    de firma soportados para el formato de firma que desee utilizar.

- format

  - Formato de firma. Consulte el apartado <u>8 Formatos de firma</u>
    para consultar aquellos disponibles.

    - Si no conoce el formato de firma utilizado en la firma original,
      indique el valor “AUTO” para especificar que se utilice el mismo
      formato que la firma original.

    - Por norma general, no se puede cofirmar una firma en un formato
      distinto al que se usó para generar dicha firma.

- params

  - Parámetros adicionales para la configuración de la operación de
    cofirma y características particulares del formato de firma
    seleccionado.

    - Si se introduce un nulo, se usará la configuración por defecto
      para el formato de firma establecido.

    - Consulte el apartado <u>7.1 Paso de parámetros adicionales</u>
      para saber cómo realizar el paso de parámetros y el apartado de
      información específica del formato de firma que desee realizar
      para saber los parámetros soportados por el formato en cuestión.

- successCb

  - Función *callback* JavaScript que se ejecutará una vez se obtenga el
    resultado de la operación de cofirma. Esta función recibirá hasta
    tres parámetros:

    1.  En el primer parámero se recibe la firma resultante codificada
        en Base64.

    2.  En el segundo parámetro se recibe el certificado usado para
        cofirmar codificado en Base64.

    3.  En el tercer parámetro, opcionalmente, se recibirá un objeto
        JSON con el nombre del fichero de firma cofirmado en caso de que
        lo haya seleccionado el usuario.

- errorCb

  - Función *callback* JavaScript que se ejecutará cuando ocurra un
    error durante la operación de firma. Esta función recibirá hasta dos
    parámetros:

    1.  En el primer parámetro se recibe un texto con el tipo del error.

    2.  En el segundo parámetro se recibe un texto con el mensaje de
        error.

A continuación, se muestran distintos ejemplos de operaciones de
cofirma:

- Cofirma electrónica de una firma ya cargada:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>var</strong> signatureB64 = … // Firma electrónica a
cofirmar</p>
<p>AutoScript.cosign(signatureB64, “SHA512withRSA”, “AUTO”,
<strong>null</strong>, successCallback, errorCallback);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

- Cofirma electrónica cargando una firma desde un fichero:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>AutoScript.cosign(<strong>null</strong>, “SHA512withRSA”, “XAdES”,
<strong>null</strong>, successCallback, errorCallback);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

- Cofirma electrónica del resultado de una firma:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>// Funcion que realiza la cofirma a partir de los datos de firma</p>
<p><strong>function</strong> cosignCallback (signatureB64) {</p>
<p>AutoScript.cosign(</p>
<p>signatureB64, “SHA512withRSA”, “XAdES”, <strong>null</strong>,
sendDataCallback, showErrorCallback</p>
<p>);</p>
<p>}</p>
<p>…</p>
<p>// Función que almacena los datos generados por la cofirma en el
campo</p>
<p>// “resultId” de un formulario y lo envia</p>
<p><strong>function</strong> sendDataCallback (cosignB64,
certificateB64) {</p>
<p>document.getElementById(“resultId”).value = cosignB64;</p>
<p>document.getElementById(“firmante”).value = certificateB64;</p>
<p>document.getElementById(“formulario”).submmit();</p>
<p>}</p>
<p>…</p>
<p>// Función para firmar datos. Si termina correctamente la operación
de firma</p>
<p>// se llama a la función “cosignFunction” con el resultado de la
operación y,</p>
<p>// si ésta también termina correctamente, se llama a la función</p>
<p>// “saveDataFunction” con el resultado de la cofirma. Si falla alguna
de</p>
<p>// estas funciones se llama al método “showError”</p>
<p><strong>function</strong> firmar(dataB64) {</p>
<p>AutoScript.sign(dataB64, “SHA512withRSA”, “XAdES”, “format=XAdES
Detached”, cosignCallback, showErrorCallback);</p>
<p>}</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

## Contrafirma electrónica

La contrafirma es la operación mediante la cual se refrenda una firma
electrónica previa. En términos generales, es el firmar una firma
electrónica. Este es el tipo de operación que realizaría un organismo,
por ejemplo, como prueba de registro de una firma electrónica en su
sistema.

La contrafirma no es una operación que soporten todos los formatos de
firma. Consulte el apartado dedicado a los algorirmos de firma
soportados para el formato de firma que desee utilizar.

La contrafirma se puede realizar por entero en el lado cliente o a
través del proceso de firma trifásica descrito en el <u>ANEXO II Firma
trifásica</u>.

La función JavaScript mediante la cual se realizan las contrafirmas es:

countersign(signB64, algorithm, format, params, successCb, errorCb);

En esta función:

- signB64

  - Firma electrónica que se desea contrafirmar codificada en Base64.

    - Una firma en Base64 puede ser el resultado obtenido por cualquier
      operación de firma, cofirma o contrafirma previa.

  - Si no se proporciona este parámetro (se usa null) o si se pasa una
    cadena vacía, el Cliente @firma mostrará al usuario un diálogo de
    selección de fichero para que seleccione el fichero de firma que
    desea contrafirmar.

    - Salvo en casos concretos, no se recomienda dejar en manos del
      usuario la selección del fichero de firma. Incluso si es necesario
      hacerlo, se recomienda hacer que el usuario cargue la firma
      previamente en servidor mediante un componente HTML y seguidamente
      se realice una operación de cofirma trifásica.

    - Para la compatibilidad con dispositivos móviles, nunca se deben
      proporcionar nulos o cadena vacía.

- algorithm

  - Algoritmo de firma. Consulte el apartado dedicado a los algorirmos
    de firma soportados para el formato de firma que desee utilizar.

- format

  - Formato de firma. Consulte el apartado <u>8 Formatos de firma</u>
    para consultar aquellos disponibles.

    - Si no conoce el formato de firma utilizado en la firma original,
      indique el valor “AUTO” para especificar que se utilice el mismo
      formato que la firma original.

    - Por norma general, no se puede contrafirmar una firma en un
      formato distinto al que se usó para generar dicha firma.

- params

  - Parámetros adicionales para la configuración de la operación de
    contrafirma y características particulares del formato de firma
    seleccionado.

    - Si se introduce un nulo, se usará la configuración por defecto
      para el formato de firma establecido.

    - La operación de contrafirma admite un parámetro adicional concreto
      para configurar qué firmas dentro del fichero de firma se quieren
      contrafirmar. Consulte el apartado <u>6.4.1 Selección de nodos</u>
      para más detalle.

    - Consulte el apartado <u>7.1 Paso de parámetros adicionales</u>
      para saber cómo realizar el paso de parámetros y el apartado de
      información específica del formato de firma que desee realizar
      para saber los parámetros soportados por el formato en cuestión.

- successCb

  - Función *callback* JavaScript que se ejecutará una vez se obtenga el
    resultado de la operación de cofirma. Esta función recibirá hasta
    tres parámetros:

    1.  En el primer parámero se recibe la firma resultante codificada
        en Base64.

    2.  En el segundo parámetro se recibe el certificado usado para
        cofirmar codificado en Base64.

    3.  En el tercer parámetro, opcionalmente, se recibirá un objeto
        JSON con el nombre del fichero de firma cofirmado en caso de que
        lo haya seleccionado el usuario.

- errorCb

  - Función *callback* JavaScript que se ejecutará cuando ocurra un
    error durante la operación de firma. Esta función recibirá hasta dos
    parámetros:

    1.  En el primer parámetro se recibe un texto con el tipo del error.

    2.  En el segundo parámetro se recibe un texto con el mensaje de
        error.

A continuación, se muestran distintos ejemplos de contrafirma:

- Contrafirma electrónica de una firma

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>var</strong> signatureB64 = … // Firma electrónica a
cofirmar</p>
<p>AutoScript.countersign(signatureB64, “SHA512withRSA”, “AUTO”,
“target=true”, successCallback, errorCallback);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

- Contrafirma electrónica del resultado de una firma

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>// Funcion callback que desencadena la operación de contrafirma</p>
<p><strong>function</strong> counterSignCallback (signatureB64) {</p>
<p>AutoScript.countersign(</p>
<p>signatureB64, “SHA512withRSA”, “XAdES”, <strong>null</strong>,</p>
<p>successCallback, errorCallback</p>
<p>);</p>
<p>}</p>
<p>…</p>
<p>// Iniciamos la operacion de firma que después se contrafirmará</p>
<p>AutoScript.sign(</p>
<p>dataB64, “SHA512withRSA”, “XAdES”, <strong>null</strong>,
counterSignCallback,</p>
<p>errorCallback);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

### Selección de nodos

La operación de contrafirma se realiza sobre una firma. Esta puede ser
una firma simple, una cofirma u otra contrafirma. Estas operaciones de
firma, cofirma y contrafirma van agregando firmas a un documento y, ya
que las contrafirmas se realizan sobre firmas previas, se forma lo que
se ha dado en llamar “árbol de firmas”. Así, por ejemplo, después de
realizar varias cofirmas y contrafirmas sobre una firma se podría
obtener una estructura como la siguiente:

<img src="media/image1.png" style="width:3.32677in;height:1.10236in" />

En esta estructura se refleja que se han firmado los datos dos veces
(firma y cofirma) y que una de esas firmas tiene una contrafirma. Debe
tenerse en cuenta que las firmas y las cofirmas son equivalentes (ambas
firman los datos) y por tanto ambas se pueden considerar cofirmas entre
sí.

En relación a esto, el Cliente @firma permite configurar que las
contrafirmas se realicen según una de las siguientes políticas de firma:

- **Firma de nodos hoja del árbol** (LEAFS): Se firmarán sólo las firmas
  del árbol que no tienen ninguna contrafirma.

- **Firma de todo el árbol de firma** (TREE): Se firman todas las firmas
  del árbol.

La configuración de qué nodos se desean firmar se realiza a través del
parámetro params de la función de contrafirma, al que, además de toda la
configuración específica del formato de firma, se le puede agregar la
propiedad target con la política de selección de nodos. Los valores que
admite esta propiedad son:

- leafs

  - Contrafirma todas las firmas que sean nodos hoja del árbol. Este es
    el valor por defecto.

- tree

  - Contrafirma todas las firmas del árbol.

Por ejemplo, si tomamos como base la estructura de firma anterior, así
quedaría al contrafirmarla con cada uno de los parámetros adminitidos:

- target=leafs

> <img src="media/image2.png" style="width:4.95669in;height:1.20866in" />

- target=tree

> <img src="media/image3.png" style="width:4.95669in;height:1.53937in" />

## Firma de lotes predefinidos

AutoFirma incorpora una funcionalidad de firma de lotes de documentos,
lo que permite a las aplicaciones enviar a firmar un grupo de datos en
una única llamada. Esta operación permite que se pueda ordenar la firma
de todos los documentos en una sola llamada al cliente de firma y que el
usuario pueda seleccionar el certificado de firma una única vez.

Las firmas de un lote de firma se realizan de forma trifásica, lo cual
se traduce en que buena parte del proceso de firma se realiza en
servidor y es necesario utilizar los servicios del WAR
“afirma-server-triphase-signer.war”. Consulte el apartado <u>5.3.2
Servicios de firma trifásica y firma de lotes</u> para saber más sobre
el despliegue y configuración de este servicio.

Al igual que ocurre con las firmas trifásicas, el sistema de firma de
lotes permite que tanto el origen de los datos como el destino de la
firma estén en servidor. Este origen y destino se determina por medio de
un gestor de documentos configurado en el servicio de firma trifásica.
En los lotes de firma no tienen porqué agregarse el contenido de los
documentos a firmar, se puede (y se debería) agregar la referencia a
esos documentos y que sea el servidor el encargado de acceder a ellos
para firmarlos y después guardar la firma. Esto lo hace el servicio de
firma trifásica a través de la clase a la que llamamos “gestor de
documentos”. Estos gestores de documentos son los mismos utilizados para
las operaciones de firma trifásica. El servicio de firma trifásica
incluye varios gestores de documentos genéricos y permite que se le
agreguen otros desarrollados expresamente para cualquier entorno (la
opción recomendada). Consulte el <u>ANEXO II Firma trifásica</u> para
saber más sobre los gestores de documentos disponibles y cómo
desarrollar el suyo propio.

Es importante entender que la aplicación que solicita la firma de un
lote recibe como resultado el listado de resultados de las firmas
generadas, es decir, si terminaron bien o mal, pero no las propias
firmas. Las firmas se deben procesar o almacenar en servidor y esto se
hará mediante el gestor de documentos configurado. Tenga en cuenta que
el valor de retorno del gestor de documentos después de procesar la
firma no se utiliza en la firma de lotes, por lo que el gestor de
documentos configurado por defecto (SelfishDocumentManager) no devuelve
las firmas (ni hace nada con ellas, así que este nunca se debe usar con
la firma de lotes) y el gestor de muestra que guarda en disco
(FileSystemDocumentManager) no proporciona el nombre del fichero de
salida. Es necesario configurar un gestor acorde a nuestra lógica de
negocio, preferiblemente creado para tal fin tal como se describe en el
apartado <u>II.1.2 Gestores de documentos personalizados</u>.

Generar una firma de lote con el Cliente @firma requiere de tres pasos:

1.  Crear un lote de firma con la configuración de firma que deberá
    aplicarse sobre cada uno de los documentos a firmar.

2.  Agregar los documentos (referencias a los datos) al lote. Si un
    documento del lote tuviese que firmarse con una configuración
    distinto a la del resto, se podría proporcionar una configuración
    específica para él.

3.  Enviar a firmar el lote. Esto conlleva la llamada al Cliente de
    firma y definir los métodos *callback* que se deberán ejecutar en
    caso de que se complete la firma del lote o si se produce un error
    bloqueante durante su procesado.

### Creación del lote

Para la creación del lote de firma se llamará al método JavaScript:

createBatch (algorithm, format, suboperation, extraparams)

Este método creaa el lote y establece la configuración de firma que se
aplicará por defecto a cada uno de los documentos que se agregue al
mismo.

Al agregar documentos al lote se podrá establecer una configuración
específica para su firma, salvo para el algoritmo de firma. El algoritmo
indicado en el método de creación del lote será el utilizado para firmar
todos los documentos del lote.

Los parámetros utilizados en este método son los siguientes:

- algorithm

  - Indica el algoritmo de firma a usar para todo el lote. Los valores
    > permitidos son:

    - SHA256withRSA

    - SHA384withRSA

    - SHA512withRSA

    - SHA1withRSA (**No se recomienda su uso por obsoleto**)

- format

  - Indicar el formato de firma que se usará por defecto para los
    documentos del lote. Los valores permitidos son:

    - CAdES

    - XAdES

    - PAdES

    - FacturaE

    - NONE

  - A pesar del nombre del formato, todas las firmas se realizarán de
    forma trifásica.

- suboperation

  - Indica la operación de firma a realizar por defecto. Los valores
    permitidos son:

    - sign

      - Firma.

    - cosign

      - Cofirma.

    - countersign

      - Contrafirma.

- extraparams

  - Cadena con el listado de propiedades que configurarán las firmas por
    defecto.

  - Se compondrá de una serie de tuplas “CLAVE=VALOR” separadas por
    “\n”, en donde la CLAVE será la propiedad a configurar y VALOR el
    valor asignado. Por ejemplo:
    “mode=implicit\nsignerClaimedRoles=Adjudicatario\|Responsable\nsignatureProductionCity=Madrid”

  - Las propiedades admitidas por cada uno de los formatos de firma se
    indican en los siguientes apartados:

    - <u>8.1.3 Parámetros adicionales</u> para las firmas CAdES.

    - <u>8.2.7 Parámetros adicionales</u> para las firmas XAdES.

    - <u>8.3.8 Parámetros adicionales</u> para las firmas PAdES.

    - <u>8.4.3 Parámetros adicionales</u> para las firmas FacturaE.

### Agregar documentos al lote

Para agregar documentos al lote se utilizará el método:

addDocumentToBatch (id, datareference, format, suboperation,
extraparams)

Este método agrega al lote un documento a firmar, pudiendo definir una
configuración específica para firmar con él u omitir esta configuración
para utilizar la configuración por defecto establecida durante la
creación del lote. El algoritmo de firma siempre será el establecido
durante la creación del lote.

Los parámetros utilizados en este método son los siguientes:

- id

  - Identificador con el que referenciar el documento. Cuando se
    devuelva el resultado de la firma del lote, se podrá saber cual ha
    sido el resultado de la firma de este documento porque vendrá
    referenciado con este mismo identificador.

  - Esta propiedad es obligatoria y no puede ser el mismo para dos
    documentos del lote.

- datareference

  - Referencia a los datos a firmar. El tipo de referencia depende del
    gestor de documentos configurado en el servicio de firma trifásica.

  - Por ejemplo:

    - Con el gestor DefaultDocumentManager, la referencia debe ser el
      propio documento codificado en Base 64.

    - Con el gestor FileSystemDocumentManager, la referencia indicada en
      este parámetro sería un nombre de fichero y el servicio de firma
      se encargaría de cargar ese fichero del directorio configurado en
      el servidor.

    - Con el gestor LegacyBatchDocumentManager, la referencia podría ser
      el propio documento en Base 64 o una URL. Si fuese el documento en
      Base 64, el servicio sólo tendría que decodificarlo, y si fuese
      una URL, el servicio accedería a la misma para descargar los
      datos.

  - Un desarrollador puede (y debería) agregar nuevos gestores de
    documentos al servicio de firma trifásica para optimizar la
    integración con sus sistemas. Por ejemplo, si los documentos se
    guardan en un repositorio de documentos, se podría crear un gestor
    de documentos que recibiese el identificador con el que se
    referencia al documento en el gestor y obtenerlo del mismo. Consulte
    el anexo <u>II.1.2 Gestores de documentos personalizados</u> para
    conocer como crear y configurar su propio gestor de documentos.

- format

  - Formato de firma a utilizar para este documento particular. Si no se
    indica ninguno, se usará el que se indicó en el método createBatch.

  - Los formatos permitidos son:

    - CAdES

    - XAdES

    - PAdES

    - FacturaE

    - NONE

  - A pesar del nombre del formato, todas las firmas se realizarán de
    forma trifásica.

- suboperation

  - Indica la operación de firma a aplicar sobre este documento. Si no
    se indica ninguna, se usará la que se indicó en el método
    createBatch.

  - Los valores permitidos son:

    - sign

      - Firma.

    - cosign

      - Cofirma.

    - countersign

      - Contrafirma.

- extraparams

  - Cadena con el listado de propiedades que configurarán esta firma
    particular. Si no se indica ninguna, se usará la que se indicó en el
    método createBatch.

  - Se compondrá de una serie de tuplas “CLAVE=VALOR” separadas por
    “\n”, en donde la CLAVE será la propiedad a configurar y VALOR el
    valor asignado. Por ejemplo:
    “mode=implicit\nsignerClaimedRoles=Adjudicatario\|Responsable\nsignatureProductionCity=Madrid”.

  - Las propiedades admitidas por cada uno de los formatos de firma se
    indican en los siguientes apartados:

    - <u>8.1.3 Parámetros adicionales</u> para las firmas CAdES.

    - <u>8.2.7 Parámetros adicionales</u> para las firmas XAdES.

    - <u>8.3.8 Parámetros adicionales</u> para las firmas PAdES.

    - <u>8.4.3 Parámetros adicionales</u> para las firmas FacturaE.

### Firma del lote

Para iniciar el proceso de firma del lote se usará el método:

signBatchProcess (stopOnError, batchPreSignerUrl, batchPostSignerUrl,
certFilters, successCallback, errorCallback)

Este método inicia el proceso de firma del lote y establece una serie de
parámetros necesarios para su funcionamiento.

Los parámetros utilizados en este método son los siguientes:

- stopOnError

  - Indica si la firma del lote debería detenerse en el momento en el
    > que se encuentre que una firma no es válida. Esto es útil cuando
    > se dé el caso en el que se deseen firmar todos los documentos o
    > ninguno.

  - Cuando se establece a “false” se indica que el proceso debe
    > continuar incluso si alguna de las firmas del lote no puede
    > completarse, y cuando se establece a “true” el proceso se para en
    > el momento en el que se produce el primer error.

  - Cuando se establece a “true”, no se guardará ninguna firma generada
    > hasta que no se hayan generado todas. En caso de error no se
    > guardará ninguna. Si fallase el guardado de una firma, se
    > ejecutaría el método rollback() del gestor de documentos sobre
    > cada una de las firmas ya guardadas para deshacer este guardado.

- batchPreSignerUrl

  - URL del servicio de prefirma de lotes.

  - Este servicio se despliega junto con el servicio de firma trifásica
    y, por defecto, tendrá el nombre presign.

  - Por ejemplo:

    - https://servidor.gob.es/aplicacion/afirma-server-triphase-signer/presign

- batchPostSignerUrl

  - URL del servicio de postfirma de lotes.

  - Este servicio se despliega junto con el servicio de firma trifásica
    y, por defecto, tendrá el nombre postsign.

  - Por ejemplo:

    - https://servidor.gob.es/aplicacion/afirma-server-triphase-signer/postsign

- certFilters

  - Permite definir los filtros para determinar qué certificados se
    pueden utilizar para firmar. Esta propiedad es opcional.

  - Se compondrá de una serie de tuplas “CLAVE=VALOR” separadas por
    “\n”, en donde la CLAVE será la propiedad a configurar y VALOR el
    valor asignado. Por ejemplo: “filters=
    subject.contains:Juan;nonexpired:true\nheadless=true”.

  - Las propiedades admitidas son las propiedades de filtros descritas
    en el apartado <u>7.2 Configuración de los filtros de</u>
    certificados y la propiedad headless del apartado <u>7.3 Selección
    automática de certificados</u>.

- successCallback

  - Método *callback* JavaScript que se debe ejecutar en caso de que se
    complete la firma del lote.

  - Si no se configura que se detenga el proceso en caso de error
    mediante el parámetro stopOnError, este método se llamará incluso si
    falla alguna de las firmas del lote. En ese caso, únicamente se
    devolverá en el listado de resultados que esa firma produjo un
    error.

  - Esta función recibirá como parámetros:

    1.  Una estructura JSON con el resultado de cada firma del lote. En
        el caso de que fallase una firma, se indica una descripción del
        error que se produjo. No se reciben las firmas generadas, el
        destino de estas es determinado por el gestor de documentos
        configurado en servidor.

    2.  El certificado utilizado para firmar codificado en Base64.

- errorCallback

  - Método *callback* JavaScript que se debe ejecutar en caso de que no
    se pueda procesar la firma del lote o si falla alguna de las firmas
    cuando se indica que debe deternerse el proceso de firma en caso de
    error.

  - Esta función recibirá dos parámetros:

    1.  El tipo de error producido.

    2.  Un texto descriptivo del error.

#### *Resultado de la firma del lote*

Cuando se termina de procesa correctamente un lote de firma, el cliente
recibe como respuesta en el método *callback* de éxito una estructura
JSON que describe como ha resultado el proceso.

Esta estructura JSON es acorde al siguiente esquema:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>{</p>
<p>"$schema": "http://json-schema.org/draft-04/schema#",</p>
<p>"type": "object",</p>
<p>"properties": {</p>
<p>"signs": {</p>
<p>"type": "array",</p>
<p>"items": [</p>
<p>{</p>
<p>"type": "object",</p>
<p>"properties": {</p>
<p>"id": {</p>
<p>"type": "string"</p>
<p>},</p>
<p>"result": {</p>
<p>"type": "string"</p>
<p>},</p>
<p>"description": {</p>
<p>"type": "string"</p>
<p>}</p>
<p>},</p>
<p>"required": [</p>
<p>"id",</p>
<p>"result"</p>
<p>]</p>
<p>}</p>
<p>]</p>
<p>}</p>
<p>},</p>
<p>"required": [</p>
<p>"signs"</p>
<p>]</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Un ejemplo de JSON devuelto podría ser el siguiente:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>{</p>
<p>"signs":[</p>
<p>{"id":"7725374e-728d-4a33-9db9-3a4efea4cead",</p>
<p>"result":"DONE_AND_SAVED"</p>
<p>}</p>
<p>,</p>
<p>{"id":"93d1531c-cd32-4c8e-8cc8-1f1cfe66f64a",</p>
<p>"result":"DONE_BUT_ERROR_SAVING",</p>
<p>"description":"java.io.IOException: No se pudo guardar el
fichero"</p>
<p>}</p>
<p>]</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

En él distinguimos un elemento “signs” con el listado de firmas del
lote. Cada uno de estos elementos tiene los siguientes atributos:

- id

  - Identificador del documento al cual corresponde el resultado. Los
    identificadores serán los mismos utilizados al agregar los
    documentos al lote. Debe tenerse en cuenta que los resultados pueden
    no estar listados en el el mismo orden en el que se agregaron los
    documentos al lote. Por eso es importante usar este ID para asociar
    cada documento firmado a su resultado.

- result

  - Resultado de realizar la firma. Esta propiedad puede adoptar uno de
    entre los siguientes estados:

    - Estado de éxito

      - DONE_AND_SAVED

        - La firma se generó y procesó correctamente.

    - Estados de error

      - DONE_BUT_ERROR_SAVING

        - Error al guardar la firma.

      - ERROR_PRE

        - Error en la primera fase del proceso de firma trifásica.

      - ERROR_POST

        - Error en la tercera fase del proceso de firma trifásica.

    - Estados intermedios

      - NOT_STARTED

        - La firma no se ha iniciado.

      - DONE_BUT_NOT_SAVED_YET

        - La firma se ha generado, pero aún no se ha guardado.

      - DONE_BUT_SAVED_SKIPPED

        - La firma se generó correctamente pero no se guardará.

      - SKIPPED

        - No se realizará la firma.

      - SAVE_ROLLBACKED

        - La firma se guardó, pero se volvió a eliminar.

  - En el caso de que no se indique que el proceso se interrumpa al
    detectar un error en una firma, todas las firmas aparecerán con el
    estado de éxito como resultado o con alguno de los resultados de
    error.

  - En el caso de que sí se indique que el proceso se interrumpa, cuando
    se detecte un error las firmas pueden quedar en alguno de los
    estados intermedios.

- description

  - Descripción del resultado del proceso (opcional). Se utiliza para
    ampliar información cuando se devuelve un estado de error.

Cuando se obtiene el resultado DONE_AND_SAVED en una firma de un lote,
se sabe que la firma se ha generado y se ha procesado correctamente
según lo establece el gestor de documentos configurado en el servicio de
firma trifásica.

### *Ejemplo de operación de firma de lote*

Aquí se incluye un ejemplo de código JavaScript que ejecuta una
operación de firma de lote:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>// Método callback para procesar el resultado del lote</p>
<p><strong>function</strong> exitoCallback(result, certB64) {</p>
<p>// Mostramos por consola el resultado de cada firma</p>
<p><strong>for</strong> (<strong>var</strong> i = 0; i &lt;
result.signs.length; i++) {</p>
<p>console.log("Id: " + result.signs[i].id</p>
<p>+ ". Result: " + result.signs[i].result</p>
<p>+ ". Description: " + result.signs[i].description);</p>
<p>}</p>
<p><strong>}</strong></p>
<p>// Método callback para tratar los errores</p>
<p><strong>function</strong> errorCallback(errorType, errorMessage)
{</p>
<p>// Mostramos por consola el error producido</p>
<p>console.log("Tipo: " + errorType + "\nMensaje: " + errorMessage);</p>
<p><strong>}</strong></p>
<p>// Método de firma</p>
<p><strong>function</strong> firmarLote() {</p>
<p>// Creamos lote con el algoritmo de firma y una configuración de
firma</p>
<p>// por defecto</p>
<p>AutoScript.createBatch("SHA512withRSA", "CAdES", "sign",
"mode=implicit");</p>
<p>// Definimos las referencias a los datos. En este caso, usaremos
nombres de</p>
<p>// ficheros codificados en Base64, ya que en el servicio de firma
trifásica</p>
<p>// tendríamos configurado el gestor de documentos
FileSystemDocumentManager</p>
<p><strong>var</strong> ref1 = Base64.encode("Entrada.txt");</p>
<p><strong>var</strong> ref2 = Base64.encode("Firma_cades.csig");</p>
<p><strong>var</strong> ref3 = Base64.encode("Entrada.pdf");</p>
<p><strong>var</strong> ref4 = Base64.encode("Entrada.jpg");</p>
<p>// Agregamos los documentos al lote, estableciendo parámetros de</p>
<p>// configuración particulares para los documentos que queramos</p>
<p>AutoScript.addDocumentToBatch("1", ref1);</p>
<p>AutoScript.addDocumentToBatch("2", ref2, "CAdES", "cosign",
"mode=explicit");</p>
<p>AutoScript.addDocumentToBatch("3", ref3, "PAdES");</p>
<p>AutoScript.addDocumentToBatch("4", ref4, "XAdES", "sign",
"format=XAdES
Detached\nsignatureProductionCountry=España\nsignatureProductionCity=Madrid");</p>
<p>// Enviamos a firmar el lote</p>
<p><strong>var</strong> baseUrl =
"https://servidor.gob.es/afirma-server-triphase-signer/"</p>
<p>AutoScript.signBatchProcess(<strong>false</strong>, baseUrl +
"presign", baseUrl + "postsign",</p>
<p>"filters=nonexpired:true\nheadless=true", exitoCallback,
errorCallback);</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

### Firma de lotes sin servidor (monofásica)

A pesar de que el funcionamiento normal de la firma de lotes es
trifásico (los datos y las firmas se procesan en servidor), es posible
configurar el despliegue para que AutoFirma haga la firma de los datos
en local y devuelva directamente las firmas generadas. Este modo de
funcionamiento está orientado a aquellas operaciones que firmen unos
pocos datos de pequeño tamaño ya residentes en cliente y por tanto no
obtengan beneficio en evitar la descarga de los datos del servidor y
subida de las firmas.

Para activar el modo de firma se deberá llamar al siguiente método de
configuración antes de la llamada al método de firma del lote:

AutoScript.setLocalBatchProcess(true)

Al realizarse por completo en local, la firma monofásica de lotes NO
requiere:

- Desplegar el servicio de firma trifásica y de lotes.

- Configurar las URL de los servicios en la llamada al método
  signBatchProcess.

Ha de tenerse en cuenta que esta operación NO es compatible con los
clientes de firma móvil. Si desea que su despliegue sea compatible con
dispositivos móviles, no utilice este modo. Si se hiciese y se ejecutase
la operación desde un móvil, se ignoraría el uso del método
setLocalBatchProcess y se requeriría despliegue y configuración del
servicio de firma trifásica.

Una vez activado este modo, hay que tener en cuenta los siguientes
aspectos:

- Los datos indicados en el parámetro datareference de las llamadas para
  agregar documentos al lote deberán ser los propios datos que se van a
  firmar.

- En la llamada al método de firma del lote, los parámetros
  batchPreSignerUrl y batchPostSignerUrl deberán ser nulos.

- El JSON de respuesta de la operación incluirá un atributo “signature”
  por cada operación completada correctamente. Este atributo contendrá
  el Base 64 de la firma generada.

- Los códigos de resultado de las operaciones son un subconjunto de los
  de la operación de firma de lotes trifásica, a pesar de que
  conceptualmente puedan no sean exactos. De esta forma la única
  diferencia que hay que tener en cuenta en el procesado de la respuesta
  de una operación u otra es de dónde se obtiene la firma. Los códigos
  de resultado devueltos podrán ser:

  - DONE_AND_SAVED

    - La firma se generó correctamente y se devuelve el resultado en el
      atributo “signature”.

  - ERROR_PRE

    - Error durante la firma.

  - SKIPPED

    - No se realizará la firma o se ignoró el resultado por haber
      encontrado un error en otra firma.

| **Advertencia:** La generación de firma de lotes monofásica obliga a que el JavaScript de la página del trámite cargue en memoria los documentos y las firmas generadas. Esto supone un problema para el navegador, que puede no ser capaz de manejar estos datos debido a limitaciones de memoria. No se recomienda usar este sistema si se trabaja con múltiples documentos o tamaños de documentos de más de unos pocos megabytes. |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

#### *Ejemplo de operación de firma monofásica de lote*

Aquí se incluye un ejemplo de código JavaScript que ejecuta una
operación de firma monofásica de lote:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>// Método callback para procesar el resultado del lote</p>
<p><strong>function</strong> exitoCallback(result, certB64) {</p>
<p>// Comprobamos que todas las firmas han terminado correctamente</p>
<p><strong>var</strong> allSignaturesOk = <strong>true</strong>;</p>
<p><strong>for</strong> (<strong>var</strong> i = 0; i &lt;
result.signs.length &amp;&amp; allSignaturesOk; i++) {</p>
<p><strong>if</strong> ("DONE_AND_SAVED" != result.signs[i].result)
{</p>
<p>allSignaturesOk = <strong>false</strong>;</p>
<p>}</p>
<p>}</p>
<p>// Si todas las firmas son correctas, las enviamos a través de un
formulario</p>
<p><strong>if</strong> (allSignaturesOk) {</p>
<p><strong>for</strong> (<strong>var</strong> i = 0; i &lt;
result.signs.length; i++) {</p>
<p>addToForm(result.signs[i].id, result.signs[i].signature);</p>
<p>}</p>
<p>getForm().submit();</p>
<p>}</p>
<p>// Si alguna de las firmas fallo, mostramos un error</p>
<p><strong>else</strong> {</p>
<p>alert("Ocurrió un error al procesar algunas de las firmas");</p>
<p>}</p>
<p><strong>}</strong></p>
<p>// Método callback para tratar los errores</p>
<p><strong>function</strong> errorCallback(errorType, errorMessage)
{</p>
<p>// Alertamos al usuario del error</p>
<p>alert("Error durante la firma del lote: " + errorMessage);</p>
<p><strong>}</strong></p>
<p>// Método de firma</p>
<p><strong>function</strong> firmarLote() {</p>
<p>// Creamos lote con el algoritmo de firma y una configuración de
firma</p>
<p>// por defecto</p>
<p>AutoScript.createBatch("SHA512withRSA", "CAdES", "sign",
"mode=explicit");</p>
<p>// Activamos el modo de firma de lote monofásica</p>
<p>AutoScript. setLocalBatchProcess(<strong>true</strong>);</p>
<p>// Agregamos al lote los datos</p>
<p>AutoScript.addDocumentToBatch("1", base64Dato1);</p>
<p>AutoScript.addDocumentToBatch("2", base64Dato2, "CAdES", "sign",
"mode=implicit");</p>
<p>AutoScript.addDocumentToBatch("3", base64Dato3);</p>
<p>AutoScript.addDocumentToBatch("4", base64Dato4);</p>
<p>// Enviamos a firmar el lote</p>
<p>AutoScript.signBatchProcess(<strong>true</strong>,
<strong>null</strong>, <strong>null</strong>,</p>
<p>"filters=nonexpired:true", exitoCallback, errorCallback);</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

#### *Resultado de la firma monofásica del lote*

El resultado de la firma monofásica del lote es igual al de su firma
trifásica, salvo porque se agrega un elemento signatura con el resultado
de la operación.

Esta estructura JSON es acorde al siguiente esquema:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>{</p>
<p>"$schema": "http://json-schema.org/draft-04/schema#",</p>
<p>"type": "object",</p>
<p>"properties": {</p>
<p>"signs": {</p>
<p>"type": "array",</p>
<p>"items": [</p>
<p>{</p>
<p>"type": "object",</p>
<p>"properties": {</p>
<p>"id": {</p>
<p>"type": "string"</p>
<p>},</p>
<p>"result": {</p>
<p>"type": "string"</p>
<p>},</p>
<p>"signature": {</p>
<p>"type": "string"</p>
<p>},</p>
<p>"description": {</p>
<p>"type": "string"</p>
<p>}</p>
<p>},</p>
<p>"required": [</p>
<p>"id",</p>
<p>"result"</p>
<p>]</p>
<p>}</p>
<p>]</p>
<p>}</p>
<p>},</p>
<p>"required": [</p>
<p>"signs"</p>
<p>]</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Un ejemplo de JSON de resultado (con parte de las cadenas base 64
omitidas) podría ser el siguiente:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>{</p>
<p>"signs":[</p>
<p>{"id":"7725374e-728d-4a33-9db9-3a4efea4cead",</p>
<p>"result":"DONE_AND_SAVED",</p>
<p>"signature":"MII…JAN4saJN="</p>
<p>}</p>
<p>,</p>
<p>{"id":"93d1531c-cd32-4c8e-8cc8-1f1cfe66f64a",</p>
<p>"result":" ERROR_PRE",</p>
<p>"description":"java.io.IOException: No se pudo guardar el
fichero"</p>
<p>}</p>
<p>]</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

### Antiguo mecanismo de firma de lotes

AutoFirma 1.7 y anteriores no disponían del mecanismo de firma de lotes
que se ha descrito. En su lugar, disponían de un mecanismo que constaba
de un único método que recibía un XML con todos los parámetros de
configuración del lote. Este mecanismo de firma de lotes sigue
existiendo en AutoFirma 1.8 y superiores, pero se considera obsoleto y
no se documenta para alentar a que los nuevos despliegues utilicen el
mecanismo de firma de lotes aquí descrito, más eficiente y sencillo de
usar.

Si su aplicación usaba el antiguo mecanismo y no desea migrar, no tiene
que hacer ningún cambio. Su aplicación seguirá funcionando con AutoFirma
1.8 y superiores.

Aquellos despliegues que usasen el antiguo mecanismo de firma de lotes y
quieran migrar al nuevo, tienen la opción de adaptar tanto el despliegue
como la lógica en servidor para optimizarla a sus fines. Para quien
desee evitar desarrollar de nuevo la lógica en servidor o reutilizar uno
de los mecanismos que ya existían, se ha incluido en el nuevo servicio
de firma trifásica un gestor de documentos que permitirá seguir
utilizando los antiguos mecanismos de carga de datos (Base 64 o a través
de URL) y los SignSavers para el guardado de las firmas (ya fuese alguno
de los incluidos por defecto para el guardado en fichero o envío a un
servicio, o uno creado a medida). Consulte el apartado <u>II.2.2 Gestor
de documentos “LegacyBatchDocumentManager”</u> para más información
sobre el nuevo gestor de documentos que permite la compatibilidad con
los antiguos SignSavers.

| **Advertencia:** Las aplicaciones móviles de firma Android y iOS son compatibles con el nuevo mecanismo de firma de lotes, mientras que no lo son con el mecanismo antiguo. |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

## Selección de certificado

El Cliente @firma permite a las aplicaciones solicitar un certificado a
los usuarios sin necesidad de realizar una operación de firma. Esta
operación puede ser útil para construir filtros de certificados para
operaciones posteriores, realizar validaciones previas sobre el
certificado y/o mostrar información de este en su aplicación web. Sin
embargo, **esta operación nunca debe usarse para autenticar a los
usuarios**, ya que lo que se obtiene es únicamente la parte pública de
los certificados y un mecanismo de autenticación que usase sólo eso
podría ser fácilmente sorteado mediante un ataque simple de inyección de
código.

La función JavaScript para permitir seleccionar un certificado de
usuario es:

function selectCertificate(params, successCallback, errorCallback);

En esta función:

- params

  - Parámetros de configuración de la operación que afecten a la
    selección de certificados.

  - Se pueden configurar filtros de certificados, como se indica en el
    apartado <u>7.2 Configuración de los filtros de</u> certificados, y
    la selección automática de certificado, como se describe en el
    apartado <u>7.3 Selección automática de certificados</u>.

- successCallback

  - Función *callback* JavaScript que se ejecutará cuando se seleccione
    un certificado. Esta función recibirá los siguientes parámetros:

    1.  El certificado seleccionado codificado en Base64.

- errorCallback

  - Función *callback* JavaScript que se ejecutará cuando ocurra un
    error al seleccionar el certificado. Esta función recibirá hasta dos
    parámetros:

    1.  En el primer parámetro se recibe un texto con el tipo del error.

    2.  En el segundo parámetro se recibe un texto con el mensaje de
        error.

El método de selección de certificado solicitará la contraseña de los
almacenes utilizados si es necesario para poder listar los certificados
que contienen, pero nunca utilizará las claves privadas de los
certificados, así que en ningún caso pedirá las contraseñas para ello.

Este método también es compatible con la función
setStickySignatory(boolean) (véase el apartado <u>6.2.1 Firma de
múltiples documentos (firma masiva)</u>) con la cual es posible fijar el
certificado seleccionado por el usuario. De esta forma se utilizará el
mismo certificado durante las siguientes operaciones de firma o
selección, siempre y cuando no se utilice la misma instancia de
AutoFirma.

A continuación, se muestran distintos ejemplos de la operación de
selección de certificado:

- Selección de certificado y envío a servidor para su análisis:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>var</strong> mostrarError =
<strong>function</strong>(errorType, errorMessage) {</p>
<p>alert(“Error en la descarga de los datos: ” + errorMessage);</p>
<p>}</p>
<p><strong>var</strong> enviarCertificado =
<strong>function</strong>(certB64) {</p>
<p>document.getElementById(“cert”).value = certB64;</p>
<p>document.getElementById(“formulario”).submit();</p>
<p>}</p>
<p><strong>var</strong> extraParams = “filters.0=issuer.contains:FNMT\n”
+</p>
<p>“filters.1=issuer.contains:Policia”;</p>
<p>AutoScript.selectCertificate (extraParams, enviarCertificado,
mostrarError);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

## Recuperación de log

AutoFirma permite obtener las trazas de su propia ejecución para después
para ayudar a las aplicaciones a identificar los problemas que sufran
sus usuarios. Para poder obtener sus trazas de ejecución es necesario
que se haya establecido la comunicación entre AutoFirma y el navegador
web, por lo que este mecanismo no ayuda a identificar errores en el
propio proceso de comunicación.

Este método debería utilizarse sólo de modo excepcional para identificar
errores que se den AutoFirma al ejecutarse en el equipo del usuario y
que sean susceptibles de ser atendidos por el equipo de soporte de su
aplicación o por el propio equipo de soporte de AutoFirma.

| **Advertencia**: La operación recuperación de logs no es compatible con los clientes de firma de Android e iOS, ni con AutoFirma cuando se comunica con el navegador a través de los servicios auxiliares. |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

La función JavaScript para recuperar las trazas de ejecución es:

getCurrentLog (successCallback, errorCallback);

En esta función:

- successCallback

  - Nombre de la función callback que se invocará en caso de recuperar
    correctamente la traza de ejecución.

  - Esta función recibirá los siguientes parámetros:

    1.  Texto plano la traza de ejecución.

- errorCallback

  - Nombre de la función callback que se invocará en caso de finalizar
    con errores la carga de la traza de ejecución.

  - Esta función recibirá como parámetros:

    1.  El tipo de error que se produjo.

    2.  El mensaje de error asociado.

A continuación, se un ejemplo de la operación recuperación de la traza
de error:

- Envio de la traza de error tras un error en la firma

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>// Función que se ejecutará cuando el proceso de firma falle</p>
<p><strong>function</strong> signErrorCallback (errorType, errorMessage)
{</p>
<p>// Llamamos a la función de la aplicación para mostrar errores</p>
<p>showError(errorMessage);</p>
<p>// Recuperamos y enviamos las trazas si no es un error de
cancelación</p>
<p><strong>if</strong> (errorType ==
"es.gob.afirma.core.AOCancelledOperationException") {</p>
<p>// No hacemos nada si falla la recuperación de las trazas</p>
<p>AutoScript.getCurrentLog(enviarTrazasCallback);</p>
<p>}</p>
<p>}</p>
<p>// Función callback que se ejecutara cuando se recuperen las trazas
de error</p>
<p><strong>function</strong> enviarTrazasCallback (trace) {</p>
<p>document.getElementById("trz").value =</p>
<p>AutoScript.getBase64FromText(trace);</p>
<p>document.getElementById("formulario").submit();</p>
<p>}</p>
<p>…</p>
<p>// Llamamos a la operación de firma</p>
<p>AutoScript.sign(<strong>null</strong>, "SHA512withRSA", "CAdES",
<strong>null</strong>,</p>
<p>successCallback, signErrorCallback);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

## Operaciones de gestión de ficheros

| **Advertencia**: Las operaciones de gestión de ficheros no son compatibles con los clientes de firma de Android e iOS. En cada uno de los siguientes subapartados se describen casos de uso alternativos para suplir el uso de los métodos aquí descritos y así mantener la compatibilidad con dispositivos móviles. |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

AutoFirma permite hacer uso de varias operaciones de carga y guardado de
ficheros en disco. Estas operaciones están orientadas a facilitar a las
aplicaciones la integración de las operaciones del cliente, sobre todo
cuando se desea firmar un fichero que el usuario tenga en su posesión o
cuando se desee permitir al usuario, justo después de firmar, guardar
copia de la firma que haya generado.

El uso de estas operaciones se puede evitar mediante JavaScript y
desarrollos en servidor, lo que por regla general darían lugar a
aplicaciones más estables y una mejor experiencia de usuario. También es
probable que su aplicación sea candidata a obtener beneficiosos del uso
de la firma trifásica. Consulte el apartado <u>ANEXO II Firma
trifásica</u> para obtener más información sobre este tipo de
operaciones. En los siguientes apartados se plantean también
alternativas para el uso de las distintas operaciones, lo cual también
hará la solución compatible con aplicaciones móviles.

### Guardado de datos en disco

La función de guardado permite proporcionar a AutoFirma unos datos
codificados en Base64 para que este ofrezca al usuario almacenarlo en
disco mediante un diálogo de guardado. Un uso común de este método es
guardar las firmas generadasalmacene el binario correspondiente en
disco.

El integrador puede seleccionar los datos que desea almacenar, la
propuesta de nombre para el fichero y otros parámetros para el diálogo
de guardado. Sin embargo, será el usuario el único que podrá decidir
donde desea almacenar los datos y qué nombre tendrá el fichero.

Los datos guardados son los datos indicados en Base64 ya descodificados.
Es decir, si deseamos almacenar el texto “SOY UN TEXTO A FIRMAR”,
convertiremos este texto a Base64 con lo que obtendríamos la cadena
“U09ZIFVOIFRFWFRPIEEgRklSTUFS” y se la pasaríamos al método de guardado.
Si abrimos el fichero resultante encontraremos que este contiene la
cadena “SOY UN TEXTO A FIRMAR”. Si lo que deseamos guardar es una firma
o un certificado obtenido en una de las funciones *callback* de las
operaciones del Cliente, proporcionaremos al método de carga tal como se
recibe en la función.

La función JavaScript para el guardado de datos en disco es:

> saveDataToFile (dataB64, title, fileName, extension, description,
> successCb, errorCb);

En esta función:

- dataB64

  - Datos que deseamos almacenar codificados como cadena Base64.

  - Comúnmente, esto será el resultado de una operación de firma o unos
    datos que se habrán procesado previamente para codificarlos a este
    formato.

- title

  - Título del diálogo de guardado.

  - Algunos sistemas operativos podrían no mostrar el título del
    diálogo.

- fileName

  - Nombre de fichero que aparecerá por defecto en el diálogo de
    guardado.

- extension

  - Extensión de fichero que se propone para el guardado. Los ficheros
    visibles del diálogo se filtrarán para sólo visualizar los que
    tienen esta extensión mientras esté seleccionada en el diálogo. Un
    ejemplo de extensión es: *pdf*

- description

  - Descripción del tipo de fichero que se va a almacenar. Esta
    descripción aparecerá asociada a la extensión indicada.

- sucessCb

  - Nombre de la función *callback* JavaScript que se ejecutará en caso
    de que el guardado de datos finalice correctamente.

  - Si se omite este parámetro, o se establece a null, no se ejecutará
    ninguna función al terminar la operación.

  - Esta función no recibe parámetros.

- errorCb

  - Nombre de la función *callback* JavaScript que se ejecutará en caso
    de que el guardado de datos finalice con errores o cuando el usuario
    cancele el diálogo de guardado.

  - Si se omite este parámetro, o se establece a null, no se ejecutará
    ninguna función al terminar la operación.

  - Esta función recibe los siguientes parámetros:

    1.  En el primer parámetro se recibe un texto con el tipo del error.

    2.  En el segundo parámetro se recibe un texto con el mensaje de
        error.

A continuación, se muestran distintos ejemplos de operaciones de
guardado de fichero:

- Guardado de una firma electrónica:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>function</strong> saveDataCb (dataB64, certB64) {</p>
<blockquote>
<p>AutoScript.saveDataToFile (dataB64, “Guardar firma electrónica”,
“firma.csig”, “csig”, “Firma binaria”);</p>
</blockquote>
<p>}</p>
<p>…</p>
<p>AutoScript.cosign (dataB64, “SHA512withRSA”, “CAdES”,
<strong>null</strong>, saveDataCb, errorCb);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

- Guardado de datos insertados por el usuario:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>var</strong> text =
document.getElementById(“userText”).value;</p>
<p><strong>var</strong> dataB64 =
AutoScript.getBase64FromText(text);</p>
<p>AutoScript.saveDataToFile (dataB64, “Guardar”, “fichero.txt”,
“txt”,</p>
<p>“Texto plano”);</p>
<p>…</p>
<p>&lt;!-- Formulario HTML con el texto que desea guardar --&gt;</p>
<p>&lt;form&gt;</p>
<p>&lt;textarea name="userText" cols="50"
rows="5"&gt;Texto&lt;/textarea&gt;</p>
<p>&lt;/form&gt;</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

La función de guardado permite únicamente almacenar en disco un dato que
ya tenemos cargado en la página web y que, probablemente, ya esté en
servidor o se desee enviar al mismo (como en el caso de las firmas
electrónicas). Según el caso, se pueden implementar alternativas en la
aplicación que eviten el uso de la función de guardado del Cliente
@firma. Por ejemplo:

- Si tenemos que deseamos guardar en servidor, en lugar de cargarlos en
  la página y luego usar esta función, se podría habilitar un servicio
  para descargarlos directamente desde el navegador.

- Si tenemos los datos cargados en la página, como una firma recién
  generada, podemos enviarla primeramente al servidor para procesarla y
  guardarla. A continuación, podríamos informar al usuario del resultado
  de la operación y ofrecerle el descargar una copia utilizando el mismo
  método que en el punto anterior.

- Si tenemos los datos en la página página y no deseamos enviarla a
  servidor, podemos utilizar JavaScript para permitir al usuario
  descargar estos datos mediante un objeto Blob y un enlace creado al
  vuelo.

### Selección y recuperación de un fichero por parte del usuario

AutoFirma permite que un usuario cargue un fichero de su sistema local y
recuperar su nombre y contenido. Este método nos permite cargar ficheros
para firmarlos, multifirmarlos u operar con ellos de cualquier otro
modo.

La función JavaScript para la carga de ficheros en disco es:

> getFileNameContentBase64 (title, extensions, description, filePath,
> successCb, errorCb);

En esta función:

- title

  - Título del diálogo de selección.

- extensions

  - Listado de extensiones de fichero permitidas. Estas aparecerán
    separadas por una coma (‘,’) y sin espacios entre ellas. Por
    ejemplo: pdf,jpg,txt. El diálogo sólo mostrará los ficheros con
    estas extensiones, salvo que el usuario establezca lo contrario
    manualmente en el diálogo.

- description

  - Descripción del tipo de fichero que se espera cargar. Esta
    descripción aparecerá asociada a las extensiones indicadas.

- filePath

  - Ruta absoluta del fichero que se debería seleccionar por defecto o
    sólo el nombre de fichero sugerido.

- successCb

  - Función *callback* JavaScript que se invocará cuando se cargue
    correctamente un fichero.

  - Esta función recibe los siguientes parámetros:

    1.  En el primer parámetro se recibe el nombre del fichero
        seleccionado.

    2.  En el segundo parámetro se recibe el contenido del fichero
        codificado en Base64.

- errorCb

  - Función *callback* JavaScript de error que se invocará cuando ocurra
    un error al cargar un fichero o cuando el usuario cancele el diálogo
    de selección.

  - Esta función recibe los siguientes parámetros:

    1.  En el primer parámetro se recibe un texto con el tipo del error.

    2.  En el segundo parámetro se recibe un texto con el mensaje de
        error.

A continuación, se muestra un ejemplo de carga de fichero:

- Carga de un fichero y recogida de su nombre:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>var</strong> fileName;</p>
<p><strong>var</strong> fileContentB64;</p>
<p>AutoScript.getFileNameContentBase64(</p>
<p>“Seleccionar fichero”, “jpg,gif,png”, “Imagen”,
<strong>null</strong>,</p>
<p>loadDataSuccessCallback, loadDataErrorCallback</p>
<p>..);</p>
<p>…</p>
<p><strong>function</strong> loadDataSuccessCallback(name, contentB64)
{</p>
<p>filename = name;</p>
<p>fileContentB64 = contentB64;</p>
<p>}</p>
<p><strong>function</strong> loadDataErrorCallback(errorType, errorMsg)
{</p>
<p>alert(“Error: ” + errorMsg);</p>
<p>}</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

La función de carga de fichero permite cargar un fichero del disco del
usuario y obtener su contenido y nombre en la página web. Sin embargo,
este fichero no debería ser tramitado directamente sin haberse realizado
las comprobaciones necesarias para saber que es válido para el objetivo
que se desee, salvo que no tengamos ningún tipo de restricción sobre el
tipo de fichero. También hay que tener en cuenta que, cuando cargamos
datos para firmar, lo común suele ser enviar posteriormente a servidor
esos datos junto con la firma generada. Según el caso, el uso del método
de carga de ficheros se podría sustituir por alguna de las siguientes
lógicas de negocio:

- Si queremos firmar un fichero y no tenemos ningún tipo de restricción
  sobre el tipo de datos que debe cargarse, podría omitirse la carga
  independiente de los datos y llamar al método de firma en cuestión sin
  pasarle datos. En ese caso, será la propia aplicación de firma la que
  ofrecerá al usuario cargar un fichero para firmarlo.

  - **Advertencia**: Este caso de uso no es compatible con el Cliente
    iOS.

- Si queremos cargar un fichero para firmarlo, pero antes queremos
  comprobar que sea un fichero válido, podríamos permitir que el usuario
  cargue los datos en la aplicación primeramente mediante un componente
  HTML de carga de fichero. Una vez cargado el documento en servidor
  podemos realizar las comprobaciones necesarias sobre él y cargar su
  contenido en el HTML de la página en Base64 para firmarlo. Después
  sólo deberíamos enviar al servidor la firma generada, ya que los datos
  ya estarían cargados.

  - Una versión mejorada de esto sería generar la firma de forma
    trifásica de tal forma que la aplicación no tenga que cargar el
    contenido del fichero en la página, se pueda firmar el documento
    mediante un identificador (haciendo uso de un DocumentManager a
    medida) y la firma se genere directamente en servidor, con lo cual
    tampoco sería necesario enviarla a posteriori. Consulte el apartado
    <u>ANEXO II Firma trifásica</u> para saber más sobre este tipo de
    firmas.

### Selección y recuperación de múltiples ficheros por parte del usuario

Además de la operación de carga de un fichero, AutoFirma incorpora una
función para la carga de múltiples ficheros que funciona de forma
análoga a la anterior.

La función JavaScript para la carga de múltiples ficheros en disco es:

> getMultiFileNameContentBase64 (title, extensions, description,
> filePath, successCb, errorCb);

En esta función:

- title

  - Título del diálogo de selección.

- extensions

  - Listado de extensiones de fichero permitidas. Estas aparecerán
    separadas por una coma (‘,’) y sin espacios entre ellas. Por
    ejemplo: pdf,jpg,txt. El diálogo sólo mostrará los ficheros con
    estas extensiones, salvo que el usuario establezca lo contrario
    manualmente en el diálogo.

- description

  - Descripción del tipo de fichero que se espera cargar. Esta
    descripción aparecerá asociada a las extensiones indicadas.

- filePath

  - Ruta absoluta de uno de los ficheros que se debería seleccionar por
    defecto o sólo el nombre sugerido de uno de los ficheros.

- successCb

  - Función *callback* JavaScript de éxito que se invocará cuando se
    cargue al menos un fichero.

  - Esta función recibe los siguientes parámetros:

    1.  En el primer parámetro se recibe un *array* con los nombres de
        los ficheros seleccionados.

    2.  En el segundo parámetro se recibe un *array* con el contenido en
        Base64 de los ficheros seleccionados.

  <!-- -->

  - El contenido de los parámetros recibidos será tal que el nombre del
    primer elemento del *array* de nombres se corresponderá con el
    contenido del primer elemento del *array* de contenidos, y así para
    cada uno de los elementos de ambos *arrays*.

- errorCb

  - Función *callback* JavaScript de error que se invocará cuando no se
    seleccionen ficheros o cuando se produzca un error durante su carga.

  - Esta función recibe los siguientes parámetros:

    1.  En el primer parámetro se recibe un texto con el tipo del error.

    2.  En el segundo parámetro se recibe un texto con el mensaje de
        error.

A continuación, se muestra un ejemplo de carga de fichero:

- Carga de ficheros y recogida de sus nombres:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>var</strong> fileNames;</p>
<p><strong>var</strong> fileContentB64s;</p>
<p>AutoScript.getMultiFileNameContentBase64(</p>
<p>“Seleccionar fichero”, “jpg,gif,png”, “Imagen”,
<strong>null</strong>,</p>
<p>loadDataSuccessCallback, loadDataErrorCallback</p>
<p>);</p>
<p>…</p>
<p><strong>function</strong> loadDataSuccessCallback(namesArray,
contentB64sArray) {</p>
<p>fileNames = namesArray;</p>
<p>fileContentB64s = contentB64sArray;</p>
<p>}</p>
<p><strong>function</strong> loadDataErrorCallback(type, msg) {</p>
<p>/* Mostramos todos los errores menos el de cancelación del diálogo.
*/</p>
<p><strong>if</strong>
(!“es.gob.afirma.core.AOCancelledOperationException”.equals(type)) {</p>
<p>/* Método del integrador para mostrar logs */</p>
<p>showLog(msg);</p>
<p>}</p>
<p>}</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

## Métodos de utilidad JavaScript

Las siguientes secciones muestran diversas funciones de utilidad que
incorpora el JavaScript de despliegue de Cliente @firma. Estas funciones
no se comunican con la aplicación nativa de firma y pueden ser
implementadas por su propia aplicación. Se suministran únicamente para
facilitar la integración del Cliente. Entre estas funciones están:

- Conversión de texto a Base64 y viceversa.

- Descarga de datos.

### Conversión de una cadena Base64 a texto

El JavaScript de despliegue del Cliente @firma proporciona un método
para la conversión de una cadena Base64 a un texto plano. Este método
permite mostrar al usuario en texto plano información que se posea
Base64. Casos en los que puede ser necesario esto son cuando se carga el
contenido de un fichero de texto plano desde disco por medio de alguno
de los métodos de carga o cuando los datos son el resultado de una firma
XML, por ejemplo. El juego de caracteres que se usará para interpretar
el texto siempre será UTF-8.

La función JavaScript para recuperar el texto plano correspondiente a la
cadena en Base64 es:

getTextFromBase64(dataB64);

En esta función:

- dataB64

  - Son los datos Base64 que se quieren mostrar como texto plano.

Este método devuelve una cadena con el texto plano correspondiente.

A continuación, se muestra un ejemplo de decodificación de un texto
Base64:

- Decodificación de una firma XML generada previamente

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>function</strong> showTextCallback (xmlSignB64) {</p>
<p><strong>var</strong> text =
AutoScript.getTextFromBase64(xmlSignB64);</p>
<p>alert(text);</p>
<p>}</p>
<p>…</p>
<p>AutoScript.sign(dataB64, “SHA1withRSA”, “XAdES”, “format=XAdES
Enveloped”, showTextCallback, errorCallback);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

### Conversión de un texto a cadena Base64

El JavaScript de despliegue del Cliente @firma proporciona un método
para la conversión de un texto plano a una cadena Base64. Este método
permite pasar al método de firma un texto insertado por el usuario, por
ejemplo. Se interpretará que el texto proporcionado es UTF-8.

La función JavaScript para convertir de texto plano a Base64 es:

getBase64FromText(plaintText);

En esta función:

- plainText

  - Es el texto plano que se desea convertir a Base64.

Este método devuelve una cadena Base64 que es la codificación del texto
plano indicado.

A continuación, se muestra un ejemplo de decodificación de un texto
Base64:

- Firma de un texto insertado por el usuario

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>var</strong> text = "Hola Mundo!!";</p>
<p><strong>var</strong> dataB64 =
AutoScript.getBase64FromText(text);</p>
<blockquote>
<p>AutoScript.sign (dataB64, "SHA512withRSA", "CAdES",
<strong>null</strong>, successCallback, errorCallback);</p>
</blockquote>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

### Descarga de datos remotos

El JavaScript de despliegue proporciona un método para la descarga de
datos remotos. Este método accede a una URL establecida por el
integrador, descarga el contenido que en ella se encuentra e invoca a un
método *callback* al que le proporciona los datos descargados en Base64.

La descarga de los datos se realiza desde JavaScript y sufre las
limitaciones que aplican los navegadores a este tipo de descargar. Por
norma, sólo podrán descargarse datos accesibles desde una URL con el
mismo dominio y esquema (HTTP o HTTPS) que la web que integra el
JavaScript de despliegue.

La descarga de los datos se realiza por medio del método GET de HTTP y
se realiza de forma asíncrona. Es decir, se descargan los datos en un
hilo de ejecución distinto al proceso principal. Una vez termina el
proceso de descarga, se invoca a un método *callback* establecido por el
integrador, de tal forma que se pueda recuperar el resultado de la
operación.

La función JavaScript para descarga de datos remotos es:

downloadRemoteData (url, successCallback, errorCallback);

En esta función:

- url

  - URL de acceso a los datos a descargar.

- successCallback

  - Nombre de la función *callback* que se invocará cuando se terminen
    de descargar los datos.

  - Esta función recibirá como único parámetro los datos descargados en
    Base64.

- errorCallback

  - Nombre de la función *callback* que se invocará cuando se produczca
    un error al descargar los datos. Esta función recibirá como
    parámetros:

    1.  En el primer parámetro se recibe un texto con el tipo del error.

    2.  En el segundo parámetro se recibe un texto con el mensaje de
        > error.

Este método devuelve no devuelve nada y su ejecución es asíncrona.

A continuación, se muestra un ejemplo de descarga de datos:

- Descarga de datos y posterior firma

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>var</strong> mostrarError = <strong>function</strong>(e)
{</p>
<p>alert(“Error en la descarga de los datos: ” + e);</p>
<p>}</p>
<p><strong>var</strong> iniciarFirma =
<strong>function</strong>(datosB64) {</p>
<p>AutoScript.sign (datosB64,</p>
<p>algorithm,</p>
<p>format,</p>
<p><strong>null</strong>,</p>
<p>successCallback,</p>
<p>errorCallback);</p>
<p>}</p>
<p><strong>var</strong> url = “http://midominio.com/informe.pdf”;</p>
<p>AutoScript.downloadRemoteData (url, iniciarFirma, mostrarError);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

# Configuración de las operaciones

## Paso de parámetros adicionales

Los métodos del API JavaScript para el uso del Cliente @firma trasladan
los datos a la aplicación de firma en forma de cadenas de texto. Algunas
de estas cadenas son datos binarios codificados en Base64 (como el
parámetro de datos a firmar), mientras que otras son textos planos (como
los nombres del formato y el algoritmo de firma). En muchas de las
operaciones del API existe un parámetro concreto, usualmente denominado
params o estraParams, que se utiliza para establecer una serie de
propiedades de configuración opcionales. Estos parámetros se expresan en
texto plano en forma de tuplas de claves y valores, emulando el formato
de los objetos de propiedades de Java (Properties).

Los mencionados objetos de propiedades tienen un formato como el que
sigue:

nombreParam1=valorParam1

nombreParam2=valorParam2

…

Para expresar cadenas en este formato desde JavaScript, se concatenarán
cada una de las líneas usando el carácter especial de nueva línea (\n)
como separador:

var params=’nombreParam1=valorParam1\nnombreParam2=valorParam2’;

Es importante especificar el nombre de las propiedades exactamente como
se indique, ya que puede existir diferenciación entre mayúsculas y
minúsculas. Cualquier parámetro no soportado por la operación invocada,
simplemente, se ignorará.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong><u>Nota:</u></strong> El Cliente @firma interpreta todos
los textos, tanto los recibidos como los devueltos en las respuestas,
usando el juego de caracteres UTF-8. Para poder transmitirlos y
mostrarlos correctamente desde una página web es necesario que esta se
encuentre codificada en UTF-8 y lo declare como tal.</p>
<p>En caso de no ser posible, se recomienda:</p>
<ul>
<li><p>Que el Base64 de los textos a proporcionar al Cliente se hayan
obtenido desde un entorno en el que se pueda gantizar que originalmente
estaban codificados en UTF-8. Por ejemplo, que el texto ya estuviese
previamente codificado o que se codifique a través de un
servicio.</p></li>
<li><p>No mostrar directamente al usuario los mensajes devueltos por el
propio Cliente.</p></li>
</ul></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Ejemplo de uso:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>AutoScript.cargarAppAfirma();</p>
<p>// Configuramos 3 parámetros adicionales:</p>
<p>// - expPolicy: Política de firma</p>
<p>// - filters: Filtros de certificados vigentes</p>
<p>// - signerClaimedRoles: Roles del firmante</p>
<p><strong>var</strong> extraParams =
"expPolicy=FirmaAGE\nfilters=nonRepudiation:\n" +</p>
<p>"signerClaimedRoles=Apoderado";</p>
<p>// Ejecutamos la operación de firma</p>
<p>AutoScript.sign (dataB64, "CAdES", "SHA512withRSA", extraParams,</p>
<p>successCallback, errorCallback);</p>
<p>…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

## Configuración de los filtros de certificados

El Cliente @firma dispone de filtros de certificados que se pueden
aplicar para restringir los certificados que podrá seleccionar el
usuario para realizar una operación de firma o multifirma. Los filtros
de certificados se pueden establecer como parámetros adicionales en las
distintas operaciones de firma y selección de certificados.

Por defecto, AutoFirma no mostrará al usuario los certificados
caducados. Sin embargo, si se establecen filtros de certificados, se
mostrarán todos aquellos certificados disponibles que cumplan con las
condiciones dadas, incluidos los certificados caducados. Para omitir
expresamente estos certificados se puede utilizar el filtro
“nonexpired:”, explicado más adelante en este apartado.

| **<u>Advertencia:</u>** El uso de filtros de certificados no esta soportado por los clientes de firma móvil. Las propiedades de configuración de filtros serán ignoradas por las aplicaciones móviles. |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

Las claves que nos permiten establecer filtros de certificados son:

- *filters*: Esta clave permite establecer uno o más de los filtros de
  certificados que se listan más adelante en este apartado. Los
  certificados deberán cumplir las condiciones establecidas en todos los
  filtros listados, o de lo contrario no se mostrarán. Los distintos
  filtros se deben separar mediante el carácter punto y coma (‘;’).
  Ejemplos:

  - filters=nonexpired:false

    - Motrar todos los certificados, incluso los caducados.

  - filters=issuer.rfc2254: (O=DIRECCION GENERAL DE LA
    > POLICIA);keyusage.nonrepudiation:true

    - Mostrar sólo certificados de firma del DNIe.

  - filters=issuer.rfc2254: (O=DIRECCION GENERAL DE LA
    > POLICIA);keyusage.nonrepudiation:true;nonexpired:

    - Mostrar sólo certificados de firma del DNIe no caducados.

- *filters.X*: En esta clave ‘X’ será un entero igual o mayor que 1. El
  Cliente @firma leerá la clave *filters.1*, a continuación, *filters.2*
  y así hasta que no encuentre una de las claves de la secuencia. Al
  contrario que con la clave *filters*, basta con que el certificado
  cumpla uno de estos filtros para que se muestre. No es necesario
  cumplirlos todos. Cada una de estas claves puede declarar varios
  filtros separados por punto y coma (‘;’) de tal forma que sí se
  deberán cumplir todos ellos para satisfacer ese sub-filtro concreto.
  Ejemplos:

  - Mostrar los certificados no caducados del ciudadano con NIF
    11111111H:

    - filters.1=subject.rfc2254:(SERIALNUMBER=\*11111111H);nonexpired:

    - filters.2=subject.rfc2254:(CN=\*11111111H\*);nonexpired:

      - **IMPORTANTE:** Las autoridades certificadoras pueden agregar el
        DNI del ciudadano en distintos campos del certificado y
        AutoFirma no dispone de un modo de localizarlo. Sin embargo, la
        mayor de ellas ya agrega el DNI como parte del RDN
        “SERIALNUMBER” del subject del certificado. Algunas también lo
        agregan como parte del CN. Así, este ejemplo, englobaría
        funcionaria con buena parte de los certificados personales
        emitidos por autoridades españolas, pero puede que no con todas.

  - Mostrar los certificados CERES y el certificado de firma del DNIe:

    - filters.1=nonexpired:;issuer.rfc2254:(O=DIRECCION GENERAL DE LA
      POLICIA);keyusage.nonrepudiation:true

    - filters.2=nonexpired:;issuer.rfc2254:(O=FNMT-RCM)

Estas claves de definición de filtros son excluyentes y tienen prioridad
según el orden en el que se han listado (*filters* y *filters.X*). Es
decir, si se establece la propiedad filters, no se procesarán las
propiedades del tipo *filters.1*, por ejemplo.

Los filtros disponibles en AutoFirma son:

- <u>Filtro de certificados caducados:</u> Filtra los certificados para
  que no se muestren aquellos que se encuentren fuera de su periodo de
  validez, que son los únicos que pueden generar una firma válida. El
  filtro determina si un certificado está vigente en base a la
  fecha/hora del equipo del usuario.

  - Para establecer este filtro se usará el valor “*nonexpired:*”.

  - Ejemplo:

    - filters=nonexpired:

> Un integrador también puede habilitar o deshabilitar expresamente este
> filtro siguiéndolo de las palabras “*true*” o “*false*”,
> respectivamente.
>
> Por defecto, si no se indica ningún filtro de certificados, AutoFirma
> omitirá los certificados que estén fuera de su periodo de validez. Si
> se desea que se muestren los certificados caducados sin indicar ningún
> otro filtro, se puede configurar la propiedad de filtrado de la
> siguiente manera:

- filters=nonexpired:false

<!-- -->

- <u>Filtro por número de serie de certificados cualificados de
  firma:</u> Filtra los certificados del almacén para que sólo se
  muestre aquellos con un número de serie concreto, lo que comúnmente
  hará que se muestre un único certificado. En el caso de que el
  certificado identificado por el filtro no sea un certificado
  cualificado para firma, se buscará en el almacén un certificado parejo
  que sí lo esté. Si se encontrase se seleccionaría este nuevo
  certificado y, si no, se seleccionará el certificado al que
  corresponde el número de serie.

  - Para establecer este filtro se usará el valor “*qualified:*” seguido
    por el número de serie del certificado en hexadecimal.

  - Ejemplos:

    - filters=qualified:45553a61

    - filters=qualified:03ea

- <u>Filtro en base a certificado codificado:</u> Filtra los
  certificados para seleccionar uno concreto proporcionado a través del
  filtro. Esto es de utilidad cuando, después de una operación realizada
  con un certificado, se quiere restringir futuras operaciones para que
  se realicen con el mismo certificado.

  - Para establecer este filtro se usará el valor “*encodedcert:*”
    seguido del certificado codificado en Base64. Esto es, tal como se
    devuelve a través del *callback* en los métodos de firma y selección
    de certificado.

  - Ejemplo:

    - filters=encodedcert:MIIIcjCCBlqgAwIB……………radvEjJ=

      - Este filtro mostrará sólo aquel certificado que hemos
        proporcionado en el filtro, en caso de que exista en el almacén.

- <u>Filtro por huella digital (*Thumbprint*):</u> Filtra los
  certificados de tal forma que sólo se mostrará aquel que tenga la
  huella digital indicada. Hay que tener en cuenta que esta huella
  digital no debe calcularse en base a un fichero (por ejemplo, un
  “.cer”), sino que es la huella digital de la codificación del
  certificado.

  - Para establecer este filtro se usará el valor “*thumbprint:*”
    seguido del algoritmo de huella digital utilizado y, separado por el
    carácter dos puntos (‘:’) la huella digital que se busque en
    hexadecimal.

  - Ejemplo:

    - filters=thumbprint:SHA1:30 3a bb 15 44 3a fd d7 c5 a2 52 dc a5 54
      f4 c5 ee 8a a5 4d

      - Este filtro sólo mostrará el certificado cuya huella digital en
        SHA1 sea la indicada.

- <u>Filtro DNIe:</u> Filtra los certificados del almacén para que sólo
  se muestren los certificados de firma de los DNIe disponibles desde
  ese almacén.

  - Para establecer este filtro se usará el valor “*dnie:*”.

  - Ejemplo:

    - filters=dnie:

- <u>Filtro de certificados SSCD:</u> Filtra los certificados del
  almacén para que se muestren sólo aquellos generados en un dispositivo
  SSCD (dispositivo seguro de creación de firma), como es el caso de los
  certificados del DNIe. Hay que tener en cuenta que el filtrado se
  realiza a partir de un atributo QCStatement declarado en el propio
  certificado. Si la autoridad de certificación no incluye este
  atributo, no será posible realizar la distinción.

  - Para establecer este filtro se usará el valor “*sscd:*”*.*

  - Ejemplo:

    - filters=sscd:

- <u>Filtro de certificados de firma:</u> Filtra los certificados del
  almacén para que se muestren todos los certificados salvo el
  certificado de autenticación del DNIe. Este filtro se crea para evitar
  excluir algunos tipos de certificados con los KeyUsage mal declarados.

  - Para establecer este filtro se usará el valor “signingCert:”.

  - Ejemplo:

    - filters=signingCert:

Para un filtrado más correcto de los certificados de firma, utilice el
filtro “*keyusage.nonrepudiation:*”.

- <u>Filtro de certificados de autenticación:</u> Filtra los
  certificados del almacén para que se muestren todos los certificados
  salvo el certificado de firma del DNIe. Este filtro se crea para
  evitar excluir algunos tipos de certificados con los KeyUsage mal
  declarados.

  - Para establecer este filtro se usará el valor “*authCert:*”*.*

  - Ejemplo:

    - filters=authCert:

Para un filtrado más correcto de los certificados de autenticación,
utilice el filtro “*keyusage.digitalsignature:*”.

- <u>Filtro RFC2254 en base al *Subject* del certificado:</u> Filtra los
  certificados a partir de una expresión regular creada según la RFC2254
  que se aplica sobre el *Subject* del certificado.

  - Para establecer este filtro se usará el valor “*subject.rfc2254:*“
    seguido de la expresión RFC2254.

  - Puede revisarse la normativa RFC 2254 en
    <http://www.faqs.org/rfcs/rfc2254.html>

  - Ejemplo:

    - filters=subject.rfc2254:(CN=\*12345678z\*)

      - Este filtro mostrará sólo aquellos certificados en los que
        aparezca la cadena “12345678z” en el *CommonName* de su
        *Subject*.

- <u>Filtro RFC2254 en base al *Issuer* del certificado:</u> Filtra los
  certificados a partir de una expresión regular creada según la RFC2254
  que se aplica sobre el *Issuer* del certificado.

  - Para establecer este filtro se usará el valor “*issuer.rfc2254:*”
    seguido de la expresión RFC2254.

  - Puede revisarse la normativa RFC 2254 en
    <http://www.faqs.org/rfcs/rfc2254.html>

  - Ejemplo:

    - filters=issuer.rfc2254:(\|(O=FNMT-RCM)(O=DIRECCION GENERAL DE LA
      POLICIA))

      - Este filtro mostrará sólo aquellos certificados cuyo *Issuer*
        tenga establecido como organización “FNMT” o “DIRECCION GENERAL
        DE LA POLICIA”, es decir, sólo mostrará los certificados del
        DNIe y los de la FNMT.

  - Este filtro puede aplicarse de forma recursiva, de tal forma que
    permitirá el uso del certificado si cualquier de los certificados de
    la cadena de certificación por encima de él mismo cumple con la
    expresión indicada. Para utilizar recursivamente este filtro se
    usará el valor *issuer.rfc2254.recurse:* seguido de la expresión
    RFC2254.

  - Ejemplo:

    - filters=issuer.rfc2254.recurse:(CN=\*FNMT\*)

      - Este filtro mostrará sólo aquellos certificados en los que
        alguno de los certificados de su cadena de certificación tenga
        la partícula “FNMT” en el nombre común

- <u>Filtro de texto en base al *Subject* del certificado:</u> Filtra
  los certificados según si contienen o no una cadena de texto en el
  *Principal* de su *Subject*.

  - Para establecer este filtro se usará el valor “*subject.contains:*”
    seguido de la cadena de texto que debe contener.

  - Ejemplo:

    - filters=subject.contains:JUAN ESPAÑOL ESPAÑOL

      - Este filtro mostrará sólo aquellos certificados en los que
        aparezca la cadena “JUAN ESPAÑOL ESPAÑOL” en el *Subject*.

- <u>Filtro de texto en base al *Issuer* del certificado:</u> Filtra los
  certificados según si contienen o no una cadena de texto en el
  *Principal* de su *Issuer*.

  - Para establecer este filtro se usará el valor “*issuer.contains:*”
    seguido de la cadena de texto que debe contener.

  - Ejemplo:

    - filters=issuer.contains:O=EMPRESA

      - Este filtro mostrará sólo aquellos certificados en los que el
        *Principal* del *Issuer* muestre el texto “O=EMPRESA”.

- <u>Filtros por uso declarado de los certificados (*KeyUsage*):</u>
  Colección de filtros que permiten filtrar según el uso declarado de
  los certificados.

  - Para establecer estos filtros usaremos las siguientes claves según
    los usos que se quieran comprobar. Las claves irán seguidas de los
    valores “true” o “false”, según se desee que el uso esté habilitado
    o no lo esté, respectivamente:

    - *keyusage.digitalsignature:*

    - *keyusage.nonrepudiation:*

    - *keyusage.keyencipherment:*

    - *keyusage.dataencipherment:*

    - *keyusage.keyagreement:*

    - *keyusage.keycertsign:*

    - *keyusage.crlsign:*

    - *keyusage.encipheronly:*

    - *keyusage.decipheronly:*

  - Los *KeyUsages* que no se declaren en el filtro no se tendrán en
    cuenta.

  - Ejemplos:

    - filters=keyusage.digitalsignature:true;keyusage.
      keyencipherment:true

      - Este filtro mostrará sólo aquellos certificados que tengan
        establecidos a true los *KeyUsage* digitalsignature
        (autenticación) y keyencipherment (sobres electrónicos),
        ignorando el valor del resto de *KeyUsages*.

    - filters=keyusage.nonrepudiation:false

      - Este filtro mostrará sólo aquellos certificados que no declaren
        el *KeyUsage* de firma avanzada.

- <u>Filtro por identificador de directiva:</u> Filtra los certificados
  por aquellos que poseen un identificador de directiva concreto. Esto
  es útil para mostrar sólo determinado tipo de certificados de una
  autoridad de certificación.

  - Para establecer este filtro se usará el valor “*policyid:*” seguido
    por el listado de OIDs, separados por comas (‘,’), por los que se
    quieran filtrar.

  - Ejemplo:

    - filters=policyid:1.3.6.1.4.1.18332.3.4.1.2.11

      - Este filtro mostrará sólo aquellos certificados con el
        identificador de directiva “1.3.6.1.4.1.18332.3.4.1.2.11”.

- <u>Filtro de seudónimo:</u> Permite filtrar los certificados
  permitiendo que el usuario se centre en los certificados de
  pseudónimo, lo que permite que su nombre real del usuario quede
  excluido de la firma.

  - Para establecer este filtro se usará uno de los siguientes valores:

    - *pseudonym:only*

      - Establece que sólo se muestren los certificados de pseudónimo.

    - *pseudonym:andothers*

      - Establece que se muestren los certificados de pseudónimo y
        aquellos que no tienen un certificado de seudónimo asociado.
        Así, quedan ocultos los certificados que tienen un certificado
        equivalente de seudónimo.

      - Es es el valor por defecto y se utilizará incluso si se escribe
        “*pseudonym:*” a secas o seguido de cualquier valor que no
        coincida con otro de los valores permitidos.

  - Ejemplo:

    - filters=pseudonym:

- <u>Filtro de almacenes externos:</u> Permite deshabilitar el botón de
  carga de almacenes PKCS#12 en el diálogo de selección de certificados.
  De esta forma sólo podrán usarse los certificados del almacén
  seleccionado por el integrador o los por defecto del navegador en caso
  de que el integrador ni especificase ningún almacén.

  - Para establecer este filtro se usará el valor
    “*disableopeningexternalstores*“.

  - Ejemplo:

    - filters=disableopeningexternalstores

Se ignorará cualquier valor establecido como filtro de certificados
distinto a los que se han listado.

Si ningún certificado cumple los criterios de filtrado, se ejecutará la
operación de error indicando que no se ha encontrado ningún certificado
que cumpla con los criterios indicados.

Si más de un certificado cumple los criterios de filtrado, se mostrarán
todos ellos en el diálogo de selección de certificados.

Si tan sólo un certificado cumple con las condiciones de los filtros
establecidos y se ha configurado la opción “*headless*” en las
propiedades adicionales de la operación, se seleccionará automáticamente
ese certificado sin mostrar el diálogo de selección al usuario. Consulte
el apartado <u>7.3 Selección automática de certificados</u> para conocer
cómo configurar la propiedad “*headless*”.

## Selección automática de certificados

Para aquellos casos en los que sólo exista un certificado en el almacén
de certificados o cuando se descarten certificados mediante filtros y
sólo haya uno que es posible seleccionar, es posible indicar a AutoFirma
que lo seleccione automáticamente en lugar de mostrar al usuario el
diálogo de selección con este único certificado. Esto podemos
configurarlo mediante la propiedad *headless*.

headless=true

Por defecto, si no se establece la propiedad *headless* o se indica un
valor distinto de *true*, se mostrará el diálogo de selección de
certificados aun cuando sólo haya un certificado para seleccionar.

Los clientes de firma móvil ignoran la propiedad *headless* por las
restricciones de seguridad de los propios sistemas.

## Configuración de la política de firma

La política de firma de una firma electrónica identifica diversos
criterios que se han cumplido durante la construcción de esta firma o
requisitos que cumple la propia firma. Los formatos de firma CAdES,
PAdES y XAdES permiten declarar la política de firma que se ha seguido
para su generación.

Tenga en cuenta que el que una firma incluya los atributos
correspondientes a una política de firma concreta no significa que
cumpla los criterios de la política. Si desea que sus firmas se ajusten
a una política de firma lea las restricciones impuestas por esa política
y genere firmas acordes a ella antes de configurarla. De esta forma,
podrá asegurarse de que sus firmas son compatibles con otros sistemas y
entornos en los que se utilicen firmas acordes a la política en
cuestión.

### Política de firma de la AGE v1.9

En el Cliente @firma se ha incluido un mecanismo para la configuración
rápida y sencilla de la política de firma de la Administración General
del Estado (AGE) v1.9. Para configurar esta política concreta basta con
indicar la siguiente propiedad propiedad adicional en la operación de
firma deseada.

> expPolicy=FirmaAGE

Esta propiedad se expandirá a las necesarias para el cumplimiento de la
política de firma de la AGE, lo que equivale a introducir las
propiedades manualmente.

Los parámetros de esta política para cada uno de los formatos
comprendidos en la misma los siguientes:

- <u>CAdES</u>

  - policyIdentifier=2.16.724.1.3.1.1.2.1.9

  - policyIdentifierHash=G7roucf600+f03r/o0bAOQ6WAs0=

  - policyIdentifierHashAlgorithm=http://www.w3.org/2000/09/xmldsig#sha1

  - policyQualifier=https://sede.administracion.gob.es/politica_de_firma_anexo_1.pdf

  - mode=implicit

- <u>XAdES</u>

  - policyIdentifier=urn:oid:2.16.724.1.3.1.1.2.1.9

  - policyIdentifierHash=G7roucf600+f03r/o0bAOQ6WAs0=

  - policyIdentifierHashAlgorithm=http://www.w3.org/2000/09/xmldsig#sha1

  - policyQualifier=https://sede.administracion.gob.es/politica_de_firma_anexo_1.pdf

  - format=XAdES Detached

- <u>PAdES</u>

  - policyIdentifier=2.16.724.1.3.1.1.2.1.9

  - policyIdentifierHash=G7roucf600+f03r/o0bAOQ6WAs0=

  - policyIdentifierHashAlgorithm=http://www.w3.org/2000/09/xmldsig#sha1

  - policyQualifier=https://sede.administracion.gob.es/politica_de_firma_anexo_1.pdf

La propiedad format, sólo se aplicará cuando el formato de firma sea
XAdES.

La propiedad mode, sólo se aplicará cuando el formato de firma sea CAdES
y los datos ocupen menos de 1 MB. Los datos no se incluirán en la firma
cuando su tamaño sea mayor, siguiendo, de forma general, la
especificación establecida por la política de firma de la AGE:

> *En el caso de que, debido al tamaño de los datos a firmar, no resulte
> técnicamente posible o aconsejable realizar las firmas con el formato
> anteriormente descrito* (que la firma contenga los datos firmados)*,
> se generará la estructura de firma detached, que incluye el hash del
> documento original en la firma.*

Debido a la generalidad de la especificación, se permite al integrador
definir qué tamaños de datos pueden incluirse dentro de la firma y
cuáles no para su aplicación, por lo que, en caso de haberse indicado
expresamente un modo de firma (parámetro mode), se utilizará el valor
establecido por el integrador.

Si se configura para la operación alguna propiedad individual que entre
en conflicto con la política indicada (por ejemplo, indicando un formato
prohibido por esta), se ignorará esa propiedad individual y prevalecerá
el valor impuesto por la política. Por ejemplo, si se configurasen las
propiedades expPolicy=FirmaAGE y format=XAdES Enveloping, para una
operación de firma con formato XAdES, se generaría una firma XAdES
Detached con la política de firma de la AGE establecida. Es decir, se
ignoraría que se estableció la propiedad format=XAdES Enveloping.

Para más información sobre la política de firma de la AGE puede
consultar la guía de implementación de la política:
<https://administracionelectronica.gob.es/ctt/politicafirma#.YBEdyzr0mbg>.

Para saber cómo configurar propiedades en las operaciones de firma,
consulte el apartado <u>7.1 Paso de parámetros adicionales</u>.

### Política de firma de Factura electrónica (Facturae)

Para la firma de facturas electrónicas se deberá utilizar siempre el
formato de firma FacturaE. Configurar este formato establecerá
automáticamente las propiedades necesarias para la firma de facturas
electrónicas, incluida la política de firma.

Las firmas generadas con este formato siempre son según la
especificación 3.1 de factura electrónica.

## Validación de firmas previas

Las operaciones de cofirma y contrafirma se realizan sobre firmas
generadas anteriormente. Salvo en casos concretos, el Cliente @Firma
permite agregar nuevas firmas a cualquier firma compatible sin
restricción. Esto implica que, por ejemplo, se podría contrafirmar una
firma que no sea válida por haberse caducado su certificado.

Es posible que desde su aplicación quiera restringirse, en la medida de
lo posible, el que se cofirmen y contrafirmen firmas inválidas, para lo
cual puede usarse la opción *checkSignatures*.

checkSignatures=true

Esta propiedad realiza una verificación criptográfica de la firma y
comprueba la caducidad de los certificados utilizados en ella. Esto **no
es una validación completa de firma**, ya que para considerar que la
firma es válida deben realizarse otras operaciones no soportadas por el
Cliente @firma, como la comprobación del estado de revocación de los
certificados o la adhesión de la firma a la política de firma que
declare.

Esta propiedad debe usarse para reducir la posibilidad de procesar
firmas inválidas, pero es responsabilidad de la aplicación saber si son
válidas antes de enviarse a procesar o, si es el usuario el que
selecciona expresamente estas firmas, el realizar una validación
posterior.

Si durante el proceso de cofirma o contrafirma se detecta que la firma
de entrada no es válida, el nuevo proceso de firma fallará y se
notificará el error a través del método *callback* configurado.

Si se pude completar este proceso de validación, la multifirma
continuará normalmente.

La verificación de las firmas previas es una operación compatible con
los siguientes formatos de firma:

- CAdES

- XAdES

- PAdES

La verficación se realiza tanto en la generación de firmas monofásicas
en AutoFirma como trifásicas con cualquiera de las aplicaciones de
firma. En el caso de las firmas monofásicas, la validación se realiza al
inicio del proceso de firma, mientras que en las firmas trifásicas el
proceso se realiza en servidor. Por este motivo, al realizar firmas
trifásicas se le pedirá el certificado al usuario incluso si la firma no
es válida, ya que esto es algo que no se identificará hasta más adelante
en el proceso de firma.

Si su despliegue es compatible con aplicaciones móviles y desea que
estas también validen la firma previa antes de agregar otra nueva,
asegúrese de que en estos entornos móviles se configura el nombre de
formato de firma que obliga a la generación de la firma de forma
trifásica (CAdEStri, XAdEStri o PAdEStri).

# Formatos de firma

El Cliente @firma permite la generación de firmas en diversos formatos
con diversos perfiles básicos. Las firmas en estos formatos pueden ser
mejoradas a posteriori con otros productos para incluir la información
longeva de firma.

Los formatos avanzados soportados son:

- **CAdES**

  - Formato avanzado de firma binaria.

- **XAdES**

  - Formato avanzado de firma XML.

- **PAdES**

  - Formato avanzado de firma de documentos PDF.

- **FacturaE**

  - Formato para la firma de facturas electrónicas. Se trata de una
    firma XAdES especialmente adaptada para cumplir los requisitos de
    firma de las facturas electrónicas.

El Cliente @firma soporta por retrocompatibilidad otros formatos de
firma, pero ninguno de estos formatos se recoge en la política de firma
de la AGE, su uso está desaconsejado y no se proporciona soporte sobre
los mismos:

- CMS

  - Formato de firma binaria no avanzado.

  - Se recomienda sustituir por el formato CAdES, con el que es
    compatible.

- XMLdSig

  - Formato de firma XML no avanzado.

  - Se recomienda sustituir por el formato XAdES, con el que es
    compatible.

- ODF

  - Formato de firma basado en XMLdSig y utilizado por
    OpenOffice/LibreOffice.

  - Se recomienda sustituirlo por firmas PAdES sobre documentos PDF para
    seguir gestionándolas junto al documento firmado o por firmas CAdES
    o XAdES si su sistema puede gestionar por separado el documento y la
    firma electronica.

- OOXML

  - Formato de firma basado en XAdES y utilizado por Microsoft Office.

  - Se recomienda sustituirlo por firmas PAdES sobre documentos PDF para
    seguir gestionándolas junto al documento firmado o por firmas CAdES
    o XAdES si su sistema puede gestionar por separado el documento y la
    firma electronica.

Adicionalmente, se soporta el nombre de formato “NONE” para permitir
realizar una firma sin formato (PKCS#1). La utilidad de esto es permitir
generar el formato de firma externa y utilizar el Cliente @firma
únicamente para generar el cifrado con el certificado del usuario.

En los siguientes apartados, se proporciona información adicional de los
principales formatos de firma soportados, junto con el listado de
opciones del Cliente @firma para configurarlos.

## Configuración de firmas CAdES

Las firmas CAdES generadas por el Cliente @firma son, por defecto,
acordes a todas las siguientes versiones del formato de firma:

- v1.7.3 (ETSI TS 101 733 v1.7.3)

- v1.7.4 (ETSI TS 101 733 v1.7.4)

- v1.8.1 (ETSI TS 101 733 v1.8.1)

- v1.8.3 (ETSI TS 101 733 v1.8.3)

- v2.1.1 (ETSI TS 101 733 v2.1.1)

- v2.2.1 (ETSI TS 101 733 v2.2.1)

Las firmas CAdES no declaran cuál es su versión de formato de firma, por
lo que puede considerarse que una misma firma se ajusta a todas las
versiones anteriormente listadas.

El Cliente @firma permite generar firmas CAdES acordes a los siguientes
perfiles de firma:

- CAdES-BES

  - Todas las firmas CAdES generadas por el Cliente @firma sin política
    de firma son consideradas CAdES-BES.

- CAdES-EPES

  - Todas las firmas CAdES generadas por el Cliente @firma con política
    de firma son consideradas CAdES-EPES.

Hay que tener en cuenta que algunas de las firmas CAdES generadas por el
Cliente @firma también pueden considerarse de tipo B-Level. Sin embargo,
el Cliente @firma no incluye un modo de operación que permita asegurar
que las firmas generadas sean acordes a este perfil.

Algunas de las propiedades de configuración listadas en el apartado
<u>8.1.3 Parámetros adicionales</u> pueden afectar a la compatibilidad
de las firmas generadas con algunas versiones o perfiles del formato.
Consulte el apartado específico de cada propiedad para saber si esta
afecta o no a la compatibilidad.

Las firmas CAdES que el Cliente @firma genera por defecto no incluyen ni
los datos firmados (firma explícita) ni política de firma y se ajusta al
perfil CAdES-BES.

### Algoritmos de firma

Las firmas CAdES generadas por el Cliente @firma aceptan los siguientes
algoritmos de firma:

- SHA512withRSA

- SHA384withRSA

- SHA256withRSA

- SHA1withRSA (No recomendado)

No es recomendable usar el algoritmo SHA1withRSA por estar obsoleto y
ser vulnerable.

El algoritmo más seguro y, por lo tanto, el recomendado para su uso es
SHA512withRSA.

Si los certificados del usuario se encuentran en tarjeta inteligente,
asegúrese de disponer de la última versión de su controlador para
garantizar la compatibilidad con estos algoritmos de firma. En caso de
que, aún así, no pueda utilizar este algoritmo con su tarjeta
inteligente, consulte la información de compatibilidad de su tarjeta y/o
pruebe con otro algoritmo.

### Firmas CAdES implícitas o explícitas

Las firmas CAdES pueden incluir internamente una copia de los datos
firmados (firmas implícitas o “*attached*”) o no incluirlos (firmas
explícitas o “*detached*”). El Cliente @firma por defecto genera firmas
explícitas, más pequeñas en tamaño, pero es posible que desee generar
firmas implícitas para disponer en un sólo fichero de los datos y la
firma electrónica, así como tener toda la información necesaria para la
validación completa de la firma. Para generar firmas implícitas, debe
indicar el siguiente parámetro adicional:

mode=implicit

### Parámetros adicionales

A continuación, se detallan los parámetros adicionales que aceptan cada
una de las operaciones de firma.

Es posible que el uso de parámetros no contemplados en las siguientes
tablas provoque otros cambios de funcionamiento del Cliente o en la
información contenida en las firmas CAdES. No obstante, **no se dará
soporte** al aplicativo si se usan parámetros no documentados, asumiendo
el integrador todo el riesgo y responsabilidad derivados del uso de
parámetros o valores distintos de los aquí descritos.

#### Firma y cofirma

<table>
<colgroup>
<col style="width: 46%" />
<col style="width: 12%" />
<col style="width: 41%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Nombre del parámetro</strong></th>
<th><strong>Valores posibles</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td rowspan="2">mode</td>
<td>explicit</td>
<td>La firma resultante no incluirá los datos firmados. Si no se indica
el parámetro mode se configura automáticamente este comportamiento.</td>
</tr>
<tr class="even">
<td>implicit</td>
<td><p>La firma resultante incluirá internamente una copia de los datos
firmados.</p>
<p>El uso de este valor podría generar firmas de gran tamaño. En las
cofirmas, este parámetro se ignorará si los datos ya estaban contenidos
en la firma original o si no se proporcionan los datos.</p></td>
</tr>
<tr class="odd">
<td>contentTypeOid</td>
<td>OID</td>
<td>Identificador del tipo de dato firmado.</td>
</tr>
<tr class="even">
<td>contentDescription</td>
<td>[Texto]</td>
<td>Descripción textual del tipo de datos firmado.</td>
</tr>
<tr class="odd">
<td rowspan="2">includeMimeTypeAttribute</td>
<td>true</td>
<td>Incluye en la firma el atributo id-aa-ets-mimeType definido en CAdES
v2.1.1 y superiores (válido en firmas baseline). El valor de mimetype se
tomará de la propiedad mimetype o, si no se incluyo, se extrapolará de
la propiedad contentTypeOid. Si tampoco fuese posible, se tratarán de
obtener estos valores de alguna de las firmas previas (en caso de
cofirmas). Si tampoco fuese posible, se obtendrá el tipo del análisis de
los datos (que podría no ser correcto o concreto). En caso de que no se
pueda obtener el tipo de ninguna manera, se usará el mimetype
application/octet-stream.</td>
</tr>
<tr class="even">
<td>false</td>
<td>No incluye el atributo id-aa-ets-mimeType en la firma. Valor por
defecto.</td>
</tr>
<tr class="odd">
<td>mimeType</td>
<td>[Texto en formato MIME-Type]</td>
<td>MIME-Type de los datos a firmar. Sólo se incluye cuando se indica la
propiedad includeMimeTypeAttribute.</td>
</tr>
<tr class="even">
<td>policyIdentifier</td>
<td>[OID o URN de tipo OID]</td>
<td>Identificador de la política de firma, necesario para generar firmas
CAdES-EPES.</td>
</tr>
<tr class="odd">
<td>policyIdentifierHash</td>
<td>[Valor en Base64]</td>
<td>Huella digital de la política de firma. Es obligatorio indicar este
parámetro si de indicó también policyIdentifier, al igual que es
obligatorio también dar valor al parámetro
policyIdentifierHashAlgorithm.</td>
</tr>
<tr class="even">
<td rowspan="4">policyIdentifierHashAlgorithm</td>
<td>SHA1</td>
<td>Indica que la huella digital indicada en la propiedad
policyIdentifierHash se calculó mediante el algoritmo SHA1.</td>
</tr>
<tr class="odd">
<td>SHA-256</td>
<td>Indica que la huella digital indicada en la propiedad
policyIdentifierHash se calculó mediante el algoritmo SHA-256.</td>
</tr>
<tr class="even">
<td>SHA-384</td>
<td>Indica que la huella digital indicada en la propiedad
policyIdentifierHash se calculó mediante el algoritmo SHA-284.</td>
</tr>
<tr class="odd">
<td>SHA-512</td>
<td>Indica que la huella digital indicada en la propiedad
policyIdentifierHash se calculó mediante el algoritmo SHA-512.</td>
</tr>
<tr class="even">
<td>policyQualifier</td>
<td>[URL hacia documento]</td>
<td>URL (universalmente accesible) hacia el documento (normalmente PDF)
que contiene una descripción textual de la política de firma. Esta
propiedad es opcional incluso si se desea generar firmas
CAdES-EPES.</td>
</tr>
<tr class="odd">
<td rowspan="2">includeOnlySignningCertificate</td>
<td>true</td>
<td>Indica que debe incluirse en la firma únicamente el certificado del
firmante.</td>
</tr>
<tr class="even">
<td>false</td>
<td>Indica que debe incluirse en la firma toda la cadena de
certificación del certificado firmante. Valor por defecto.</td>
</tr>
<tr class="odd">
<td>signatureProductionCity</td>
<td>[Texto]</td>
<td>Agrega a la firma un campo con la ciudad en la que se realiza la
firma. La codificación debe ser UTF-8.</td>
</tr>
<tr class="even">
<td>signatureProductionPostalCode</td>
<td>[Texto]</td>
<td>Agrega a la firma un campo con el código postal en donde se realiza
la firma. La codificación debe ser UTF-8.</td>
</tr>
<tr class="odd">
<td>signatureProductionCountry</td>
<td>[Texto]</td>
<td>Agrega a la firma un campo con el país en la que se realiza la
firma. La codificación debe ser UTF-8.</td>
</tr>
<tr class="even">
<td>signerClaimedRoles</td>
<td>[Texto]</td>
<td>Agrega a la firma campos con los cargos atribuidos al firmante.
Deben separarse los cargos con el carácter “|” (y este no puede estar en
el propio texto de ningún cargo).</td>
</tr>
<tr class="odd">
<td>commitmentTypeIndications</td>
<td>[Entero]</td>
<td>Indica el número de CommitmentTypeIndications que se van a declarar.
Estos son los motivos que se declaran para la firma. Los valores
concretos se especifican con
commitmentTypeIndication<em><strong>n</strong></em>Identifier y
commitmentTypeIndication<em><strong>n</strong></em>Description, donde
‘<em><strong>n</strong></em>’ va desde 0 hasta el valor indicado en esta
propiedad menos 1.</td>
</tr>
<tr class="even">
<td
rowspan="6">commitmentTypeIndication<em><strong>n</strong></em>Identifier</td>
<td>1</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> (contando desde cero) es “<strong>Prueba de
origen</strong>”.</td>
</tr>
<tr class="odd">
<td>2</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> (contando desde cero) es “<strong>Prueba de
recepción</strong>”.</td>
</tr>
<tr class="even">
<td>3</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> (contando desde cero) es “<strong>Prueba de
entrega</strong>”.</td>
</tr>
<tr class="odd">
<td>4</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> (contando desde cero) es “<strong>Prueba de
envío</strong>”.</td>
</tr>
<tr class="even">
<td>5</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> (contando desde cero) es “<strong>Prueba de
aprobación</strong>”.</td>
</tr>
<tr class="odd">
<td>6</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> (contando desde cero) es “<strong>Prueba de
creación</strong>”.</td>
</tr>
<tr class="even">
<td>commitmentTypeIndication<em><strong>n</strong></em>CommitmentTypeQualifiers</td>
<td>[Texto]</td>
<td>Lista de indicadores textuales separados por el carácter '|' que se
aportan como calificadores adicionales del CommitmentTypeIndication
número n (atributo opcional). Normalmente son OID.<br />
Los elementos de la lista no pueden contener el carácter '|' (ya que
este se usa como separador).</td>
</tr>
<tr class="odd">
<td rowspan="3">signingCertificateV2</td>
<td>true</td>
<td>Se incluirá el atributo SigningCertificateV2 en la firma.</td>
</tr>
<tr class="even">
<td>false (U otro valor)</td>
<td>Se incluirá el atributo SigningCertificate en la firma</td>
</tr>
<tr class="odd">
<td>Sin especificar</td>
<td>Se incluirá SigningCertificate si la firma utiliza un algoritmo de
firma SHA1 y SigningCertificateV2 para el resto de los algoritmos.</td>
</tr>
<tr class="even">
<td rowspan="2">includeSigningTimeAttribute</td>
<td>true</td>
<td>Se incluye en la firma la marca de tiempo con la hora del equipo.
Valor por defecto.</td>
</tr>
<tr class="odd">
<td>false</td>
<td>No se incluye la marca de tiempo en la firma. Esta opción sólo se
debería usar para generar una firma apta para componer una firma
PAdES.</td>
</tr>
<tr class="even">
<td rowspan="2">includeContentHintAttribute</td>
<td>true</td>
<td>Se incluye el atributo content-hints en la firma con la información
de los datos firmados. Este valor se ignorará cuando se configure
expresamente un tipo de firma que no permite este atributo. Valor por
defecto.</td>
</tr>
<tr class="odd">
<td>false</td>
<td>No se incluye el atributo content-hints en la firma. Esta opción
sólo se debería usar para generar una firma apta para componer una firma
PAdES.</td>
</tr>
<tr class="even">
<td rowspan="3">allowSignLTSignature</td>
<td>true</td>
<td>Se permite la cofirma/contrafirma de firmas de archivo longevo, a
pesar de que estas no serán válidas posteriormente.</td>
</tr>
<tr class="odd">
<td>false (U otro valor)</td>
<td>No se permite la cofirma/contrafirma de firmas de archivo
longevo.</td>
</tr>
<tr class="even">
<td>Sin especificar</td>
<td>Se consultará al usuario en caso de intentar
confirmarse/contrafirmarse una firma de archivo longevo.</td>
</tr>
</tbody>
</table>

#### Contrafirma

| **Nombre del parámetro**                                | **Valores posibles**      | **Descripción**                                                                                                                                                                                                                                                                                                                          |
|---------------------------------------------------------|---------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| policyIdentifier                                        | \[OID o URN de tipo OID\] | Identificador de la política de firma, necesario para generar firmas CAdES-EPES.                                                                                                                                                                                                                                                         |
| policyIdentifierHash                                    | \[Valor en Base64\]       | Huella digital de la política de firma. Es obligatorio indicar esta propiedad si de indicó también policyIdentifier, al igual que es obligatorio también dar valor al parámetro policyIdentifierHashAlgorithm.                                                                                                                           |
| policyIdentifierHashAlgorithm                           | SHA1                      | Indica que la huella digital indicada en el parámetro policyIdentifierHash se calculó mediante el algoritmo SHA1.                                                                                                                                                                                                                        |
|                                                         | SHA-256                   | Indica que la huella digital indicada en el parámetro policyIdentifierHash se calculó mediante el algoritmo SHA-256.                                                                                                                                                                                                                     |
|                                                         | SHA-384                   | Indica que la huella digital indicada en el parámetro policyIdentifierHash se calculó mediante el algoritmo SHA-284.                                                                                                                                                                                                                     |
|                                                         | SHA-512                   | Indica que la huella digital indicada en el parámetro policyIdentifierHash se calculó mediante el algoritmo SHA-512.                                                                                                                                                                                                                     |
| policyQualifier                                         | \[URL hacia documento\]   | URL (universalmente accesible) hacia el documento (normalmente PDF) que contiene una descripción textual de la política de firma. Esta propiedad es opcional incluso si se desea generar firmas CAdES-EPES.                                                                                                                              |
| includeOnlySignningCertificate                          | true                      | Indica que debe incluirse en la firma únicamente el certificado del firmante.                                                                                                                                                                                                                                                            |
|                                                         | false                     | Indica que debe incluirse en la firma toda la cadena de certificación del certificado firmante. Valor por defecto.                                                                                                                                                                                                                       |
| signerClaimedRoles                                      | \[Texto\]                 | Agrega a la firma campos con los cargos atribuidos al firmante. Deben separarse los cargos con el carácter “\|” (y este no puede estar en el propio texto de ningún cargo).                                                                                                                                                              |
| signatureProductionCity                                 | \[Texto\]                 | Agrega a la firma un campo con la ciudad en la que se realiza la firma. La codificación debe ser UTF-8.                                                                                                                                                                                                                                  |
| signatureProductionPostalCode                           | \[Texto\]                 | Agrega a la firma un campo con el código postal en donde se realiza la firma. La codificación debe ser UTF-8.                                                                                                                                                                                                                            |
| signatureProductionCountry                              | \[Texto\]                 | Agrega a la firma un campo con el país en la que se realiza la firma. La codificación debe ser UTF-8.                                                                                                                                                                                                                                    |
| commitmentTypeIndications                               | \[Entero\]                | Indica el número de CommitmentTypeIndications que se van a declarar. Estos son los motivos que se declaran para la firma. Los valores concretos se especifican con commitmentTypeIndication***n***Identifier y commitmentTypeIndication***n***Description, donde ‘***n***’ va desde 0 hasta el valor menos 1 indicado en esta propiedad. |
| commitmentTypeIndication***n***Identifier               | 1                         | Establece que el CommitmentTypeIndication número ***n*** es “**Prueba de origen**”.                                                                                                                                                                                                                                                      |
|                                                         | 2                         | Establece que el CommitmentTypeIndication número ***n*** es “**Prueba de recepción**”.                                                                                                                                                                                                                                                   |
|                                                         | 3                         | Establece que el CommitmentTypeIndication número ***n*** es “**Prueba de entrega**”.                                                                                                                                                                                                                                                     |
|                                                         | 4                         | Establece que el CommitmentTypeIndication número ***n*** es “**Prueba de envío**”.                                                                                                                                                                                                                                                       |
|                                                         | 5                         | Establece que el CommitmentTypeIndication número ***n*** es “**Prueba de aprobación**”.                                                                                                                                                                                                                                                  |
|                                                         | 6                         | Establece que el CommitmentTypeIndication número ***n*** es “**Prueba de creación**”.                                                                                                                                                                                                                                                    |
| commitmentTypeIndication***n***CommitmentTypeQualifiers | \[OID\]                   | Lista de OID separados por el caracter '\|' que se aportan como calificadores adicionales del CommitmentTypeIndication número n (atributo opcional).                                                                                                                                                                                     |
| allowSignLTSignature                                    | true                      | Se permite la cofirma/contrafirma de firmas de archivo longevo, a pesar de que estas no serán válidas posteriormente.                                                                                                                                                                                                                    |
|                                                         | false (U otro valor)      | No se permite la cofirma/contrafirma de firmas de archivo longevo.                                                                                                                                                                                                                                                                       |
|                                                         | Sin especificar           | Se consultará al usuario en caso de intentar confirmarse/contrafirmarse una firma de archivo longevo.                                                                                                                                                                                                                                    |

## Configuración de firmas XAdES

Las firmas XAdES generadas por defecto con el Cliente @firma son acordes
a la versión 1.3.2 del formato de firma (ETSI TS 101 903 v1.3.2).

Es posible configurar las operaciones de firma para que se generen
conforme a la versión 1.4.1 del formato (ETSI TS 101 903 v1.4.1). Para
ello, será necesario configurar los parámetros adicionales
xadesNamespace y signedPropertiesTypeUrl.

El Cliente @firma permite generar firmas acordes a los siguientes
perfiles:

- XAdES-BES

  - Todas las firmas XAdES generadas por el Cliente @firma sin política
    de firma son consideradas XAdES-BES.

- XAdES-EPES

  - Todas las firmas XAdES generadas por el Cliente @firma con política
    de firma son consideradas XAdES-EPES.

Hay que tener en cuenta que algunas de las firmas XAdES generadas por el
Cliente @firma también pueden considerarse de tipo B-Level. Sin embargo,
El Cliente @firma versión 1.7 no incluye un modo de operación que
permita asegurar que las firmas generadas sean acordes a este perfil.

Con independencia del perfil de firma, es posible realizar las firmas
XAdES en cuatro modos diferentes:

- *Enveloping* (Por defecto)

- *Enveloped*

- *Internally Detached* (también referida en este documento como
  *Detached*)

- *Externally Detached*

Algunas de las propiedades de configuración listadas en el apartado
<u>8.2.7 Parámetros adicionales</u> pueden afectar a la compatibilidad
de las firmas generadas con algunas versiones del formato o perfiles de
firma. Consulte el apartado específico de cada propiedad para saber si
esta afecta o no a la compatibilidad.

### Algoritmos de firma

Las firmas XAdES aceptan los siguientes algoritmos de firma (deben
escribirse exactamente como aquí se muestran):

- SHA512withRSA

- SHA384withRSA

- SHA256withRSA

- SHA1withRSA (No recomendado)

No es recomendable usar el algoritmo SHA1withRSA por estar obsoleto y
ser vulnerable.

El algoritmo más seguro y, por lo tanto, el recomendado para su uso es
SHA512withRSA.

Si los certificados del usuario se encuentran en tarjeta inteligente,
asegúrese de disponer de la última versión de su controlador para
garantizar la compatibilidad con estos algoritmos de firma. En caso de
que, aún así, no pueda utilizar este algoritmo con su tarjeta
inteligente, consulte la información de compatibilidad de su tarjeta y/o
pruebe con otro algoritmo.

### Algoritmos de huella digital para las referencias

XAdES hace cálculos de huella digital (*hash*) para cada una de las
referencias firmadas. El algoritmo por defecto para estas huellas es
SHA-512. Este puede cambiarse mediante el parámetro adicional
referencesDigestMethod.

En el caso de las referencias de las firmas con manifest, el algoritmo
de huella se toma del parámetro adicional precalculatedHashAlgorithm. En
caso de que esta propiedad no se indique, se utilizaría el algoritmo del
parámetro referencesDigestMethod o, de no estar configurado, el
algoritmo SHA-512.

Consulte el apartado <u>8.2.7 Parámetros adicionales</u> para conocer
los valores que pueden adoptar estos parámetros.

### Situación del nodo de firma en XAdES Enveloped

Cliente @firma sitúa por defecto la firma electrónica en las firmas
XAdES Enveloped en un nodo “Signature” directamente como hijo de la raíz
del XML. No obstante, hay situaciones en las que puede interesar situar
este nodo de firma en otra posición del XML.

Para ello, puede usarse el parámetro adicional
insertEnvelopedSignatureOnNodeByXPath, en el que, mediante una expresión
XPath v1, podemos indicar el nodo en el que queremos se inserte la firma
(el nodo “Signature” pasará a ser el primer hijo de este). Si la
expresión XPath resolviese varios nodos, se usará el primero de ellos.

Por ejemplo, en el siguiente XML:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>&lt;?xml version=<em>"1.0"</em>
encoding=<em>"UTF-8"</em>?&gt;</p>
<p>&lt;bookstore&gt;</p>
<p>&lt;book category=<em>"COOKING"</em>&gt;</p>
<p>&lt;title lang=<em>"en"</em>&gt;Everyday Italian&lt;/title&gt;</p>
<p>&lt;author&gt;Giada De Laurentiis&lt;/author&gt;</p>
<p>&lt;year&gt;2005&lt;/year&gt;</p>
<p>&lt;price&gt;30.00&lt;/price&gt;</p>
<p>&lt;/book&gt;</p>
<p>&lt;book category=<em>"CHILDREN"</em>&gt;</p>
<p>&lt;title lang=<em>"en"</em>&gt;Harry Potter&lt;/title&gt;</p>
<p>&lt;author&gt;J K. Rowling&lt;/author&gt;</p>
<p>&lt;year&gt;2005&lt;/year&gt;</p>
<p>&lt;price&gt;29.99&lt;/price&gt;</p>
<p>&lt;/book&gt;</p>
<p>&lt;/bookstore&gt;</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Si indicamos el parámetro con este valor:

| insertEnvelopedSignatureOnNodeByXPath = /bookstore/book\[1\]/title |
|--------------------------------------------------------------------|

La firma se insertará como nodo hijo del título del primer libro:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>&lt;?xml version=<em>"1.0"</em>
encoding=<em>"UTF-8"</em>?&gt;</p>
<p>&lt;bookstore&gt;</p>
<p>&lt;book category=<em>"COOKING"</em>&gt;</p>
<p>&lt;title lang=<em>"en"</em>&gt;</p>
<p>Everyday Italian</p>
<p><strong>&lt;ds:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#" Id="S1"&gt;</strong></p>
<p><strong>…</strong></p>
<p><strong>&lt;/ds:Signature&gt;</strong></p>
<p>&lt;/title&gt;</p>
<p>&lt;author&gt;Giada De Laurentiis&lt;/author&gt;</p>
<p>&lt;year&gt;2005&lt;/year&gt;</p>
<p>&lt;price&gt;30.00&lt;/price&gt;</p>
<p>&lt;/book&gt;</p>
<p>&lt;book category=<em>"CHILDREN"</em>&gt;</p>
<p>&lt;title lang=<em>"en"</em>&gt;Harry Potter&lt;/title&gt;</p>
<p>&lt;author&gt;J K. Rowling&lt;/author&gt;</p>
<p>&lt;year&gt;2005&lt;/year&gt;</p>
<p>&lt;price&gt;29.99&lt;/price&gt;</p>
<p>&lt;/book&gt;</p>
<p>&lt;/bookstore&gt;</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Si en la expresión XPath desea referenciar nodos dentro de un espacio de
nombres, debe usar funciones XPath como namespace-uri() o local-name().
Por ejemplo, para seleccionar el primer nodo dentro del espacio de
nombres de factura electrónica podríamos usar la expresión:

| //\*\[namespace-uri()='http://www.facturae.es/Facturae/2007/v3.1/Facturae'\] |
|------------------------------------------------------------------------------|

### Transformaciones sobre el contenido a firmar

Es posible declarar transformaciones adicionales sobre el contenido a
firmar. Esto se realizará mediante las siguientes propiedades:

- xmlTransform***n***Type

  - Tipo de transformación.

- xmlTransform***n***Subtype

  - Subtipo de transformación.

- xmlTransformnBody:

  - Transformación específica.

Las combinaciones de valores que pueden adoptar estas propiedades son:

- Transformación XPATH

  - Tipo: http://www.w3.org/TR/1999/REC-xpath-19991116

  - Subtipos: No tiene subtipos.

  - Cuerpo: Especificado mediante sentencias de tipo XPATH.

- Transformación XPATH2

  - Tipo: <http://www.w3.org/2002/06/xmldsig-filter2>

  - Subtipos:

    - subtract: Resta.

    - intersect: Intersección

    - union: Unión

  - Cuerpo: Especificado mediante sentencias de tipo XPATH2.

- Transformación BASE64. La transformación es inversa, es decir, los
  datos se decodifican desde Base64 antes de firmarse, por lo que estos
  deben estar previamente codificados en Base64 e indicarse mediante el
  parámetro adicional “encodign=base64“.

  - Tipo: http://www.w3.org/2000/09/xmldsig#base64

  - Subtipos: No tiene subtipos.

  - Cuerpo: No tiene cuerpo.

No es posible especificar transformaciones complejas que incluyan varias
sentencias. En su lugar, puede declararse una sucesión de
transformaciones simples que produzcan el mismo resultado. Cada una de
las transformaciones se aplicará de forma ordenada sobre el resultado de
la anterior.

El listado de transformaciones se inicia con aquella declarada con el
índice 0. Por ejemplo, si se desean insertar 2 transformaciones
adicionales, se deberán establecer los parámetros:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>xmlTransforms=2</p>
<p>xmlTransform0Type=…</p>
<p>xmlTransform0Subtype=… (Opcional)</p>
<p>xmlTransform0Body=…</p>
<p>xmlTransform1Type=…</p>
<p>xmlTransform1Subtype=… (Opcional)</p>
<p>xmlTransform1Body=…</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

### Uso de estructuras *Manifest* en firmas XAdES

Es posible crear firmas XAdES en las que, siguiendo el punto 2.3 de la
especificación XMLDSig
(<http://www.w3.org/TR/2000/WD-xmldsig-core-20000510/#sec-o-Manifest>),
las referencias XML no se firmen directamente, sino que se firme una
estructura de tipo *Manifest* que a su vez contenga las referencias a
firmar.

De esta forma, tal y como indica la normativa, la resolución de las
referencias incluidas dentro de una estructura *Manifest* no es
responsabilidad del sistema validador, sino de la aplicación que generó
la firma o una delegada por la misma. Al unir esto con el uso de
referencias a datos externos a la firma, obtenemos la ventaja de que la
firma no contendrá los datos firmados (muy recomendable para trabajar
con datos grandes) y que la plataforma validadora no tiene que acceder a
los datos para comprobar la validez de la propia firma. Consulte la
especificación XMLDSig para más información.

De igual manera que el sistema validador no tiene que acceder a los
datos referenciados desde el *manifest*, no será responsabilidad del
Cliente @firma acceder a estos datos para su análisis y el cálculo de su
huella digital. La propia aplicación que ordena la firma será la
encargada de proporcionar al Cliente @firma las referencias a los datos
y la huella digital de los mismos.

Las referencias a los datos firmados en un Manifest se expresan mediante
direcciones URI. Estas URI no tiene necesariamente que ser una URL, así
puede estructurarse de la manera necesaria para ayudar a determinar
inequívocamente cuales son los datos que se firman. Por ejemplo,
podríamos construir una URI en forma de URN, en la que referenciásemos a
un recurso concreto dentro de uno de nuestros gestores de contenido,
para lo que podríamos crear una URN a medida que tuviese los datos
necesarios para identificar el repositorio de datos y el recurso en
cuestión:

> urn:rp:mirp:asset:CDC8D258

Un sistema de validación externo no resolverá la URI que referencia a
los datos desde un *Manifest*, ya que puede que esta sólo sea accesible
y/o comprensible desde el entorno en el que se generó la firma. Por
ende, la propia aplicación que firma los datos mediante *Manifest* o una
aplicación delegada por la misma debe poder asegurar que los datos
referenciados mediante la URI no cambiaran y ser capaz de comprobarlos
calculando su huella digital (*hash*).

Para aprovechar todas las ventajas de las firmas *Manifest*, **todas las
firmas *Manifest generadas por* el Cliente @firma serán *externally
detached***, independientemente de la configuración establecida.

Un ejemplo muy simplificado de la estructura de una firma con *Manifest*
sería:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>&lt;ds:Signature Id=<em>"Signature-02553"</em>&gt;</p>
<p>&lt;ds:SignedInfo&gt;</p>
<p>&lt;ds:Reference Id=<em>"Reference-894bfd39"</em></p>
<p>Type=<a
href="http://www.w3.org/2000/09/xmldsig#Manifest"><em>http://www.w3.org/2000/09/xmldsig#Manifest</em></a></p>
<p>URI=<em>"#Manifest-36e2de7b"</em>&gt;</p>
<p>…</p>
<p>&lt;/ds:Reference&gt;</p>
<p>&lt;/ds:SignedInfo&gt;</p>
<p>…</p>
<p>&lt;ds:Object Id=<em>"ManifestObject-ffd54e53"</em>&gt;</p>
<p>&lt;ds:Manifest Id=<em>"Manifest-36e2de7b"</em>&gt;</p>
<p>&lt;ds:Reference Id=<em>"Reference-894bfd39"</em></p>
<p>URI=<em>"myscheme://path/file"</em>&gt;</p>
<p>&lt;ds:DigestMethod</p>
<p>Algorithm=<em>"http://www.w3.org/2001/04/xmlenc#sha512"</em>/&gt;</p>
<p>&lt;ds:DigestValue&gt;…&lt;/ds:DigestValue&gt;</p>
<p>&lt;/ds:Reference&gt;</p>
<p>&lt;/ds:Manifest&gt;</p>
<p>&lt;/ds:Object&gt;</p>
<p>…</p>
<p>&lt;/ds:Signature&gt;</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

En este ejemplo, el contenido firmado es “**myscheme://path/file**”,
pero al firmar no se ha intentado acceder a ese fichero, y se ha
asignado la huella digital proporcionada como la correspondiente a los
datos.

#### Generar firma manifest con el Cliente @firma

Para crear firmas XAdES con estructuras *manifest* desde el Cliente
@firma debe especificarse el parámetro adicional useManifest con el
valor “true”.

Adicionalmente, se deberá indicar la URI y la huella digital (*hash*) de
los datos firmados. El Cliente @firma permite firmar más de un dato
simultáneamente mediante *manifest* así que será posible indicar más de
una URI y huella digital al configurar una firma *manifest*. Como
resultado, se obtendrá una única firma que engloba todas las
referencias. Para que esta firma tuviese validez completa, todos los
datos referenciarlos deberían mantenerse sin cambios a lo largo del
tiempo.

Para generar firmas manifest deberán indicarse a través de los
parámetros adicionales de la aplicación las propiedades que se listan a
continuación por cada referencia a firmar. Para ello, se sustituirá la
‘X’ del nombre del parámetro por el número de referencia en cuestión
(empezando en 1):

- uriX

  - Obligatorio. URI que referencia a los datos.

- mdX

  - Obligatorio. Huella digital (*hash*) en Base64 de los datos. El
    algoritmo de huella digital se indicará mediante el parámetro
    “precalculatedHashAlgorithm”.

- mimeTypeX

  - Opcional. MimeType correspondiente a los datos referenciados. Si no
    se indica, se usará “application/octet-stream”.

- contentTypeOidX

  - Opcional. OID correspondiente al tipo de dato referenciado. Si no se
    indica, se intentará extrapolar a partir del MimeType. En caso de no
    conseguirlo, no se usará ninguno.

- encodingX

  - Opcional. URI identificadora de la codificación de los datos si
    estuviesen codificados. Por defecto, no se usa ninguna.

- precalculatedHashAlgorithm

  - Algoritmo de huella digital que se ha utilizado para calcular la
    huella de los datos. Esta propiedad aplica a todas las referencias
    insertadas. Si no se indica, se hereda la configuración del
    parámetro “referencesDigestMethod”. Si este otro parámetro tampoco
    se indicase se interpretará que las huellas digitales se han
    calculado con el algoritmo SHA-512.

Al realizar firmas *manifest* no será necesario indicar datos en el
parámetro de datos del método de firma del Cliente. El propio Cliente
detectará que se va a realizar una firma manifest y no solicitará estos
datos al usuario.

Por ejemplo, podríamos hacer una firma *manifest* de unos datos usando
los siguientes parámetros adicionales (*extraParams*):

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>useManifest=true</p>
<p>uri1=urn:id:3086</p>
<p>md1=4hrn/3Y9c/fn/uyq12w+D9A2aKc=</p>
<p>mimeType1=plain/xml</p>
<p>precalculatedHashAlgorithm=SHA-1</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

En la llamada al método de firma, además de estos *extraParams*,
indicaríamos null como el parámetro de datos a firmar:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p>AutoScript.sign (<strong>null</strong>, "SHA512withRSA", "XAdES",
extraParams, successCallback, errorCallback);</p>
</blockquote></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Como resultado, obtendremos una firma XAdES Detached con un *manifest*,
en el que aparecerá la referencia indicada a los datos y su huella
digital.

### Tratamiento de las hojas de estilo XSL de los XML a firmar

Cuando se firma o cofirma (no aplica a la contrafirma) un XML que
contiene hojas de estilo, estas se firman igualmente a menos que se
indique lo contrario con el parámetro ignoreStyleSheets. Las reglas que
se siguen para procesar las hojas de estilo son las siguientes:

| **Referencia / Formato**          | **XAdES *Enveloped***                                                                                   | **XAdES *Enveloping***                                  | **XAdES *Internally Detached***                         | **XAdES *Externally Detached*** |
|-----------------------------------|---------------------------------------------------------------------------------------------------------|---------------------------------------------------------|---------------------------------------------------------|---------------------------------|
| Ruta relativa a la hoja de estilo | No se firma                                                                                             | No se firma                                             | No se firma                                             | No se firma                     |
| Ruta absoluta a la hoja de estilo | Se incluye la declaración a la hoja de estilo y se firma una referencia canonizada a la hoja de estilo. | Se firma una referencia canonizada a la hoja de estilo. | Se firma una referencia canonizada a la hoja de estilo. | No se firma                     |
| Hoja de estilo empotrada          | Se incluye la declaración a la hoja de estilo                                                           | No es necesaria ninguna acción                          | No es necesaria ninguna acción                          | No se firma                     |

### Parámetros adicionales

A continuación, se detallan los parámetros adicionales que aceptan cada
una de las operaciones de firma.

Es posible que el uso de parámetros no contemplados en las siguientes
tablas provoque otros cambios de funcionamiento. No obstante, **no se
dará soporte** al aplicativo si se usan parámetros no documentados,
asumiendo el integrador todo el riesgo y responsabilidad derivados del
uso de parámetros o valores distintos de los aquí descritos.

#### Firma y cofirma

<table>
<colgroup>
<col style="width: 34%" />
<col style="width: 20%" />
<col style="width: 44%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Nombre del parámetro</strong></th>
<th><strong>Valores posibles</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>insertEnvelopedSignatureOnNodeByXPath</td>
<td>[Texto (expresión XPath v1)]</td>
<td><p>Indica, mediante una expresión XPath (v1), el nodo bajo el cual
debe insertarse el nodo de firma en el caso de una firma
<em>Enveloped</em>.</p>
<p>Si la expresión devuelve más de un nodo, se usa solo el primero. Si
la expresión no devuelve nodos o está mal construida se lanzará una
excepción.</p>
<p>Esta propiedad solo tiene efecto en firmas
<em>Enveloped</em>.</p></td>
</tr>
<tr class="even">
<td rowspan="2">useManifest</td>
<td>true</td>
<td><p>Usa un Manifest de XMLDSig con las referencias de firma en vez de
firmar directamente estas referencias. Se ignora en la operación de
cofirma.</p>
<p>Esto permite que sea opcional la comprobación del destino y huellas
digitales de las referencias.</p></td>
</tr>
<tr class="odd">
<td>false</td>
<td>Genera las firmas normalmente, sin Manifest (comportamiento por
defecto)</td>
</tr>
<tr class="even">
<td>uri</td>
<td>[URI]</td>
<td>URI que referencia a los datos que se desean firmar en una firma
<em>Externally Detached</em>. La huella de los datos se proporcionará en
el propio parámetro de datos y el algoritmo de huella a través de
“precalculatedHashAlgorithm”.</td>
</tr>
<tr class="odd">
<td>uri<em><strong>n</strong></em></td>
<td>[URI]</td>
<td>URI que referencia a los datos que se desean firmar dentro de una
firma <em>manifest</em>. ‘<em><strong>n</strong></em>’ indica el número
de referencia de entre las que se quieren firmar, empezando en ‘1’.</td>
</tr>
<tr class="even">
<td>md<em><strong>n</strong></em></td>
<td>[Texto Base64]</td>
<td>Huella digital de los datos asociados a la referencia
‘<em><strong>n</strong></em>’ en una firma <em>manifest</em>.</td>
</tr>
<tr class="odd">
<td>mimeType<em><strong>n</strong></em></td>
<td>[Texto en formato MIME-Type]</td>
<td>MIME-Type de los datos asociados a la referencia
‘<em><strong>n</strong></em>’ en una firma <em>manifest</em>. Si no se
indica esta propiedad, se utilizará el tipo
‘application/octet-stream’.</td>
</tr>
<tr class="even">
<td>contentTypeOid<em><strong>n</strong></em></td>
<td>[OID o URN de tipo OID]</td>
<td>Identificador del tipo de dato firmado para la referencia número
‘<em><strong>n</strong></em>’ en una firma <em>manifest</em>. Esta
propiedad es complementaria (que no excluyente) al parámetro
mimeTypeX.</td>
</tr>
<tr class="odd">
<td>encoding<em><strong>n</strong></em></td>
<td>[URI]</td>
<td>Codificación de los datos asociados a la referencia número
‘<em><strong>n</strong></em>’ en una firma manifest. Un uso incorrecto
de esta propiedad puede provocar la generación de una firma
inválida.</td>
</tr>
<tr class="even">
<td rowspan="4">precalculatedHashAlgorithm</td>
<td>SHA1</td>
<td>Indica que las huellas digitales de los datos referenciados en el
<em>manifest</em> se calcularon mediante el algoritmo SHA1.</td>
</tr>
<tr class="odd">
<td>SHA-256</td>
<td>Indica que las huellas digitales de los datos referenciados en el
<em>manifest</em> se calcularon mediante el algoritmo SHA-256.</td>
</tr>
<tr class="even">
<td>SHA-384</td>
<td>Indica que las huellas digitales de los datos referenciados en el
<em>manifest</em> se calcularon mediante el algoritmo SHA-384.</td>
</tr>
<tr class="odd">
<td>SHA-512</td>
<td>Indica que las huellas digitales de los datos referenciados en el
<em>manifest</em> se calcularon mediante el algoritmo SHA-512.</td>
</tr>
<tr class="even">
<td rowspan="2">addKeyInfoKeyValue</td>
<td>true</td>
<td>Incluye el nodo KeyValue dentro de KeyInfo de XAdES (comportamiento
por defecto).</td>
</tr>
<tr class="odd">
<td>false</td>
<td>No incluye el nodo KeyValue dentro de KeyInfo de XAdES.</td>
</tr>
<tr class="even">
<td rowspan="2">addKeyInfoKeyName</td>
<td>true</td>
<td>Incluye el nodo KeyName dentro de KeyInfo de XAdES.</td>
</tr>
<tr class="odd">
<td>false</td>
<td>No incluye el nodo KeyName dentro de KeyInfo de XAdES
(comportamiento por defecto).</td>
</tr>
<tr class="even">
<td rowspan="2">avoidXpathExtraTransformsOnEnveloped</td>
<td>true</td>
<td>Evita la inclusión de la transformación XPATH2 que normalmente se
añade para posibilitar las cofirmas y que elimina todas las firmas del
documento para dejar únicamente el contenido.
<strong>ADVERTENCIA:</strong> La cofirma de un documento en el que al
menos una de las firmas no incluye la transformación XPATH, dará lugar a
un documento de firma que potencialmente será validado incorrectamente
por los validadores de firma. Por este motivo, sólo se permite el uso de
esta propiedad en la operación de firma (no en la de cofirma).</td>
</tr>
<tr class="odd">
<td>false</td>
<td>Incluye la transformación XPATH2 posibilita las cofirmas eliminando
todas las firmas del documento para dejar únicamente el contenido
(comportamiento por defecto).</td>
</tr>
<tr class="even">
<td rowspan="4">format</td>
<td>XAdES Enveloping</td>
<td>Genera firmas en formato <em>Enveloping</em>. Este es el formato que
se utiliza por defecto cuando no se indica ninguno.</td>
</tr>
<tr class="odd">
<td>XAdES Enveloped</td>
<td>Genera firmas en formato <em>Enveloped</em>.</td>
</tr>
<tr class="even">
<td>XAdES Detached</td>
<td>Genera firmas en formato <em>Internally Detached</em>.</td>
</tr>
<tr class="odd">
<td>XAdES Externally Detached</td>
<td>Genera firmas en formato <em>Externally Detached</em>.</td>
</tr>
<tr class="even">
<td rowspan="2">includeOnlySignningCertificate</td>
<td>true</td>
<td>Indica que debe incluirse en la firma únicamente el certificado del
firmante.</td>
</tr>
<tr class="odd">
<td>false</td>
<td>Indica que debe incluirse en la firma toda la cadena de
certificación del certificado firmante. Valor por defecto.</td>
</tr>
<tr class="even">
<td>policyIdentifier</td>
<td>[URL]</td>
<td>Identificador de la política de firma (normalmente una URL hacia la
política en formato XML procesable), necesario para generar firmas
XAdES-EPES.</td>
</tr>
<tr class="odd">
<td>policyIdentifierHash</td>
<td>[Valor en Base64]</td>
<td>Huella digital de la política de firma. Es obligatorio indicar esta
propiedad si el valor indicado en policyIdentifier no es universalmente
accesible. Si se da valor a esta propiedad es obligatorio también dar
valor al parámetro policyIdentifierHashAlgorithm.</td>
</tr>
<tr class="even">
<td rowspan="4">policyIdentifierHashAlgorithm</td>
<td>SHA1</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA1.</td>
</tr>
<tr class="odd">
<td>SHA-256</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA-256.</td>
</tr>
<tr class="even">
<td>SHA-384</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA-384.</td>
</tr>
<tr class="odd">
<td>SHA-512</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA-512.</td>
</tr>
<tr class="even">
<td>policyQualifier</td>
<td>[URL hacia documento]</td>
<td><p>URL (universalmente accesible) hacia el documento (normalmente
PDF) que contiene una descripción textual de la política de firma.</p>
<p>Esta propiedad es opcional incluso si se desea generar firmas
XAdES-EPES.</p></td>
</tr>
<tr class="odd">
<td>policyDescription</td>
<td>[Texto]</td>
<td><p>Descripción textual de la política de firma. En el caso de que se
firme un XML, la codificación del texto usado debe adecuarse al XML
firmado.</p>
<p>Esta propiedad es opcional incluso si se desea generar firmas
XAdES-EPES.</p></td>
</tr>
<tr class="even">
<td>signerClaimedRoles</td>
<td>[Texto]</td>
<td><p>Agrega a la firma campos con los cargos atribuidos al firmante.
Deben separarse los cargos con el carácter “|” (y este no puede estar en
el propio texto de ningún cargo).</p>
<p>En el caso de que se firme un XML, la codificación del texto usado
debe adecuarse al XML firmado.</p></td>
</tr>
<tr class="odd">
<td>signatureProductionCity</td>
<td>[Texto]</td>
<td><p>Agrega a la firma un campo con la ciudad en la que se realiza la
firma.</p>
<p>En el caso de que se firme un XML, la codificación del texto usado
debe adecuarse al XML firmado.</p></td>
</tr>
<tr class="even">
<td>signatureProductionProvince</td>
<td>[Texto]</td>
<td><p>Agrega a la firma un campo con la provincia en la que se realiza
la firma.</p>
<p>En el caso de que se firme un XML, la codificación del texto usado
debe adecuarse al XML firmado.</p></td>
</tr>
<tr class="odd">
<td>signatureProductionPostalCode</td>
<td>[Texto]</td>
<td><p>Agrega a la firma un campo con el código postal en donde se
realiza la firma.</p>
<p>En el caso de que se firme un XML, la codificación del texto usado
debe adecuarse al XML firmado.</p></td>
</tr>
<tr class="even">
<td>signatureProductionCountry</td>
<td>[Texto]</td>
<td><p>Agrega a la firma un campo con el país en el que se realiza la
firma.</p>
<p>En el caso de que se firme un XML, la codificación del texto usado
debe adecuarse al XML firmado.</p></td>
</tr>
<tr class="odd">
<td rowspan="3">referencesDigestMethod</td>
<td><a
href="http://www.w3.org/2000/09/xmldsig#sha1">http://www.w3.org/2000/09/xmldsig#sha1</a></td>
<td>Usa el algoritmo SHA1 para el cálculo de las huellas digitales de
las referencias XML firmadas.</td>
</tr>
<tr class="even">
<td><a
href="http://www.w3.org/2001/04/xmlenc#sha256">http://www.w3.org/2001/04/xmlenc#sha256</a></td>
<td>Usa el algoritmo SHA-256 para el cálculo de las huellas digitales de
las referencias XML firmadas.</td>
</tr>
<tr class="odd">
<td><a
href="http://www.w3.org/2001/04/xmlenc#sha512">http://www.w3.org/2001/04/xmlenc#sha512</a></td>
<td>Usa el algoritmo SHA-512 para el cálculo de las huellas digitales de
las referencias XML firmadas. Este es el comportamiento por
defecto.</td>
</tr>
<tr class="even">
<td>mimeType</td>
<td>[Texto en formato MIME-Type]</td>
<td>MIME-Type de los datos a firmar. Si no se indica esta propiedad el
sistema intenta auto-detectar el tipo, estableciendo el más aproximado
(que puede no ser el estrictamente correcto).</td>
</tr>
<tr class="odd">
<td>encoding</td>
<td>[URI]</td>
<td><p>Codificación de los datos a firmar (vease la documentación del
elemento Object de XMLDSig para más información). Un uso incorrecto de
esta propiedad puede provocar la generación de una firma inválida.</p>
<p>Si se proporcionan datos a firmar previamente codificados en Base 64
pero se desea sean considerados como su forma descodificada, debe
establecerse este valor a http://www.w3.org/2000/09/xmldsig#base64 y
especificarse el tipo real en el parámetro mimeType.</p>
<p>Por ejemplo, para firmar una imagen PNG haciendo que la firma se
refiera a su forma binaria directa, puede proporcionarse la imagen
directamente codificada en Base64 indicando el encoding como
http://www.w3.org/2000/09/xmldsig#base64 y el mimeType como
image/png.</p>
<p>El valor debe ser siempre una URI.</p></td>
</tr>
<tr class="even">
<td>outputXmlEncoding</td>
<td>[Texto]</td>
<td><p>Codificación del XML de salida.</p>
<p>Si no se indica este valor se intenta auto-detectar a partir del XML
de entrada (si los datos a firmar son un XML).</p></td>
</tr>
<tr class="odd">
<td>contentTypeOid</td>
<td>[OID o URN de tipo OID]</td>
<td>Identificador del tipo de dato firmado. Esta propiedad es
complementaria (que no excluyente) al parámetro mimeType.</td>
</tr>
<tr class="even">
<td rowspan="4">canonicalizationAlgorithm</td>
<td><a
href="http://www.w3.org/TR/2001/REC-xml-c14n-20010315">http://www.w3.org/TR/2001/REC-xml-c14n-20010315</a></td>
<td>Se firma el XML con canonizado XML 1.0 inclusivo (valor por
defecto).</td>
</tr>
<tr class="odd">
<td>http://www.w3.org/TR/2001/REC-xml-c14n-20010315#WithComments</td>
<td>Se firma el XML con canonizado XML 1.0 inclusivo con
comentarios.</td>
</tr>
<tr class="even">
<td><a
href="http://www.w3.org/2001/10/xml-exc-c14n">http://www.w3.org/2001/10/xml-exc-c14n#</a></td>
<td>Se firma el XML con canonizado XML 1.0 exclusivo.</td>
</tr>
<tr class="odd">
<td>http://www.w3.org/2001/10/xml-exc-c14n#WithComments</td>
<td>Se firma el XML con canonizado XML 1.0 exclusivo con
comentarios.</td>
</tr>
<tr class="even">
<td rowspan="2">xadesNamespace</td>
<td>http://uri.etsi.org/01903/v1.3.2#</td>
<td>Establece el espacio de nombres correspondiente a la versión 1.3.2
de XAdES. Este es el valor por defecto.</td>
</tr>
<tr class="odd">
<td>http://uri.etsi.org/01903/v1.2.2#</td>
<td>Establece el espacio de nombres correspondiente a la versión 1.2.2
de XAdES. Si se establece esta propiedad es posible que se necesite
establecer también el parámetro signedPropertiesTypeUrl para evitar
incoherencias en la versión de XAdES. El uso de estas propiedades no
garantiza que la firma generada sea acorde a esta versión de XAdES.</td>
</tr>
<tr class="even">
<td rowspan="3">signedPropertiesTypeUrl</td>
<td>http://uri.etsi.org/01903#SignedProperties</td>
<td>Establece la URL de definición del tipo de las propiedades firmadas
(<em>Signed Properties</em>) de XAdES. Este es el valor por
defecto.</td>
</tr>
<tr class="odd">
<td>http://uri.etsi.org/01903/1.3.2#SignedProperties</td>
<td>Establece la URL de definición del tipo de las propiedades firmadas
(<em>Signed Properties</em>) de XAdES v1.3.2.</td>
</tr>
<tr class="even">
<td>http://uri.etsi.org/01903/1.2.2#SignedProperties</td>
<td>Establece la URL de definición del tipo de las propiedades firmadas
(<em>Signed Properties</em>) de XAdES v1.2.2. Si se establece esta
propiedad es posible que se necesite establecer también el parámetro
xadesNamespace para evitar incoherencias en la versión de XAdES. El uso
de estas propiedades no garantiza que la firma generada sea acorde a
esta versión de XAdES.</td>
</tr>
<tr class="odd">
<td rowspan="2">ignoreStyleSheets</td>
<td>true</td>
<td>Si se firma un XML con hojas de estilo, ignora éstas dejándolas sin
firmar.</td>
</tr>
<tr class="even">
<td>false</td>
<td>Si se firma un XML con hojas de estilo, firma también las hojas de
estilo (valor por defecto, consultar notas adicionales sobre firma de
hojas de estilo).</td>
</tr>
<tr class="odd">
<td rowspan="2">avoidBase64Transforms</td>
<td>true</td>
<td>No declara transformaciones Base64 incluso si son necesarias.</td>
</tr>
<tr class="even">
<td>false</td>
<td>Declara las transformaciones Base64 cuando se han codificado
internamente los datos a firmar en Base64 (valor por defecto).</td>
</tr>
<tr class="odd">
<td rowspan="2">headless</td>
<td>true</td>
<td>Evita que se muestren diálogos gráficos adicionales al usuario
(como, por ejemplo, para la <em>dereferenciación</em> de hojas de estilo
enlazadas con rutas relativas).</td>
</tr>
<tr class="even">
<td>false</td>
<td>Permite que se muestren diálogos gráficos adicionales al
usuario.</td>
</tr>
<tr class="odd">
<td>xmlTransforms</td>
<td>[Número]</td>
<td>Número de transformaciones a aplicar al contenido firmado. Debe
indicarse posteriormente igual número de parámetros xmlTransformnType,
sustituyendo <em>n</em> por un ordinal consecutivo, comenzando en 0 (ver
notas adicionales sobre indicación de transformaciones
adicionales).</td>
</tr>
<tr class="even">
<td rowspan="3">xmlTransform<em><strong>n</strong></em>Type</td>
<td>http://www.w3.org/2000/09/xmldsig#base64</td>
<td>Indica que los datos que se proporcionan para firmar ya están
codificados en Base64 y se debe declarar esta transformación adicional
para que se decodifiquen antes de firmarlos. Esta transformación Base64
es adicional a la transformación necesaria para pasar los datos a través
de los métodos de firma del cliente.</td>
</tr>
<tr class="odd">
<td>http://www.w3.org/TR/1999/REC-xpath-19991116</td>
<td>El contenido se debe procesar mediante esta transformación XPATH
antes de ser firmado. Únicamente es aplicable cuando se firma contenido
XML.</td>
</tr>
<tr class="even">
<td>http://www.w3.org/2002/06/xmldsig-filter2</td>
<td>El contenido se debe procesar mediante esta transformación XPATH2
antes de ser firmado. Únicamente es aplicable cuando se firma contenido
XML.</td>
</tr>
<tr class="odd">
<td>xmlTransform<em><strong>n</strong></em>Subtype</td>
<td>[Texto]</td>
<td>Subtipo de la transformación <em><strong>n</strong></em>. Los
valores aceptados y sus funcionalidades dependen del valor indicado en
xmlTransformnType.</td>
</tr>
<tr class="even">
<td>xmlTransform<em><strong>n</strong></em>Body</td>
<td>[Texto]</td>
<td>Cuerpo de la transformación <em><strong>n</strong></em>. Los valores
aceptados y sus funcionalidades dependen de los valores indicados en
xmlTransform<em><strong>n</strong></em>Type y en
xmlTransform<em><strong>n</strong></em>Subtype.</td>
</tr>
<tr class="odd">
<td>nodeToSign</td>
<td>[Texto]</td>
<td>Identificador del nodo (establecido mediante el atributo “Id”) que
se desea firmar dentro de un XML.</td>
</tr>
<tr class="even">
<td>commitmentTypeIndications</td>
<td>[Entero]</td>
<td>Indica el número de CommitmentTypeIndications que se van a declarar.
Estos son los motivos que se declaran para la firma. Los valores
concretos se especifican con
commitmentTypeIndication<em><strong>n</strong></em>Identifier y
commitmentTypeIndication<em><strong>n</strong></em>Description, donde
‘<em><strong>n</strong></em>’ va desde 0 hasta el valor menos 1 indicado
en esta propiedad.</td>
</tr>
<tr class="odd">
<td
rowspan="6">commitmentTypeIndication<em><strong>n</strong></em>Identifier</td>
<td>1</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> es “<strong>Prueba de origen</strong>”.</td>
</tr>
<tr class="even">
<td>2</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> es “<strong>Prueba de
recepción</strong>”.</td>
</tr>
<tr class="odd">
<td>3</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> es “<strong>Prueba de
entrega</strong>”.</td>
</tr>
<tr class="even">
<td>4</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> es “<strong>Prueba de envío</strong>”.</td>
</tr>
<tr class="odd">
<td>5</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> es “<strong>Prueba de
aprobación</strong>”.</td>
</tr>
<tr class="even">
<td>6</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> es “<strong>Prueba de
creación</strong>”.</td>
</tr>
<tr class="odd">
<td>commitmentTypeIndication<em><strong>n</strong></em>Description</td>
<td>[Texto]</td>
<td>Establece la descripción del CommitmentTypeIndications número
<em><strong>n</strong></em>.. Este atributo es opcional.</td>
</tr>
<tr class="even">
<td>commitmentTypeIndication<em><strong>n</strong></em>DocumentationReferences</td>
<td>[Texto]</td>
<td><p>Lista de URL separadas por el carácter '|' que se aportan como
referencias documentales del CommitmentTypeIndication número
<em><strong>n</strong></em> (atributo opcional).</p>
<p>Las URL de la lista no pueden contener el carácter '|' (ya que este
se usa como separador).</p></td>
</tr>
<tr class="odd">
<td>commitmentTypeIndication<em><strong>n</strong></em>CommitmentTypeQualifiers</td>
<td>[Texto]</td>
<td>Lista de indicadores textuales separados por el carácter '|' que se
aportan como calificadores adicionales del CommitmentTypeIndication
número n (atributo opcional). Normalmente son OID.<br />
Los elementos de la lista no pueden contener el carácter '|' (ya que
este se usa como separador).</td>
</tr>
<tr class="even">
<td rowspan="3">allowSignLTSignature</td>
<td>true</td>
<td>Se permite la cofirma/contrafirma de firmas de archivo longevo, a
pesar de que estas pueden no ser válidas posteriormente.</td>
</tr>
<tr class="odd">
<td>false (o cualquier otro valor)</td>
<td>No se permite la cofirma/contrafirma de firmas de archivo
longevo.</td>
</tr>
<tr class="even">
<td>Sin indicar</td>
<td>Se consultará al usuario en caso de intentar
confirmarse/contrafirmarse una firma de archivo longevo.</td>
</tr>
</tbody>
</table>

#### Contrafirma

<table>
<colgroup>
<col style="width: 38%" />
<col style="width: 12%" />
<col style="width: 49%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Nombre del parámetro</strong></th>
<th><strong>Valores posibles</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td rowspan="2">addKeyInfoKeyValue</td>
<td>true</td>
<td>Incluye el nodo KeyValue dentro de KeyInfo de XAdES (comportamiento
por defecto).</td>
</tr>
<tr class="even">
<td>false</td>
<td>No incluye el nodo KeyValue dentro de KeyInfo de XAdES.</td>
</tr>
<tr class="odd">
<td rowspan="2">addKeyInfoKeyName</td>
<td>true</td>
<td>Incluye el nodo KeyName dentro de KeyInfo de XAdES.</td>
</tr>
<tr class="even">
<td>false</td>
<td>No incluye el nodo KeyName dentro de KeyInfo de XAdES
(comportamiento por defecto).</td>
</tr>
<tr class="odd">
<td>policyIdentifier</td>
<td>[URL]</td>
<td>Identificador de la política de firma (normalmente una URL hacia la
política en formato XML procesable), necesario para generar firmas
XAdES-EPES.</td>
</tr>
<tr class="even">
<td>policyIdentifierHash</td>
<td>[Texto Base64]</td>
<td>Huella digital de la política de firma. Es obligatorio indicar esta
propiedad si el valor indicado en policyIdentifier no es universalmente
accesible. Si se da valor a esta propiedad es obligatorio también dar
valor al parámetro policyIdentifierHashAlgorithm.</td>
</tr>
<tr class="odd">
<td rowspan="4">policyIdentifierHashAlgorithm</td>
<td>SHA1</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA1.</td>
</tr>
<tr class="even">
<td>SHA-256</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA-256.</td>
</tr>
<tr class="odd">
<td>SHA-384</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA-384.</td>
</tr>
<tr class="even">
<td>SHA-512</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA-512.</td>
</tr>
<tr class="odd">
<td>policyQualifier</td>
<td>[URL hacia documento]</td>
<td><p>URL (universalmente accesible) hacia el documento (normalmente
PDF) que contiene una descripción textual de la política de firma.</p>
<p>Esta propiedad es opcional incluso si se desea generar firmas
XAdES-EPES.</p></td>
</tr>
<tr class="even">
<td>policyDescription</td>
<td>[Texto]</td>
<td><p>Descripción textual de la política de firma. En el caso de que se
firme un XML, la codificación del texto usado debe adecuarse al XML
firmado.</p>
<p>Esta propiedad es opcional incluso si se desea generar firmas
XAdES-EPES.</p></td>
</tr>
<tr class="odd">
<td>signerClaimedRoles</td>
<td>[Texto]</td>
<td><p>Agrega a la firma campos con los cargos atribuidos al firmante.
Deben separarse los cargos con el carácter “|” (y este no puede estar en
el propio texto de ningún cargo).</p>
<p>En el caso de que se firme un XML, la codificación del texto usado
debe adecuarse al XML firmado.</p></td>
</tr>
<tr class="even">
<td>signatureProductionCity</td>
<td>[Texto]</td>
<td><p>Agrega a la firma un campo con la ciudad en la que se realiza la
firma.</p>
<p>En el caso de que se firme un XML, la codificación del texto usado
debe adecuarse al XML firmado.</p></td>
</tr>
<tr class="odd">
<td>signatureProductionProvince</td>
<td>[Texto]</td>
<td><p>Agrega a la firma un campo con la provincia en la que se realiza
la firma.</p>
<p>En el caso de que se firme un XML, la codificación del texto usado
debe adecuarse al XML firmado.</p></td>
</tr>
<tr class="even">
<td>signatureProductionPostalCode</td>
<td>[Texto]</td>
<td><p>Agrega a la firma un campo con el código postal en donde se
realiza la firma.</p>
<p>En el caso de que se firme un XML, la codificación del texto usado
debe adecuarse al XML firmado.</p></td>
</tr>
<tr class="odd">
<td>signatureProductionCountry</td>
<td>[Texto]</td>
<td><p>Agrega a la firma un campo con el país en el que se realiza la
firma.</p>
<p>En el caso de que se firme un XML, la codificación del texto usado
debe adecuarse al XML contrafirmado.</p></td>
</tr>
<tr class="even">
<td>encoding</td>
<td>[Texto]</td>
<td>Fuerza una codificación para la firma resultante. Un uso incorrecto
de esta propiedad puede provocar la generación de una firma
inválida.</td>
</tr>
<tr class="odd">
<td>commitmentTypeIndications</td>
<td>[Entero]</td>
<td>Indica el número de CommitmentTypeIndications que se van a declarar.
Estos son los motivos que se declaran para la firma. Los valores
concretos se especifican con commitmentTypeIndicationnIdentifier y
commitmentTypeIndicationnDescription, donde ‘n’ va desde 0 hasta el
valor menos 1 indicado en esta propiedad.</td>
</tr>
<tr class="even">
<td
rowspan="6">commitmentTypeIndication<em><strong>n</strong></em>Identifier</td>
<td>1</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> es “<strong>Prueba de origen</strong>”.</td>
</tr>
<tr class="odd">
<td>2</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> es “<strong>Prueba de
recepción</strong>”.</td>
</tr>
<tr class="even">
<td>3</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> es “<strong>Prueba de
entrega</strong>”.</td>
</tr>
<tr class="odd">
<td>4</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> es “<strong>Prueba de envío</strong>”.</td>
</tr>
<tr class="even">
<td>5</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> es “<strong>Prueba de
aprobación</strong>”.</td>
</tr>
<tr class="odd">
<td>6</td>
<td>Establece que el CommitmentTypeIndications número
<em><strong>n</strong></em> es “<strong>Prueba de
creación</strong>”.</td>
</tr>
<tr class="even">
<td>commitmentTypeIndication<em><strong>n</strong></em>Description</td>
<td>[Texto]</td>
<td>Establece la descripción del CommitmentTypeIndications número
<em><strong>n</strong></em>. Este atributo es opcional.</td>
</tr>
<tr class="odd">
<td>commitmentTypeIndication<em><strong>n</strong></em>DocumentationReferences</td>
<td>[Texto]</td>
<td><p>Lista de URL separadas por el carácter '|' que se aportan como
referencias documentales del CommitmentTypeIndication número
<em><strong>n</strong></em> (atributo opcional).</p>
<p>Las URL de la lista no pueden contener el carácter '|' (ya que este
se usa como separador).</p></td>
</tr>
<tr class="even">
<td>commitmentTypeIndication<em><strong>n</strong></em>CommitmentTypeQualifiers</td>
<td>[Texto]</td>
<td>Lista de indicadores textuales separados por el carácter '|' que se
aportan como calificadores adicionales del CommitmentTypeIndication
número n (atributo opcional). Normalmente son OID.<br />
Los elementos de la lista no pueden contener el carácter '|' (ya que
este se usa como separador).</td>
</tr>
<tr class="odd">
<td rowspan="3">allowSignLTSignature</td>
<td>true</td>
<td>Se permite la cofirma/contrafirma de firmas de archivo longevo, a
pesar de que estas no serán válidas posteriormente.</td>
</tr>
<tr class="even">
<td>false (o cualquier otro valor)</td>
<td>No se permite la cofirma/contrafirma de firmas de archivo
longevo.</td>
</tr>
<tr class="odd">
<td>Sin indicar</td>
<td>Se consultará al usuario en caso de intentar
confirmarse/contrafirmarse una firma de archivo longevo.</td>
</tr>
</tbody>
</table>

## Configuración de firmas PAdES

El Cliente @firma permite generar firmas PAdES acordes a las partes 2 y
3 del estándar ETSI TS 102 778 V1.2.1.

Los perfiles de firma soportados son los descritos en el mencionado
estándar:

- PAdES-Básico

  - Las firmas PAdES en las que se declara el subfiltro
    “adbe.pkcs7.detached”.

- PAdES-BES

  - Las firmas PAdES en las que se declara el subfiltro
    “ETSI.CAdES.detached” son PAdES-BES. Estas son las firmas por
    defecto.

- PAdES-EPES

  - Las firmas PAdES en las que se configura política de firma son
    PAdES-EPES.

Hay que tener en cuenta que algunas de las firmas PAdES generadas por el
Cliente @firma también pueden considerarse de tipo B-Level. Sin embargo,
no se incluye un modo de operación que permita asegurar que las firmas
generadas sean acordes a este perfil.

Una salvedad en la realización de firmas PAdES con respecto al estándar,
es que no se soporta la firma de ficheros adjuntos o empotrados en los
documentos PDF.

### Algoritmos de firma

Las firmas PAdES aceptan los siguientes algoritmos de firma:

- SHA512withRSA

- SHA384withRSA

- SHA256withRSA

- SHA1withRSA (No recomendado)

El estándar PAdES recomienda no usar el algoritmo SHA1withRSA por no ser
el más seguro.

Si los certificados del usuario se encuentran en tarjeta inteligente,
asegúrese de disponer de la última versión de su controlador para
garantizar la compatibilidad con estos algoritmos de firma. En caso de
que, aún así, no pueda utilizar este algoritmo con su tarjeta
inteligente, consulte la información de compatibilidad de su tarjeta y/o
pruebe con otro algoritmo.

### Operaciones no soportadas y notas de interés

- Las firmas PAdES no admiten contrafirmas.

- Una cofirma PAdES consiste en la adición de una firma adicional al
  documento PDF, sin que se establezca ninguna relación de
  interdependencia con las firmas existentes.

  - Cofirmar un documento PDF es completamente equivalente a firmar un
    documento PDF ya firmado.

- Versiones antiguas de Adobe Acrobat/Reader no soportan múltiples
  firmas cuando hay firmas PAdES-BES.

- El formato PAdES sólo puede utilizarse sobre documentos PDF.

- No se firman los posibles adjuntos o empotrados que pudiese contener
  el documento PDF.

### Creación de una firma visible

El Cliente @firma permite la creación de firmas visibles dentro de un
documento PDF, que lo son tanto en pantalla (por ejemplo, usando Adobe
Reader) como en papel una vez impreso el documento.

<img src="media/image4.png" style="width:6.1375in;height:4.36875in" />

Para ello debemos indicar mediante parámetros adicionales la página o
las páginas del documento en donde situar la visualización de la firma y
las coordenadas con la posición en la que debe mostrarse. Sólo es
posible establecer una posición para la firma visible, por lo que la
posición será la misma en todas las páginas en las que se muestre la
firma.

Las coordenadas de la visualización se indican partiendo de la esquina
inferior izquierda, según el siguiente diagrama:

<img src="media/image5.emf" style="width:6.22153in;height:2.66806in" />

Las coordenadas del campo de firma y la página en la que se desea
insertar se establecen usando los parámetros adicionales, por ejemplo:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>signaturePositionOnPageLowerLeftX = 100</p>
<p>signaturePositionOnPageLowerLeftY = 100</p>
<p>signaturePositionOnPageUpperRightX = 200</p>
<p>signaturePositionOnPageUpperRightY = 200</p>
<p>signaturePages = 1,5,10--1</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Los documentos PDF comienzan su numeración de páginas desde uno (1). Si
se indica un valor de página negativo, se empezará a contar desde la
última página del documento hacia atrás. Por ejemplo, si se configura en
el número de página el valor -1, la firma se insertará en la última
página del documento. Si se configura el valor -2, se insertará en la
penúltima página. Una firma se puede mostrar en más de una página de un
documento. Para ello se permite indicar un listado de páginas y/o rangos
de páginas en las que debe mostrarse. También se puede indicar
directamente que se muestre en todas las páginas del documento o en una
nueva página al final de este.

La forma de indicar la página o páginas donde firmar será posible
indicarla a través del parámetro signaturePages. Tal y como se explica
en el párrafo anterior, esté parámetro se puede configurar para indicar
la firma visible en una o varias páginas:

- all:

  - Para indicar que la firma visible aparezca en todas las páginas del
    documento, se le deberá de dar este valor al parámetro
    signaturePages.

- append:

  - Si la firma visible debe de aparecer en una nueva página en blanco
    añadida al final del documento, se le deberá de dar este valor al
    parámetro signaturePages.

- Página o listado de páginas:

  - Si se desea indicar una página o varias páginas donde estampar la
    firma visible, es posible indicando página a página con una
    separación de comas (1,4,7: Se estampa en las páginas 1, 4 y 7) o
    indicando un rango de páginas a través de un guión (1-8: Se estampa
    en las páginas desde la 1 hasta la 8). Tal y como se explica en el
    párrafo anterior, se permite indicar las páginas con un valor
    negativo, donde se comenzará desde el final (1,-1: Se estampará en
    la primera y última página). También es posible combinar páginas
    individuales con rangos de páginas, como, por ejemplo:

    - 3-6, 8, 10: Indica que se estampará en las páginas desde la 3 a la
      6 y también en la 8 y 10.

Dentro del recuadro marcado por las coordenadas indicadas, es posible
mostrar distintos elementos:

<img src="media/image6.png" style="width:2.09524in;height:2.11111in" />

- Una imagen:

  - En este caso debe indicarse qué imagen usar aportando el binario en
    formato JPEG codificado en Base64.

    - La imagen de firma se configura a través del parámetro adicional
      signatureRubricImage.

  - La imagen se adapta al recuadro marcado por las coordenadas para
    ocupar el mayor espacio posible sin deformarse, por lo que se
    debería configurarse un tamaño de firma adecuado para que la imagen
    se ajuste al mismo sin dejar espacio vacío.

  - **NOTA**: No se soportan imágenes con transparencias. Incluso si la
    imagen no incluye transparencias, internamente se convertirá a JPEG
    si no lo era, por lo que se recomienda que se proporcione
    directamente la image en JPEG para garantizar que la visualización
    será la deseada.

<img src="media/image7.png" style="width:2.06977in;height:2.06977in" />

- Texto (que puede combinarse con una imagen)

  - Es necesario indicar no solo el texto a sobreimprimir en el cuadro
    visible, sino también indicaciones sobre su formato (tipo de letra,
    tamaño, color, etc.).

  - El texto introduce de forma automática los retornos de carro
    necesarios para adaptarse al recuadro.

  - El texto aparece siempre sobre la imagen indicada, si se indicó
    alguna.

  - El texto puede incluir una serie de patrones que serán sustituidos
    en el momento de la firma:

    - **\$\$SUBJECTCN\$\$** Nombre común (CN, Common Name) dentro del
      X.500 Principal del titular del certificado de firma. Salvo que se
      indique lo contrario, los identificadores de usuario encontrados
      en esta propiedad se procesarán para ocultar parte de sus
      caracteres.

    - **\$\$ISSUERCN\$\$** Nombre común (CN, Common Name) dentro del
      X.500 Principal del emisor del certificado de firma.

    - **\$\$CERTSERIAL\$\$** Número de serie del certificado de firma.

    - **\$\$SIGNDATE=*PATRÓN*\$\$** Fecha de la firma, donde *PATRÓN*
      debe indicar el formato en el que debe mostrarse la fecha,
      siguiendo el esquema definido por Oracle para la clase
      SimpleDateFormat. Así, por ejemplo, el texto "*Firmado por
      \$\$SUBJECTCN\$\$ el día \$\$SIGNDATE=dd/MM/yyyy\$\$.*" resultará
      finalmente en el PDF como "*Firmado por Tomás García-Merás el día
      04/01/2016.*" suponiendo que el CN del titular del certificado de
      firma es *Tomás García-Merás* y que la firma se realiza el
      *04/01/2016*.

    - **\$\$GIVENNAME\$\$** Nombre declarado del titular del
      certificado. Este valor podría no aparecer en el certificado, en
      cuyo caso, el patrón se sustituirá por cadena vacía.

    - **\$\$SURNAME\$\$** Apellidos declarados del titular del
      certificado. Este valor podría no aparecer en el certificado, en
      cuyo caso, el patrón se sustituirá por cadena vacía.

    - **\$\$ORGANIZATION\$\$** Organización declarada del titular en el
      certificado. Este valor podría no aparecer en el certificado, en
      cuyo caso, el patrón se sustituirá por cadena vacía.

    - **\$\$REASON\$\$** Razón por la que se firma el PDF. Este valor
      podría no aparecer en el certificado, en cuyo caso, el patrón se
      sustituirá por cadena vacía.

    - **\$\$LOCATION\$\$** Ciudad en la que se firma el PDF. Este valor
      podría no aparecer en el certificado, en cuyo caso, el patrón se
      sustituirá por cadena vacía.

    - **\$\$CONTACT\$\$** Información de contacto del firmante del PDF.
      Este valor podría no aparecer en el certificado, en cuyo caso, el
      patrón se sustituirá por cadena vacía.

Las propiedades para configurar la visualización de un texto de la firma
se listan a continuación:

- layer2Text

  - Texto que mostrar en la firma visible.

- layer2FontFamily

  - Tipo de letra a usar en el texto de la firma visible.

- layer2FontSize

  - Tamaño de letra a usar en el texto de la firma visible.

- layer2FontStyle

  - Estilo del tipo de letra a usar en el texto de la firma visible.
    Cada estilo se identifica mediante un valor numérico y es posible
    combinar estilos aplicando la operación lógica *o* sobre los valores
    numéricos de cada uno de ellos.

- layer2FontColor

  - Color del texto de la firma visible.

- obfuscateCertText

  - Indica si deben ofuscarse o no los identificadores de usuario (como
    el DNI o NIE) localizados automáticamente en el texto visible del
    PDF. Por defecto, se ofuscarán.

- signatureRotation

  - Número de grados que rotar el texto y la imagen del campo de firma
    en sentido horario.

- includeQuestionMark

  - Indica si debe permitirse al lector de PDF mostrar junto a la firma
    una marca que índique el resultado obtenido al validarla. La
    apariencia de esta marca depende completamente del lector de PDF
    utilizado y es este el que decide si se muestra. Por ejemplo, la
    marca podría no mostrarse cuando se definiese una imagen de fondo en
    la firma.

<img src="media/image8.png" style="width:4.15833in;height:1.49945in" />

Consulte el apartado <u>8.3.8 Parámetros adicionales</u> para saber más
sobre los valores que se pueden asignar a las propiedades anteriores.

#### Configuración de la firma visible por usuario

Existe la posibilidad de que la configuración de la firma visible sea
realizada por el usuario, y no por la aplicación integradora. De este
modo, es el usuario quien decide el área donde mostrar la firma y su
aspecto.

La aplicación podrá configurar que sea el usuario el que seleccione el
área del documento en el que desea insertar la firma visible PDF y si es
obligatorio o no que seleccione un área. También podrá configurar si
quiere que el usuario seleccione el aspecto de la firma (texto, imagen,
fuente, rotación, etc.) o que se use el aspecto por defecto.

Para la configuración de la visible por parte del usuario se podrán
utilizar los siguientes parámetros adicionales:

- visibleSignature

  - Permite configurar si se desea que el usuario seleccione el área de
    una firma visible PDF y si es obligatorio o no el realizar una firma
    visible.

- visibleAppearance

  - Permite configurar que sea el usuario el que seleccione el aspecto
    de una firma visible PDF. Esta propiedad sólo tiene efecto cuando
    también se indica el parámetro visibleSignature y siempre que el
    usuario termine seleccionado el área de firma.

Consulte el apartado <u>8.3.8 Parámetros adicionales</u> para saber más
sobre estos parámetros de configuración.

Esta funcionalidad únicamente está disponible en AutoFirma. Los clientes
móviles siempre usarán la configuración de firma visible proporcionada
por la aplicación y no darán la posibilidad de configurarla al usuario.

### Inserción de una imagen en un documento PDF antes de ser firmado

El Cliente @firma permite, principalmente como ayuda para la inserción
de Códigos Seguros de Verificación (CSV), insertar una imagen en un
documento PDF justo antes de firmarlo.

Para agregar una imagen debemos configurar una página y una zona dentro
de esta para insertarla, usando para ello el mismo sistema de
coordenadas descrito en el apartado <u>8.3.3 Creación de una firma
visible</u>, es decir, a partir de la esquina inferior izquierda. La
imagen debe proporcionarse en formato JPEG codificado en Base64.

Para indicar la página, podemos usar su número (empezando a contar desde
uno como primera página), usar -1 para referirnos a la última página del
documento o 0 (cero) para insertar la imagen en todas las páginas.

Debe tenerse en cuenta que el agregar imágenes al PDF puede invalidar
firmas previas que tuviese el documento. Asegúrese de no utilizar esta
funcionalidad cuando el documento ya contenga firmas.

Es importante recalcar también que la imagen se deforma para adaptarse
al recuadro marcado por las coordenadas, siendo útil para evitar este
efecto que ambos tengan la misma relación de aspecto.

Igualmente, no se proporcionan funcionalidades de rotado, por lo que si
se quiere insertar una imagen de lado (por ejemplo, en el margen de la
página, esta debe venir rotada en origen.

Los parámetros adicionales para la inserción de imágenes son:

- image

  - Imagen que se desea insertar en el PDF.

- imagePage

  - Página donde desea insertarse la imagen.

- imagePositionOnPageLowerLeftX

  - Coordenada horizontal inferior izquierda de la posición de la
    imagen.

- imagePositionOnPageLowerLeftY

  - Coordenada vertical inferior izquierda de la posición de la imagen.

- imagePositionOnPageUpperRightX

  - Coordenada horizontal superior derecha de la posición de la imagen.

- imagePositionOnPageUpperRightY

  - Coordenada vertical superior derecha de la posición de la imagen.

Consulte el apartado <u>8.3.8 Parámetros adicionales</u> para obtener
más información sobre los posibles valores que pueden adoptar estos
parámetros.

### Firma de documentos PDF cifrados o protegidos con contraseña

Si bien es posible firmar documentos PDF cifrados o protegidos con
contraseña, deben tenerse en cuenta las siguientes limitaciones:

- No se pueden firmar como parte de un proceso de firma masiva
  documentos PDF cifrados.

- No se soporta la firma de PDF cifrados con certificados o con
  algoritmo AES256.

- Puede que no sea posible, en todos los casos, validar u obtener
  justificantes de validación de documentos PDF cifrados o protegidos
  por contraseña usando la plataforma de validación VALIDE del Gobierno
  de España.

  - <https://valide.redsara.es/valide/>

### Documentos certificados

Las firmas de un PDF pueden ser catalogadas como firmas de aprobación
(por defecto) o firmas certificadas.

Una firma de aprobación o de formulario se realiza sobre un campo de
firma de formulario del documento (preexistente o creado automáticamente
en el momento de la firma). Un documento puede contener tantas firmas de
aprobación como necesite. Esta es la opción común de firma.

Una firma certificada o de documento se aplica sobre un campo de firma
identificado como de documento (preexistente o creado automáticamente en
el momento de la firma). Un documento puede contener un único campo de
este tipo y por tanto una única firma certificada. En caso de agregarse
una firma certificada al documento, esta debe ser la primera que se
agregue. Si hubiese alguna firma previa el resultado no sería válido.

Independientemente de sus nombres, ambos tipos de firma aplican al
conjunto de datos de todo el documento, nunca sólo a los datos de un
formulario. Sólo cambia la designación del campo en el que se almacenan.

Una firma certificada restringe modificaciones posteriores sobre el
documento. Las modificaciones permitidas vendrán determinadas por el
nivel de certificación aplicado a la firma. El Cliente @firma permite
configurar el nivel de certificación de una firma por medio del
parámetro certificationLevel. Los tipos de firma que puede crear son:

- Firma sin certificar.

  - Esta sería una firma de aprobación.

  - Este es el tipo de firma generada por defecto por el Cliente y se
    configura con el valor: 0

- Firma certificada de autor.

  - Tras este tipo de firma certificada, no se permite ningún cambio
    posterior en el documento (no se pueden agregar firmas, ni rellenar
    formularios).

  - Se configura con el valor: 1

- Firma certificada de autor para formularios.

  - Tras este tipo de firma certificada, sólo se permite el relleno de
    los campos de formulario (no se pueden agregar firmas).

  - Se configura con el valor: 2

- Firma certificada común.

  - Tras este tipo de firma certificada, se permite el relleno de los
    campos de formulario y la creación de firmas de aprobación.

  - Se configura con el valor: 3

### Comprobación de *PDF Shadow Attack*

Existe una vulnerabilidad en el formato PDF que hace posible que una
revisión de un documento altere la presentación de un elemento de una
revisión anterior, incluso si está firmada. Esto quiere decir que se
podría modificar un PDF firmado de tal forma que parezca a simple vista
que se firmó algo distinto a lo que realmente se firmó. Alterar de esta
forma el documento firmado es lo que se conoce como *PDF Shadow Attack*
y, aunque el propio formato proporciona los medios para comprobar cuál
es el contenido que realmente se firmó, un firmante posterior deberá
tener cuidado de no firmar un documento alterado creyendo que alguien
firmó anteriormente ese mismo contenido.

AutoFirma 1.8 y superiores incorpora la comprobación de *PDF Shadow
Attack* en su operativa de validación de firmas. Primeramente, para que
se validen las firmas que se van a multifirmar se debe habilitar la
validación de firmas previas mediante el parámetro adicional
checkSignatures, tal como se describe en el apartado <u>7.5 Validación
de firmas previas</u>.

Para configurar la comprobación de *PDF Shadow Attack* se proporciona la
propiedad allowShadowAttack, de tal forma que al validar una firma PDF
pueden ocurrir los siguientes casos según su valor:

- Si se establece a true, se omite la validación del *PDF Shadow Attack*
  durante la validación de las firmas previas.

- Si se establece a false (o cualquier otro valor) y si se sospecha que
  el PDF puede haber sido modificado, se bloquea la firma dando por
  hecho que el PDF ha sido modificado.

- Si no se establece ningún valor y se sospecha que el PDF puede haber
  sido modificado, se muestra al usuario un diálogo solicitándole que
  compruebe el PDF y confirme que desea firmarlo a pesar de la sospecha
  de que haya sido modificado.

Ya que la comprobación del *PDF Shadow Attack* es computacionalmente
costosa y no garantiza que se haya una modificado maliciosamente el
documento, sólo se aplicará la comprobación sobre n número de páginas
determinado. El número de páginas por defecto es de 10, pero la
aplicación puede configurar este número mediante la propiedad
pagesToCheckShadowAttack, que puede adoptar los siguientes valores:

- Entero positivo: Número de páginas que se comprobarán.

- Entero negativo o 0: No se comprobarán modificaciones de tipo PDF
  Shadow Attack.

- all: Todas las páginas.

En el caso de la firma trifásica, la carga de la comprobación del PDF
recae en el propio servidor, así que el servicio puede limitar a través
de su configuración el número de páginas máximo que se deberán
comprobar. Consulte el apartado <u>5.3.2.1 Configuración del servicio
trifásico</u> para saber más de la configuración del servicio.

La comprobación del *PDF Shadow Attack* también detectaría sin
diferenciarlo cualquier cambio en los valores de un formulario
realizados después de firmar. Si el integrador o el usuario aceptasen
que se permiten cambios en los valores de los formularios después de
firmar, estará aceptando que el documento puede cambiar, por lo que se
desactivará la comprobación de *PDF Shadow Attack*.

### Parámetros adicionales

A continuación, se listan las propiedades adicionales que pueden
configurarse en las firmas en formato PAdES con el Cliente @firma.

Es posible que el uso de parámetros no contemplados en las siguientes
tablas provoque otros cambios de funcionamiento. No obstante, **no se
dará soporte** al aplicativo si se usan parámetros no documentados,
asumiendo el integrador todo el riesgo y responsabilidad derivados del
uso de parámetros o valores distintos de los aquí descritos.

<table style="width:100%;">
<colgroup>
<col style="width: 36%" />
<col style="width: 14%" />
<col style="width: 49%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Nombre del parámetro</strong></th>
<th><strong>Valores posibles</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td rowspan="2">includeOnlySignningCertificate</td>
<td>true</td>
<td>Indica que debe incluirse en la firma únicamente el certificado del
firmante.</td>
</tr>
<tr class="even">
<td>false</td>
<td>Indica que debe incluirse en la firma toda la cadena de
certificación del certificado firmante. Valor por defecto.</td>
</tr>
<tr class="odd">
<td rowspan="2">alwaysCreateRevision</td>
<td>true</td>
<td>Siempre creará una revisión al firmar. Requiere que el documento
cumpla la especificación PDF 1.7 (ISO 32000-1:2008)</td>
</tr>
<tr class="even">
<td>false</td>
<td>No creará revisión en la primera firma y sí en las siguientes.</td>
</tr>
<tr class="odd">
<td>image</td>
<td>[Texto Base64]</td>
<td>Imagen JPEG que insertar en el PDF. Esta opción sólo se puede usar
en la primera firma del documento.</td>
</tr>
<tr class="even">
<td rowspan="3">imagePage</td>
<td>[Entero positivo]</td>
<td>Insertar imagen en el número de página indicado.</td>
</tr>
<tr class="odd">
<td>0</td>
<td>Insertar en todas las páginas.</td>
</tr>
<tr class="even">
<td>-1</td>
<td>Insertar imagen en la última página.</td>
</tr>
<tr class="odd">
<td>imagePositionOnPageLowerLeftX</td>
<td>[Entero positivo]</td>
<td>Coordenada horizontal desde la esquina inferior izquierda de la
página a la esquina inferior izquierda de la imagen.</td>
</tr>
<tr class="even">
<td>imagePositionOnPageLowerLeftY</td>
<td>[Entero positivo]</td>
<td>Coordenada vertical desde la esquina inferior izquierda de la página
a la esquina inferior izquierda de la imagen.</td>
</tr>
<tr class="odd">
<td>imagePositionOnPageUpperRightX</td>
<td>[Entero positivo]</td>
<td>Coordenada horizontal desde la esquina inferior izquierda de la
página a la esquina superior derecha de la imagen.</td>
</tr>
<tr class="even">
<td>imagePositionOnPageUpperRightY</td>
<td>[Entero positivo]</td>
<td>Coordenada vertical desde la esquina inferior izquierda de la página
a la esquina superior derecha de la imagen.</td>
</tr>
<tr class="odd">
<td>attach</td>
<td>[Texto Base64]</td>
<td>Contenido a añadir como adjunto al PDF. Requiere establecer
attachFileName.</td>
</tr>
<tr class="even">
<td>attachFileName</td>
<td>[Texto]</td>
<td>Nombre del que asignar al fichero adjunto.</td>
</tr>
<tr class="odd">
<td>attachDescription</td>
<td>[Texto]</td>
<td>Descripción del documento adjunto.</td>
</tr>
<tr class="even">
<td rowspan="4">certificationLevel</td>
<td>0</td>
<td>Firma sin certificar. Esta sería una firma de aprobación. Es el
valor por defecto.</td>
</tr>
<tr class="odd">
<td>1</td>
<td>Firma certificada de autor. Tras este tipo de firma certificada, no
se permite ningún cambio posterior en el documento (no se pueden agregar
firmas, ni rellenar formularios).</td>
</tr>
<tr class="even">
<td>2</td>
<td>Firma certificada de autor para formularios. Tras este tipo de firma
certificada, sólo se permite el relleno de los campos de formulario (no
se pueden agregar firmas).</td>
</tr>
<tr class="odd">
<td>3</td>
<td>Firma certificada común. Tras este tipo de firma certificada, se
permite el relleno de los campos de formulario y la creación de firmas
de aprobación.</td>
</tr>
<tr class="even">
<td rowspan="2">compressPdf</td>
<td>true</td>
<td>Comprime el PDF firmado para que ocupe menos tamaño. Sólo se aplica
si se trata de un PDF v4 o superior. Este es el valor por defecto.</td>
</tr>
<tr class="odd">
<td>false</td>
<td>Nunca se comprime el PDF firmado.</td>
</tr>
<tr class="even">
<td rowspan="6">pdfVersion</td>
<td>2</td>
<td>Se declara que la versión del PDF de salida es 1.2.</td>
</tr>
<tr class="odd">
<td>3</td>
<td>Se declara que la versión del PDF de salida es 1.3.</td>
</tr>
<tr class="even">
<td>4</td>
<td>Se declara que la versión del PDF de salida es 1.4.</td>
</tr>
<tr class="odd">
<td>5</td>
<td>Se declara que la versión del PDF de salida es 1.5.</td>
</tr>
<tr class="even">
<td>6</td>
<td>Se declara que la versión del PDF de salida es 1.6.</td>
</tr>
<tr class="odd">
<td>7</td>
<td>Se declara que la versión del PDF de salida es 1.7.</td>
</tr>
<tr class="even">
<td>signatureSubFilter</td>
<td>[Texto]</td>
<td>Subfiltro declarado. Por defecto se utiliza el de las firmas BES
(“ETSI.CAdES.detached”). Puede usarse la cadena “adbe.pkcs7.detached”
para crear firmas basicas.</td>
</tr>
<tr class="odd">
<td>signatureField</td>
<td>[Texto]</td>
<td>Nombre del campo de firma preexistente en el que insertar la
firma.</td>
</tr>
<tr class="even">
<td>signaturePages</td>
<td>[Cadena]</td>
<td>Página o rango de páginas donde estampar la firma visible. Para más
detalles consultar el apartado “<a
href="#creación-de-una-firma-visible">8.3.3 Creación de una firma
visible</a>”.</td>
</tr>
<tr class="odd">
<td>signaturePositionOnPageLowerLeftX</td>
<td>[Entero positivo]</td>
<td>Coordenada horizontal desde la esquina inferior izquierda de la
página a la esquina inferior izquierda del campo de firma visible.</td>
</tr>
<tr class="even">
<td>signaturePositionOnPageLowerLeftY</td>
<td>[Entero positivo]</td>
<td>Coordenada vertical desde la esquina inferior izquierda de la página
a la esquina inferior izquierda del campo de firma visible.</td>
</tr>
<tr class="odd">
<td>signaturePositionOnPageUpperRightX</td>
<td>[Entero positivo]</td>
<td>Coordenada horizontal desde la esquina inferior izquierda de la
página a la esquina superior derecha del campo de firma visible.</td>
</tr>
<tr class="even">
<td>signaturePositionOnPageUpperRightY</td>
<td>[Entero positivo]</td>
<td>Coordenada vertical desde la esquina inferior izquierda de la página
a la esquina superior derecha del campo de firma visible.</td>
</tr>
<tr class="odd">
<td>signatureRubricImage</td>
<td>[Texto Base64]</td>
<td>Imagen JPEG que mostrar en el campo de firma visible.</td>
</tr>
<tr class="even">
<td>layer2Text</td>
<td>[Texto]</td>
<td>Texto que mostrar en el campo de firma visible.</td>
</tr>
<tr class="odd">
<td rowspan="4">layer2FontFamily</td>
<td>0</td>
<td>El texto de la firma visible se mostrará con fuente Courier. Este es
el valor por defecto.</td>
</tr>
<tr class="even">
<td>1</td>
<td>El texto de la firma visible se mostrará con fuente Helvética.</td>
</tr>
<tr class="odd">
<td>2</td>
<td>El texto de la firma visible se mostrará con fuente Times
Roman.</td>
</tr>
<tr class="even">
<td>3</td>
<td>El texto de la firma visible se mostrará con fuente Symbol.</td>
</tr>
<tr class="odd">
<td>layer2FontSize</td>
<td>[Entero positivo]</td>
<td>Tamaño de fuente del texto de la firma visible.</td>
</tr>
<tr class="even">
<td rowspan="5">layer2FontStyle</td>
<td>0</td>
<td>Texto de la firma visible sin estilo. Valor por defecto.</td>
</tr>
<tr class="odd">
<td>1</td>
<td>Texto de la firma visible en negrita.</td>
</tr>
<tr class="even">
<td>2</td>
<td>Texto de la firma visible en cursiva.</td>
</tr>
<tr class="odd">
<td>4</td>
<td>Texto de la firma visible subrayado.</td>
</tr>
<tr class="even">
<td>8</td>
<td>Texto de la firma visible tachado.</td>
</tr>
<tr class="odd">
<td rowspan="7">layer2FontColor</td>
<td>black</td>
<td>El texto de la firma visible será de color negro. Este es el valor
por defecto.</td>
</tr>
<tr class="even">
<td>white</td>
<td>El texto de la firma visible será de color blanco.</td>
</tr>
<tr class="odd">
<td>gray</td>
<td>El texto de la firma visible será de color gris.</td>
</tr>
<tr class="even">
<td>lightGray</td>
<td>El texto de la firma visible será de color gris claro.</td>
</tr>
<tr class="odd">
<td>darkGray</td>
<td>El texto de la firma visible será de color gris oscuro.</td>
</tr>
<tr class="even">
<td>red</td>
<td>El texto de la firma visible será de color rojo.</td>
</tr>
<tr class="odd">
<td>pink</td>
<td>El texto de la firma visible será de color rosa.</td>
</tr>
<tr class="even">
<td rowspan="2">obfuscateCertText</td>
<td>true</td>
<td>Se ofuscan los identificadores de usuario extraidos del CN o DN del
certificado y mostrados en la firma visible PDF. No se ofuscan los datos
de los certificados de seudónimo. Este es el valor por defecto.</td>
</tr>
<tr class="odd">
<td>false</td>
<td>No se ofusca la información de los certificados.</td>
</tr>
<tr class="even">
<td>obfuscationMask</td>
<td>[Texto]</td>
<td><p>Criterios de ofuscación de los identificadores de usuario en las
firmas visibles PDF. Debe mostrar el siguiente patrón:</p>
<p>caracter;longitudDigitos;posiciones;desplazamiento</p>
<p>En este patrón:</p>
<ul>
<li><p>caracter: Es el carácter que usar para ofuscar
caracteres.</p></li>
<li><p>longitudDigitos: Número mínimo de dígitos que debe tener una
cadena de texto para que se considere que debe ofuscarse.</p></li>
<li><p>posiciones: Listado de posiciones que indica qué caracteres deben
mostrarse. El listado se expresa con una sucesión de true/false
separados por comas (','), en donde true indica que el carácter debe
mostrarse y false que no.</p></li>
<li><p>desplazamiento: Indica si se admite el desplazamiento de
posiciones de la máscara para mostrar todos los caracteres indicados
(true) o si esta debe respetarse (false).</p></li>
</ul></td>
</tr>
<tr class="odd">
<td rowspan="3">visibleSignature</td>
<td>default</td>
<td>Se realizará firma visible PDF si se han proporcionado los
parámetros con el área y la página de firma. Este es el valor por
defecto.</td>
</tr>
<tr class="even">
<td>want</td>
<td><p>El usuario debe seleccionar el área de firma visible. En caso de
cancelar el proceso:</p>
<ul>
<li><p>Si la petición también incluye los parámetros de área de firma
visible (posición y página), se usarán dichos parámetros y se continuará
con el proceso de firma.</p></li>
<li><p>Si la petición no incluye los parámetros de área de firma
visible, se cancelará el proceso de firma.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>optional</td>
<td><p>El usuario podrá elegir si desea incluir o no el área de firma
visible. En caso de cancelar el proceso:</p>
<ul>
<li><p>Si la petición también incluye los parámetros de área de firma
visible (posición y página), se usarán dichos parámetros y se continuará
con el proceso de firma.</p></li>
<li><p>Si la petición no incluye los parámetros de área de firma
visible, se realizará una firma no visible.</p></li>
</ul></td>
</tr>
<tr class="even">
<td rowspan="2">visibleAppearance</td>
<td>default</td>
<td>Se aplicará el aspecto por defecto para la firma visible PDF o, si
se proporcionaron los parámetros de aspecto, el aspecto configurado.
Este es el valor por defecto.</td>
</tr>
<tr class="odd">
<td>custom</td>
<td>El usuario puede elegir el aspecto de la firma visible. En caso de
cancelar el proceso, se usará el aspecto por defecto.</td>
</tr>
<tr class="even">
<td rowspan="4">signatureRotation</td>
<td>0</td>
<td>No rota el campo de firma. Este es el valor por defecto.</td>
</tr>
<tr class="odd">
<td>90</td>
<td>Rota 90 grados en sentido horario el campo de firma.</td>
</tr>
<tr class="even">
<td>180</td>
<td>Rota 180 grados en sentido horario el campo de firma.</td>
</tr>
<tr class="odd">
<td>270</td>
<td>Rota 270 grados en sentido horario el campo de firma.</td>
</tr>
<tr class="even">
<td rowspan="2">includeQuestionMark</td>
<td>true</td>
<td>Permitirse al lector de PDF mostrar junto a la firma visible una
marca que índique el resultado obtenido al validarla. La apariencia de
esta marca depende completamente del lector de PDF utilizado y es este
el que decide si se muestra. Por ejemplo, la marca podría no mostrarse
cuando se definiese una imagen de fondo en la firma.</td>
</tr>
<tr class="odd">
<td>false</td>
<td>No permite mostrar la marca con el resultado de la validación. Este
es el valor por defecto.</td>
</tr>
<tr class="even">
<td>signReason</td>
<td>[Texto]</td>
<td>Razón por la que se realiza la firma.</td>
</tr>
<tr class="odd">
<td>signatureProductionCity</td>
<td>[Texto]</td>
<td>Ciudad en la que se realiza la firma.</td>
</tr>
<tr class="even">
<td>signerContact</td>
<td>[Texto]</td>
<td>Información de contacto del firmante.</td>
</tr>
<tr class="odd">
<td>signerClaimedRoles</td>
<td>[Texto]</td>
<td>Listado de roles declarados por el firmante (separados por “|”)</td>
</tr>
<tr class="even">
<td>policyIdentifier</td>
<td>[URL]</td>
<td>Identificador de la política de firma (normalmente una URL hacia la
política en formato XML procesable), necesario para generar firmas
XAdES-EPES.</td>
</tr>
<tr class="odd">
<td>policyIdentifierHash</td>
<td>[Texto Base64]</td>
<td>Huella digital de la política de firma. Es obligatorio indicar esta
propiedad si el valor indicado en policyIdentifier no es universalmente
accesible. Si se da valor a esta propiedad es obligatorio también dar
valor al parámetro policyIdentifierHashAlgorithm.</td>
</tr>
<tr class="even">
<td rowspan="4">policyIdentifierHashAlgorithm</td>
<td>SHA1</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA1.</td>
</tr>
<tr class="odd">
<td>SHA-256</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA-256.</td>
</tr>
<tr class="even">
<td>SHA-384</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA-384.</td>
</tr>
<tr class="odd">
<td>SHA-512</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA-512.</td>
</tr>
<tr class="even">
<td>policyQualifier</td>
<td>[URL hacia documento]</td>
<td>URL hacia el documento que contiene una descripción textual de la
política de firma.</td>
</tr>
<tr class="odd">
<td>ownerPassword</td>
<td>[Texto]</td>
<td>Contraseña de apertura del PDF. No se soporta la firma de documentos
PDF cifrados con certificados o algoritmo AES-256.</td>
</tr>
<tr class="even">
<td rowspan="2">headless</td>
<td>true</td>
<td>No interrumpe el proceso de firma solicitando interacción del
usuario.</td>
</tr>
<tr class="odd">
<td>false</td>
<td>Muestra diálogos al usuario si requiere de su autorización o algún
dato adicional para firmar. Este es el valor por defecto.</td>
</tr>
<tr class="even">
<td rowspan="3">allowSigningCertifiedPdfs</td>
<td>true</td>
<td>Permite la firma de documentos PDF certificados. El resultado podría
invalidar firmas anteriores del PDF.</td>
</tr>
<tr class="odd">
<td>false</td>
<td>Produce un error al firmar documentos PDF certificados.</td>
</tr>
<tr class="even">
<td>Se omite</td>
<td><p>En caso de detectar que el documento PDF de entrada está
certificado, se aplicará uno de los siguientes comportamientos:</p>
<ul>
<li><p>Si la firma es monofásica (formato “PAdES”), se advertirá al
usuario de que la firma podría invalidar firmas anteriores y se le
permitirá elegir si firmar o cancelar la operación.</p></li>
<li><p>Si la firma es trifásica (formato “PAdEStri”), fallará la
operación de firma.</p></li>
</ul>
<p>Tenga en cuenta que, en los clientes móviles, las firmas podrían ser
trifásicas independientemente del nombre de formato indicado.</p></td>
</tr>
<tr class="odd">
<td rowspan="2">allowCosigningUnregisteredSignatures</td>
<td>true</td>
<td>Permite firmar documentos PDF con firmas previas no
registradas.</td>
</tr>
<tr class="even">
<td>false</td>
<td>No permite firmar documentos PDF con firmas previas no
registradas.</td>
</tr>
<tr class="odd">
<td rowspan="3">signingCertificateV2</td>
<td>true</td>
<td>Se utiliza el atributo signingCertificateV2 en las firmas.</td>
</tr>
<tr class="even">
<td>false</td>
<td>Se utiliza el atributo signingCertificateV1 en las firmas.</td>
</tr>
<tr class="odd">
<td>Se omite</td>
<td>Se utiliza el atributo signingCertificateV1 en las firmas
SHA1withRSA y signingCertificateV2 en el resto.</td>
</tr>
<tr class="even">
<td>signReservedSize</td>
<td>[Entero positivo]</td>
<td>Tamaño máximo en bytes de la firma que se incorporará al PDF. Por
defecto, 27000.</td>
</tr>
<tr class="odd">
<td rowspan="3">allowShadowAttack</td>
<td>true</td>
<td>No se realizará la comprobación de <em>PDF Shadow Attack</em>
durante la validación de las firmas previas (checkSignatures=true).</td>
</tr>
<tr class="even">
<td>false</td>
<td>Se realizará la comprobación de <em>PDF Shadow Attack</em> durante
la validación de las firmas previas (checkSignatures=true) y, en caso de
detectarse, se dará la firma por inválida. Este valor bloqueará también
la operación si se detecta cualquier modificación de un campo de
formulario posterior a la última firma.</td>
</tr>
<tr class="odd">
<td>Se omite</td>
<td>Se realizará la comprobación de <em>PDF Shadow Attack</em> durante
la validación de las firmas previas (checkSignatures=true) y, en caso de
detectarse, se consultará al usuario si se debe continuar con la
operación.</td>
</tr>
<tr class="even">
<td rowspan="3">allowModifiedForm</td>
<td>true</td>
<td>No se realizará la comprobación de cambios en los formularios
durante la validación de las firmas previas (checkSignatures=true). Este
valor desactiva también la validación de <em>PDF Shadow Attack</em>, ya
que se estarán permitiendo cambios en el documento posteriores a la
firma.</td>
</tr>
<tr class="odd">
<td>false</td>
<td>Se realizará la comprobación de cambios en los formularios del
documento durante la validación de las firmas previas
(checkSignatures=true) y, en caso de detectarse, se dará la firma por
inválida.</td>
</tr>
<tr class="even">
<td>Se omite</td>
<td>Se realizará la comprobación de cambios en los formularios del
documento durante la validación de las firmas previas
(checkSignatures=true) y, en caso de detectarse, se consultará al
usuario si se debe continuar con la operación. Si el usuario acepta la
operación, estará aceptando cambios en documento posteriores a la firma,
por lo que no se realizará la comprobación de <em>PDF Shadow
Attack</em>.</td>
</tr>
</tbody>
</table>

## Configuración de firmas de factura electrónica

El formato de factura electrónica configura todas las propiedades
imprescindibles para generar una firma válida de factura, como la
política de firma o las referencias a los nodos, por lo que no deberán
establecerse manualmente.

Este formato sólo puede utilizarse sobre facturas electrónicas y éstas
sólo admiten la operación de firma. No permiten cofirmarlas ni
contrafirmarlas.

La política de firma utilizada por defecto para firmar es la 3.1, aunque
puede configurarse para el uso de la política 3.0 mediante los
parámetros adicionales “policyIdentifier” y “policyIdentifierHash”.

### Operaciones no soportadas y notas de interés

- Las facturas electrónicas se firman con el formato XAdES Enveloped,
  pero con unas particularidades concretas que no es posible replicar
  configurando directamente el formato XAdES en el Cliente @firma. Es
  necesario utilizar el formato FacturaE para la firma de facturas.

- El formato FacturaE sólo puede utilizarse sobre facturas electrónicas
  acordes al estándar.

- Las facturas electrónicas no soportan las operaciones de cofirma ni
  contrafirma. Si se intenta hacer una operación de cofirma o
  contrafirma sobre una factura electrónicas se notificará que no es
  posible porque ésta ya cuenta con una firma.

### Algoritmos de firma

Las firmas de FacturaE aceptan los siguientes algoritmos de firma (deben
escribirse exactamente como aquí se muestran):

- SHA512withRSA

- SHA384withRSA

- SHA256withRSA

- SHA1withRSA (No recomendado)

El algoritmo más seguro, y por lo tanto el recomendado para su uso es
SHA512withRSA.

### Parámetros adicionales

Aquí se listan los parámetros adicionales que acepta el formato FacturaE
para la configuración de la operación y de la firma electrónica
generada.

Es posible que el uso de parámetros no contemplados en las siguientes
tablas provoque otros cambios de funcionamiento. No obstante, **no se
dará soporte** al aplicativo si se usan parámetros no documentados,
asumiendo el integrador todo el riesgo y responsabilidad derivados del
uso de parámetros o valores distintos de los aquí descritos.

<table>
<colgroup>
<col style="width: 28%" />
<col style="width: 28%" />
<col style="width: 43%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Nombre del parámetro</strong></th>
<th><strong>Valores posibles</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>signatureProductionCity</td>
<td>[Texto]</td>
<td>Agrega a la firma un campo con la ciudad en la que se realiza la
firma.</td>
</tr>
<tr class="even">
<td>signatureProductionProvince</td>
<td>[Texto]</td>
<td>Agrega a la firma un campo con la provincia en la que se realiza la
firma.</td>
</tr>
<tr class="odd">
<td>signatureProductionPostalCode</td>
<td>[Texto]</td>
<td>Agrega a la firma un campo con el código postal en donde se realiza
la firma.</td>
</tr>
<tr class="even">
<td>signatureProductionCountry</td>
<td>[Texto]</td>
<td>Agrega a la firma un campo con el país en el que se realiza la
firma.</td>
</tr>
<tr class="odd">
<td>xadesNamespace</td>
<td>[URL]</td>
<td><p>URL de definición del espacio de nombres de XAdES (el uso de esta
propiedad puede condicionar la declaración de versión de XAdES).</p>
<p>Si se establece esta propiedad es posible que se necesite establecer
también el parámetro signedPropertiesTypeUrl para evitar incoherencias
en la versión de XAdES.</p></td>
</tr>
<tr class="even">
<td>signedPropertiesTypeUrl</td>
<td>[URL]</td>
<td><p>URL de definición del tipo de las propiedades firmadas
(<em>Signed Properties</em>) de XAdES. Si se establece esta propiedad es
posible que se necesite establecer también el parámetro xadesNamespace
para evitar incoherencias en la versión de XAdES.</p>
<p>Si no se establece se usa el valor por defecto:
http://uri.etsi.org/01903#SignedProperties.</p></td>
</tr>
<tr class="odd">
<td rowspan="6">signerClaimedRoles</td>
<td>emisor</td>
<td>Declara que el firmante es el emisor de la factura. Este es el valor
por defecto.</td>
</tr>
<tr class="even">
<td>receptor</td>
<td>Declara que el firmante es el receptor de la factura.</td>
</tr>
<tr class="odd">
<td>tercero</td>
<td>Declara que el firmante es un tercero con respecto a la
factura.</td>
</tr>
<tr class="even">
<td>supplier</td>
<td>Declara que el firmante es el emisor de la factura. Este es el valor
por defecto.</td>
</tr>
<tr class="odd">
<td>customer</td>
<td>Declara que el firmante es el receptor de la factura.</td>
</tr>
<tr class="even">
<td>third party</td>
<td>Declara que el firmante es un tercero con respecto a la
factura.</td>
</tr>
<tr class="odd">
<td rowspan="2">policyIdentifier</td>
<td>http://www.facturae.es/politica_de_firma_formato_facturae/politica_de_firma_formato_facturae_v3_1.pdf</td>
<td>Identificador de la política de firma 3.1. Este es el valor por
defecto.</td>
</tr>
<tr class="even">
<td>http://www.facturae.es/politica de firma formato facturae/politica
de firma formato facturae v3_0.pdf</td>
<td>Identificador de la política de firma 3.0.</td>
</tr>
<tr class="odd">
<td rowspan="2">policyIdentifierHash</td>
<td>Ohixl6upD6av8N7pEvDABhEL6hM=</td>
<td>Huella digital para configurar la política de firma 3.1. Este es el
valor por defecto.</td>
</tr>
<tr class="even">
<td>xmfh8D/Ec/hHeE1IB4zPd61zHIY=</td>
<td>Huella digital para configurar la política de firma 3.0.</td>
</tr>
<tr class="odd">
<td>policyIdentifierHashAlgorithm</td>
<td>SHA1</td>
<td>Indica que la huella digital indicada en el parámetro
policyIdentifierHash se calculó mediante el algoritmo SHA1.</td>
</tr>
</tbody>
</table>

# Compatibilidad con dispositivos móviles y AutoFirma

Una aplicación web puede utilizar el JavaScript de despliegue para
llamar al Cliente @firma y que este realice las operaciones de firma que
se soliciten. Para que estas operaciones puedan ejecutarse, es necesario
que se haya instalado previamente en el equipo la aplicación del Cliente
correspondiente a ese entorno. La aplicación de firma puede ser:

- AutoFirma.

  - En equipos de sobremesa (Windows, Linux o macOS).

- Cliente de firma Android.

  - En disposivos Android.

- Cliente de firma iOS.

  - En dispositivos iOS (iPhone y iPad).

No todas estas aplicaciones funcionan de igual modo y las aplicaciones
móviles no soportan todas las operaciones del Cliente. Por este motivo,
un desarrollador que desee que su despliegue funcione en entornos
móviles deberá tener en cuenta una serie de restricciones a la hora de
intregar las funciones en la aplicación.

## Requisitos de despliegue

Para que nuestro despliegue del Cliente @firma sea compatible con los
clientes móviles, deben desplegarse también los servicios auxiliares de
comunicación y de firma trifásica. Para ello se desplegarse los
archivos:

- afirma-signature-storage.war

- afirma-signature-retriever.war

- afirma-server-triphase-signer.war

La descripción de estos servicios puede encontrarse en el apartado
<u>5.3 Servicios</u> .

Además de su despliegue y configuración, es necesario indicar al Cliente
donde se encuentran los servicios desplegados:

- Para establecer la ubicación de los servicios de comunicación se
  utilizará el método setServlets. La descripción del uso de este método
  se realiza en el apartado <u>6.1.2 Configuración de los servicios
  auxiliares de comunicación</u>.

- Para establecer la ubicación del servicio de firma trifásica se
  utilizará el parámetro adicional serverUrl, descrito en el apartado
  <u>ANEXO II Firma trifásica</u>.

## Limitaciones

Debe tenerse en cuenta que las versiones actuales de los distintos
clientes móviles no implementan toda la funcionalidad del Cliente
@firma, y que los clientes móviles de Android e iOS cuentan con distinta
funcionalidad entre sí. Las limitaciones existentes, ya sea porque aún
no se han desarrollado o por la imposibilidad de hacerlo para ese
sistema concreto, son las siguientes:

### Limitaciones de formato

Los clientes móviles de Android y iOS son capaces de realizar firmas en
todos los formatos avanzados soportados por AutoFirma:

- CAdES.

- XAdES.

- PAdES.

- FacturaE.

Sin embargo, salvo en casos concretos, las firmas en los dispositivos
móviles siempre se realizarán a través del servicio de firma trifásica,
por lo cual la firma en dispositivo móvil siempre requerirá:

- El despliegue de este servicio tal como se describe en el apartado
  <u>5.3.2 Servicios de firma trifásica y firma de lotes</u>.

- Configurar en los parámetros adicionales de las operaciones de firma
  la URL del servicio anterior a través de la propiedad “serverUrl”.

Los Clientes de firma móvil realizarán siempre la operación de firma
trifásica, independientemente de que se configure el nombre de formato
común (XAdES, PAdES…) o el trifásico (XAdEStri, PAdEStri). Las únicas
excepciones son los formatos de firma CAdES y PAdES con el Cliente de
firma Android, que sí realizará la firma sin depender del servidor
trifásico cuando se use el nombre monofásico de los formatos.

### Limitaciones funcionales

Los clientes de firma móvil no permiten la configuración del almacén de
claves que deben utilizar ni su comportamiento:

- El cliente de firma Android siempre usará el almacén del sistema o un
  DNIe por NFC (si se encuentra habilitada esta opción en la
  aplicación).

- El Cliente de firma iOS siempre usará el almacén de la propia
  aplicación.

Este comportamiento hace que ambas aplicaciones ignoren las llamadas a
los siguientes métodos de configuración:

- setKeyStore(keystore)

- setStickySignatory(sticky)

También se ignorarán las propiedades para la configuración de filtros de
certificados (*filters*) y la selección automática de certificados
cuando sólo haya uno en el almacén (*headless*).

Por otra parte, las aplicaciones móviles no implementan las operaciones
auxiliares para la carga de ficheros y la aplicación iOS tampoco soporta
la función de guardado:

- getFileNameContentBase64(title, extension, description, filePath,
  successCallback, errorCallback)

- getMultiFileNameContentBase64(title, extension, description, filePath,
  successCallback, errorCallback)

- function saveDataToFile(dataB64, title, fileName, extension,
  description, successCallback, errorCallback)

En el apartado <u>6.8 Operaciones de gestión de ficheros</u>, se
plantean casos de uso alternativos para evitar el uso de estos métodos.

Las aplicaciones móviles tampoco son compatibles con la opción de llamar
al método de firma sin proporcionarle los datos a firmar para que sea la
propia aplicación la que se los solicite al usuario. Los datos deben
proporcionárselos siempre la aplicación.

Por último, las aplicaciones móviles no son compatibles con el método de
recuperación del log de la aplicación:

- getCurrentLog (successCallback, errorCallback)

### Limitaciones de entono

Las aplicaciones móviles sólo permiten las conexiones sin cifrado SSL a
los dominios indicados de antemano. Sin embargo, el cliente móvil puede
conectarse con cualquier dominio, así que no establece estas
excepciones. Para que nuestro despliegue sea compatible con el cliente
móvil, deberá accederse a nuestra web siempre a través de HTTPS.

## Recomendaciones de despliegue

Más allá de lo anteriormente expuesto, existen una serie de limitaciones
en los entornos móviles que hacen que un despliegue que funcione
correctamente en un equipo con AutoFirma pueda presentar problemas con
un dispositivo y el cliente de firma móvil. Buena parte de estas
limitaciones viene por la necesidad de utilizar la comunicación por
servidor intermedio, el que se detengan los JavaScripts cuando el
navegador está en segundo plano y varias restricciones de seguridad
impuestas por algunos navegadores, como Google Chrome (no permite varias
llamadas a una aplicación externa sin interacción del usuario entre
ellas y no permite que se haga esa llamada pasados unos segundos desde
la interacción del usuario). Por este motivo, se recogen aquí una serie
de recomendaciones para garantizar el correcto funcionamiento de las
aplicaciones:

- **Forzar siempre el uso de firma trifásica:**

  - Esto se consigue utilizando los nombres de formato de firma
    trifásica (CAdEStri, PAdEStri, etc.) e indicando la URL del servidor
    trifásico a través de la propiedad “serverUrl”. De esta forma se
    garantiza que las firmas generadas por todas las aplicaciones sean
    siempre iguales, ya que la firma se ejecuta en servidor (que será el
    mismo para todas las aplicaciones), mientras que en la firma
    monofásica la ejecuta cada aplicación y podría haber diferencias en
    las implementaciones de los formatos de firma entre distintas
    versiones de las aplicaciones cliente.

- **Configurar un gestor de documentos apropiado y utilizar referencias
  a los datos:**

  - Cuando se proporciona en la llamada de firma los datos a firmar y
    estos no pueden ser transferidos directamente a la aplicación de
    firma, se subern al servidor intermedio y la aplicación de firma los
    descarga de este. Sin embargo, en los dispositivos móviles la subida
    de los datos puede quedar detenida en el momento de llamar a la
    aplicación de firmam cuando el navegador web queda en segundo plano.
    Por otro lado, si se suben los datos antes de la llamada a la
    aplicación, es probable que a partir de cierto tamaño la subida
    requiera cantidad de tiempo suficiente como para que la llamada a la
    aplicación de firma se retrase, lo que hará que las medidas de
    seguridad de algunos navegadores, como Google Chrome, bloqueen la
    apertura de la aplicación. Para evitar estos problemas, en lugar de
    proporcionar al cliente los datos a firmar, se debería proporcionar
    únicamente la referencia a los datos y configurar a través de la
    propiedad “document.manager” del servicio de firma trifásica un
    gestor de documentos capaz de obtener los datos a partir de estas
    referencias. Idealmente, se debería programar un gestor de
    documentos optimizado para su aplicación, pero se podría utilizar
    alguno de los ya disponibles, como el
    es.gob.afirma.triphase.server.document.FileSystemDocumentManager,
    que carga los datos de un fichero en un directorio configurado en
    servidor y almacena la firma en un directorio distinto.

  - El uso de
    es.gob.afirma.triphase.server.document.SelfishDocumentManager no
    sería válido ya que este no obtiene los datos a partir de una
    referencia, sino que requiere que se le envíen los datos completos.

  - Si nuestra aplicación requiere que sea el usuario el que proporcione
    los datos, se podría organizar el trámite de firma para que
    primeramente se suban esos datos al servidor a través de un
    formulario web y, una vez cargados, se le presente al usuario el
    botón para iniciar el proceso de firma, en donde se indicará la
    referencia a esos datos ya cargados.

- **Evitar múltiples peticiones de firma:**

  - En dispositivos móviles cada nueva operación de firma implica una
    nueva llamada al cliente de firma. Sin embargo, algunos navegadores,
    como Google Chrome en dispositivos móviles, bloquean el que se
    puedan hacer llamadas consecutivas a una aplicación externa. Esto
    significa que, si tratamos de encadenar varias operaciones de firma
    consecutivas, por ejemplo, agregando la llamada a la operación de
    firma en la función callback que se ejecuta al finalizar una
    operación anterior, sólo se ejecutará la primera operación. Para
    evitar este problema, si necesita ejecutar múltiples operaciones de
    firma, utilice la funcionalidad de firma de lotes.

## Notificaciones al usuario

Es obligatorio que el usuario tenga instalado el Cliente de firma
Android o iOS, según corresponda, antes de realizar una operación de
firma desde su dispositivo móvil. Se recomienda por ello que se advierta
al usuario antes de alcanzar la operación de la firma de la necesidad de
instalar esta aplicación. El *javascript* de despliegue del Cliente
facilita a las aplicaciones la labor de detectar el entorno del usuario
mediante las siguientes funciones:

- function isAndroid()

  - Detecta si el usuario accede a la página web desde un dispositivo
    Android.

- function isIOS()

  - Detecta si el usuario accede a la página web desde un iPod, iPhone o
    iPad.

Al detectar que el usuario accede a la aplicación desde Android o iOS,
la aplicación puede, por ejemplo, mostrarle al usuario el enlace para la
instalación de la aplicación desde la tienda de aplicaciones
correspondiente

Un ejemplo del uso de estas funciones sería:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>// Si es Android, mostramos el mensaje de advertencia para
Android</p>
<p><strong>if</strong> (AutoScript.isAndroid()) {</p>
<p>document.getElementById(“androidWarning”).style.display =
"block";</p>
<p>}</p>
<p>// Si es iOS, mostramos el mensaje de advertencia para iOS</p>
<p><strong>else</strong> <strong>if</strong> (AutoScript.isIOS()) {</p>
<p>document.getElementById(“iOSWarning”).style.display = "block";</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

El integrador sería el responsable de preparar esos mensajes de
advertencia.

También se puede agregar a la página web los enlaces para la descarga de
las aplicaciones:

- Enlace a Google Play:

  - \<a
    href="https://play.google.com/store/apps/details?id=es.gob.afirma"\>\<img
    alt="Get it on Google Play"
    src="https://play.google.com/intl/en_us/badges/images/generic/es-play-badge-border.png"
    style="width: 140px;"/\>\</a\>

- Enlace a la App Store:

  - \<a
    href="https://itunes.apple.com/us/app/cliente-firma-movil/id627410001?mt=8&uo=4"
    target="itunes_store"
    style="display:inline-block;overflow:hidden;background:url(https://linkmaker.itunes.apple.com/assets/shared/badges/es-es/appstore-lrg.svg)
    no-repeat;width:135px;height:40px;background-size:contain;"\>\</a\>

# Problemas conocidos

Se han detectado una serie de situaciones problemáticas asociadas al uso
del Cliente @firma y sus servicios. Un usuario o aplicación puede verse
afectado por estas situaciones si obtiene los siguientes errores al
utilizar el Cliente @firma:

- <u>No se puede acceder al almacén de claves de Firefox 49.0 y
  superiores</u>

- <u>No se puede acceder al almacén de claves de Firefox 58</u>

- <u>No se detecta la inserción/extracción del DNIe en el lector (u otra
  tarjeta inteligente)</u>

- <u>Falla la operación de firma con DNIe o una tarjeta de la FNMT</u>

- <u>No se permite la firma de PDF con ciertos certificados</u>

- <u>El servicio de firma trifásica genera un error al realizar firmas
  XAdES en servidores JBoss</u>

- <u>Las firmas con DNIe requieren que se introduzca el PIN del DNIe por
  cada operación de firma</u>

- <u>Error al cargar el listado de certificados después del cambio en
  caliente del almacén por defecto</u>

- <u>AutoFirma no puede comunicarse con el navegador en macOS</u>

- <u>Sólo se realiza la firma del primer documento de una serie cuando
  se realizan las firmas desde Google Chrome</u>

- <u>No se abre la aplicación de firma al realizar la firma desde Google
  Chrome</u>

- <u>No se abre la aplicación de firma con Edge Legacy (EdgeHTML)</u>

- <u>No se abre la aplicación de firma con Firefox cuando el servidor
  declara una política de seguridad (CSP)</u>

A continuación, se describen los problemas asociados a estos casos de
error.

## No se puede acceder al almacén de claves de Firefox 49.0 y superiores

Para el acceso al almacén de claves y certificados de Firefox 49 y
superiores en Windows necesita se que se tenga instalado el entorno de
ejecución redistribuible de Microsoft Visual C++ 2015. Si no consigue
acceder a sus certificados y claves privadas desde AutoFirma, necesitará
descargar este software e instalarlo manualmente.

El entorno de ejecución redistribuible de Microsoft Visual C++ 2015
puede descargarse desde:

- <https://www.microsoft.com/en-us/download/details.aspx?id=53840>

Una vez en el enlace, seleccione el idioma y la arquitectura adecuada
para su sistema operativo.

El proceso de instalación puede requerir permisos de administrador.

## No se puede acceder al almacén de claves de Firefox 58

El navegador web Firefox basa su almacén de claves y certificados en NSS
y, concretamente, en Firefox 58 se hace uso de NSS 3.34. Se han
encontrado problemas de compatibilidad entre esta versión de NSS y Java
que impiden que AutoFirma pueda acceder al almacén de certificados
internos del navegador. Este problema está relacionado con la forma en
la que Firefox 58 genera los almacenes de claves.

Un usuario que desee utilizar Firefox 58 puede, como solución parcial,
instalarse una versión previa de Firefox, por ejemplo, Firefox 56,
instalar sus certificados en el almacén y, a continuación, actualizar el
navegador. Por defecto, el propio navegador se actualizará al
reiniciarlo, así que los certificados deben instalarse en el momento de
abrirlo la primera vez.

Pueden descargarse versiones anteriores de Firefox desde:

<https://ftp.mozilla.org/pub/firefox/releases/>

## No se detecta la inserción/extracción del DNIe en el lector (u otra tarjeta inteligente)

A veces puede ocurrir que el navegador no detecta la extracción o
introducción del DNIe (u otra tarjeta inteligente) en el lector, por lo
que, si no hemos introducido la tarjeta previamente a que se arranque el
cliente de firma, no se encontrará el certificado. Otro posible caso es
que una vez cargado el cliente, se extraiga la tarjeta y, al realizar
una operación de firma, el navegador muestre los certificados de la
tarjeta (aunque ya no esté presente) fallando al intentar utilizarlo.

Puede forzar a la recarga del almacén mediante el botón de actualizar
del diálogo de selección de certificados
(<img src="media/image9.png" style="width:0.22917in;height:0.21336in" />).
Si el cliente sigue sin detectar la tarjeta, pruebe a insertar la
tarjeta antes de iniciar la operación de firma.

## Falla la operación de firma con DNIe o una tarjeta de la FNMT

Se conoce de cierta incompatibilidad de AutoFirma con los controladores
de DNIe y las tarjetas de la FNMT. Esta incompatibilidad puede llevar a
que no se pueda firmar con estas tarjetas o que sólo se pueda realizar
una firma y falle el proceso cuando se intente hacer alguna más.

Para solventar este problema, AutoFirma incorpora la biblioteca
JMulticard, un controlador Java para DNIe y algunas tarjetas de la FNMT.

Si se produce algún error al generar firmas con DNIe o tarjetas de la
FNMT, abra AutoFirma, acceda al panel de “Preferencias”, pestaña
“General” y verifique que en el panel “Opciones generales” se encuentra
activada la opción “Habilitar JMulticard para el uso de tarjetas de la
FNMT y DNIe (requiere reiniciar AutoFirma)”.

Si sigue sin funcionar la operación de firma, es posible que AutoFirma
no sea compatible con su tarjeta inteligente. En ese caso, asegúrese de
que dispone de la última versión de los controladores de la tarjeta.

## No se permite la firma de PDF con ciertos certificados

Las firmas de documentos PDF realizadas externamente (que es el método
utilizado por el Cliente @firma) tienen un tamaño máximo de octetos que
pueden ocupar dentro del PDF.

Como la firma incluye la cadena de certificación completa, si esta es
muy extensa puede llegar a agotarse este espacio y resultar en una firma
inválida o corrupta.

## El servicio de firma trifásica genera un error al realizar firmas XAdES en servidores JBoss

A partir de determinada versión del servidor de aplicaciones JBoss (7 /
EAP 6), este incorpora de serie diversas bibliotecas Java que entran en
conflicto con la versión de estas mismas bibliotecas incorporadas en el
JRE/JDK de Oracle. A saber, las bibliotecas Xalan y Xerces de Apache.
Esto deriva en que durante el proceso de firma se produce un error de
*casting* o similar, según sea la operación y versión de JBoss. El error
se produce a que la JVM da preferencia a las bibliotecas proporcionadas
por el servidor de aplicaciones frente a las suyas propias.

Frente a esto, se propone una sucesión de posibles soluciones de tal
forma que si la primera de ellas no es viable se intente la siguiente
solución y así sucesivamente:

- **Solución 1:** Revisar la documentación del servidor de aplicaciones
  en cuestión para comprobar si existe un mecanismo documentado para dar
  preferencias a las bibliotecas de Java frente a las bibliotecas
  importadas por el propio servidor de aplicaciones.

- **Solución 2:** Otra opción, no tan eficiente como la anterior, aunque
  puede que más sencilla, viene a ser identificar el fichero “rt.jar” de
  la JVM de nuestro servidor e introducirlo en el directorio de
  bibliotecas del WAR del servicio de firma trifásico (directorio
  WEB-INF/lib). Al igual que en el caso anterior, así conseguiremos que
  la JVM dé prioridad a la versión de Xalan/Xerces que incorpora este
  JAR, los por defecto de Java, en lugar de a las bibliotecas del
  servidor de aplicaciones.

- **Solución 3:** Si todo lo anterior fracasase, pero supiésemos que
  ninguna otra aplicación hace uso de estas bibliotecas del servidor de
  aplicaciones, podríamos sustituirlas por la versión 1.4.6 de Xerces y
  sus dependencias. De esta forma, se podría ejecutar la operación de
  firma, aunque varias funcionalidades de JBoss relacionadas con los
  despliegues seguros conforme a la arquitectura definida por RedHat
  podrían verse afectados.

## Las firmas con DNIe requieren que se introduzca el PIN del DNIe por cada operación de firma

El DNIe y los controladores que le dan soporte están desarrollados
conforme a diversas normativas de seguridad, entre ellas, la norma
europea EN14890. Esta norma define la necesidad de que el PIN del DNIe
se presente ante cada una de las operaciones de firma.

AutoFirma incorpora la biblioteca JMulticard, un controlador Java que le
permite utilizar el DNIe sin necesidad de que se encuentre instalado el
controlador oficial. Así mismo, permite activar o desactivar este
controlador que, por defecto, se encuentra activado.

Cuando se se utiliza JMulticard, el diálogo de inserción de PIN
permitirá seleccionar la opción de recordar la contraseña, pero esta
sólo se recordará mientras AutoFirma se encuentre cargado y no se vuelva
a pedir la selección de certificado. Si desea que la contraseña se
recuerde durante varias operaciones, utilice el método
setStickySignatory() del JavaScript de despliegue para dejar
preseleccionado el certificado después de seleccionarlo.

Cuando no se utilice JMulticard, la necesidad de volver a requerir el
PIN de la tarjeta recaerá sobre el propio controlador de DNIe, que podrá
o no recordarlo entre operaciones.

Tenga en cuenta que la contrafirma de un documento con múltiples firmas
puede implicar firmar varias veces, aunque sólo se genere una única
firma electrónica. Así pues, este tipo de firmas pueden requerir que el
usuario inserte varias veces el PIN de su DNIe.

Pueden consultar más información acerca del DNIe en el siguiente enlace:

<http://www.dnielectronico.es/PortalDNIe/>

## Error al cargar el listado de certificados después del cambio en caliente del almacén por defecto 

Se ha detectado que después de haber cargado el almacén del sistema en
Windows (realizando una operación de firma, por ejemplo) puede
producirse un error al cargar el almacén de Mozilla Firefox después de
usar el método setKeyStore para cambiar entre ellos. Este error se debe
a que al realizar el cambio en caliente no se han cargado correctamente
las dependencias necesarias del almacén de Mozilla.

Este problema no tiene solución actualmente.

## AutoFirma no puede comunicarse con el navegador en macOS

En algunos casos la instalación de AutoFirma en macOS finaliza sin
errores, pero no se instala el perfil de seguridad que permiten que
AutoFirma se comunique de forma segura con el navegador web. En estos
casos, al realizar una operación de firma se arrancará correctamente
AutoFirma pero este no será capaz de transmitir el resultado de la firma
al navegador web. Esto puede generar un error del navegador con el texto
“No se ha podido conectar con AutoFirma.”.

Para solventar este problema será necesario configurar manualmente la
confianza en los certificados de AutoFirma.

Para ello:

1.  Acceda a la aplicación “Acceso a llavero”.

2.  Acceda al llavero “SISTEMA” y a la opción “Certificados”.

3.  En el listado de certificados mostrados deben aparecer los
    certificados “127.0.0.1” y “AutoFirma ROOT”. Si el icono que aparece
    junto a estos muestra el signo ‘+’, se confía en los certificados y
    la comunicación con AutoFirma debería funcionar correctamente. Si
    no, continue con el proceso.

4.  Haga clic sobre el certificado “127.0.0.1” y pulse en la opción
    “Confiar”.

5.  En el diálogo que debe haber aparecido, despliegue el listado “Al
    utilizar este certificado” y seleccione la opción “Confiar siempre”.

6.  Repita los pasos 4 y 5 para el certificado “AutoFirma ROOT”.

7.  Compruebe que en ambos certificados aparece ahora el símbolo ‘+’
    junto a su icono.

8.  Cierre la ventana de los llaveros.

9.  Introduzca la contraseña de su usuario en el diálogo para confirmar
    el cambio en la configuración de seguridad.

## Sólo se realiza la firma del primer documento de una serie cuando se realizan las firmas desde Google Chrome

El navegador Google Chrome dispone de un mecanismo de seguridad en base
al cual no permite realizar más de una llamada a una URL externa ante
una única interacción del usuario, como la pulsación de un botón, por
ejemplo. Esta limitación aplica a la llamada al Cliente @firma, tanto a
AutoFirma en entornos de escritorio como a Cliente de firma móvil en
entornos Android, por lo que sólo se podrá abrir la aplicación una sóla
vez ante una única operación del usuario.

La realización de firmas en serie con el cliente se debe realizar
siempre invocando una operación de firma una vez ha terminado la
anterior (comúnmente desde las funciones callback que notifican el final
de una firma). En el caso por defecto de AutoFirma esta limitación no
afecta al usuario, ya que sólo se invoca la aplicación la primera vez y
se le solicitan firmar los distintos documentos a través de un socket.

Sin embargo, la limitación impuesta por Google Chrome sí afecta a
AutoFirma cuando se fuerza que la comunicación entre AutoFirma y el
navegador se realice mediante servidor intermedio (mediante el uso de la
sentencia “AutoScript.setForceWSMode(true)”) y afectará siempre al uso
del Cliente de Firma Android. En estos casos, la aplicación se abrirá
para procesar la primera firma de la serie, pero se ignorarán las
llamadas para procesar los siguientes documentos.

Cuando se deba realizar la firma de múltiples documentos
simultáneamente, se recomienda aplicar alguna de las siguientes
directrices:

- Utilizar el modelo de firma de lotes de documentos.

- Nunca forzar la comunicación por servidor intermedio.

- Recomendar a los usuarios de Android el uso de un navegador distinto a
  Google Chrome.

Esta limitación está relacionada con la descrita en el problema <u>10.11
No se abre la aplicación de firma al realizar la firma desde Google
Chrome</u>.

## No se abre la aplicación de firma al realizar la firma desde Google Chrome

El navegador Google Chrome dispone de un mecanismo de seguridad en base
al cual no permite realizar una llamada a una URL externa pasados unos
pocos segundos entre la interacción del usuario con la página, como la
pulsación de un botón, y la propia llamada. Esta limitación aplica a la
llamada al Cliente @firma, tanto a AutoFirma en entornos de escritorio
como a Cliente de firma móvil en entornos Android, por lo que la
aplicación no se abrirá si transcurre demasiado tiempo entre la
solicitud de firma del usuario y la llamada a la aplicación.

Esto no debe afectar al uso de AutoFirma desde Chrome ya que, por
defecto, la llamada a la aplicación se realiza de forma inmediata y los
datos se transmiten a través de un socket.

Sin embargo, la limitación impuesta por Google Chrome sí puede afectar
AutoFirma cuando se fuerza que la comunicación entre AutoFirma y
navegador se realice mediante servidor intermedio (mediante el uso de la
sentencia “AutoScript.setForceWSMode(true)”) y en cualquier caso al uso
del Cliente de Firma Android. En estos casos, si los datos no pueden
enviarse a través de la URL de invocación a la aplicación, deberán
subirse primeramente al servidor intermedio para que después la
aplicación de firma los descague. Cuando esta subida de los datos dure
más de unos pocos segundos, la aplicación de firma no se abrirá.

Por regla general, para evitar los problemas derivados de esta
restricción de navegador Chrome, se deberían seguir las siguientes
sugerencias:

- Utilizar el modelo de firma trifásica con un DocumentManager a medida
  (no con el por defecto), para que los datos a transmitir entre el
  navegador y la aplicación sean siempre pequeños.

- Nunca forzar la comunicación por servidor intermedio.

- Recomendar a los usuarios de Android el uso de un navegador distinto a
  Google Chrome.

Esta limitación está relacionada con la descrita en el apartado <u>10.10
Sólo se realiza la firma del primer documento de una serie cuando se
realizan las firmas desde Google Chrome</u>.

## No se abre la aplicación de firma con Edge Legacy (EdgeHTML)

Existen determinada configuración de Microsoft Edge Legacy que impide el
uso de sockets, lo que lleva a que la aplicación no se pueda comunicar
con el JavaScript de despliegue y este termine dando un error pasado un
tiempo de espera.

Este error se puede identificar cuando al inciar la operación se muestra
la imagen de inicio de AutoFirma (*splash)* pero nunca se llega a
mostrar la aplicación. Además, en la consola de Edge aparece
recurrentemente un error con el mensaje:

SCRIPT12029: SCRIPT12029: WebSocket Error: Network Error 12029, No se
pudo establecer una conexión con el servidor

Este problema se debe a que el navegador está aplicando ciertas
restricciones a la aplicación considerando que se trata de un servidor
externo. Esto se produce cuando se encuentra en Windows habilitada la
opción de considerar parte de la intranet los sitios a los que no se
acceda a través de un servidor proxy. Puede ver esta opción a través del
panel “Opciones de Internet” del sistema operativo, pestaña “Seguridad”,
al pulsar en la zona “Intranet” y seguidamente en el botón “Sitios”.

<img src="media/image10.png" style="width:3.11667in;height:1.85941in" />

Es probable que esta opción se encuentre habilitada como parte de una
configuración de maqueta corporativa. Si es así, NO deshabilite esta
opción, ya que podría afectar negativamente a la seguridad de su equipo
o el funcionamiento de aplicaciones coorporativas. Con esta opción
habilitada no podrá utilizar AutoFirma con Edge Legacy. Si es posible,
actualice a Edge Chromium o utilice otro navegador web.

## No se abre la aplicación de firma con Firefox cuando el servidor declara una política de seguridad (CSP)

Mozilla Firefox no abre por defecto las URL con esquemas personalizados
cuando el servidor web declara una política de seguridad. Para permitir
las llamadas con protocolo “afirma” utilizadas por el Cliente @firma,
será necesario agregar a la política de seguridad el esquema
correspondiente. Consulte el apartado <u>5.4 Configuración del *Content
Security Policy*</u> para más información.

# Comunicación JavaScript de despliegue – Cliente @firma

El JavaScript de despliegue del Cliente @firma es el que incluye la
lógica de comunicación entre el navegador Web y el cliente de firma.
Algunas de las operaciones solicitadas a través del JavaScript de
despliegue serán procesadas directamente por el propio JavaScript,
mientras que otras sí requerirán que traslade la solicitud al Cliente de
firma.

A pesar de que es el JavaScript de despliegue el que gestiona la
delegación de tareas en la aplicación nativa correspondiente a cada
entorno, deben cumplirse una serie de requisitos para que esto sea
posible.

AutoFirma es una herramienta nativa que puede instalarse en Windows,
Linux y macOS como herramienta independiente de firma de datos locales.
Sin embargo, al instalarse en el sistema también registran el protocolo
“afirma“, mediante lo cual atienden a las llamadas realizadas a este
protocolo. La llamada por protocolo es un mecanismo de invocación de
aplicaciones (si acaso la propia aplicación que realiza la llamada no
puede atender a este protocolo) mediante el que puede pasarse una
cantidad limitada de información a modo de parámetros. Sin embargo, este
protocolo sólo permite la comunicación en un sentido ya que la
aplicación invocada no puede hacer referencia a la instancia de aquella
que la invocó.

Es por esto que, para permitir la comunicación bidireccional, Autofirma
establece 2 mecanismos distintos:

- La comunicación mediante *socket*.

  - Este sistema se utiliza cuando se ejecuta la operación en un equipo
    sobremesa y navegador Chrome, Firefox, Safari, Internet Explorer 11
    y Edge.

- La comunicación mediante un servidor intermedio.

  - Este sistema requiere el despliegue de los dos servicios auxiliares
    de comunicación y puede utilizarse potencialmente en cualquier
    navegador. Consulte el apartado <u>Servicios</u> para más
    información.

  - Dado que este sistema ofrece un peor rendimiento, por defecto sólo
    se utiliza en entornos de usuario que no soportan la comunicación
    por sockets o en los que puede dar problemas: dispositivos móviles,
    Internet Explorer 10 e inferiores, Safari 10….

Por regla general, **siempre se deberían desplegar los servicios
auxiliares para la comunicación por servidor intermedio**, ya que hay
entornos que dependen de esos servicios, incluso si no son los más
utilizados.

# Comunicación por sockets

En la comunicación por *socket*, AutoFirma abre un *socket* local SSL y
el JavaScript de despliegue traslada las peticiones de la aplicación a
través del él. Las respuestas se obtienen a través del propio *socket*.

<img src="media/image11.png" style="width:5.69167in;height:1.68125in" /><img src="media/image12.png" style="width:5.69167in;height:1.68125in" /><img src="media/image13.png" style="width:5.69167in;height:1.68125in" />La
arquitectura de comunicación seguida en este proceso se describe a
continuación:

Primeramente, el trámite ordena la operación en cuestión por medio del
JavaScript de despliegue del Cliente @firma, por ejemplo, una operación
de firma. A continuación, el JavaScript detectará que el entorno del
usuario soporta la comunicación por sockets y lanzará AutoFirma mediante
una invocación por protocolo junto con las instrucciones para abrirlo.
AutoFirma abrirá este *socket* cifrando el canal mediante un certificado
SSL y el JavaScript podrá enviar la orden de firma a través del este.

Una vez abierta la aplicación, cualquier petición posterior se realizará
a través del mismo socket, sin necesidad de relanzarla. AutoFirma se
cerrará al detectar que el puerto se ha cerrado o, si no es posible
detectarlo, cuando pase un tiempo sin haber recibido más peticiones
desde el JavaScript.

La comunicación a través del socket se cifra mediante el protocolo TLS
v1.1/v1.2. Es necesario tener habilitados estos protocolos en el
navegador para poder establecer la comunicación con AutoFirma.

# Comunicación por servidor intermedio

Este modo de comunicación se basa en dos servicios disponibles en el
mismo dominio que el trámite Web en el que se va a firmar. Cuando el
JavaScript de despliegue y la aplicación de firma necesiten comunicarse,
subirán la información de la operación a realizar a un servidor, de
donde tendrá que descargárselo el destinatario de dichos datos.

La comunicación por servidor intermedio es la utilizada por defecto
cuando se accede a la página desde un dispositivo móvil (en el que no
podemos abrir un socket local) y cuando se accede desde otro entorno con
un navegador no compatible con la comunicación por sockets o en el que
se han encontrado problemas.

La arquitectura de comunicación seguida en este proceso se describe a
continuación:

<img src="media/image11.png" style="width:5.76111in;height:3.83264in" /><img src="media/image12.png" style="width:5.76111in;height:3.83264in" /><img src="media/image130.png"
style="width:5.76111in;height:3.83264in" /><img src="media/image14.png" style="width:5.76111in;height:3.83264in" />

Cuando el JavaScript de despliegue deba enviar a la aplicación de firma
la ejecución de una operación, subirá los datos que deba enviarle al
servidor intermedio por medio del servicio de guardado, invocará a la
aplicación de firma mediante una llamada por protocolo y ésta se
descargará los datos por medio del servicio de recuperación. Una vez
procesados los datos, la aplicación almacenará el resultado en el
servidor intermedio y el JavaScript de despliegue descargará estos datos
del servidor para obtener el resultado final.

En este modo de comunicación, el JavaScript de despliegue abre la
aplicación de firma por cada operación. Después de finalizar una
operación, la aplicación se cierra o queda en segundo plano.

Consulte el apartado <u>5.3.1 Servicios auxiliares de comunicación</u>
para saber más de estos servicios del Cliente @firma y cómo
desplegarlos.

# Firma trifásica

Una firma electrónica se compone de los siguientes pasos:

1.  Construir la estructura que el usuario debe firmar según el formato
    de firma y la configuración seleccionada.

2.  Realizar la firma digital de esos datos con el certificado del
    usuario.

3.  Introducir la firma digital en la estructura de firma.

En el comportamiento por defecto, AutoFirma realizaría todos estos pasos
consecutivamente. Sin embargo, el proceso puede realizarse en tres fases
separadas, en donde la primera y la tercera fase, que son las que no
requieren la clave privada de firma, se realicen en un servidor remoto,
mientras que la segunda seguiría realizándose en el equipo cliente. Este
proceso de firma dividido en 3 fases es lo que se denomina firma
trifásica.

Esta operativa resulta de mucho interés en determinados casos:

- El **origen y/o el destino de la información es un servidor**, de tal
  forma que se pueden pre-procesar los datos en servidor (Fase I) y
  mandar al usuario sólo la información mínima necesaria; el usuario la
  firmaría en su sistema (Fase II) y el resultado se enviaría de vuelva
  a servidor; en donde se compondría la firma (Fase III) y podría
  postprocesarse y almacenarse.

- Se **necesita firmar documentos muy grandes**. La firma trifásica
  interesa en este caso porque la mayor carga de proceso recaería sobre
  el servidor y no sobre el sistema del usuario que presuntamente tendrá
  menos recursos.

El uso de la firma trifásica en estos casos conlleva una serie de
ventajas y desventajas:

- **Ventajas**

  - El documento no viaja a través de la red.

  - Mayor facilidad para desarrollos sobre dispositivos móviles y
    similares, ya que no es necesario programar la lógica del formato
    para el dispositivo, sólo es necesaria la fase del cifrado de los
    datos con la clave del usuario.

  - Menos propenso a errores debido a que la parte cliente no se vería
    expuesta a las muchas variables del entorno que pueden afectar a los
    distintos formatos de firma (versiones preinstaladas de bibliotecas,
    cambios en Java, …). Las operaciones más complejas se realizan en
    servidor, un entorno mucho más controlado.

- **Desventajas:**

  - Implica un mayor número de conexiones de red, aunque el tráfico de
    red, según el caso, podría sea menor.

  - Requiere el despliegue de un servicio en el servidor que se encargue
    de realizar las fases 1 y 3.

Debe recalcarse que el procedimiento de firma trifásica es útil cuando
los datos a firmar residen en servidor y la firma generada se necesita
también en servidor. En estos casos, se podría indicar al servidor de
donde obtener los datos a firmar y qué hacer con la firma generada. Si
los datos y/o la firma deben estar en cliente, no solo se produce un
innecesario tráfico de red, sino que se aumenta la posibilidad de fallo
y se incrementan las necesidades de memoria del cliente de firma.

El proceso de firma de lotes del Cliente @firma realiza siempre firmas
trifásicas, ya que en un escenario en el que se deben cargar múltiples
datos y se generan múltiples firmas se puede volver inviable el
conservar en memoria toda la información, además del hecho de que
probablemente haya que descargarla y luego subirla de nuevo al servidor.
Cuando se hable de un proceso de firma de lotes se debe entender que se
usarán firmas trifásicas, sólo que se hará uso de los servicios de
prefirma y postfirma de lotes en lugar del servicio de firma trifásica
tradicional. Por lo demás, todas las consideraciones de firma trifásica
afectan de igual manera al proceso de firma de lotes.

# Servicios de firma trifásica y de lotes

Los servicios de firma trifásica y de lotes realizan en servidor la
primera y tercera fase del proceso de firma. Junto al Cliente @firma se
distribuye el archivo WAR “afirma-server-triphase-signer.war” que
despliega los servicios con las funcionalidades de firma trifásica.
Estoa servicios no es dependientes de ningún servidor de aplicaciones
concreto. Consulte el manual de su servidor de aplicaciones para saber
cómo desplegar este fichero WAR y el apartado <u>5.3.2 Servicios de
firma trifásica y firma de lotes</u> para saber como configurar los
servicios.

Estos servicios soportan la generación de firmas en formato CAdES,
XAdES, PAdES y FacturaE y admiten las mismas opciones de configuración
que las firmas monofásicas de estos formatos.

Desplegar y configurar estos servicios es necesario para la generación
expresa de firmas trifásicas, el uso de la operativa de firma de lotes,
en la que todas las firmas se generan de forma trifásica. También puede
ser necesario para el uso del Cliente de firma móvil, ya que este delega
en el servicio trifásico la generación de las firmas en los formatos que
no soportan nativamente. Para saber más acerca del Cliente @firma móvil,
consulte el apartado <u>9 Compatibilidad con dispositivos móviles y
AutoFirma</u>.

# Gestor de documentos del servicio

La principal ventaja del proceso de firma trifásica es que no es
necesario descargar a la página web los datos a firmar para luego
pasárselos al método de firma, ni será necesario recoger la firma en un
método *callback* para luego enviarla al servidor. Los datos pueden
cargarse directamente en servidor, no es necesario que viajen al equipo
del usuario, y la firma puede guardarse directamente, sin necesidad de
que la recoja nuestra aplicación. Esta lógica de cargar los datos y
guardar la firma la gestiona el servicio de firma trifásica por medio de
lo que llamaremos “gestor de documentos” (*Document Manager*).

Nuestro servicio de firma trifásica tendrá configurado un gestor de
documentos que le dirá cómo obtener los datos y guardar las firmas. Este
gestor de documentos se configura a través de la propiedad
“document.manager” del fichero de configuración del servicio. Este
gestor se utilizará tanto para las operaciones de firma trifásica
individuales como para las operaciones de firma de lotes.

Un desarrollador puede crear un gestor de documentos optimizado para el
proceso en el que se va a utilizar, pero el servicio de firma trifásica
se distribuye con varios gestores de documento ya integrados:

- es.gob.afirma.triphase.server.document.SelfishDocumentManager

  - Es el *Document Manager* por defecto y emula el comportamiento de la
    firma monofásica del cliente.

  - Si no tenemos interés en la firma trifásica, pero sí queremos que
    nuestra aplicación sea compatible con la operación de firma de los
    clientes móviles de firma, deberemos desplegar el servicio de firma
    trifásica con este gestor de documentos configurado. Este servicio
    permitirá completar la firma cuando se utilice un formato no
    soportado por la aplicación móvil en cuestión:

    - Cliente @firma Android:

      - XAdES y FacturaE.

    - Cliente @firma iOS:

      - XAdES, FacturaE y PAdES.

  - **Nota**: Este gestor de documentos carece de valor en las
    operaciones de firma de lotes, ya que no hace nada con las firmas y
    estas se pierden.

  - Recibe:

    - Los datos a firmar.

  - Devuelve:

    - La firma generada.

- es.gob.afirma.triphase.server.document.FileSystemDocumentManager

  - Permite cargar los datos a firmar desde un directorio de entrada y
    guarda las firmas resultantes en un directorio de salida.

  - Recibe:

    - El nombre del fichero de datos a firmar.

  - Devuelve:

    - El nombre con el que se ha guardado el fichero de firma.

  - Si se configura este *Document Manager*, se pueden configurar otras
    cuatro propiedades en el fichero de configuración del servicio:

    - docmanager.filesystem.indir: Directorio del servidor en donde se
      encuentran los documentos de datos.

    - docmanager.filesystem.outdir: Directorio del servidor en donde se
      almacenan las firmas generadas.

    - docmanager.filesystem.overwrite: Configura si se deben
      sobrescribir los ficheros de firma si ya existe una con el mismo
      nombre (true) o no (false).

    - docmanager.filesystem.maxDocSize: Permite limitar a un tamaño
      máximo los ficheros que se quieren firmar. El tamaño se indicará
      en bytes. Si el fichero supera este tamaño, no se firmará.

  - **Advertencia:** La inclusión del FileSystemDocumentManager busca
    servir como ejemplo de gestor de documentos. Este gestor no debería
    usarse salvo que se ajuste muy concretamente a sus necesidades. Si
    no es así, lo correcto es que implemente su propio gestor de
    documentos optimizado para la carga y el guardado de documentos en
    sus sistemas.

  - Consulte el apartado <u>II.2.1 Gestor de documentos
    “FileSystemDocumentManager”</u> para obtener información sobre cómo
    integrar el uso de este gestor de documentos en su aplicación.

- es.gob.afirma.triphase.server.document.LegacyBatchDocumentManager

  - Permite mantener la compatibilidad con los SaveSigner del antiguo
    mecanismo de lotes. Este gestor no se debería utilizar más que para
    esta finalidad. Permite los dos mecanismos de entrada que permitía
    el antiguo sistema de firmas (datos en Base64 o URL), y es
    compatible con los SignSaver que existían por defecto y cualquier
    otro agregado a posteriori.

  - Recibe:

    - Los datos coficiados en Base 64 o una URL a los mismos.

  - Devuelve:

    - La cadena “OK”.

  - Si se configura este *Document Manager*, también se puede configurar
    las siguientes propiedades en el fichero de configuración del
    servicio:

    - docmanager.legacybatch.allowedsources: Fuentes de datos de entrada
      admitidos. Deberá indicar las distintas fuentes de datos separadas
      por punto y coma (‘;’). Los valores admitidos son:

      - base64: Datos de entrada en Base 64.

      - file:/: URL de un fichero de datos en servidor. Se puede
        completar con la parte de la ruta que se desee y terminar con
        asterisco (‘\*’) para determinar cualquier fichero en esa ruta.
        (No se recomienda el uso de este esquema)

      - http://: URL con esquema HTTP para el acceso remoto a los datos.
        Se puede completar con la parte de la ruta que se desee y
        terminar con asterisco (‘\*’) para determinar cualquier origen
        en esa ruta.

      - https://: URL con esquema HTTPS para el acceso remoto a los
        datos. Se puede completar con la parte de la ruta que se desee y
        terminar con asterisco (‘\*’) para determinar cualquier origen
        en esa ruta.

      - ftp://: URL para el acceso remoto a los datos en un FTP. Se
        puede completar con la parte de la ruta que se desee y terminar
        con asterisco (‘\*’) para determinar cualquier origen en esa
        ruta.

> Por ejemplo:

- base64;https://www.midominio.com/datos/\*

  - Admite datos en base 64 y datos proporcionados a través de una
    dirección HTTPS determinada.

<!-- -->

- docmanager.legacybatch.checksslcerts: Indica si se debe comprobar la
  confianza en el certificado SSL de las fuentes de datos en los que se
  encuentre el canal cifrado. Si se establece con valor true, se
  realizará la comprobación y se se establece a false, no.

- docmanager.legacybatch.maxDocSize: Permite limitar a un tamaño máximo
  los ficheros que se quieren firmar. El tamaño se indicará en bytes. Si
  el fichero supera este tamaño, no se firmará.

<!-- -->

- Consulte el apartado <u>II.2.2 Gestor de documentos
  “LegacyBatchDocumentManager”</u> para obtener información sobre cómo
  integrar el uso de este gestor de documentos en su aplicación.

Un desarrollador Java podría crear nuevos gestores de documentos e
integrarlos en el servicio. Esto le permitiría crear procesos óptimos
que accediesen a sus entornos para recoger los datos y guardar las
firmas y así se evitase la descarga de los datos redujese la
transferencia de datos entre el cliente de firma y los servidores del
por red.

# Gestores de documentos personalizados

# Desarrollo de un gestor de documentos personalizado

Sólo el responsable de un entorno conoce los requisitos de acceso al
mismo, el proceso adecuado para acceder y las medidas de seguridad que
es necesario implementar. Es por esto por lo que el servicio trifásico
permite que los integradores desarrollen su propia clase gestora de
documentos y configurar en el servicio de firma trifásica el que se
utilice esta. Por ejemplo, si los documentos a firmar se almacenasen en
un repositorio de contenidos remoto y las firmas se deben guardar en
base de datos, podremos implementar la lógica de nuestra clase gestora
de documentos para que acceda a estos entornos usando las credenciales
adecuadas, recupere los documentos y almacene las firmas.

Para implementar un gestor de documentos, se deberá implementar la
interfaz es.gob.afirma.triphase.server.DocumentManager o
es.gob.afirma.triphase.server.BatchDocumentManager (que hereda de la
anterior), disponibles en el módulo
“afirma-server-triphase-signer-document” del proyecto. Si se desea, se
puede importar a su proyecto mediante la siguiente referencia de Maven:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>&lt;dependency&gt;</p>
<p>&lt;groupId&gt;es.gob.afirma&lt;/groupId&gt;</p>
<p>&lt;artifactId&gt;afirma-server-triphase-signer-document&lt;/artifactId&gt;</p>
<p>&lt;version&gt;1.8.0&lt;/version&gt;</p>
<p>&lt;/dependency&gt;</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

La interfaz DocumentManager define los siguientes métodos que deberemos
implementar:

- byte\[\] getDocument(String dataRef, X509Certificate\[\] certChain,
  Properties prop) throws IOException;

  - Método para la obtención del documento que se desea firmar.

  - Los parámetros recibidos en este método serán:

    - dataRef: Referencia a los datos que se deben firmar. Esta cadena
      es la que se introduce en el método de firma o agregar documento a
      un lote.

    - certChain: Cadena de certificación del certificado utilizado para
      firmar. Según el tipo de operación, la aplicación utilizada y el
      almacén del usuario, es posible que este valor sólo contenga el
      certificado de firma o incluso que el parámetro sea nulo.

    - prop: Parámetros para la configuración de firma. Este es parámetro
      extraParams proporcionado en el método de firma del Cliente @firma
      o el de agregar documento al lote. Se podrían incluir aquí
      parámetros que no entren en conflicto con los de firma y que nos
      sirvan para proporcionar mayor información a la clase gestora de
      documentos.

  - Esta función debe devolver el binario del documento a firmar.

  - En caso de producirse un error al recuperar el documento, la clase
    gestora deberá lanzar una excepción de tipo IOException.

- String storeDocument(String dataRef, X509Certificate\[\] certChain,
  byte\[\] data, Properties prop) throws IOException;

  - Método para el tratamiento y guardado de la firma generada.

  - Además del guardado, en este método se podrían implementar funciones
    adicionales de las que se quiera liberar a las distintas
    aplicaciones que hagan uso del gestor. Por ejemplo, se podría
    implementar aquí el proceso de validación de la firma o la
    agregación de un sello de tiempo (agregar un un sello de tiempo con
    @firma lleva implícito el validar la firma). De esta forma, si
    fallase este proceso, el Cliente @firma nortificaría al usuario de
    forma inmediata.

  - Los parámetros recibidos en este método serán:

    - dataRef: Identificador de los datos que se firmaron. Es el mismo
      valor que se debió recibir en el método getDocument.

    - certChain: Cadena de certificación del certificado utilizado para
      firmar. Según el tipo de operación, la aplicación utilizada y el
      almacén del usuario, es posible que este valor sólo contenga el
      certificado de firma o incluso que el parámetro sea nulo.

    - data: Firma electrónica generada. Son los datos que se deberán
      tratar y guardar.

    - prop: Parámetros para la configuración de firma. Este es parámetro
      extraParams proporcionado en el método de firma del Cliente @
      firma o el de agregar documento al lote. Se podrían incluir aquí
      parámetros que no entren en conflicto con los de firma y que nos
      sirvan para proporcionar mayor información a la clase gestora de
      documentos.

  - Este método debe devolver una cadena en Base 64, que será la que se
    reciba como parámetro de datos en el método de éxito de firma de la
    aplicación que invocó al Cliente @firma. Esta cadena no tiene que
    ser un dato significativo si no es necesario. Por ejemplo, podría
    limitarse a devolver la cadena “OK” (codificada en base 64),
    únicamente para que la aplicación sepa que ha finalizado
    correctamente. Este valor de retorno no se devuelve a la aplicación
    cuando se ha realizado una firma de lote. En este caso, se obtiene
    una estructura JSON con el estado en el que ha terminado cada una de
    las firmas del lote.

  - En caso de producirse un error al tratar y guardar el documento, la
    clase gestora deberá lanzar una excepción de tipo IOException.

Por su parte, la interfaz BatchDocumentManager declara los siguientes
métodos adicionales:

- void rollback(String dataRef, X509Certificate\[\] certChain,
  Properties prop) throws IOException

  - Este método revierte el proceso de guardado de una firma mediante el
    método storeDocument. Este método se utilizaría si se produjese un
    fallo en el guardado de un documento del lote y la aplicación
    hubiese indicado que se desea detener el proceso en caso de error,
    ya que se debía guardar todo o nada.

  - Los parámetros recibidos en este método son los mismos usados en el
    de guardado:

    - dataRef: Referencia a los datos firmados. Esta cadena es la que se
      introduce en el método de firma o agregar documento a un lote.

    - certChain: Cadena de certificación del certificado utilizado para
      firmar. Según el tipo de operación, la aplicación utilizada y el
      almacén del usuario, es posible que este valor sólo contenga el
      certificado de firma o incluso que el parámetro sea nulo.

    - config: Parámetros para la configuración de firma. Este es
      parámetro extraParams proporcionado en el método de firma del
      Cliente @ firma o el de agregar documento al lote. Se podrían
      incluir aquí parámetros que no entren en conflicto con los de
      firma y que nos sirvan para proporcionar mayor información a la
      clase gestora de documentos.

  - En caso de producirse un error al revertir el guardado, se deberá
    lanzar una excepción de tipo IOException.

- void init (Properties config)

  - Este método inicializa el gestor con los parámetros de configuración
    establecidos en el fichero de configuración del servidor trifásico
    (“tps_config.properties”). Esto permite configurar el comportamiento
    del gestor por medio de este fichero.

Si no se implementa la interfaz BatchDocumentManager, pero aún se quiere
poder configurar el gestor con las propiedades del fichero de
configuración del servicio, se puede implementar en la clase gestora un
constructor que reciba un objeto Properties. El servicio de firma
trifásica hará uso de este constructor para inicializar la clase y le
proporcionará a través de este parámetro todas las propiedades del
fichero de configuración. Si se implementa la interfaz
BatchDocumentmanager, siempre se utilizará el constructor vacío y el
método init de la clase.

Una clase que herede de DocumentManager también se puede usar como
gestor de documentos en las operaciones de firma de lote, pero al no
tener definido esta interfaz el método rollback, el uso con el parámetro
stopOnError de la firma de lotes estaría desaconsejado, ya que no se
desharían los guardados que se hiciesen.

# Configuración de un gestor de documentos personalizado

Para configurar una clase gestora de documentos personalizada se deberá
incluir esta como parte del servicio de firma trifásica. Esto se puede
hacer generando una JAR con las clases y recursos necesarios del
conector e incluyéndola dentro del WAR del servicio de firma trifásica.
Para esto, se debe abrir el WAR “afirma-server-triphase-signer.war” con
una aplicación de compresión de ficheros y agregar el JAR en el
subdirectorio “\WEB-INF\lib\\”. Esta versión modificada del WAR es la
que se deberá desplegar en lugar del WAR por proporcionado.

Seguidamente, se deberán establecer en el fichero de configuración del
servicio (“tps_config.properties”) la propiedad “document.manager” con
el nombre completo de nuestra clase gestora de documentos y todas
aquellas propiedades adicionales que quieran tomar de este fichero.
Puede consultar más información sobre este fichero en el apartado
<u>5.3.2.1 Configuración del servicio trifásico</u>.

Si la recuperación de los documentos del gestor de documentos puede
cosiderarse una tarea pesada, puede valorarse activar la caché del
servicio de firma trifásica. Consulte más acerca de esta propiedad en el
apartado <u>5.3.2.1 Configuración del servicio trifásico</u>.

# Uso de la firma trifásica con los gestores de documentos

En este apartado se describe cómo deben utilizarse las operaciones de
firma trifásica y de lotes con cada uno de los gestores de documentos
incluidos por defecto en el servicio.

# Gestor de documentos “FileSystemDocumentManager”

# Parámetros de uso y descripción del funcionamiento

La clase gestora de documentos FileSystemDocumentManager permite
gestionar la firma de ficheros almacenados en servidor. Esta clase
utiliza como identificador de documento el nombre de fichero, tanto en
la entrada (fichero a firmar) como en la salida (fichero de firma).

Esta clase gestora está preparada para recibir el nombre de los ficheros
codificados en Base 64. Por ejemplo:

- El documento “documento.pdf” se indicaría con la cadena
  “ZG9jdW1lbnRvLnBkZg==”.

- El documento “firma.xsig” se indicaría con la cadena
  “ZmlybWEueHNpZw==”.

El resultado depende del tipo de operación. En la función *callback* de
éxito de la operación de firma se proporcionará el nombre del fichero
codificado en Base64. En la función *callback* de éxito de la firma del
lote, se proporcionará únicamente el JSON con el resultado de la
operación del lote, independientemente de la clase gestora de documentos
empleada.

Es importante tener en cuenta que los nombres de fichero utilizados
deben cumplir las restricciones del sistema de ficheros donde se
almacenen los documentos. Así, por ejemplo, en un sistema de ficheros
NTFS no deberíamos indicar nunca un nombre de ficheros que contuviese el
carácter dos puntos (“:”).

Por ejemplo, si quisiéramos realizar una firma trifásica con el Cliente
@firma y nuestro servicio de firma trifásica tuviese configurado el
gestor de documentos FileSystemDocumentManager podríamos firmar así:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p><strong>var</strong> params =
"expPolicy=FirmaAGE\nserverUrl=https://miweb.com/afirma-server-triphase-signer/SignatureService
";</p>
<p>// Queremos firmar el documento "12345678.pdf" del directorio de
entrada</p>
<p>AutoScript.sign (AutoScript.getBase64FromText("12345678.pdf"),</p>
<p>"SHA512withRSA",</p>
<p>"PAdEStri",</p>
<p>params,</p>
<p>successCallback,</p>
<p>errorCallback);</p>
<p>…</p>
<p><strong>function</strong> successCallback(filenameB64, certB64) {</p>
<p>// filenameB64 es el nombre del fichero de firma codificado en Base
64</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

En una operación de firma de lote, se usaría de la siguiente manera:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>…</p>
<p>// Creamos el lote</p>
<p>AutoScript.createBatch("SHA512withRSA", "PAdES", "sign",
<strong>null</strong>);</p>
<p>// Agregamos los documentos que queramos al lote</p>
<p>AutoScript.addDocumentToBatch("1",</p>
<p>AutoScript.getBase64FromText("12345678.pdf"));</p>
<p>…</p>
<p>// Iniciamos la firma</p>
<p><strong>var</strong> baseUrl = "
https://miweb.com/afirma-server-triphase-signer/"</p>
<p>AutoScript.signBatchProcess (<strong>false</strong>,</p>
<p>baseUrl + "presign",</p>
<p>baseUrl + "postsign",</p>
<p><strong>null</strong>,</p>
<p>successCallback,</p>
<p>errorCallback);</p>
<p>…</p>
<p><strong>function</strong> successCallback(jsonResult, certB64) {</p>
<p>// jsonResult estructura JSON con el resultado de cada</p>
<p>// operación de firma del lote</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

**Advertencia**: Este gestor de documentos se incluye a modo
ilustrativo. Si se desea utilizar en un entorno productivo, es necesario
tener en cuenta algunos requisitos de seguridad. Por ejemplo, los
documentos sólo deberían almacenarse en el directorio de entrada del
servidor en el que se vaya a iniciar el proceso de firma y debería
eliminarse del mismo una vez finalizada. De otra forma, este documento
podría ser recuperado por una aplicación malintencionada mediante
llamadas al servicio trifásico. Las firmas en el directorio de salida
también se deberían retirar una vez generadas.

# Configuración en alta disponibilidad con varios nodos

Los directorios configurados para el uso de este gestor deben ser
siempre directorios visibles y compartidos por todas las instancias en
ejecución.

Este aspecto es especialmente importante en configuraciones de
servidores de aplicaciones en alta disponibilidad, donde puede haber
varios nodos que presten el servicio trifásico, cada uno de ellos en un
sistema de ficheros diferente. En este entorno, si se especifica una
ruta local, puede ocurrir que esta ruta apunte a un directorio distinto
en cada nodo (distinto servidor, disco diferente, otro sistema de
ficheros, etc.).

El que todos los nodos accedan al mismo directorio referenciado en la
configuración se puede lograr usando un almacenamiento compartido entre
todos ellos (con el mismo punto de montaje), mediante enlaces
simbólicos, etc. Es importante también asegurarse de que todos los nodos
tienen los permisos adecuados sobre los directorios configurados.

# Gestor de documentos “LegacyBatchDocumentManager”

El gestor de documentos LegacyBatchDocumentManager permite emular el
funcionamiento del antiguo mecanismo de firma de lotes, facilitando así
la migración al mecanismo descrito en el apartado <u>6.5 Firma de lotes
predefinidos</u>. Este gestor permite reutilizar los modos de
referenciación de documentos y los SignSaver que se usaban con el
mecanismo anterior. Sin embargo, este gestor sólo se debería utilizar
cuando no se puede abordar el desarrollo de un DocumentManager que
implemente las funciones que se necesiten, ya que este gestor es un mero
intermediario para comunicar un sistema con otro.

Tenga en cuenta que, a pesar de emular el funcionamiento antiguo, la
configuración de este gestor de documentos debe encontrarse en el
fichero “tps_config.properties”. El antiguo fichero
“signbatch_config.properties” sólo es necesario si se utiliza el antiguo
mecanismo de firma de lotes.

# Parámetros de uso y descripción del funcionamiento

Este gestor de documentos admite varias fuentes de datos:

- Permite recibir los datos directamente codificados en Base 64.

- Permite recibir una URL para el acceso a los datos (HTTP, HTTPS, FTP o
  FILE).

Por ejemplo, referencias válidas que se pueden utilizar son:

- wqFIb2xhIE11bmRvIQ==

  - Firma la cadena “¡Hola Mundo!”, que se obtiene al decodificar este
    Base 64.

- https://servidor.es/aplicacion/datos/prueba.txt

  - Firma el contenido del fichero prueba.txt obtenido al descargarlo a
    través de la URL.

- file://C:/datos/prueba.txt

  - Firma el contenido del fichero prueba.txt cargado desde disco.

En el fichero de configuración “tps_config.properties” se puede
configurar la propiedad “docmanager.legacybatch.allowedsources” para
establecer qué protocolos se pueden usar para el acceso a los datos y si
se permite indicar los datos en Base 64 o no. Consulte el apartado
<u>5.3.2.1 Configuración del servicio trifásico</u> para conocer el
listado completo de opciones de configuración.

El procesado y guardado de la firma lo realiza este gestor de documentos
a través de los SignSaver que se utilizaban en el antiguo mecanismo de
firma de lotes. Para seleccionar y configurar el SignSaver, se deberán
proporcionar una serie de propiedades de configuración a través del
parámetro extraParams del método de creación del lote o, si varía la
configuración para cada uno de los documentos, a través del extraParam
del método de agregar documentos al lote.

El SignSaver a utilizar se configurará por medio de la propiedad
“signSaver”. Con esta propiedad el administrador podrá configurar que
clase de guardado se utilizará. Esta puede ser una agregada por el al
servicio o una de las que se encuentran ya integradas. Las clases
integradas son:

- es.gob.afirma.signers.batch.SignSaverFile

  - Clase para el guardado de la firma en disco en el servidor.

  - Esta clase admite además la siguiente propiedad para su
    configuración:

    - FileName

      - Establece la ruta de guardado de la firma.

- es.gob.afirma.signers.batch.SignSaverHttpPost

  - Clase para el envío de la firma a un servidor remoto.

  - Esta clase admite además las siguientes propiedades para su
    configuración:

    - PostUrl

      - Configura la URL del servicio de guardado.

    - PostParamName

      - Nombre del parámetro en el que se agregará la firma.

Un ejemplo de llamada al método de agregar a documentos al lote cuando
se encuentre este gestor de documentos configurado podría ser:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>var</strong> ref1 = Base64.encode("Hola Mundo!!");</p>
<p><strong>var</strong> params1 =
"mode=implicit\nsignSaver=es.gob.afirma.signers.batch.SignSaverFile\nFileName=C:/Users/miusuario/firmas/firma1.csig";</p>
<p>AutoScript.addDocumentToBatch("1", ref1, "CAdES", "sign",
params1);</p>
<p><strong>var</strong> ref2 = "https://www.google.es";</p>
<p><strong>var</strong> params2 = "format=XAdES
Detached\nsignSaver=es.gob.afirma.signers.batch.SignSaverFile\nFileName=C:/Users/miusuario/firmas/firma2.xsig";</p>
<p>AutoScript.addDocumentToBatch("2", ref2, "XAdES", "sign",
params2);</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

Si ya disponía de una clase SignSaver propia, podrá seguir utilizándola
a través de esta clase gestora de documentos. Para ello, configure a
través del parámetro de configuración la propiedad “signSaver” con el
nombre completo de su clase y agregue al mismo parámetro cualquier
propiedad adicional que deba cargar su clase a través de su método init.

<img src="media/image19.png" style="width:0.91667in;height:0.32292in"
alt="Creative Commons License" />

Esta obra está bajo una licencia [Creative Commons
Reconocimiento-NoComercial-CompartirIgual 3.0
Unported](#Licencia_Creative_Commons).
