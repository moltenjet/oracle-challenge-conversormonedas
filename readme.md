Conversor de Monedas - Aplicación de Consola en Java

Descripción General
    Esta es una aplicación en Java que funciona como un Conversor de Monedas, obteniendo tasas de cambio en tiempo real desde una API, lo que permite a los usuarios convertir entre varias monedas a través de una interfaz basada en consola. Maneja la manipulación de datos JSON, realiza solicitudes HTTP y ofrece una experiencia interactiva en la que los usuarios pueden seleccionar monedas, convertir montos y ver el historial de conversiones.

Características
    - Tasas de cambio en tiempo real: Obtiene las últimas tasas de conversión de moneda utilizando la API de tasas de cambio.
    - Monedas soportadas: El convertidor admite un conjunto predefinido de monedas (ARS, BOB, BRL, CLP, COP, USD) y se puede ampliar fácilmente para incluir más.
    - Conversión de monedas: Convierte montos ingresados de una moneda a otra utilizando las tasas proporcionadas por la API.
    - Interfaz interactiva de consola: Los usuarios interactúan con el programa mediante un menú sencillo en la consola, ingresando las monedas y montos deseados.
    - Historial de conversiones: La aplicación almacena y muestra el historial de las actividades de conversión del usuario.
    - Registros con marcas de tiempo: Cada conversión se registra con la fecha y hora para referencia.

Requisitos Previos
    Antes de ejecutar esta aplicación, asegúrate de tener lo siguiente instalado:
    - Java JDK: Versión 11 o superior.
    - Biblioteca Gson: Versión 2.10.1 o superior.
    - Postman: (Opcional) Se puede utilizar para probar y explorar solicitudes a la API si es necesario.


Instrucciones
1. Importar la Biblioteca Gson en IntelliJ. Para utilizar Gson en el análisis de JSON, necesitarás importar la biblioteca Gson en tu proyecto de IntelliJ. Puedes hacerlo agregando la siguiente dependencia en tu archivo pom.xml (si utilizas Maven):

        <dependency>
            <groupId>com.google.code.gson</groupId>
            <artifactId>gson</artifactId>
            <version>2.10.1</version>
        </dependency>
        Si no usas Maven, descarga el archivo JAR de Gson y añádelo manualmente a tu proyecto.

2. Configuración y Ejecución
        Clona el repositorio o copia los archivos fuente a tu entorno local.
        Asegúrate de haber importado la biblioteca Gson y que Java JDK 11+ esté configurado correctamente.
        Compila y ejecuta el archivo CurrencyConverter.java.
        El programa obtendrá automáticamente las tasas de cambio de la API y cargará las monedas soportadas en la aplicación.
    
3. Usar la Aplicación
        Al ejecutar el programa, verás el menú principal:
        Opción 1: Convertir entre monedas.
        Opción 2: Ver el historial de conversiones pasadas.
        Opción 3: Salir de la aplicación.
        Convertir monedas:
        Se te pedirá ingresar los códigos de moneda (por ejemplo, USD a ARS) y el monto a convertir.
        El programa mostrará el valor convertido.
        Ver historial:
        Puedes ver las conversiones anteriores junto con la fecha y hora en que se realizaron.
    
4. Modificar las Monedas Soportadas
        Para agregar o modificar las monedas que soporta el conversor:
        Abre el archivo CurrencyConverter.java.
        Modifica el array supportedCurrencies para incluir los códigos de moneda adicionales.
        Ajusta el método populateCurrencyMap() para asignar nombres a los nuevos códigos de moneda.


Ejemplo de Salida en Consola

    === Conversor de Monedas ===
    1. Convertir monedas
    2. Ver historial
    3. Salir
    Elija una opción: 1

    Monedas disponibles:
    ARS - Peso argentino
    BOB - Boliviano
    BRL - Real brasileño
    CLP - Peso chileno
    COP - Peso colombiano
    USD - Dólar estadounidense

    Ingrese la moneda de origen (Código): USD
    Ingrese la moneda de destino (Código): ARS
    Ingrese la cantidad a convertir: 100
    Resultado: 100.00 USD = 35375.00 ARS

    === Conversor de Monedas ===
    1. Convertir monedas
    2. Ver historial
    3. Salir
    Elija una opción: 2

    === Historial de Conversiones ===
    [2024-10-11 14:35:21] 100.00 USD -> 35375.00 ARS


Clases y Métodos Clave
    1. HttpClient y HttpRequest: Maneja el envío de solicitudes GET a la API de tasas de cambio y la obtención de las tasas en tiempo real.
    2. Gson para el Análisis de JSON: La biblioteca Gson se utiliza para analizar la respuesta JSON de la API. Extrae las tasas de cambio y las almacena en un mapa para acceder rápidamente durante las conversiones.
    3. LocalDateTime y DateTimeFormatter: Estas clases se usan para registrar la fecha y hora exacta de cada conversión, permitiendo un historial de transacciones con marcas de tiempo.

Notas Adicionales
    Uso de la API: La aplicación está configurada para utilizar la API de tasas de cambio. Asegúrate de que la URL de la API sea correcta y, si es necesario, incluye tu clave API.
    Manejo de Errores: La aplicación valida los códigos de moneda y los montos ingresados, asegurando que el usuario proporcione entradas válidas.

Mejoras Futuras
    Soporte Extendido de Monedas: Permitir a los usuarios obtener la lista completa de monedas soportadas directamente desde la API.
    Interfaz Gráfica de Usuario (GUI): Implementar una interfaz más amigable utilizando JavaFX o Swing.
    Manejo Avanzado de Errores: Mejorar el manejo de errores, incluyendo mejores mensajes de error de la API y manejo de tiempos de espera de red.
