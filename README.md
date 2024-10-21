Proyecto: Testing de API - Explora Argentina.
Este proyecto contiene la batería de pruebas para la API de reservas del sistema Explora Argentina. El propósito principal es validar las funcionalidades de la API, asegurando que cumplan con los criterios de aceptación definidos y que manejen correctamente errores y excepciones.

Índice
Descripción del Proyecto
Tecnologías Utilizadas
Ejecución de las Pruebas
Casos de Prueba
Resumen de Resultados
Instalación y Configuración
Descripción del Proyecto
El proyecto contiene una colección de pruebas automatizadas que validan los diferentes endpoints relacionados con las reservas de productos turísticos en la API de Explora Argentina. Cada prueba evalúa una funcionalidad específica, verificando tanto casos exitosos como el manejo adecuado de errores.

Las pruebas se han desarrollado utilizando Postman y se han ejecutado a través de Newman, generando un informe detallado con estadísticas sobre los tests ejecutados.

Tecnologías Utilizadas
Postman: Para la creación y ejecución de las pruebas.
Newman: Para la ejecución de las pruebas en línea de comandos y la generación de reportes.
HTML: Los reportes de las pruebas están disponibles en formato HTML.
Ejecución de las Pruebas
Las pruebas se ejecutan a través de Newman, y los resultados se almacenan en un archivo HTML. Puedes revisar el informe de los tests en la siguiente dirección: file:///C:/Users/fabri/OneDrive/Desktop/testing/Testing-explora-Argentina/newman/index.html

Para ejecutar las pruebas localmente, sigue estos pasos:

Clona el repositorio.
Instala Newman si aún no lo tienes:
npm install -g newman
Ejecuta la colección de pruebas:
newman run ./collection.json -r html --reporter-html-export ./newman/index.html
Casos de Prueba
1. Registrar una Reserva:
Endpoint: /reservar/registrar
Método: POST
Descripción: Permite al usuario registrar una reserva de un producto para una fecha específica.
Test: Verifica si la reserva se realiza correctamente y si retorna 409 Conflict en caso de que el producto ya esté reservado para esa fecha.
2. Listar Reservas de un Usuario:
Endpoint: /reservar/usuario/historial/{usuarioId}
Método: GET
Descripción: Obtiene el historial de reservas del usuario.
Test: Verifica si el historial se lista correctamente y si maneja el caso en que el usuario no tenga reservas.
3. Consultar Disponibilidad de un Producto por Fecha:
Endpoint: /reservar/productosPorFecha/{fecha}
Método: GET
Descripción: Permite consultar la disponibilidad de productos para una fecha específica.
Test: Verifica que se retorne correctamente la lista de productos disponibles y el manejo de fechas no válidas.
4. Error: Reservar Producto No Disponible:
Endpoint: /reservar/registrar
Método: POST
Descripción: Intenta reservar un producto que ya está reservado para la fecha seleccionada.
Test: Verifica que retorne un error 409 Conflict.
5. Consultar Reservas de un Producto:
Endpoint: /reservar/producto/{productoId}
Método: GET
Descripción: Lista las fechas en las que un producto está reservado.
Test: Verifica si se listan correctamente las fechas reservadas de un producto.
6. Error: Reserva No Encontrada:
Endpoint: /reservar/{id}
Método: GET
Descripción: Consulta una reserva por ID.
Test: Verifica si retorna 404 Not Found cuando el ID de la reserva no existe.
Resumen de Resultados
Los resultados de las pruebas incluyen un total de:

Total requests: X
Failed tests: X
Skipped tests: X
Los detalles completos se pueden consultar en el informe HTML generado.

Instalación y Configuración
Clona el repositorio.
Instala las dependencias necesarias:
npm install
Asegúrate de tener configurada la URL de la API correctamente en los tests de Postman.
Ejecuta las pruebas siguiendo las instrucciones de la sección Ejecución de las Pruebas.
