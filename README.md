Banco de 100 Preguntas de Evaluación: Programación de Dispositivos Móviles con Flutter y TDD

Este banco de evaluación ha sido diseñado para medir el dominio teórico y práctico de los alumnos en el desarrollo de aplicaciones móviles con Flutter, guiado por la metodología de Desarrollo Guiado por Pruebas (TDD) y principios de Arquitectura Limpia. La estructura abarca desde los fundamentos de interfaz y consumo de servicios hasta algoritmos avanzados de realidad aumentada, sincronización distribuida, persistencia relacional y arquitectura de ecosistemas digitales.

Guía Didáctica y Criterios de Evaluación

El presente instrumento evalúa cuatro dimensiones clave del aprendizaje:

1. Dominio del Ciclo TDD: Habilidad para concebir pruebas unitarias en Dart puro antes de implementar la lógica y refactorizar sin romper comportamiento.
2. Arquitectura y Aislamiento de Capas: Comprensión del patrón Puerto/Adaptador y separación entre lógica de dominio, datos e interfaz.
3. Manejo de Casos de Borde e Invariantes: Identificación de fallas potenciales en concurrencia, limites de tipos numéricos, horas de silencio, red y persistencia.
4. Seguridad y Resiliencia: Aplicación de buenas prácticas en protección de llaves API, sanitización de datos y degradación elegante.

Módulo 1: Fundamentos de Flutter, UI y Consumo de APIs HTTP

Pregunta 1

¿Cuál es la función principal del widget FutureBuilder en aplicaciones que consumen APIs externas como la de CoinGecko o TMDB?

* A) Ejecutar peticiones HTTP en un hilo aislado de fondo indefinidamente.
* B) Construir la interfaz de manera reactiva en función del estado de una operación asíncrona (ConnectionState.waiting, hasData, hasError).
* C) Cachear automáticamente la respuesta JSON en el almacenamiento persistente del dispositivo.
* D) Convertir cadenas JSON en mapas de Dart sin necesidad de jsonDecode.

Pregunta 2

En el desarrollo de la aplicación del clima usando la API de OpenWeatherMap, ¿por qué es indispensable el uso del widget CircularProgressIndicator dentro del árbol de widgets?

* A) Para pausar la ejecución del SDK de Flutter mientras se activa el GPS.
* B) Para ofrecer retroalimentación visual al usuario durante el estado de carga (ConnectionState.waiting) y evitar pantallas en blanco.
* C) Para medir la velocidad de descarga de la conexión a internet.
* D) Para forzar el redibujado de toda la pantalla cada segundo.

Pregunta 3

Al construir una URL dinámica para servicios como Cataas (Cats as a Service) o Wikipedia a partir de un TextField, ¿qué función de Dart debe emplearse para evitar romper la sintaxis de la URI al incluir espacios o caracteres especiales?

* A) Uri.encodeComponent() o Uri.encodeQueryComponent().
* B) String.replaceAll().
* C) jsonEncode().
* D) utf8.encode().

Pregunta 4

¿Qué código de respuesta HTTP indica que el cliente ha excedido la cuota permitida de peticiones a un servicio web (Rate Limit)?

* A) HTTP 400 Bad Request.
* B) HTTP 401 Unauthorized.
* C) HTTP 429 Too Many Requests.
* D) HTTP 503 Service Unavailable.

Pregunta 5

En el paquete http de Dart, ¿qué sucede por defecto cuando una petición HTTP retorna un código de estado 404 o 500?

* A) Lanza automáticamente una excepción de tipo SocketException.
* B) Retorna un objeto http.Response donde statusCode refleja el código del servidor, sin lanzar excepción por sí solo.
* C) Cierra la aplicación de manera abrupta por falla irrecuperable.
* D) Reintenta la petición automáticamente hasta cinco veces.

Pregunta 6

¿Cuál es la ventaja de transformar la respuesta en bytes UTF-8 mediante http.Response.bytes(utf8.encode(...)) durante las pruebas unitarias de servicios web?

* A) Incrementar la velocidad de ejecución de las pruebas en un 50%.
* B) Preservar correctamente la codificación de caracteres especiales (acentos, eñes) evitando corrupción de texto.
* C) Encriptar los datos para que no se puedan leer en los logs de la consola.
* D) Simular una latencia de red de baja velocidad.

Pregunta 7

En el widget ListView.builder, ¿qué propiedad determina la cantidad exacta de elementos a renderizar de forma perezosa?

* A) itemExtent.
* B) itemCount.
* C) shrinkWrap.
* D) scrollDirection.

Pregunta 8

¿Para qué se utiliza el método setState() en un StatefulWidget dentro de aplicaciones interactivas sencillas como el convertidor de criptomonedas?

* A) Para registrar una nueva ruta en el historial de navegación de Flutter.
* B) Para notificar al marco de trabajo que el estado interno ha cambiado y se requiere recalcular el método build().
* C) Para guardar la información en memoria flash antes de cerrar la app.
* D) Para reiniciar el ciclo de vida del widget desde initState().

Pregunta 9

Al trabajar con campos numéricos ingresados mediante TextField (como montos en USD para conversión a crypto), ¿cuál es la forma correcta de parsear el texto a número decimal controlando entradas inválidas?

* A) int.parse(text).
* B) double.parse(text).
* C) double.tryParse(text) y verificar si el resultado es null.
* D) text as double.

Pregunta 10

¿Qué rol cumple el parámetro headers: {'Accept': 'application/json'} en una petición HTTP cliente?

* A) Exigir al servidor que autoclave la conexión.
* B) Informar explícitamente al servidor el formato de contenido esperado por la aplicación cliente.
* C) Encriptar la cabecera de la petición mediante TLS.
* D) Indicar al dispositivo que no guarde imágenes en la memoria caché.

Módulo 2: Metodología TDD en Dart Puro (Rojo, Verde, Refactor)

Pregunta 11

¿Cuál es la secuencia estricta de pasos que define el ciclo del Desarrollo Guiado por Pruebas (TDD)?

* A) 1. Escribir código, 2. Escribir pruebas, 3. Corregir errores.
* B) 1. Rojo (escribir prueba que falle), 2. Verde (código mínimo para pasar), 3. Refactor (ordenar sin romper comportamiento).
* C) 1. Diseñar UI, 2. Escribir pruebas de integración, 3. Compilar APK.
* D) 1. Refactor, 2. Verde, 3. Rojo.

Pregunta 12

¿Por qué se exige que la carpeta de lógica de dominio (por ejemplo lib/dominio/) no contenga importaciones del paquete flutter ni de plugins de infraestructura?

* A) Para permitir que las pruebas unitarias se ejecuten en Dart puro en milisegundos, sin depender del motor gráfico ni de dispositivos.
* B) Para reducir el tamaño de descarga de la aplicación desde la Google Play Store.
* C) Porque el lenguaje Dart prohíbe importar Flutter fuera de la carpeta lib/presentacion/.
* D) Para evitar requerir permisos de internet en el dispositivo.

Pregunta 13

Durante la etapa Rojo en TDD, ¿cuál es el significado de que una prueba falle correctamente?

* A) Que la herramienta de pruebas tiene un error de configuración.
* B) Que la prueba es capaz de detectar la ausencia de la funcionalidad o un comportamiento erróneo antes de implementar el código.
* C) Que el compilador de Dart ha detectado un bucle infinito.
* D) Que la computadora no tiene conexión a la red local.

Pregunta 14

En el principio de la etapa Verde en TDD, ¿qué cantidad de código se debe escribir?

* A) La implementación completa y optimizada con todos los casos de borde futuros.
* B) El código estrictamente mínimo y suficiente para lograr que la prueba pase a verde.
* C) Únicamente comentarios explicativos del algoritmo.
* D) El diseño visual completo del widget en Flutter.

Pregunta 15

¿Qué actividad está permitida durante la etapa de Refactor en TDD?

* A) Agregar nuevas funcionalidades que no estén cubiertas por pruebas existentes.
* B) Mejorar la nombres, estructura y legibilidad del código manteniendo todas las pruebas en verde sin modificar el comportamiento externo.
* C) Eliminar las pruebas que causen advertencias de linter.
* D) Cambiar los requisitos de negocio acordados con el cliente.

Pregunta 16

Al probar algoritmos numéricos o matemáticos delicados en Dart (como la similitud de cadenas en Levenshtein o el desglose de IVA), ¿qué buena práctica se recomienda para definir los valores esperados?

* A) Adivinar los valores a ojo durante la ejecución de la prueba.
* B) Calcular los casos de prueba previamente a mano o mediante un script independiente en otro lenguaje (como Python).
* C) Dejar la aserción en blanco hasta ver qué imprime el programa.
* D) Redondear todos los resultados al entero más cercano.

Pregunta 17

¿Qué función de la biblioteca flutter_test se utiliza para comparar el valor obtenido contra el valor esperado en una prueba unitaria?

* A) assert().
* B) expect(actual, matcher).
* C) verify().
* D) check().

Pregunta 18

En el contexto de TDD, ¿qué es una prueba de regresión?

* A) Una prueba que mide el tiempo de respuesta de la interfaz de usuario.
* B) Una prueba existente en la suite que confirma que los cambios o refactorizaciones recientes no han roto funcionalidades que previamente funcionaban.
* C) Una prueba que se ejecuta únicamente cuando el dispositivo pierde conexión a internet.
* D) Una prueba diseñada para fallar intencionalmente en producción.

Pregunta 19

¿Qué representa el comparador closeTo(valor, tolerancia) en las pruebas de Dart?

* A) Compara si dos cadenas de texto tienen una longitud similar.
* B) Verifica que un valor numérico de tipo double se encuentre dentro de un margen o tolerancia específica respecto al valor esperado.
* C) Comprueba si dos objetos residen en direcciones de memoria cercanas.
* D) Determina si una fecha está próxima a la hora actual.

Pregunta 20

¿Por qué se considera mala práctica modificar una prueba que estaba en verde solo para hacer que vuelva a pasar tras introducir un cambio que rompió el comportamiento?

* A) Porque incrementa el tiempo de compilación del proyecto.
* B) Porque destruye la red de seguridad del TDD, enmascarando un fallo en la lógica de negocio en lugar de corregir la implementación.
* C) Porque Dart genera un error de sintaxis en tiempo de ejecución.
* D) Porque inhabilita el uso de la memoria caché del navegador.

Módulo 3: Arquitectura Limpia, Inyección de Dependencias y Patrón Puerto/Adaptador

Pregunta 21

En el patrón de Arquitectura Limpia con Puertos y Adaptadores (Hexagonal), ¿qué representa una clase abstracta como PuertoNotificaciones o PuertoPush?

* A) La implementación concreta vinculada al SDK del sistema operativo.
* B) El contrato o interfaz que define lo que el dominio necesita del mundo exterior, aislando la lógica de los detalles de infraestructura.
* C) La vista o pantalla que interactúa directamente con el usuario final.
* D) La base de datos SQLite en memoria.

Pregunta 22

¿Qué es la Inyección de Dependencias y cuál es su beneficio principal en TDD?

* A) La importación automática de paquetes desde pub.dev al compilar.
* B) Pasar las dependencias de una clase (como el reloj, repositorios o puertos) a través de su constructor, permitiendo sustituirlas por dobles de prueba (Mocks o Falsos).
* C) Insertar código SQL directamente en los controladores de la vista.
* D) Ejecutar múltiples aislamientos (isolates) en paralelo para procesar peticiones.

Pregunta 23

En la práctica de "Ajolotito Hambriento", ¿por qué se reemplaza la llamada directa a DateTime.now() por una abstracción Reloj?

* A) Porque DateTime.now() no funciona en dispositivos Android 13.
* B) Para permitir que las pruebas unitarias controlen el paso del tiempo mediante un RelojFalso sin tener que esperar horas reales en la ejecución.
* C) Para formatear automáticamente la fecha en español.
* D) Para sincronizar la hora del dispositivo con un servidor NTP en la nube.

Pregunta 24

¿Qué diferencia a una clase "Doble de Prueba" de tipo Falso (PuertoFalso / AlmacenMemoria) de una implementación real?

* A) El Falso ejecuta la lógica real llamando a APIs en la nube pero sin guardar archivos.
* B) El Falso implementa la misma interfaz guardando el estado en memoria de forma simplificada y determinista, sin tocar el SO ni plugins.
* C) El Falso es generado automáticamente por el compilador de Flutter.
* D) El Falso solo funciona cuando el dispositivo está en modo avión.

Pregunta 25

¿Qué es el "Composition Root" (Raíz de Composición) en un proyecto de Flutter?

* A) El archivo pubspec.yaml donde se configuran los activos visuales.
* B) El único lugar de la aplicación (generalmente en main.dart o dependencias.dart) donde se instancian las implementaciones reales y se conectan las dependencias.
* C) El método build() del widget raíz MaterialApp.
* D) La tabla principal de la base de datos relacional.

Pregunta 26

En la arquitectura propuesta para "SuperApp Dolores", ¿por qué las mini-apps reciben únicamente un ContextoMiniApp en lugar de la instancia completa de Plataforma?

* A) Para evitar que la aplicación supere el límite de memoria RAM.
* B) Para aplicar el Principio de Menor Privilegio, limitando el acceso de cada mini-app estrictamente a los permisos y servicios autorizados.
* C) Porque Dart impide pasar clases complejas a widgets secundarios.
* D) Para acelerar el renderizado de gráficos 2D.

Pregunta 27

¿Qué ventaja ofrece abstraer el cliente HTTP detrás de una interfaz o usar MockClient de http/testing.dart?

* A) Permitir probar la respuesta a escenarios como HTTP 500, timeouts o JSON roto de forma instantánea sin tumbar el servidor real.
* B) Hacer que el servidor responda el doble de rápido en producción.
* C) Evitar configurar los permisos de internet en el AndroidManifest.xml.
* D) Convertir automáticamente respuestas HTML a widgets de Flutter.

Pregunta 28

¿Qué principio de diseño se aplica al invertir una lista de datos para reutilizar un algoritmo de desplazamiento horizontal (como en Nieves 2048 o en Geodesia) en lugar de duplicar código?

* A) Principio de Única Responsabilidad y Reutilización de Lógica Base (DRY - Don't Repeat Yourself).
* B) Herencia Múltiple Dinámica.
* C) Encapsulamiento Nulo.
* D) Programación Orientada a Aspectos.

Pregunta 29

Si se actualiza la versión de un paquete de terceros (por ejemplo flutter_local_notifications), ¿en qué capa del proyecto debe realizarse la adaptación si se aplicó el patrón Puerto/Adaptador?

* A) En todos los ViewModel y widgets de la aplicación.
* B) Únicamente dentro del archivo del adaptador de infraestructura (ej. lib/infra/puerto_real.dart), manteniendo intacto el dominio y las pruebas.
* C) En el archivo de configuración pubspec.yaml excluyendo el código Dart.
* D) En la base de datos SQLite.

Pregunta 30

¿Qué caracteriza a un modelo de dominio "puro" en Dart?

* A) Estar compuesto de variables globales accesibles desde cualquier archivo.
* B) Ser agnóstico a Flutter, no importar paquetes de interfaz ni plugins de terceros, y ser 100% testeable de forma independiente.
* C) Contener instrucciones de pintado gráfico con Canvas.
* D) Requiere compilación previa en código C++.

Módulo 4: Gestor de Estado ViewModel, Reactividad y Manejo de Estados de UI

Pregunta 31

¿Cuál es la responsabilidad principal de un ViewModel (usando ChangeNotifier) en la arquitectura de la aplicación?

* A) Realizar peticiones HTTP directas sin usar servicios ni repositorios.
* B) Exponer el estado de la pantalla a la vista, reaccionar a las acciones del usuario, coordinar el dominio y notificar cambios mediante notifyListeners().
* C) Dibujar los píxeles de los botones en la pantalla.
* D) Almacenar las credenciales del usuario de forma encriptada en disco.

Pregunta 32

¿Qué estados fundamentales se deben gestionar explícitamente en el ViewModel para representar el ciclo de vida de una pantalla orientada a datos (ej. Directorio Dolorense)?

* A) creado, destruido, pausado.
* B) inicial, cargando, listo, vacio y error.
* C) activo, inactivo, suspendido.
* D) online, offline.

Pregunta 33

¿Qué widget de Flutter se utiliza para escuchar los cambios de un ChangeNotifier y redibujar únicamente la sub-rama de la interfaz afectada?

* A) ListenableBuilder (o AnimatedBuilder).
* B) Container.
* C) SingleChildScrollView.
* D) Column.

Pregunta 34

Al implementar la interacción en vivo con el usuario (como un buscador de negocios o productos), ¿qué técnica previene que se lance una petición HTTP por cada tecla presionada?

* A) Inyección de código en el servidor.
* B) Pausa por Debounce (temporizador que espera una pausa de e.g. 400 ms de inactividad antes de consultar).
* C) Forzar el apagado del teclado virtual.
* D) Duplicar la memoria RAM asignada al widget.

Pregunta 35

¿Qué sucede si un ViewModel olvida invocar notifyListeners() tras actualizar una variable interna observada por la interfaz?

* A) La aplicación lanza un error de compilación inmediato.
* B) La variable cambia en memoria pero la interfaz de usuario no se redibuja, mostrando datos desactualizados.
* C) La base de datos SQLite elimina el registro.
* D) Se envía una notificación push al servidor.

Pregunta 36

¿Por qué se recomienda instanciar el ViewModel en el initState() del StatefulWidget o mediante una fábrica inyectada?

* A) Para garantizar que el objeto sobreviva a las reconstrucciones repetidas del widget padre y mantener su ciclo de vida controlado.
* B) Porque de lo contrario Flutter no permite usar formularios.
* C) Para asegurar que la app corra en modo de 60 fotogramas por segundo.
* D) Para habilitar la rotación automática de pantalla.

Pregunta 37

En el manejo de formularios (como el cobro en Caja o registro de usuarios), ¿cuál es el papel del ViewModel ante un error de validación producido en el dominio?

* A) Cerrar la pantalla inmediatamente.
* B) Capturar la excepción de negocio y exponer un mensaje seguro (mensajeError) para que la vista lo muestre al usuario de forma clara.
* C) Imprimir el stack trace completo en un diálogo emergente.
* D) Ignorar el error y continuar el flujo.

Pregunta 38

En el patrón Carga<T> utilizado en el tablero de 5 APIs de "Dolores Hoy", ¿qué beneficio aporta tener un estado de carga independiente por cada servicio/tarjeta?

* A) Que las 5 APIs compartan la misma dirección IP.
* B) Resiliencia y degradación elegante: si una API falla, su tarjeta muestra un estado de error específico mientras las otras 4 continúan funcionando normalmente.
* C) Reducir el consumo de batería en un 80%.
* D) Evitar requerir una clave de API.

Pregunta 39

¿Qué método del ciclo de vida de un State en Flutter debe utilizarse para liberar los recursos de un ViewModel o TextEditingController (ej. mediante dispose())?

* A) initState().
* B) build().
* C) dispose().
* D) didUpdateWidget().

Pregunta 40

¿Cómo se verifica en una prueba unitaria de ViewModel (usando flutter_test) que se emitió la secuencia correcta de estados (ej. de cargando a listo)?

* A) Inspeccionando el color del pixel central de la pantalla.
* B) Agregando un oyente (vm.addListener(...)) que registre cada cambio de estado en una lista antes de llamar al método asíncrono.
* C) Leyendo el archivo de logs del sistema operativo.
* D) Reiniciando el simulador en cada aserción.

Módulo 5: Persistencia Local con SQLite, Transacciones y Manejo Finito del Dinero

Pregunta 41

En aplicaciones financieras o de punto de venta (como "Punto de Venta Dolorense"), ¿por qué es una regla de oro evitar el uso de tipos de datos double para representar montos de dinero?

* A) Porque el tipo double requiere el doble de espacio en disco que un entero.
* B) Porque la representación binaria de coma flotante introduce errores de imprecisión decimal (ej. 0.1 + 0.2 = 0.30000000000000004) que descuadran los cortes de caja.
* C) Porque la base de datos SQLite no soporta números reales.
* D) Porque el lenguaje Dart no permite aplicar operaciones matemáticas a variables double.

Pregunta 42

¿Cómo se debe representar internamente un precio de $1,234.56 en el modelo de dominio para garantizar cálculos exactos?

* A) Como una cadena de texto "1234.56".
* B) Como un entero de centavos: 123456.
* C) Como un arreglo de enteros [1234, 56].
* D) Como un flotante de 32 bits.

Pregunta 43

En las pruebas unitarias de persistencia con sqflite, ¿qué configuración se utiliza para probar las consultas SQL en memoria sin crear archivos físicos en el sistema de archivos?

* A) path = "/tmp/test.db".
* B) inMemoryDatabasePath proporcionado por el paquete sqflite_common_ffi.
* C) path = "null".
* D) Un archivo JSON temporal.

Pregunta 44

Al ejecutar el cobro de un carrito en el repositorio de ventas, ¿por qué es crítico envolver las operaciones de actualización de inventario e inserción de la venta en una transacción SQL atómica (db.transaction)?

* A) Para comprimir los datos antes de guardarlos en el disco.
* B) Para garantizar que todas las operaciones se completen con éxito o se reviertan completamente (rollback) si ocurre una falla, evitando inventarios inconsistentes o ventas a medias.
* C) Para evitar que la pantalla parpadee al presionar el botón de cobro.
* D) Para cifrar los precios de los productos.

Pregunta 45

¿Cuál es la responsabilidad del método aMapa() y del constructor desdeMapa() en una clase de modelo de dominio relacional (como Producto)?

* A) Convertir la interfaz visual a código Dart.
* B) Servir de traductor de ida y vuelta entre los objetos fuertemente tipados de Dart y los mapas clave-valor que entiende el driver de SQLite.
* C) Cargar las imágenes del producto desde una red CDN.
* D) Generar la clave primaria de forma aleatoria.

Pregunta 46

Si al intentar insertar un producto con un código de barras duplicado SQLite lanza una excepción técnica (DatabaseException por restricción UNIQUE), ¿qué debe hacer el repositorio?

* A) Mostrar el mensaje de error de SQL directamente en la pantalla del usuario.
* B) Capturar la excepción técnica de la base de datos y relanzar una excepción de dominio con nombre propio (ej. CodigoDuplicadoException).
* C) Ignorar la inserción y continuar en silencio.
* D) Cerrar la base de datos y volverla a abrir.

Pregunta 47

En el desglose de IVA (16%) a partir de un total que ya incluye impuestos (ej. $116.00 total), ¿cuál es la fórmula matemática exacta para obtener el IVA en centavos?

* A) totalCentavos * 0.16.
* B) porcentaje(totalCentavos, 16).
* C) totalCentavos - (totalCentavos * 100 ~/ 116).
* D) totalCentavos / 1.16.

Pregunta 48

¿Por qué se debe revalidar la existencia de inventario suficiente dentro de la transacción SQL de cobro, aun cuando el carrito de compras ya haya validado las existencias previamente en memoria?

* A) Porque el carrito en memoria no sabe formatear números.
* B) Para evitar condiciones de carrera (race conditions) donde el inventario haya cambiado entre el momento de agregar al carrito y el momento exacto del cobro.
* C) Porque SQLite requiere al menos tres consultas por transacción.
* D) Para calcular las comisiones de la tarjeta de crédito.

Pregunta 49

En una consulta SQL para obtener el corte de caja del día (corteDelDia), ¿qué función de agregación SQL permite retornar 0 en lugar de NULL si no se realizaron ventas en el periodo?

* A) COUNT(*).
* B) COALESCE(SUM(total_centavos), 0).
* C) MAX(total_centavos).
* D) AVG(total_centavos).

Pregunta 50

¿Qué beneficio aporta el patrón Repositorio al aislar la base de datos SQLite detrás de una interfaz?

* A) Que la vista pueda ejecutar sentencias SQL SELECT directamente.
* B) Que el resto de la app use el almacenamiento sin saber si los datos vienen de SQLite local, memoria o un servidor web, facilitando las pruebas y el mantenimiento.
* C) Que no se requiera definir tipos de datos para los modelos.
* D) Que la base de datos se actualice automáticamente en Google Drive.

Módulo 6: Notificaciones Locales vs. Push (FCM), Canales y Manejo de Antesegundo Plano

Pregunta 51

¿Cuál es la diferencia fundamental entre una notificación local (flutter_local_notifications) y una notificación Push (firebase_messaging)?

* A) Las notificaciones locales requieren servidor en la nube y las push no.
* B) Las notificaciones locales son programadas y gestionadas por el propio dispositivo sin internet; las push son enviadas desde un servidor externo a través de la nube.
* C) Las notificaciones push no funcionan cuando la aplicación está cerrada.
* D) Las notificaciones locales solo pueden contener texto sin formato.

Pregunta 52

En el desarrollo de "Ajolotito Hambriento", ¿qué regla de oro gobierna la frecuencia y momento de envío de notificaciones locales al usuario?

* A) Enviar notificaciones cada 15 minutos sin importar la hora.
* B) Respetar las reglas de buena educación (ej. no notificar en horas de silencio entre 22:00 y 08:00 salvo urgencias explícitas) y pedir permiso en el momento oportuno.
* C) Solicitar el permiso del sistema operativo inmediatamente al abrir la app por primera vez.
* D) Reintentar la notificación indefinidamente si el usuario la ignora.

Pregunta 53

¿Qué cambio crítico introdujo Android 13 (API 33) respecto a las notificaciones que afecta a las aplicaciones de Flutter?

* A) Prohibió el uso de imágenes en las notificaciones.
* B) Requirió la solicitud explícita en tiempo de ejecución del permiso POST_NOTIFICATIONS.
* C) Eliminó los canales de notificación.
* D) Obligó al uso de Firebase en todas las aplicaciones.

Pregunta 54

En el manual de "Lotería Push", ¿cuál es la premisa arquitectónica fundamental sobre la relación entre el mensaje Push y el servidor backend?

* A) El mensaje Push contiene la verdad absoluta e inmutable del juego.
* B) "El push es un AVISO; el servidor es la VERDAD." La app usa el push para enterarse, pero sincroniza con el servidor para corregir huecos, desorden o pérdidas.
* C) Si un push se pierde, la aplicación debe reiniciarse desde cero.
* D) El servidor sólo envía notificaciones cuando la app está abierta en primer plano.

Pregunta 55

¿Por qué el API de Firebase Cloud Messaging (FCM) exige que todos los valores dentro del mapa data de una notificación push sean de tipo String?

* A) Porque las cadenas de texto son el único tipo de dato soportado por el protocolo de red subyacente de FCM entre plataformas (Android/iOS).
* B) Para evitar que los desarrolladores usen números enteros.
* C) Porque Dart no soporta mapas con valores heterogéneos.
* D) Para acelerar la velocidad de encriptación SSL.

Pregunta 56

Al recibir notificaciones Push en FCM, ¿cuáles son los tres estados posibles de la aplicación móvil y qué manejador responde en cada uno?

* A) online, offline, desconectado.
* B) Primer plano (onMessage), segundo plano (onMessageOpenedApp) y cerrada (getInitialMessage / onBackgroundMessage).
* C) inicial, cargando, listo.
* D) debug, profile, release.

Pregunta 57

¿Qué requisito estricto debe cumplir la función anotada con @pragma('vm:entry-point') que procesa notificaciones FCM en segundo plano (onBackgroundMessage)?

* A) Debe ser un método de instancia dentro de un widget de tipo StatefulWidget.
* B) Debe ser una función de nivel superior (top-level), fuera de cualquier clase, y no puede interactuar directamente con la interfaz de usuario.
* C) Debe retornar un objeto de tipo BuildContext.
* D) Debe ejecutarse dentro del método main() antes de runApp().

Pregunta 58

¿Qué es el payload de una notificación y cuál es su utilidad al ser tocada por el usuario?

* A) Es la imagen decorativa del icono de la app.
* B) Es una cadena de texto oculta codificada en el mensaje que indica a la app a qué pantalla específica o acción navegar al abrirse.
* C) Es el certificado de seguridad SSL del servidor.
* D) Es el código identificador de la red Wi-Fi.

Pregunta 59

¿Para qué sirven los Canales de Notificación (NotificationChannel) en Android?

* A) Para medir el tráfico de datos consumido por la app.
* B) Para categorizar los avisos (ej. "cartas" vs. "momento importante") permitiendo al usuario configurar la importancia, sonido y vibración de cada categoría de forma independiente.
* C) Para transmitir video en tiempo real.
* D) Para conectar la app con redes sociales.

Pregunta 60

Al migrar de Tokens de FCM hacia Identificadores de Instalación de Firebase (FID / FirebaseInstallations), ¿por qué la arquitectura limpia minimiza el impacto en el código?

* A) Porque el FID se guarda automáticamente en SQLite.
* B) Porque el destino de notificación se abstrajo como un objeto de valor DestinoPush en el dominio, limitando el cambio al adaptador de infraestructura (PuertoFcm).
* C) Porque el compilador de Dart realiza la conversión automáticamente.
* D) Porque los FIDs no requieren permisos de sistema.

Módulo 7: Buenas Prácticas de Seguridad, Manejo de Secretos y Defensa en Capas

Pregunta 61

¿Por qué constituye una falla grave de seguridad guardar claves privadas de APIs (como la API Key de la NASA, OpenAI o Stripe) directamente en el código fuente de una aplicación móvil Flutter?

* A) Porque incrementa el tiempo de inicio de la aplicación en un segundo.
* B) Porque cualquier persona puede extraer las claves descompilando el archivo APK/IPA o inspeccionando las cadenas del binario.
* C) Porque el servidor de Google Play rechaza aplicaciones con texto plano.
* D) Porque el lenguaje Dart elimina las cadenas constantes al compilar.

Pregunta 62

¿Cuál es la forma recomendada en Flutter de ingresar llaves de API al compilar sin escribirlas en el código rastreable por Git?

* A) Escribirlas en los comentarios del archivo main.dart.
* B) Pasar las llaves durante la compilación mediante --dart-define o --dart-define-from-file=secrets.json y leerlas con String.fromEnvironment().
* C) Guardarlas en la carpeta assets/images/.
* D) Solicitar al usuario que teclee la llave cada vez que abre la app.

Pregunta 63

En una arquitectura cliente-servidor profesional, ¿cuál es el nivel más alto de seguridad (Nivel 4) para proteger llaves de APIs costosas o sensibles?

* A) Cifrar la llave con base64 dentro de la app.
* B) Implementar un servidor Proxy backend que guarde la llave de forma privada, autogestione las peticiones hacia la API externa y autentique a la app cliente.
* C) Cambiar la llave de API todos los días a medianoche.
* D) Guardar la llave en las preferencias compartidas (SharedPreferences).

Pregunta 64

Al escribir logs de depuración o rastreo en producción, ¿qué responsabilidad tiene la función ClienteSeguro.redactar(Uri uri)?

* A) Convertir la URL a mayúsculas.
* B) Sanitizar los parámetros sensibles de la URL (reemplazando valores de api_key o token por ***) para evitar filtración de secretos en consolas o servicios de monitoreo.
* C) Eliminar los acentos de los parámetros.
* D) Comprimir la dirección URL mediante algoritmo GZIP.

Pregunta 65

¿Qué regla de seguridad en el manejo de excepciones establece la función mensajeSeguro(Object error) en las aplicaciones evaluadas?

* A) Mostrar siempre el stack trace completo con rutas de archivos locales para ayudar al usuario.
* B) Diferenciar las excepciones esperadas de dominio (ErrorDeApp) de las no controladas, mostrando mensajes amables y genéricos ante errores inesperados para evitar filtrar detalles técnicos a potenciales atacantes.
* C) Enviar un correo al desarrollador cada vez que ocurre un error.
* D) Silenciar todos los errores y mostrar una pantalla en blanco.

Pregunta 66

Al recibir URLs de recursos desde APIs de terceros (como imágenes de Wikipedia o la NASA), ¿qué validación de seguridad realiza la función soloHttps(url)?

* A) Verifica que la imagen tenga dimensiones cuadradas.
* B) Revisa que la dirección utilice estrictamente el esquema https://, descartando esquemas inseguros (http://) o potencialmente maliciosos (javascript:, file://).
* C) Descarga la imagen en segundo plano antes de mostrarla.
* D) Cambia la extensión de la imagen a PNG.

Pregunta 67

En el cliente HTTP seguro (ClienteSeguro), ¿por qué se impone un límite explícito de tamaño en bytes (maxBytes) a las respuestas recibidas?

* A) Para ahorrar memoria RAM en el servidor web.
* B) Para prevenir ataques de denegación de servicio local por agotamiento de memoria si un servidor responde con un payload masivo o inesperado.
* C) Porque el SDK de Flutter no puede procesar archivos de más de 1 KB.
* D) Para acelerar la velocidad de animación de la interfaz.

Pregunta 68

Al almacenar información altamente sensible en el dispositivo (como tokens de autenticación o tarjetas de crédito tokenizadas), ¿qué paquete debe utilizarse en lugar de SharedPreferences?

* A) path_provider.
* B) flutter_secure_storage (que utiliza Keystore en Android y Keychain en iOS).
* C) sqflite sin contraseña.
* D) dart:io.

Pregunta 69

En el algoritmo de validación de tarjetas de crédito (Algoritmo de Luhn), ¿cuál es su propósito primario antes de llamar a la pasarela de pagos?

* A) Verificar que la tarjeta tenga fondos suficientes para la compra.
* B) Validar la integridad sintáctica del número de tarjeta mediante su suma de verificación de dígitos, evitando peticiones erróneas a la red de pagos.
* C) Obtener el nip secreto del cuentahabiente.
* D) Transferir el monto directamente a la cuenta del vendedor.

Pregunta 70

¿Qué previene la implementación de una Clave de Idempotencia (Idempotency Key) en las peticiones a una pasarela de pagos durante una falla de red?

* A) Que la tarjeta de crédito expire durante la transacción.
* B) Que un reintento de cobro por parte de la aplicación genere un cargo doble al cliente si la primera petición llegó a procesarse en el servidor.
* C) Que el banco rechace la tarjeta por falta de firma.
* D) Que la pantalla cambie de color durante el proceso.

Módulo 8: Geodesia, Realidad Aumentada (AR), Sensores y CustomPainter

Pregunta 71

En las aplicaciones de geodesia y realidad aumentada ("Rally" y "Dolores AR"), ¿qué calcula la fórmula de Haversine entre dos coordenadas geográficas (latitud, longitud)?

* A) La diferencia de altitud en metros sobre el nivel del mar.
* B) La distancia sobre la superficie de la esfera terrestre (distancia en ortodrómica) medida en metros o kilómetros.
* C) La velocidad promedio del usuario al caminar.
* D) El nivel de batería consumido por el sensor GPS.

Pregunta 72

¿Qué representa el azimut o rumbo en grados (rumboGrados) entre una posición de origen y una de destino?

* A) La distancia vertical entre ambos puntos.
* B) El ángulo en grados respecto al Norte magnético/geográfico (de 0° a 360°) hacia el cual se encuentra el punto de destino.
* C) El porcentaje de precisión del sensor GPS.
* D) La hora del día calculada por el sol.

Pregunta 73

En el problema directo de la geodesia (función destino(origen, rumbo, distancia)), ¿qué resultado se obtiene?

* A) La distancia recorrida tras 10 minutos de caminata.
* B) Una nueva coordenada geográfica (latitud, longitud) resultante de desplazar el punto de origen una distancia dada en metros siguiendo un rumbo determinado.
* C) El nombre de la calle del punto de llegada.
* D) La velocidad angular del giroscopio.

Pregunta 74

Al proyectar la posición de un objeto en la pantalla de la cámara mediante el campo de visión horizontal (FOV), ¿cómo se calcula la posición horizontal relativa x (de 0.0 a 1.0)?

* A) Dividiendo la latitud entre la longitud.
* B) Mapeando la diferencia angular entre el rumbo del dispositivo y el rumbo hacia el objeto dentro del abanico del FOV (donde el centro de la pantalla es 0.5).
* C) Multiplicando la distancia en metros por el número de píxeles.
* D) Asignando un valor aleatorio entre 0 y 1.

Pregunta 75

¿Por qué se requiere un algoritmo especial (diferenciaAngular) para calcular la distancia angular entre dos rumbos en lugar de una resta simple?

* A) Porque los rumbos se miden en radianes en lugar de grados.
* B) Porque la escala de acimut es circular (0° a 360°), por lo que la diferencia entre 350° y 10° debe ser de 20° (cruzando el Norte) y no de 340°.
* C) Porque los sensores de la brújula solo entregan valores pares.
* D) Porque la curvatura de la Tierra deforma la resta.

Pregunta 76

Al promediar lecturas continuas de la brújula magnética para evitar vibraciones en las etiquetas de AR, ¿por qué falla un promedio aritmético estándar cerca del Norte?

* A) Porque el valor de la latitud se vuelve cero.
* B) Porque promediar valores cercanos al salto de la discontinuidad (ej. 359° y 1°) daría un promedio erróneo de 180° (Sur), haciendo que la pantalla dé un giro violento.
* C) Porque el magnetómetro se apaga al detectar el Norte.
* D) Porque el paquete flutter_compass se bloquea.

Pregunta 77

En la función de suavizado angular (suavizarAngulo), ¿cómo se resuelve la interpolación sin sufrir saltos en la discontinuidad de 0°/360°?

* A) Convirtiendo las lecturas a números enteros.
* B) Calculando la diferencia angular corta mediante diferenciaAngular y aplicando un factor de suavizado (lpha) antes de normalizar de nuevo a 0..360^\circ.
* C) Multiplicando el valor por \pi.
* D) Reiniciando el sensor en cada muestra.

Pregunta 78

¿Qué papel cumple la clase CustomPainter en la creación del widget de radar polar?

* A) Cargar imágenes JPG desde internet.
* B) Ofrecer un lienzo (Canvas) 2D para dibujar formas geométricas personalizadas (círculos concéntricos, líneas de barrido y puntos de objetos) mediante coordenadas cartesianas traducidas desde polares.
* C) Renderizar modelos 3D complejos con iluminación en tiempo real.
* D) Detectar toques táctiles en la pantalla.

Pregunta 79

En la integración de modelos 3D en Realidad Aumentada con model_viewer_plus, ¿cuáles son los dos formatos de archivo 3D estándar utilizados para Android (Scene Viewer) e iOS (Quick Look) respectivamente?

* A) .obj y .fbx.
* B) .glb (o .gltf) para Android y .usdz para iOS.
* C) .stl y .blend.
* D) .png y .svg.

Pregunta 80

En el desarrollo de "Dolores AR" y "Rally AR", ¿por qué se incluye un "Modo Demo" respaldado por PosicionSimulada y BrujulaSimulada?

* A) Para permitir la prueba completa del juego, animación y mecánicas dentro del salón de clases o en escritorio sin requerir caminatas reales ni sensores físicos.
* B) Para engañar al sistema operativo respecto a los permisos.
* C) Para desactivar el consumo de datos móviles en producción.
* D) Para reducir la resolución de la cámara.

Módulo 9: Algoritmos Complejos (2048, Levenshtein, Repetición Espaciada SM-2, EMA)

Pregunta 81

En la lógica del juego Nieves 2048, al compactar y fusionar una fila con el contenido [2, 2, 2, null], ¿cuál es el resultado correcto tras deslizar hacia la izquierda?

* A) [8, null, null, null].
* B) [4, 2, null, null].
* C) [4, 4, null, null].
* D) [2, 4, null, null].

Pregunta 82

¿Por qué en Nieves 2048 la fila [2, 2, 2, null] NO debe convertirse en [8, null, null, null] en un solo movimiento?

* A) Porque la regla clásica del juego establece que una ficha recién combinada en un turno no puede volver a fusionarse dentro del mismo movimiento.
* B) Porque la suma de 2+2+2 es igual a 6 y no a 8.
* C) Porque el array contiene un valor null.
* D) Para evitar ganar el juego demasiado rápido.

Pregunta 83

En el algoritmo de Nieves 2048, ¿cómo se implementa el movimiento en las cuatro direcciones (izquierda, derecha, arriba, abajo) sin duplicar el código de compactación y fusión?

* A) Escribiendo cuatro clases independientes con bucles for anidados.
* B) Reutilizando la función base de mover a la izquierda mediante inversión de filas (para la derecha) y transposición de matrices (para arriba y abajo).
* C) Usando expresiones regulares sobre la matriz.
* D) Reiniciando el estado del tablero en cada giro.

Pregunta 84

¿Cómo determina el motor del juego Nieves 2048 si debe o no agregar una nueva ficha aleatoria tras un deslizamiento del usuario?

* A) Agrega una ficha en cada turno sin importar el resultado del movimiento.
* B) Compara la matriz antes y después del movimiento; solo agrega una nueva ficha si la matriz sufrió algún cambio en la posición de sus elementos.
* C) Agrega una ficha solo si el usuario obtuvo más de 100 puntos.
* D) Agrega una ficha únicamente cuando el temporizador llega a cero.

Pregunta 85

En la aplicación "Habla Fluido", ¿qué mide la distancia de Levenshtein entre la frase dicha por el alumno y la frase modelo?

* A) El tono de voz en decibelios.
* B) El número mínimo de operaciones de edición (inserciones, eliminaciones o sustituciones de caracteres/palabras) requeridas para transformar una secuencia en la otra, evaluando inteligibilidad.
* C) La velocidad de habla en palabras por minuto.
* D) La cantidad de reglas gramaticales aplicadas.

Pregunta 86

En la comparación de cadenas de pronunciación, ¿qué transformación realiza la función normalizar(texto) antes de calcular la similitud?

* A) Traduce el texto del inglés al español.
* B) Convierte el texto a minúsculas, remueve signos de puntuación y preserva apóstrofos válidos (ej. "Don't").
* C) Encripta la cadena con MD5.
* D) Separa las palabras por sílabas fonéticas.

Pregunta 87

En el algoritmo de Repetición Espaciada SM-2 (SuperMemo 2) utilizado para el aprendizaje de idiomas, ¿qué ocurre con el intervalo de revisión de una tarjeta cuando el estudiante califica su recuerdo como un fallo (calidad < 3)?

* A) El intervalo se duplica automáticamente.
* B) Las repeticiones se reinician a cero y el intervalo se restablece a 1 día para revisar la tarjeta inmediatamente al día siguiente.
* C) La tarjeta se elimina del mazo de estudio.
* D) El factor de facilidad se fija en 5.0.

Pregunta 88

En el algoritmo SM-2, ¿cuál es el valor mínimo absoluto al que puede bajar el Factor de Facilidad (Easiness Factor) de una tarjeta difícil para evitar programaciones infinitas?

* A) 0.0.
* B) 1.3.
* C) 2.5.
* D) 1.0.

Pregunta 89

Para calcular la métrica de dominio continuo de un alumno en una habilidad sin que un solo mal intento destruya su histórico, ¿por qué se prefiere un Promedio Móvil Exponencial (EMA) sobre un promedio aritmético simple?

* A) Porque el EMA otorga mayor peso ponderado a los intentos más recientes conservando memoria de los anteriores (nuevo = viejo * 0.7 + intento * 0.3).
* B) Porque el promedio aritmético requiere ordenar los datos en cada iteración.
* C) Porque el EMA funciona únicamente con números enteros.
* D) Para evitar almacenar datos en disco.

Pregunta 90

En la lógica de la "Tanda Doloreña", ¿qué condición debe cumplirse obligatoriamente para poder ejecutar la función cerrarRondaYAvanzar()?

* A) Que hayan transcurrido exactamente 30 días desde la creación de la tanda.
* B) Que todos los participantes registrados hayan realizado su aportación correspondiente a la ronda actual (puedeCerrarRonda() == true).
* C) Que el organizador de la tanda apruebe la solicitud por escrito.
* D) Que el total reunido supere los $10,000 pesos.

Módulo 10: Arquitectura de SuperApps, Bus de Eventos, Permisos y Analítica de Retención

Pregunta 91

¿Cuál es la característica arquitectónica principal que define a una SuperApp (como "Super Dolores") frente a un conjunto de aplicaciones independientes?

* A) Que ocupa más de 1 GB de espacio en la memoria interna del teléfono.
* B) Un ecosistema unificado con una sola identidad de usuario, un monedero digital compartido y múltiples mini-apps integradas que colaboran entre sí.
* C) Que requiere permisos de superusuario (root) para ejecutarse.
* D) Que no requiere conexión a internet en ninguna de sus funciones.

Pregunta 92

En la arquitectura de la SuperApp, ¿cuál es la función del Bus de Eventos (BusEventos)?

* A) Renderizar animaciones de autobuses en el mapa.
* B) Permitir la comunicación desacoplada basada en eventos (publicar/suscribir) entre servicios independientes (ej. al pagar un viaje se publica un evento que el motor de lealtad escucha sin acoplar los módulos).
* C) Guardar los archivos de imágenes en la memoria caché.
* D) Encriptar el código fuente de la aplicación en tiempo de ejecución.

Pregunta 93

Si durante la publicación de un evento en el BusEventos uno de los suscriptores lanza una excepción no controlada, ¿cómo debe actuar el bus para mantener el aislamiento de fallos?

* A) Interrumpir la ejecución y tumbar la aplicación completa.
* B) Capturar la excepción del suscriptor fallido, registrarla y continuar entregando el evento a los demás suscriptores de la lista sin detener el flujo principal.
* C) Eliminar a todos los suscriptores del bus de eventos.
* D) Revertir las transacciones SQL de la base de datos local.

Pregunta 94

¿Qué es el patrón de "Kill Switch" (Feature Flag) aplicado al registro de mini-apps en la SuperApp?

* A) Un botón físico en el dispositivo para apagar la pantalla.
* B) Un mecanismo de la plataforma que permite desactivar o encender dinámicamente el acceso a una mini-app específica en tiempo de ejecución sin necesidad de volver a desplegar la aplicación.
* C) Un filtro que bloquea mensajes con palabras altisonantes.
* D) Una prueba unitaria que verifica si el dispositivo tiene batería suficiente.

Pregunta 95

En el Motor de Lealtad de "Super Dolores", ¿qué mecanismo previene que el usuario gane puntos de lealtad duplicados al recibir el mismo evento de compra dos veces por un reintento de red?

* A) Reducir el saldo del monedero a la mitad.
* B) Verificación de Idempotencia almacenando los identificadores de eventos procesados (_eventosProcesados.add(e.id)) e ignorando duplicados.
* C) Reiniciar el nivel de lealtad del usuario a Bronce.
* D) Solicitar la clave nip del usuario en cada compra.

Pregunta 96

En la regla de bonificación por variedad de servicios de la SuperApp, ¿qué debe ocurrir si un usuario utiliza 3 servicios distintos (ej. chat, comercio y transporte) dentro de la misma semana?

* A) Se le concede un préstamo bancario automático.
* B) Otorga un bono de puntos escalonado (+100 puntos) una sola vez por escalón alcanzado dentro de esa semana calendario.
* C) Se le cobran comisiones dobles por transacción.
* D) Se le bloquea la cuenta por actividad sospechosa.

Pregunta 97

En el diseño de notificaciones promocionales en la SuperApp, ¿qué regla aplica la clase Notificador para proteger la experiencia del usuario y evitar spam?

* A) Enviar notificaciones promocionales únicamente a las 3 de la mañana.
* B) Imponer un límite o cuota máxima diaria (ej. máximo 2 notificaciones promocionales al día por usuario) y respetar la preferencia del usuario si decide desactivarlas.
* C) Cobrar 10 puntos de lealtad por cada notificación enviada.
* D) Convertir las notificaciones en llamadas telefónicas automáticas.

Pregunta 98

¿Qué sugiere el algoritmo de "Siguiente Mejor Acción" (sugerirServicio) a un usuario en su pantalla de inicio?

* A) El producto más caro disponible en la tienda virtual.
* B) El servicio relevante que el usuario AÚN NO ha probado (fomentando el descubrimiento de la plataforma según la hora del día), o el menos utilizado si ya probó todos.
* C) Un enlace para desinstalar la aplicación.
* D) Una lista de contactos aleatorios de su libreta.

Pregunta 99

En el análisis de métricas de retención de usuarios (DAU, WAU, MAU), ¿qué mide la métrica de Usuarios Activos Diarios (DAU)?

* A) El número de descargas totales de la app en la tienda de aplicaciones.
* B) La cantidad de usuarios únicos que realizaron al menos una acción con valor en la plataforma (enviar mensaje, pagar, comprar o viajar) durante un día determinado.
* C) El porcentaje de usuarios que eliminaron la aplicación en las primeras 24 horas.
* D) El tiempo total que la pantalla permaneció encendida.

Pregunta 100

Al interpretar los datos analíticos de retención que muestran que los usuarios que usan 4 servicios se conservan mejor que los que usan 1, ¿por qué es incorrecto afirmar categóricamente que "forzar el uso de 4 servicios CAUSA mayor retención"?

* A) Porque los números calculados por la computadora siempre son falsos.
* B) Por el principio estadístico fundamentales de que "Correlación no implica Causalidad"; los usuarios más comprometidos naturalmente usan más servicios (sesgo de selección), y verificar causalidad requiere experimentos controlados (pruebas A/B).
* C) Porque las métricas de retención solo aplican para aplicaciones de juegos.
* D) Porque el monedero digital no almacena el historial de transacciones.

Clave de Respuestas y Explicaciones Detalladas

Pregunta	Respuesta	Justificación Técnica Fundada en los Manuales
1	B	FutureBuilder escucha el estado del Future y reconstruye la UI según ConnectionState (Reto 1 Películas & Reto 4 Cripto).
2	B	Evita pantallas vacías informando el estado de carga durante peticiones asíncronas (Reto 3 Clima).
3	A	Uri.encodeComponent escapa caracteres no válidos en URLs dinámicas (Reto 2 Gatos & Manual Wikipedia).
4	C	HTTP 429 indica saturación de cuota o límite de peticiones (Manual 5 APIs / ClienteSeguro).
5	B	El paquete http no lanza excepción en códigos 404/500; retorna Response con dicho statusCode (Manual Consumo API Local).
6	B	utf8.encode() garantiza que caracteres multibyte (acentos, ñ) no se corrompan en pruebas (Manual 5 APIs).
7	B	itemCount establece el número de elementos a construir dinámicamente en ListView.builder (Reto 4).
8	B	setState() notifica al framework para ejecutar de nuevo build() con los nuevos datos (Retos 2 y 4).
9	C	double.tryParse() devuelve null si el texto no es un decimal válido, evitando excepciones no controladas (Reto 4).
10	B	La cabecera Accept especifica que el cliente espera una respuesta formateada en JSON (Manual 5 APIs).
11	B	El ciclo TDD inmutable es Rojo (prueba que falla), Verde (código mínimo) y Refactor (limpieza) (Manual Ajolotito / Todos).
12	A	Desacoplar el dominio de Flutter permite ejecutar cientos de pruebas unitarias en milisegundos en la máquina virtual de Dart (Todos los manuales).
13	B	Una prueba que falla confirma que el test verifica activamente la ausencia de la característica requerida (Todos los manuales).
14	B	En la fase Verde se debe escribir únicamente el código mínimo para pasar la prueba, evitando sobre-ingeniería (Todos).
15	B	Refactor permite mejorar la calidad y nombres del código sin modificar el comportamiento ni romper pruebas (Todos).
16	B	Calcular resultados esperados de forma independiente (ej. con Python o a mano) evita caer en sesgos al probar matemática (Manuales Ajolotito, Habla Fluido).
17	B	expect(actual, matcher) es la función estándar de aserción en flutter_test (Todos).
18	B	Las pruebas de regresión aseguran que nuevas adiciones no destruyan características que ya funcionaban (Todos).
19	B	closeTo() verifica que un valor flotante esté dentro de una tolerancia aceptable respecto al valor objetivo (Manuales Ajolotito, Habla Fluido, Geodesia).
20	B	Modificar la prueba para validar un error invalida la red de seguridad del TDD (Todos).
21	B	Una clase abstracta en el dominio actúa como contrato (Puerto), independizándolo de la infraestructura (Manual Ajolotito, Lotería, Dolores AR).
22	B	Inyectar dependencias por constructor permite sustituir servicios reales por dobles de prueba deterministas (Todos).
23	B	Abstraer el tiempo mediante una interfaz Reloj permite simular el avance de horas instantáneamente en las pruebas (RelojFalso) (Manual Ajolotito).
24	B	Un doble Falso implementa el puerto guardando estado en memoria sin tocar plugins ni APIs (Manuales Ajolotito, Lotería, Rally).
25	B	El Composition Root (main.dart / dependencias.dart) instanciar y ensambla todas las dependencias reales (Manuales 5 APIs, Punto de Venta, Tienda Talavera).
26	B	Limitar el contexto a un ContextoMiniApp aplica el principio de menor privilegio sobre permisos y servicios (Manual SuperApp).
27	A	MockClient intercepta peticiones HTTP para simular respuestas (200, 500, timeouts) instantáneamente sin red (Manuales Consumo API Local, 5 APIs).
28	A	Reutilizar la lógica de movimiento horizontal invirtiendo o transponiendo matrices evita duplicar código algorítmico (DRY) (Manual Nieves 2048).
29	B	El patrón Puerto/Adaptador confina los cambios de paquetes o plugins a la clase adaptadora de infraestructura (Manuales Ajolotito, Lotería).
30	B	Un dominio puro se compone exclusivamente de código Dart sin dependencias de Flutter ni de plugins (Todos los manuales).
31	B	El ViewModel expone el estado de UI, gestiona acciones del usuario y notifica cambios a la vista mediante notifyListeners() (Todos los manuales).
32	B	Representar explícitamente inicial, cargando, listo, vacio y error cubre todos los estados de la experiencia de usuario (Manual Consumo API Local).
33	A	ListenableBuilder / AnimatedBuilder escucha un ChangeNotifier y reconstruye su sub-árbol al recibir notificaciones (Manuales Ajolotito, Punto de Venta).
34	B	Debounce retrasa la ejecución hasta que el usuario deja de teclear por un intervalo determinado, evitando saturación (Manual Consumo API Local).
35	B	Sin notifyListeners(), el estado interno cambia pero la interfaz no se enterará ni se redibujará (Todos los manuales).
36	A	Instanciar el ViewModel en initState() o inyectarlo preserva el objeto a través de reconstrucciones de widgets (Todos los manuales).
37	B	El ViewModel captura las excepciones de dominio y actualiza un campo de mensaje seguro para que la UI lo despliegue (Todos los manuales).
38	B	Manejar un objeto Carga<T> independiente por servicio permite que fallas en una API no afecten a las demás (Manual 5 APIs).
39	C	El método dispose() de un State es el lugar adecuado para cancelar suscripciones y liberar controladores (Todos los manuales).
40	B	Escuchar los cambios agregando un listener previo a la llamada registra las transiciones de estado para su validación (Manuales 5 APIs, Consumo API Local).
41	B	El almacenamiento binario de double produce impresiciones flotantes que provocan desbalances en los cortes financieros (Manual Punto de Venta).
42	B	Representar el dinero en enteros de centavos elimina el riesgo de errores de coma flotante (Manuales Punto de Venta, Tienda Talavera, SuperApp).
43	B	inMemoryDatabasePath de sqflite_common_ffi crea bases de datos SQLite volátiles en RAM para pruebas rápidas (Manual Punto de Venta).
44	B	Las transacciones db.transaction garantizan la atomicidad (se ejecuta todo o se revierte todo) de la venta e inventario (Manual Punto de Venta).
45	B	aMapa() y desdeMapa() adaptan las instancias tipadas de Dart a los mapas estructurados que requiere SQLite (Manual Punto de Venta).
46	B	El repositorio captura la excepción técnica de la BD y la traduce a una excepción de negocio comprensible (CodigoDuplicadoException) (Manual Punto de Venta).
47	C	Para obtener el IVA (16%) incluido en un total T, el desglose exacto en enteros es T - (T * 100 ~/ 116) (Manual Punto de Venta).
48	B	Revalidar existencias dentro de la transacción atómica evita vender productos que fueron tomados por otra venta simultánea (Manual Punto de Venta).
49	B	COALESCE(SUM(...), 0) asegura que la consulta SQL retorne 0 en centavos cuando la tabla de ventas esté vacía (Manual Punto de Venta).
50	B	Abstraer SQLite mediante el repositorio permite cambiar el motor de persistencia o probarlo con dobles sin tocar la UI ni el dominio (Manual Punto de Venta).
51	B	Las notificaciones locales son internas del dispositivo; las push son enviadas desde un servidor externo a través de la nube (Manuales Ajolotito, Lotería Push).
52	B	Se debe pedir permiso previa explicación y evitar notificar en horas de silencio (ej. 22:00 a 08:00) salvo urgencia (Manual Ajolotito).
53	B	Android 13 (API 33) convirtió el permiso de notificaciones en un permiso runtime explícito (POST_NOTIFICATIONS) (Manuales Ajolotito, Lotería Push).
54	B	El push puede perderse o desordenarse; la app debe usarlo como aviso y consultar al servidor para obtener el estado verdadero (Manual Lotería Push).
55	A	El protocolo de transporte de FCM exige que los valores del mapa data sean exclusivamente cadenas de texto (Manual Lotería Push).
56	B	FCM expone onMessage (primer plano), onMessageOpenedApp (segundo plano tocado) y getInitialMessage / onBackgroundMessage (cerrada/fondo) (Manual Lotería Push).
57	B	El manejador de fondo debe ser una función top-level anotada con @pragma('vm:entry-point') ejecutada en un isolate independiente (Manual Lotería Push).
58	B	El payload es el dato interno en el mensaje que indica a la app la acción o pantalla hacia donde debe navegar al tocar la notificación (Manuales Ajolotito, Lotería Push).
59	B	Los canales de Android organizan las notificaciones por categorías para que el usuario controle su nivel de importancia e interrupción (Manuales Ajolotito, Lotería Push).
60	B	El uso del objeto de valor DestinoPush encapsula los detalles de Tokens FCM o FIDs, protegiendo al dominio de cambios en la infraestructura (Manual Lotería Push).
61	B	Las cadenas almacenadas dentro del código compilado de la app son fácilmente extraíbles mediante ingeniería inversa o descompilación del APK (Manuales 5 APIs, Habla Fluido).
62	B	--dart-define inyecta valores al compilar que se leen en tiempo de ejecución mediante String.fromEnvironment() (Manuales 5 APIs, Habla Fluido).
63	B	Un servidor Proxy intermediario custodia la llave de API real y autentica las peticiones del cliente (Manuales 5 APIs, Habla Fluido).
64	B	ClienteSeguro.redactar reemplaza valores de llaves o tokens en la URL por *** antes de imprimir logs (Manual 5 APIs).
65	B	mensajeSeguro() filtra detalles técnicos en excepciones no controladas y sólo expone mensajes seguros para el usuario (Manuales 5 APIs, Habla Fluido, SuperApp).
66	B	soloHttps() valida que los recursos de red externos utilicen protocolos seguros cifrados https:// (Manuales 5 APIs, Tienda Talavera).
67	B	Limitar los bytes máximos previene desbordamientos de memoria local si un servidor responde con payloads maliciosos o masivos (Manual 5 APIs).
68	B	flutter_secure_storage almacena secretos cifrados en el Keystore/Keychain del SO (Manual Tienda Talavera).
69	B	El algoritmo de Luhn detecta errores sintácticos en el número de tarjeta en el cliente sin requerir llamadas a la pasarela (Manual Tienda Talavera).
70	B	La clave de idempotencia garantiza que la pasarela no procese un cobro dos veces ante reintentos por pérdidas de red (Manual Tienda Talavera).
71	B	La fórmula de Haversine calcula la distancia ortodrómica sobre la esfericidad terrestre entre dos coordenadas (Manuales Rally AR, Dolores AR).
72	B	El azimut es el ángulo en grados (0° a 360°) respecto al Norte hacia donde yace la coordenada de destino (Manuales Rally AR, Dolores AR).
73	B	El problema directo de la geodesia calcula las nuevas coordenadas (latitud, longitud) al avanzar una distancia en un rumbo dado (Manual Rally AR).
74	B	La posición x en pantalla se obtiene proyectando la diferencia angular entre la vista del usuario y el objetivo dentro del rango del FOV (Manuales Rally AR, Dolores AR).
75	B	La diferencia angular debe calcular la trayectoria más corta considerando la discontinuidad circular entre 360° y 0° (Manuales Rally AR, Dolores AR).
76	B	Promediar de forma simple valores cercanos a 360° y 0° genera una media cercana a 180°, provocando saltos bruscos en la UI (Manuales Rally AR, Dolores AR).
77	B	suavizarAngulo calcula el delta corto con diferenciaAngular y aplica el factor de suavizado (lpha) manteniendo la continuidad (Manuales Rally AR, Dolores AR).
78	B	CustomPainter provee un lienzo 2D para renderizar primitivas matemáticas arbitrarias como radares polares (Manual Rally AR).
79	B	.glb/.gltf es el estándar para Android (Scene Viewer) y .usdz para iOS (Quick Look) en AR basada en modelos 3D (Manuales Dolores AR, Tienda Talavera).
80	A	El Modo Demo simula sensores (GPS/Brújula) permitiendo ejecutar y evaluar las mecánicas en entornos estáticos o de desarrollo (Manuales Rally AR, Dolores AR).
81	B	Al deslizar [2, 2, 2, null], los dos primeros 2 se fusionan en 4 y el tercero ocupa el siguiente espacio disponible: [4, 2, null, null] (Manual Nieves 2048).
82	A	Las reglas de 2048 impiden que un elemento recién fusionado participe en una segunda fusión durante el mismo movimiento (Manual Nieves 2048).
83	B	Transponer la matriz o invertir filas permite reusar el algoritmo de desplazamiento a la izquierda para todas las direcciones (Manual Nieves 2048).
84	B	El motor compara la matriz antes y después del movimiento y sólo genera una nueva ficha si hubo desplazamientos reales (Manual Nieves 2048).
85	B	La distancia de Levenshtein contabiliza las ediciones mínimas (inserción, borrado, sustitución) para evaluar la similitud fonética/textual (Manual Habla Fluido).
86	B	normalizar() homogeniza el texto pasando a minúsculas, quitando puntuación pero conservando apóstrofos en contracciones (Manual Habla Fluido).
87	B	Un fallo en SM-2 (calidad < 3) reinicia las repeticiones consecutivas a 0 y restablece el intervalo a 1 día (Manual Habla Fluido).
88	B	El algoritmo SM-2 establece un piso mínimo de 1.3 para el factor de facilidad, evitando tarjetas atascadas en bucles de revisión infinita (Manual Habla Fluido).
89	A	El Promedio Móvil Exponencial (EMA) pondera más las ejecuciones recientes permitiendo reflejar el avance sin descartar el historial (Manual Habla Fluido).
90	B	cerrarRondaYAvanzar() requiere que todos los participantes registrados hayan entregado su aportación en la ronda corriente (Manual Tanda Doloreña).
91	B	Una SuperApp integra múltiples servicios interconectados bajo una única identidad y un monedero digital unificado (Manual SuperApp).
92	B	El BusEventos permite la comunicación asíncrona desacoplada entre módulos independientes mediante el patrón Publicar/Suscribir (Manual SuperApp).
93	B	El bus captura las excepciones de suscriptores individuales para evitar que un fallo en un módulo afecte a los demás (Manual SuperApp).
94	B	El "Kill Switch" permite desactivar o habilitar mini-apps dinámicamente desde el registro central sin redesplegar la app (Manual SuperApp).
95	B	El motor de lealtad verifica si el ID de un evento ya fue procesado antes de otorgar puntos para garantizar idempotencia (Manual SuperApp).
96	B	Usar 3 o más servicios distintos en una misma semana otorga un bono de variedad de puntos una sola vez por escalón semanal (Manual SuperApp).
97	B	El Notificador aplica cuotas máximas diarias de notificaciones promocionales por usuario para evitar saturación y spam (Manual SuperApp).
98	B	El algoritmo de sugerencias prioriza servicios no probados por el usuario según el momento del día para estimular el descubrimiento (Manual SuperApp).
99	B	DAU contabiliza los usuarios únicos que interactuaron activamente con valor en la plataforma durante un periodo de 24 horas (Manual SuperApp).
100	B	Correlación no implica causalidad; los usuarios con mayor compromiso usan más servicios de forma natural (sesgo de selección) (Manual SuperApp).

Banco de 100 Preguntas de Evaluación elaborado a partir de los Manuales de Desarrollo Móvil Integral con Flutter y TDD.
