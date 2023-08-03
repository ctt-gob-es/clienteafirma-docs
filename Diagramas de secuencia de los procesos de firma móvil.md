---
title: Diagramas de secuencia de los procesos de firma móvil
---

# Firma monofásica (Windows 8 / Windows RT y Android)

![](media/image1.emf)**Descripción**

1.  El usuario inicia un trámite desde su navegador, activando un flujo
    de trabajo JavaScript

2.  El flujo JavaScript arranca una App nativa de firma electrónica
    mediante una invocación por protocolo.

3.  La App nativa realiza la firma electrónica.

4.  La App nativa deposita la firma electrónica en un servidor
    intermedio.

5.  El flujo JavaScript recupera la firma electrónica desde el servidor
    intermedio y termina el proceso de negocio.

6.  El usuario termina su trámite en el navegador Web.

# Firma trifásica (Apple iOS)

![](media/image2.emf)

**Descripción**

1.  El usuario inicia un trámite desde su navegador, activando un flujo
    de trabajo JavaScript

2.  El flujo JavaScript arranca una App nativa de firma electrónica
    mediante una invocación por protocolo.

3.  La App nativa solicita la prefirma al servidor (1ª fase).

4.  La App nativa realiza la firma electrónica PKCS#1 (2ª fase).

5.  La App nativa solicita la postfirma al servidor (3ª fase).

6.  La App nativa deposita la firma electrónica en un servidor
    intermedio.

7.  El flujo JavaScript recupera la firma electrónica desde el servidor
    intermedio y termina el proceso de negocio.

8.  El usuario termina su trámite en el navegador Web.

# Firma trifásica en portafirmas (Apple iOS y Android)

![](media/image3.emf)

**Descripción**

1.  El usuario inicia un trámite desde su App nativa, activando el flujo
    de trabajo.

2.  La App nativa solicita al servidor intermedio la firma de un
    fichero.

3.  El servidor intermedio solicita el fichero binario al servidor de
    portafirmas (que a su vez tiene acceso al servidor documental).

4.  El servidor intermedio solicita la prefirma al servidor de firma (1ª
    fase), entregándola de vuelta a la App nativa.

5.  La App nativa realiza la firma electrónica PKCS#1 (2ª fase),
    devolviéndola al servidor intermedio.

6.  El servidor intermedio solicita la postfirma al servidor (3ª fase).

7.  El servidor intermedio deposita la firma electrónica en el servidor
    de portafirmas y se propaga hacia la App nativa la confirmación de
    la finalización correcta de la operación.
