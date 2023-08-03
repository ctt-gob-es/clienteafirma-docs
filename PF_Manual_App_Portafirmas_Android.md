<img src="media/image1.png" style="width:6.21875in;height:1.21875in"
alt="C:\Users\carlos.gamuci\AppData\Local\Microsoft\Windows\INetCache\Content.Word\logo_portafirmas.png" />

Manual Portafirmas Android

Versión 1.8.0

# Índice de contenidos

[1 Descarga del portafirmas
[3](#descarga-del-portafirmas)](#descarga-del-portafirmas)

[2 Portafirmas Android [4](#portafirmas-android)](#portafirmas-android)

[3 Primera ejecución [5](#primera-ejecución)](#primera-ejecución)

[4 Acceder al Portafirmas
[6](#acceder-al-portafirmas)](#acceder-al-portafirmas)

[4.1 Selección del servidor de Portafirmas
[6](#selección-del-servidor-de-portafirmas)](#selección-del-servidor-de-portafirmas)

[4.1.1 Selección del servidor
[7](#selección-del-servidor)](#selección-del-servidor)

[4.1.2 Agregar nuevo servidor
[7](#agregar-nuevo-servidor)](#agregar-nuevo-servidor)

[4.1.3 Modificar un servidor existente
[7](#modificar-un-servidor-existente)](#modificar-un-servidor-existente)

[4.1.4 Eliminar un servidor
[8](#eliminar-un-servidor)](#eliminar-un-servidor)

[4.2 Acceso con certificado local
[8](#acceso-con-certificado-local)](#acceso-con-certificado-local)

[4.3 Acceso con certificado remoto (Cl@ve Permanente)
[9](#acceso-con-certificado-remoto-clve-permanente)](#acceso-con-certificado-remoto-clve-permanente)

[4.4 Acceso con DNIe [10](#acceso-con-dnie)](#acceso-con-dnie)

[5 Selección de rol [12](#selección-de-rol)](#selección-de-rol)

[6 Bandejas de peticiones
[13](#bandejas-de-peticiones)](#bandejas-de-peticiones)

[6.1 Acceso como usuario firmante
[13](#acceso-como-usuario-firmante)](#acceso-como-usuario-firmante)

[6.1.1 Firma de peticiones con certificado local
[16](#firma-de-peticiones-con-certificado-local)](#firma-de-peticiones-con-certificado-local)

[6.1.2 Firma de peticiones con certificado remoto
[16](#firma-de-peticiones-con-certificado-remoto)](#firma-de-peticiones-con-certificado-remoto)

[6.1.3 Firma de peticiones con DNIe
[17](#firma-de-peticiones-con-dnie)](#firma-de-peticiones-con-dnie)

[6.2 Acceso como usuario validador
[17](#acceso-como-usuario-validador)](#acceso-como-usuario-validador)

[6.3 Filtrado de peticiones
[18](#filtrado-de-peticiones)](#filtrado-de-peticiones)

[6.4 Detalle de petición
[19](#detalle-de-petición)](#detalle-de-petición)

[7 Gestión de autorizaciones y validadores
[22](#gestión-de-autorizaciones-y-validadores)](#gestión-de-autorizaciones-y-validadores)

[7.1 Gestión de autorizaciones
[22](#gestión-de-autorizaciones)](#gestión-de-autorizaciones)

[7.2 Gestión de validadores
[26](#gestión-de-validadores)](#gestión-de-validadores)

[8 Gestión del sistema de notificaciones
[28](#gestión-del-sistema-de-notificaciones)](#gestión-del-sistema-de-notificaciones)

[ANEXO 1. Importar certificado de usuario
[29](#importar-certificado-de-usuario)](#importar-certificado-de-usuario)

# Descarga del portafirmas

El primer paso para el acceso al Portafirmas Android es la descarga de
la aplicación desde la Play Store. Para encontrarla podemos buscar por
“Port@firmas movil”.

<img src="media/image2.png" style="width:2.17323in;height:3.86614in" />

A continuación, pulsaremos sobre el botón “INSTALAR”.

# Portafirmas Android

El portafirmas de Asuntos Económicos y Transformación Digital es una
plataforma web para la gestión del flujo de peticiones de firma que
permite a sus usuarios revisar dichas peticiones, firmarlas, darles el
visto bueno o rechazarlas. El ministerio dispone de dos despliegues de
su portafirmas, pero también lo distribuye para que otros organismos
puedan implantarlo.

La aplicación móvil del portafirmas permite el acceso a cualquier
instancia del portafirmas del ministerio, o a cualquier instancia del
mismo desplegada por otros organismos. La aplicación móvil permite a sus
usuarios acceder y realizar las operaciones básicas sobre las peticiones
de firma de dicho usuario.

Un usuario sólo podrá acceder a una instancia del portafirmas si
previamente se le ha creado una cuenta para el mismo. Cualquier persona
que pueda acceder al portafirmas a través de la web podrá acceder al
mismo portafirmas desde la aplicación móvil.

El portafirmas móvil utiliza certificados electrónicos reconocidos tanto
para el acceso a la cuenta del usuario como para la firma de sus
peticiones. Estos pueden ser:

- Certificados locales instalados en el dispositivo.

- Certificados en la nube de Cl@ve Permanente.

Por defecto, los accesos se realizarán mediante certificados instalados
en el dispositivo, pero un usuario puede activar el uso de los
certificados remotos mediante la opción de menú “Usar certificados
remotos” de la pantalla principal de la aplicación móvil.

Su certificado, local o remoto, permite al portafirmas identificarle y
con ello identificar su cuenta del portafirmas seleccionado. Esto quiere
decir que no es necesario dar de alta este certificado en el servicio
portafirmas y que, si tiene cuenta en más de un portafirmas, podrá
acceder a todos ellos con el mismo certificado.

# Primera ejecución

<img src="media/image3.jpg" style="width:1.9685in;height:4.17323in" />Al
ejecutar la aplicación por primera vez se le mostrará al usuario la
ventana de presentación y el asistente de configuración del Portafirmas
móvil. Este asistente le facilitará configurar algunas de las opciones
de la aplicación:

- **Selección de portafirmas**: El Portafirmas móvil le permite acceder
  a múltiples portafirmas y ya viene configurado con la ruta de acceso a
  dos de ellos. Desde la primera ventana del asistente el usuario podrá
  seleccionar cuál de estos portafirmas debe establecerse como el por
  defecto o indicar que se va a utilizar otro Portafirmas distinto. El
  usuario podrá posteriormente cambiar entre los portafirmas
  configurados y agregar otros nuevos mediante la opción “Servidores
  Portafirmas” del menú de la pantalla principal de la aplicación. Para
  saber más, consulte el apartado “<u>4.1 Selección del servidor de
  Portafirmas</u>”.

> <img src="media/image4.jpg" style="width:1.9685in;height:4.17323in" />

- **Selección de origen del certificado:** El Portafirmas móvil permite
  el uso tanto de certificados locales como de certificados remotos para
  para las operaciones de autenticación y firma. Esta pantalla del
  asistente le permitirá configurar si desea usar por defecto un
  certificado local, un certificado remoto o su DNIe. Para el uso de un
  certificado local deberá haber importado el certificado tal como se
  describe en el “<u>ANEXO 1 Importar certificado de usuario</u>”. Para
  el uso de un certificado remoto, deberá haberse registrado en Cl@ve
  mediante certificado electrónico o de forma presencial
  (<https://clave.gob.es/clave_Home/registro/Como-puedo-registrarme.html>)
  y, posteriormente, activar su usuario de Cl@ve Permanente
  ([https://clave.gob.es/clave_Home/
  Clave-Permanente/Procedimientos.html](https://clave.gob.es/clave_Home/%20Clave-Permanente/Procedimientos.html)).
  Para usar DNIe, su dispositivo deberá contar con conexión NFC y usted
  disponer de un DNIe 3.0 o 4.0 con los certificados vigentes.

# Acceder al Portafirmas

El Portafirmas móvil permite conectar con múltiples Portafirmas
compatibles y autenticarse y firmar tanto con certificados locales como
certificados remotos. Al utilizar un certificado local, se usará este
para la autenticación del usuario y la firma de las peticiones. En el
caso de usar certificados remotos, se utilizará Cl@ve para la
autenticación (con su certificado de Cl@ve Permanente) y FIRe para la
firma (con su certificado de Cl@ve Firma).

## Selección del servidor de Portafirmas

El portafirmas móvil permite tener configuradas múltiples instancias de
Portafirmas. Si no se seleccionó mediante el asistente a qué Portafirmas
se desea acceder, se deberá hacer en este momento. La aplicación tiene
configurados por defecto los dos siguientes servidores Portafirmas:

- Portafirmas General AGE

- Portafirmas RedSARA

Un usuario puede acceder a cualquiera de estos portafirmas, dar de alta
otros, editarlos o eliminarlos.

El listado de servidores Portafirmas configurados puede verse desde la
pantalla inicial de la aplicación al pulsar el botón de menú y la opción
“Servidores Portafirmas”. Desde este diálogo se puede seleccionar un
servidor, agregar uno nuevo, editarlos y eliminarlos.

<img src="media/image5.png" style="width:2.09972in;height:3.59028in" />

### Selección del servidor

Para seleccionar a qué servidor Portafirmas deseamos acceder basta con
pulsar sobre el servidor deseado. Seguidamente, pulsaremos sobre el
botón “Aceptar”.

### Agregar nuevo servidor

Para agregar un servidor distinto a los que vienen por defecto,
pulsaremos en el botón “Nuevo servidor” del listado de servidores. En el
nuevo diálogo que aparecerá se introducirá el alias o nombre con el que
queremos referirnos al servidor y la URL del mismo. A continuación,
pulsaremos el botón “Aceptar”.

<img src="media/image6.png" style="width:2.26378in;height:3.83858in" />

La URL de un servidor Portafirmas deberá proporcionarla el organismo
responsable del mismo.

### Modificar un servidor existente

Para editar un servidor que ya tenemos dado de alta en la lista de
servidores, debemos mantener pulsado el elemento correspondiente hasta
que se abra el dialogo de edición. En este diálogo podemos modificar el
nombre y la URL del servidor. Para aplicar los cambios, pulsaremos sobre
el botón “Aceptar”.

<img src="media/image7.png" style="width:2.42847in;height:4.15105in" />

### Eliminar un servidor

Para eliminar un servidor portafirmas deberemos mantener pulsado el
elemento de la lista de servidores hasta que aparezca el diálogo de
edición. A continuación, pulsaremos el botón “Eliminar”.

Si el usuario elimina todos los servidores de la lista, automáticamente
se volverán a agregar los servidores por defecto.

## Acceso con certificado local

Para acceder al portafirmas seleccionado con certificado local,
deberemos disponer previamente de un certificado instalado en el
dispositivo tal como se indica en el apartado <u>ANEXO 1 Importar
certificado de usuario</u> y haber seleccionado el servidor portafirmas
deseado.

Para el uso del certificado local, comprobaremos que la opción “Usar
certificados remotos” del menú de la pantalla principal se encuentra
desactivado. A continuación, pulsaremos el botón “Acceder”.

El sistema operativo abrirá un diálogo con los certificados instalados
en el sistema en el que deberemos seleccionar aquel que se deseemos
utilizar. Después deberemos pulsar el botón “Permitir”.

<img src="media/image8.jpeg" style="width:2.54825in;height:2.91026in"
alt="Image 16a.jpg" />

**Advertencia:** El certificado seleccionado es el que se utilizará
tanto para la autenticación del usuario (mediante un proceso de
validación realizado por el propio Portafirmas web), como para la firma
de las peticiones. Por este motivo, se recomienda que se utilice siempre
un certificado de firma (no repudio) para acceder a la aplicación.

**Un usuario sólo podrá acceder a un servicio de portafirmas si dispone
de una cuenta en el mismo**. De no ser así, se producirá un error de
conexión.

La aplicación móvil establece una sesión con el Portafirmas web para
permitir ver y firmar las peticiones del usuario. Si el establecimiento
de sesión es correcto, el usuario será redirigido a la pantalla de
peticiones pendientes de firmar.

## Acceso con certificado remoto (Cl@ve Permanente)

Para acceder al portafirmas seleccionado con certificado remoto,
deberemos habernos dado previamente de alta en Cl@ve y activar Cl@ve
Permanente. Puede obtener más información sobre los procedimientos
necesarios en:

<https://clave.gob.es/clave_Home/clave.html>

Para configurar el Portafirmas móvil para el uso del certificado remoto,
marcaremos la opción “Usar certificados remotos” del menú de la pantalla
principal de la aplicación. A continuación, pulsaremos el botón
“Acceder”.

La aplicación móvil accederá a su cuenta de portafirmas con certificado
remoto por medio de Cl@ve Permanente que necesita que el usuario
introduzca su DNI y los datos de autenticación. La aplicación mostrará
para esto la página web de Cl@ve Permanente en donde el usuario podrá
insertar su DNI, la contraseña de Cl@ve y, si procede, el código enviado
a su teléfono por SMS.

<img src="media/image9.png" style="width:2.42847in;height:4.16147in" />
<img src="media/image10.png" style="width:2.42847in;height:4.17189in" />

**Advertencia:** No todos los servicios de portafirmas permiten el uso
de certificado remoto. Consulte con el proveedor de su portafirmas si
tiene dudas acerca de la disponibilidad de esta opción.

## Acceso con DNIe

Para acceder con su DNIe deberá disponer de un DNIe 3.0 o 4.0 con los
certificados vigentes y su dispositivo móvil deberá contar con conexión
NFC. En caso de que en el momento de iniciar la conexión con la tarjeta
el NFC del dispositivo se encuentre apagado, se redirigirá al usuario a
la pantalla de gestión de conexiones de Android y se le pedirá que lo
active.

Para poder conectar con su DNIe vía NFC, será necesario que primero
inserte el número CAN de su tarjeta. Puede encontrar este número de seis
dígitos en la zona inferior derecha del frontal de su tarjeta.

<img src="media/image11.jpg" style="width:1.69685in;height:3.38976in" />
<img src="media/image12.jpg" style="width:1.69685in;height:3.38976in"
alt="Interfaz de usuario gráfica, Aplicación Descripción generada automáticamente" />

Una vez insertado el número CAN deberá acercar su DNIe al reverso de su
dispositivo móvil. Cuando Android detecte la tarjeta emitirá un pitido
y/o una vibración, momento en el que se iniciará la conexión.

Una vez establecida la conexión, se pedirá al usuario que inserte el PIN
del DNIe para poder acceder a sus certificados.

<img src="media/image13.jpg" style="width:1.68898in;height:3.57874in"
alt="Interfaz de usuario gráfica, Texto, Aplicación Descripción generada automáticamente" />

En caso de insertar incorrectamente el PIN se abortará la operación de
acceso o firma. El diálogo de inserción de PIN muestra cuantos intentos
de inserción de PIN tiene disponible la tarjeta. Si ese número llega a
cero por haber introducido incorrectamente el PIN varias veces seguidas,
su DNIe quedará bloqueado y debería acudir a una comisaría de expedición
de DNIe para desbloquearlo a través de los kioscos habilitados.

La aplicación recordará el CAN y el PIN del DNIe para poder firmar las
peticiones sin volverlos a solicitar mientras dure la sesión del usuario
y no se interrumpa la conexión. Si en algún momento se interrumpe la
conexión entre el DNIe y la aplicación, se le volverá a pedir al usuario
que vuelva a acercar el DNIe al dispositivo (para lo cual es posible que
primero deba separarlo si no lo estaba para que el sistema operativo
vuelva a detectar la tarjeta) y se le volverá a pedir el PIN.

# Selección de rol

En caso de que el usuario tenga permitido el acceso con distintos roles,
tras acceder a la aplicación, se mostrará un listado con las distintas
opciones disponibles.

<img src="media/image14.png" style="width:2.20058in;height:4.22014in" />

El usuario podrá seleccionar el rol con el que desea acceder a la
aplicación. Una vez dentro, podrá cambiar de rol pulsando en la opción
“Cambiar rol” del menú.

# Bandejas de peticiones

Al entrar en el portafirmas, se accede a la pantalla que muestra la
bandeja de peticiones que el usuario tiene pendientes de procesar. Las
peticiones que puede ver y las acciones que puede realizar sobre ellas
dependerá de si accedió como usuario firmante o como validador de otro
usuario. Posteriormente el usuario podrá cambiar de rol desde la opción
correspondiente del menú.

## Acceso como usuario firmante

Se accede como usuario firmante cuando no se es validador de ningún otro
usuario o cuando se selecciona expresamente en la pantalla de selección
de rol.

Los usuarios firmantes verán por defecto el listado de peticiones que
tiene pendiente de firmar o aprobar. Si hubiese peticiones próximas a
caducar, se mostrarían al principio del listado:

<img src="media/image15.png" style="width:2.55208in;height:4.378in" />
<img src="media/image16.png" style="width:2.27083in;height:4.37946in" />

En este listado se muestran al usuario las peticiones pendientes
recibidas, quién la envío, el asunto del que trata, la criticidad y si
la petición debe firmarse
(<img src="media/image17.png" style="width:0.19792in;height:0.17708in" />)
o aprobarse
(<img src="media/image18.png" style="width:0.20833in;height:0.20833in" />).
Se puede actualizar el listado arrastrando la lista hacia abajo cuando
ya nos encontramos en la parte superior o mediante la opción de
actualizar del menú. Para ver el detalle de una petición se puede pulsar
sobre la misma.

Debe tenerse en cuenta que, si el usuario tiene validadores asignados,
por defecto sólo se le mostrarán las peticiones que estos hayan validado
previamente. Para ver todas las peticiones dirigidas a él, el usuario
debe acceder al apartado de filtros mediante la opción “Filtrar” del
menú de la pantalla, activarlos y seleccionar el tipo de petición “Todos
los tipos”.

Para firmar o aprobar peticiones desde este listado, un usuario puede
activar la casilla que se muestra a la derecha de cada petición y pulsar
el botón “Firmar/VºBº”. Cuando se pulse el botón, se mostrará al usuario
un resumen con el número de peticiones que se van a procesar:

<img src="media/image19.png" style="width:2.4433in;height:4.711in" />

También puede rechazarlas mediante el botón “Rechazar”. Cuando se
rechacen peticiones se permitirá al usuario indicar el motivo por el que
se rechazan. Indicar este dato es opcional.

<img src="media/image20.png" style="width:2.42708in;height:4.65191in" />

Es posible seleccionar todas las peticiones de la pantalla mediante la
opción “Seleccionar todas” del menú para así procesarlas
simultáneamente.

Al procesar una petición, si el proceso se realiza correctamente, la
petición pasa a la bandeja de “Firmadas”. Al rechazar peticiones, estas
pasan a la bandeja de “Rechazadas”. Pueden visualizarse estas bandejas
de peticiones las opciones de menú “Ver solicitudes firmadas” y “Ver
solicitudes rechazadas”, respectivamente.

### Firma de peticiones con certificado local

La firma de peticiones con certificado local se realiza con el mismo
certificado que se haya seleccionado para el acceso al Portafirmas. El
uso de este certificado es transparente para el usuario.

### Firma de peticiones con certificado remoto

La firma de peticiones con certificado remoto se realiza con el
certificado de firma de Cl@ve Firma del usuario. Para hacer uso de este
certificado se redirige al usuario a la página de FIRe desde el que
puede seleccionarlo. Seguidamente deberá introducir su contraseña de
Cl@ve y el código recibido por SMS a su número de móvil asociado.

<img src="media/image21.png" style="width:2.42913in;height:4.15748in" />
<img src="media/image22.png" style="width:2.42913in;height:4.16142in" />

### Firma de peticiones con DNIe

La firma de peticiones con DNIe se realiza con el certificado de firma
del DNIe. Si no se ha interrumpido la conexión con el DNIe desde el
acceso o última firma, la firma de las peticiones se realizará de forma
transparente al usuario. Si se interrumpió, se pedirá al usuario que
vuelva a acercar el DNIe al dispositivo y que inserte su PIN.

## Acceso como usuario validador

Cuando un usuario accede como usuario validador no ve las peticiones que
se le envían a él, sino las peticiones enviadas al usuario del cual es
validador. Su función es la de revisar estas peticiones y validarlas
para que así aparezca en la bandeja de peticiones pendientes de la
persona responsable de darles visto bueno o firmarlas.

<img src="media/image23.png" style="width:2.43307in;height:4.6811in" />

El usuario validador ve por defecto únicamente las peticiones que están
pendientes de validar. Si fuese necesario ver también las peticiones ya
validadas, puede cambiarlo mediante el filtro “Tipo de petición”,
accesible mediante la opción “Filtrar” del menú del listado de
peticiones pendientes. Se puede actualizar el listado arrastrando la
lista hacia abajo cuando ya nos encontramos en la parte superior o
mediante la opción de actualizar del menú.

## Filtrado de peticiones

Desde cualquiera de las bandejas de peticiones podemos activar los
filtros para que se muestren solamente aquellas peticiones que cumplan
las condiciones establecidas en esos campos. Esto puede hacerse a través
de la opción “Filtrar” del menú contextual de los listados. Este diálogo
también permite seleccionar el criterio de ordenación del listado.

<img src="media/image24.png" style="width:2.13166in;height:3.90364in" />

## Detalle de petición

Pulsando directamente en una petición accederemos a una pantalla para
ver su información. Entre ella veremos el asunto, referencia, la fecha
de envío, la fecha de caducidad (si aplica), la aplicación desde la que
se envía, el motivo de rechazo (si aplica), los remitentes y el mensaje
asociado.

<img src="media/image25.png" style="width:2.43264in;height:4.73658in" />

Desde esta pantalla también se puede firmar, dar visto bueno, rechazar o
validar una petición pendiente a través que los botones que aparecen en
la parte superior de la pantalla. Estos procesos son análogos a los
realizados desde el listado de peticiones pendientes, pero afectarán
únicamente a esta petición y a sus documentos.

La pestaña “Líneas de firma” muestra el flujo de vistos buenos y firmas
que seguirá la petición, quienes deberán procesarla y la operación en
cuestión a realizar (Firma o Visto Bueno). Cuando se indica que la firma
de una petición es “en cascada”, se indica que deberá procesarla uno de
los individuos de una línea de firma antes que la petición llegue a los
de la siguiente línea. Cuando la petición sea “en paralelo” los
individuos de las distintas líneas de firma podrán procesarla en
paralelo.

<img src="media/image26.png" style="width:2.47569in;height:4.22582in" />

La pestaña “Documentos” contiene los documentos que se van a firmar y,
si existen (y la versión del Portafirmas web al que se conecta lo
soporta), los documentos anexos a la petición, los cuales no se firman
nunca, pero pueden ayudar al usuario a determinar si debe firmar los
documentos. Estos documentos se podrán abrir o visualizar siempre que el
dispositivo disponga de una aplicación asociada al tipo de documento.

Cuando se visualice el detalle de una petición firmada se podrá también
descargar las firmas generadas y visualizar los documentos con el
detalle de las firmas (informes de firma).

<img src="media/image27.png" style="width:2.47569in;height:4.22582in" />

# Gestión de autorizaciones y validadores

La aplicación móvil permite gestionar las autorizaciones y los
validadores del usuario cuando se accede a una versión del Portafirmas
que soporte esta funcionalidad. De ser el caso, podremos hacerlo a
través de la opción “Configuración” del menú del listado de peticiones.
Esta opción sólo está disponible cuando se accede como usuario firmante.

## Gestión de autorizaciones

El listado de autorizaciones muestra todas aquellas autorizaciones que
hemos concedido o que nos han concedido a nosotros, independientemente
del estado en el que se encuentren.

De cada autorización del listado podemos ver:

1.  Mediante el primer icono, si la autorización se ha enviado
    (<img src="media/image28.png" style="width:0.16535in;height:0.16535in" />)
    o recibido
    (<img src="media/image29.png" style="width:0.16535in;height:0.16535in" />).

2.  Mediante el segundo icono, el estado de la petición: activa
    (<img src="media/image30.png" style="width:0.16667in;height:0.16667in" />),
    revocada
    (<img src="media/image31.png" style="width:0.16667in;height:0.16667in" />)
    o pendiente de aprobar
    (<img src="media/image32.png" style="width:0.16667in;height:0.16667in" />).

3.  El emisor o receptor de la autorización, según si la hemos recibido
    o enviado, respectivamente.

4.  La fecha de revocación de la autorización si ya no está activa o si
    está activa, pero tiene fecha de caducidad.

<img src="media/image33.png" style="width:2.42913in;height:4.66929in" />

Al pulsar sobre una de las autorizaciones podremos ver el detalle de la
misma: quien la envía o recibe, el estado, fecha de inicio y fin y
descripción. En caso de tratarse de una autorización pendiente o activa,
también aparecerán los botones que nos permitirán realizar las distintas
opciones disponibles sobre ella:

- Cancelar aquellas peticiones activas o las peticiones pendientes que
  hayamos enviado nosotros.

- Aceptar o revocar las peticiones pendientes que nos hayan enviado.

<img src="media/image34.png" style="width:2.42913in;height:4.66929in" />
<img src="media/image35.png" style="width:2.42913in;height:4.66929in" />

Se puede dar de alta una nueva autorización pulsando el botón “Añadir
nuevo” cuando se esté mostrando el listado de autorizaciones. A
continuación, se nos mostrará un buscador desde el que podremos buscar y
seleccionar al usuario al que queremos autorizar. La búsqueda puede
realizarse mediante nombre o DNI.

<img src="media/image36.png" style="width:2.42913in;height:4.66929in" />

Una vez seleccionado el usuario, podremos configurar los datos relativos
a la autorización:

- Fecha y hora de inicio. Si no se indican, se utilizará la fecha y hora
  actuales.

- Fecha y hora de caducidad. Si no se indican, la autorización no
  caducará.

- Tipo de autorización: delegado o sustituto.

- Observaciones opcionales.

<img src="media/image37.png" style="width:2.42913in;height:4.6811in" />

La autorización se crea al pulsar en el botón “Crear autorización”, pero
no estará activa hasta que el usuario al que se ha enviado la acepte.

## Gestión de validadores

El listado de validadores muestra los usuarios encargados de validar las
peticiones que recibimos antes de que se nos muestren en nuestra bandeja
de peticiones pendientes. El Portafirmas móvil no distingue entre
validadores generales o aquellos que sólo gestionan aplicaciones
concretas.

<img src="media/image38.png" style="width:2.42913in;height:4.66929in" />

Se puede dar de alta a un nuevo validador pulsando el botón “Añadir
nuevo” cuando se esté mostrando el listado de validadores. A
continuación, se nos mostrará un buscador desde el que podremos buscar y
seleccionar al usuario al que queremos nombrar validador. La búsqueda
puede realizarse mediante nombre o DNI. Al pulsar sobre el usuario en
cuestión, se nos pedirá confirmación para darlo de alta como validador.

<img src="media/image39.png" style="width:2.42913in;height:4.66929in" />
<img src="media/image40.png" style="width:2.46124in;height:4.6951in" />

Podemos dar de baja a un validador con sólo pulsar sobre el mismo en el
listado de validadores. Al hacerlo, se nos pedirá confirmación antes de
darlo de baja.

# Gestión del sistema de notificaciones

Cuando el servidor Portafirmas al que se conecte lo soporte, en el menú
contextual de los listados de peticiones le aparecerá la opción
“Habilitar notificaciones” o “Deshabilitar notificaciones”. En caso de
habilitar esta opción, el usuario actual recibirá notificaciones en su
dispositivo cada vez que reciba una nueva petición en el Portafirmas al
que esté conectado.

<img src="media/image41.png" style="width:3.74409in;height:0.64961in" />

Al pulsar sobre una de las notificaciones el usuario podrá acceder al
portafirmas web en cuestión.

En caso de deshabilitarlas, se cancelará la subscripción al sistema de
notificaciones.

# Importar certificado de usuario

Para importar el certificado de usuario es necesario primero guardar el
archivo del certificado en el sistema de ficheros. Este archivo debe
contener la clave privada ya que se usará para firmar. En general la
extensión de este fichero será .pfx o .p12. El archivo se puede copiar
desde el ordenador conectando el dispositivo o se puede enviar como
adjunto en un correo.

Con el archivo ya en el sistema de ficheros, pulsar en “Importar
Certificado”. Se abrirá una nueva pantalla que permite recorrer las
carpetas del sistema y localizar el archivo anterior. La pantalla del
diálogo de selección de fichero puede variar según la versión de
Android.

<img src="media/image42.png" style="width:2.23622in;height:3.79134in" />

Seleccionamos el archivo, introducimos la clave que permite su uso y le
asignamos un nombre que es el que se visualizará cuando queramos
conectarnos al portafirmas:

<img src="media/image43.png" style="width:2.24651in;height:3.80461in" />
<img src="media/image44.png" style="width:2.27608in;height:3.82325in" />

Al aceptar, el certificado se importa en el almacén del dispositivo y ya
está listo para ser usado.

<img src="media/image45.png" style="width:0.91667in;height:0.32292in"
alt="Creative Commons License" />

Esta obra está bajo una licencia.
