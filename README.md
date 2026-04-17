
 Punto 2 — Arquitectura y selección de librerías

2.a — Módulos nativos de Node.js a utilizar
La aplicación se desarrolla usando módulos nativos de Node.js, lo que permite construir un servidor sin dependencias externas para la lógica principal. A continuación se describen los módulos usados,  funciones y su justificación.

 Módulo http
Propósito general
El módulo http nos permite crear un servidor web  que sea capaz de recibir peticiones HTTP y enviar respuestas.
 Funciones usadas
•	http.createServer((req, res) => {}): crea el servidor y maneja las peticiones entrantes. 
•	server.listen(PORT): inicia el servidor en un puerto deeseado. 
•	res.writeHead(status, headers): define el código de estado y encabezados HTTP. 
•	res.write() / res.end():le envía contenido al cliente y finaliza la respuesta. 
 Justificación
Se eligió este módulo porque permite implementar un servidor web sin frameworks, lo cual cumple el objetivo  de poder entender el funcionamiento  del protocolo HTTP.

 Módulo fs (File System)
Propósito general
Permite interactuar con el sistema de archivos del sistema operativo.
Funciones utilizadas
•	fs.readFile(): lee archivos como noticias.txt o archivos estáticos. 
•	fs.appendFile(): agrega nuevas noticias al final del archivo sin sobrescribir el contenido. 

 Justificación
Se usa este módulo para tener persistencia de datos mediante archivos de texto, y evitar el uso de bases de datos y simplificando la lógica del proyecto.

Módulo url
Propósito general
Permite analizar URLs entrantes y extraer información estructurada como rutas y parámetros.
 Funciones / propiedades utilizadas
•	new URL(req.url, base): crea un objeto URL para su análisis. 
•	pathname: obtiene la ruta del recurso solicitado. 
•	searchParams.get('id'): obtiene  los parámetros enviados por query string. 
Justificación
Se usa  para poder manejar rutas dinámicas como /noticia?id=3, lo que permite generar contenido dinámico en base a parámetros enviados por el usuario.
