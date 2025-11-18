![ORS4 Net Scan Banner](https://github.com/n0rs4rt/ors4nmap/blob/c76d995fd71d1bb7eea9e7df76cb3fe37468edd6/assets/ors4net.jpg)

# ORS4 Net Scan

Herramienta de análisis de red desarrollada en Python, pensada para técnicos, administradores y entusiastas que necesitan centralizar tareas básicas y avanzadas de diagnóstico en una sola interfaz.

[🔗 Descargar última versión](URL_DESCARGA_AQUI)

---

## Descripción general

**ORS4 Net Scan** reúne en un único panel varias funciones que normalmente requieren ejecutar múltiples comandos o utilizar diferentes herramientas.  
Permite descubrir hosts activos en la red, analizar puertos, servicios y versiones, intentar identificar el sistema operativo, consultar vulnerabilidades conocidas a través de scripts NSE, resolver IPs de dominios, identificar fabricantes a partir de direcciones MAC y más.

La herramienta combina **automatización** (para tareas rápidas y frecuentes) con **flexibilidad**, ofreciendo una opción de comandos personalizados para usuarios que necesitan exprimir al máximo Nmap sin salir del entorno de ORS4 Net Scan.

---

## 🔧 Requisitos y dependencias

ORS4 Net Scan depende de algunas herramientas y servicios externos para funcionar correctamente.

### 1. Nmap (obligatorio para funciones de escaneo)

Es necesario tener **Nmap instalado en el sistema** para usar las siguientes funciones:

- Escaneo de red local (hosts activos)
- Detección de sistema operativo
- Escaneo de puertos, servicios y versiones
- Escaneo de vulnerabilidades (NSE)
- Ejecución de comandos Nmap personalizados (opción avanzada)

> **Nota:** Nmap para Windows incluye Npcap/WinPcap, necesarios para ciertos tipos de escaneo.  
> Se recomienda instalarlo desde el sitio oficial de Nmap.

### 2. Conexión a Internet (obligatoria para funciones específicas)

Las siguientes opciones requieren acceso activo a Internet:

- **Identificar fabricante (MAC)**  
  Consulta un servicio remoto (API) para obtener el fabricante asociado a la dirección MAC.
- **Mostrar mi IP pública**  
  Obtiene la IP externa a través de un servicio online.
- **Mostrar IP asociada a un dominio (DNS)**  
  Realiza una resolución DNS remota para devolver la IP del dominio indicado.
- **Escaneo de vulnerabilidades (NSE)**  
  Algunos scripts requieren conexión para consultar información actualizada sobre vulnerabilidades.

Si no hay conexión, estas funciones no podrán devolver resultados válidos.

### 3. Compatibilidad

- Sistema operativo: **Windows 10/11**
- Puede requerir ejecutar la herramienta con **permisos de administrador** para ciertos tipos de escaneo.
- El usuario final **no necesita tener Python instalado**, ya que se distribuye en formato ejecutable (`.exe`).

---

![Vista general de ORS4 Net Scan](https://github.com/n0rs4rt/ors4nmap/blob/f78b85a2422b94bd6026d630a8653f869dcdfb95/assets/menu-principal.png)

## 🧩 Funciones principales

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

- Se envía la MAC a un servicio remoto (API) que mantiene una base de datos actualizada de fabricantes.
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

## 🖼️ Capturas de pantalla

```markdown
![Puertos](https://github.com/n0rs4rt/Ors4NetScan/blob/1ced2238929ca7347a381a6119023b5cbbc683ad/assets/puertos.png)
![Vulnerabilidades][(URL_CAPTURA_ESCANEO_AQUI)](https://github.com/n0rs4rt/Ors4NetScan/blob/1ced2238929ca7347a381a6119023b5cbbc683ad/assets/vulnerabilidades.png)
