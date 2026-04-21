[![English](https://img.shields.io/badge/lang-en-blue.svg)](README_EN.md)

# eMuleModernWebInterface

Interfaz web moderna y adaptativa para el cliente P2P eMule. 

![alt text](image-2.png)

_¿Por qué usar estas plantillas?_

Me gusta eMule, pero su interfaz web es anticuada para dispositivos móviles, ofreciendo una UX (experiencia de usuario) pésima y dificultándome el control remoto de mi cliente eMule cuando quiero descargar archivos (películas, series, etc.) y estoy fuera de casa. 

Este repositorio contiene plantillas personalizadas (`.tmpl`) diseñadas para renovar visualmente la interfaz web de control remoto de eMule, ofreciendo una experiencia de usuario contemporánea, rápida y compatible con dispositivos móviles y tablets.

También se ha actualizado la interfaz para vista de escritorio.

**_¿No existía ya Mobile Mule?_**

Mobile Mule fue originalmente diseñada para teléfonos ya antiguos, capaces de ejecutar aplicaciones **Java (J2ME)**, pero su desarrollo se abandonó hace años. 

En 2026 se considera obsoleta; **es mucho más eficiente usar la Web Interface desde el navegador del móvil**. Es por eso que he decidido crear estas plantillas.

## Archivos

### 📄 `Modern_eMule.tmpl`

- **Tecnologías**: Utiliza Tailwind CSS, Google Fonts (Inter y JetBrains Mono) y efectos de glassmorphism.
- **Características**: Totalmente responsive (adaptable a móviles y tablets), modo oscuro profundo, animaciones sutiles y una disposición de elementos optimizada para la gestión remota.
- **Propósito**: Proporcionar una interfaz de vanguardia para los usuarios de la versión más reciente de la comunidad.

![alt text](image-5.png)

![alt text](image-6.png)

![alt text](image-7.png)

![alt text](image-8.png)

![alt text](image-9.png)

## Configuración

1. Localiza la carpeta de instalación de tu eMule (normalmente en `C:\Program Files\eMule\config` o donde se guarden los archivos del servidor web).
2. Haz una copia de seguridad de tu archivo `eMule.tmpl` actual (por ejemplo, `eMule_backup.tmpl`).
3. Copia el archivo de este repositorio (ej. `Modern_eMule.tmpl`) a esa carpeta.
4. Renombra el archivo a `eMule.tmpl`.
5. Habilita el servidor web en las Preferencias de eMule.
6. Establece la ruta de la plantilla en el _Template_ de la Web interface:

![alt text](image-3.png)

7. Aplica los cambios (_Aplicar_).

#### Recomendaciones
1. Establece contraseña para poder acceder a la interfaz web.
2. Habilita la _Gzip compression_ para mejorar el rendimiento.


### Cómo acceder a eMule desde red externa 

Si por ejemplo tu eMule está instalado en un PC con IP local `[IP_ADDRESS]` y el puerto del servidor web es el `4711`, y tratamos de conectarnos desde nuestro dispositivo móvil usando datos móviles (es decir, desde fuera de nuestra red local), no podremos conectarnos, ya que el router bloqueará la conexión. 

#### Port Forwarding
Para acceder a la interfaz web desde una red externa, debemos configurar el reenvío de puertos (port forwarding) en nuestro router. 

La configuración del reenvío de puertos varía según el modelo de router, pero en general, debemos seguir los siguientes pasos:

1. Acceder a la interfaz de administración de nuestro router. 
2. Buscar la sección de "Port Forwarding" o "Reenvío de puertos".
3. Crear una nueva regla de reenvío de puertos.  
4. Configurar la regla de la siguiente manera:
![alt text](image-1.png)

Una vez configurado lo anterior, abre el navegador de tu móvil/dispositivo externo y escribe en la barra de direcciones la dirección IP pública del PC donde tienes ejecutándose el eMule y el puerto configurado en el paso anterior:
```http
http://[PUBLIC_IP_ADDRESS]:4711
```
Ojo! 
> `[PUBLIC_IP_ADDRESS]` debe ser la IPv4 pública del PC que aloja el servicio eMule. Puedes consultarla en: https://whatismyipaddress.com/.    

> `4711` es el puerto configurado en el paso anterior. Puedes cambiarlo si lo deseas.

> Para que la Web Interface funcione, el ordenador debe estar encendido y el programa eMule debe estar ejecutándose.