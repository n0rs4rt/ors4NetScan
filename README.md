![ORS4 Net Scan Banner](https://github.com/n0rs4rt/ors4nmap/blob/c76d995fd71d1bb7eea9e7df76cb3fe37468edd6/assets/ors4net.jpg)

# ORS4 Net Scan

Herramienta de análisis de red desarrollada en Python, diseñada para técnicos, administradores y entusiastas que necesitan centralizar tareas de diagnóstico en una sola interfaz.  
Permite realizar escaneos completos de dispositivos, puertos y servicios, con detección de vulnerabilidades y recopilación de información relevante del entorno.  
Los resultados pueden exportarse en **JSON, CSV o PDF**, facilitando la documentación, auditorías y reportes.

La herramienta es totalmente **portable**, no requiere instalación y puede ejecutarse desde cualquier ubicación.  

[ Descargar última versión](https://github.com/n0rs4rt/Ors4NetScan/releases/download/v1.2/Or4NetScan.zip)

---

## Descripción general

**ORS4 Net Scan** reúne en un único panel varias funciones que normalmente requieren ejecutar múltiples comandos o utilizar diferentes herramientas.  
Permite descubrir hosts activos en la red, analizar puertos, servicios y versiones, intentar identificar el sistema operativo, consultar vulnerabilidades conocidas a través de scripts NSE, resolver IPs de dominios, identificar fabricantes a partir de direcciones MAC y más.

La herramienta combina **automatización** (para tareas rápidas y frecuentes) con **flexibilidad**, ofreciendo una opción de comandos personalizados para usuarios que necesitan exprimir al máximo Nmap sin salir del entorno de ORS4 Net Scan.

---

##  Requisitos y dependencias

ORS4 Net Scan depende de algunas herramientas y servicios externos para funcionar correctamente.

### 1. Nmap (obligatorio para funciones de escaneo)

Es necesario tener **Nmap instalado en el sistema** para usar las siguientes funciones:

- Escaneo de red local (hosts activos)
- Detección de sistema operativo
- Escaneo de puertos, servicios y versiones
- Escaneo de vulnerabilidades (NSE)
- Ejecución de comandos Nmap personalizados (opción avanzada)

> **Nota:**  
> La descarga de esta herramienta ya incluye todo lo necesario para su funcionamiento, incluyendo el binario de Nmap y las dependencias requeridas.  
> Si deseas contar siempre con la versión más reciente de Nmap, puedes instalarla directamente desde su sitio web oficial

### 2. Conexión a Internet (obligatoria para funciones específicas)

Las siguientes opciones requieren acceso activo a Internet:

- **Identificar fabricante (MAC)**  
  Consulta un servicio remoto (API) para obtener el fabricante asociado a la dirección MAC.
- **Mostrar mi IP pública**  
  Obtiene tu IP publica a través de un servicio online.
- **Mostrar IP asociada a un dominio (DNS)**  
  Realiza una resolución DNS remota para devolver la IP del dominio indicado.
- **Escaneo de vulnerabilidades (NSE)**  
  Requiere conexión para consultar información actualizada sobre vulnerabilidades.

Si no hay conexión, estas funciones no podrán devolver resultados válidos.

### 3. Compatibilidad

- Sistema operativo: **Windows 10/11**
- El usuario final **no necesita tener Python instalado**, ya que se distribuye en formato ejecutable (`.exe`).

---

![Vista general de ORS4 Net Scan](https://github.com/n0rs4rt/ors4nmap/blob/f78b85a2422b94bd6026d630a8653f869dcdfb95/assets/menu-principal.png)

##  Funciones principales

A continuación se describen las opciones del menú principal de ORS4 Net Scan.

### 1. Escanear red local (ver IPs activas)

Realiza un escaneo de la red local para detectar hosts activos y muestra:

- Lista de todas las IPs encontradas.
- Posibilidad de filtrar resultados por IP o por dirección MAC.
- Opción para **exportar**:
  - Todos los hosts encontrados, o
  - Solo los resultados filtrados (por IP o MAC).

### 2. Detección de sistema operativo de host(s)

Intenta identificar el sistema operativo de los equipos objetivo:

- Puede analizar **una IP específica**.
- También puede trabajar sobre **todas las IP detectadas previamente** en el escaneo de red local.

> Para obtener información de SO en otros apartados (por ejemplo, junto a escaneos de puertos), es recomendable ejecutar primero esta opción.

### 3. Escanear puertos, servicios y versiones

Permite distintas modalidades de escaneo de puertos:

- Escanear **puertos comunes** de una sola IP.
- Escanear **puertos comunes** de todas las IP detectadas previamente.
- Escanear **todos los puertos** o un **rango personalizado** en una IP concreta.

Durante el análisis se intenta identificar servicios y versiones asociados a los puertos abiertos.  
Algunos tipos de escaneo pueden ser más lentos pero más precisos.

### 4. Escanear vulnerabilidades conocidas (NSE)

Realiza escaneos utilizando scripts NSE para detectar vulnerabilidades conocidas:

- Escaneo completo de vulnerabilidades sobre una IP y un conjunto amplio de puertos.
- Escaneo más rápido utilizando puertos personalizados.

Los resultados muestran exactamente lo que devuelve Nmap y sus scripts, sin aplicar filtros adicionales.  
Para obtener información actualizada sobre vulnerabilidades es **necesaria conexión a Internet**.

### 5. Identificar fabricante (MAC)

Permite consultar el fabricante de un dispositivo a partir de su dirección MAC:

- Se envía la MAC a un servicio remoto que mantiene una base de datos actualizada de fabricantes.
- Si la dirección se encuentra registrada, devuelve el proveedor (vendor) asociado.
- El servicio admite un número alto de consultas diarias por IP.

### 6. Mostrar mi IP pública

Muestra la **IP pública** asignada por tu proveedor de internet, consultando un servicio remoto.  
Es útil para verificar la IP con la que sales a Internet sin abrir el navegador.

### 7. Mostrar IP asociada a un dominio (DNS)

Realiza una **resolución DNS** para mostrar la dirección IP asociada a un dominio indicado por el usuario.

Ejemplo:  
`ejemplo.com → 93.184.216.34`

### 8. Cargar escaneos exportados (Historial)

Permite cargar y visualizar escaneos previamente exportados por la herramienta, siempre que:

- Los archivos se mantengan en sus carpetas originales.
- No hayan sido modificados manualmente.

Es útil para revisar resultados antiguos sin volver a ejecutar un escaneo completo.

### 9. Ejecutar comando Nmap personalizado

Opción pensada para usuarios avanzados:

- Permite escribir y ejecutar directamente **cualquier comando Nmap** desde la interfaz de ORS4 Net Scan.
- No aplica automatizaciones ni simplificaciones: el comportamiento depende completamente del comando definido por el usuario.

---

##  Capturas de pantalla
## Deteccion de Puertos
![Puertos](https://github.com/n0rs4rt/Ors4NetScan/blob/1ced2238929ca7347a381a6119023b5cbbc683ad/assets/puertos.png)

## Deteccion de vulnerabilidades
![Vulnerabilidades](https://github.com/n0rs4rt/Ors4NetScan/blob/1ced2238929ca7347a381a6119023b5cbbc683ad/assets/vulnerabilidades.png)


##  Preguntas frecuentes (FAQ)

###  **1. El script no muestra correctamente los iconos o caracteres en la consola. ¿A qué se debe?**
Esto suele ocurrir por dos motivos principales:

- El script se está ejecutando como **Administrador**, y en ese modo Windows lo ejecuta con CMD el cual es una terminal obsoleta y restringe ciertos caracteres.
- La terminal utilizada no soporta **Unicode moderno**, como ocurre con el CMD clásico o versiones antiguas.

**Recomendación:** utilizar **Windows Terminal** como consola predeterminada, ya que ofrece compatibilidad completa con iconos, emojis y codificación UTF-8.  
Opcionalmente, se puede instalar una terminal mas moderna alternativa incluida en el enlace del proyecto.

## Utilizar la terminal de windows de forma predeterminada:

Basta con ir a la siguiente configuracion (Windows 11)
![Windows Terminal](https://github.com/n0rs4rt/Ors4NetScan/blob/6dbe86e9b9c0c1a28decbbbcd437fed72eb3abc8/assets/terminal%20windows.png)
---

###  **2. Los nombres de los dispositivos (hostnames) no aparecen y son mostrados como “desconocido”.**
Esto puede deberse a varias causas:

- El router no soporta o no entrega correctamente los nombres de host.  
- Existe un firewall o filtrado que bloquea la resolución de nombres.  
- El escaneo se realiza por **Wi-Fi**, lo cual suele limitar la obtención de hostnames.  
- La red no cuenta con un **servidor DHCP** que gestione y registre adecuadamente los nombres.

En infraestructuras correctamente configuradas (empresas, routers profesionales, DHCP centralizado) los nombres suelen aparecer sin inconvenientes.

---

###  **3. El escaneo de puertos no detecta el sistema operativo.**
La detección de sistema operativo no siempre se incluye en un escaneo general.  
Para resultados precisos:

1. Ejecutar un **escaneo específico para detección de sistema operativo**.  
2. Luego realizar el escaneo de puertos.

El reconocimiento de OS requiere un tipo particular de fingerprint que no siempre está presente en un scan completo.

---

###  **4. No aparecen vulnerabilidades durante el análisis. ¿Es un fallo del script?**
No. Para identificar vulnerabilidades es necesario que el dispositivo objetivo:

- Esté encendido.  
- Tenga puertos abiertos.  
- Responda al escaneo.  
- No esté protegido por un firewall restrictivo.

Si un dispositivo no expone puertos, no se detectará ninguna vulnerabilidad.  
Esto es completamente normal en sistemas protegidos o redes bien configuradas.

---

###  **5. El escaneo por Wi-Fi muestra resultados incompletos o inconsistentes.**
Las redes inalámbricas pueden generar interferencias, pérdida de paquetes, aislamiento de clientes o limitaciones del router.  
Para obtener resultados más confiables se recomienda realizar los escaneos **por cable Ethernet**.

---

##  Notas adicionales
- Windows Terminal es la opción recomendada para visualizar correctamente el script.  
- Ejecutar el script como usuario estándar, no como Administrador.  
- En redes domésticas con routers básicos es normal que ciertos datos no se devuelvan.

---

## Dudas o errores
Si se presentan problemas de visualización, resultados incompletos o errores inesperados, se puede comunicar vía mensaje directo o comentario para revisar el caso.

---

## Consejos para mejores resultados
- Priorizar escaneos por cable.  
- Mantener Windows Terminal actualizada.  
- Considerar las limitaciones de los routers de gama baja.  
- Separar la detección de sistema operativo del escaneo general para obtener mayor precisión.
