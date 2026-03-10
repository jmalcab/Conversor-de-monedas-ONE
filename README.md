# Conversor de Moneda - Challenge ONE

Este proyecto es una aplicación de consola desarrollada en Java que permite a los usuarios realizar conversiones de divisas en tiempo real. La aplicación consume la [ExchangeRate-API](https://www.exchangerate-api.com/) para obtener las tasas de cambio actualizadas y procesa las respuestas en formato JSON.

## ⚙️ Tecnologías Utilizadas

* **Java 11+**: Lenguaje principal del proyecto.
* **java.net.http.HttpClient**: Para el manejo nativo de solicitudes y respuestas HTTP.
* **Gson (Google)**: Librería para la serialización y deserialización de objetos JSON.
* **IntelliJ IDEA**: Entorno de desarrollo integrado (IDE).

## 🚀 Funcionalidades

El sistema despliega un menú interactivo en la consola que evalúa entradas numéricas mediante la clase `Scanner`. Las opciones de conversión implementadas soportan las siguientes divisas frente al Dólar estadounidense (USD):

1.  Peso argentino (ARS)
2.  Real brasileño (BRL)
3.  Peso colombiano (COP)

El bucle de ejecución se mantiene activo hasta que el usuario selecciona explícitamente la opción de salida (7).

## 🔧 Requisitos Previos e Instalación

Para compilar y ejecutar este proyecto correctamente, tu entorno de desarrollo debe cumplir con las siguientes dependencias:

1.  **JDK 11 o superior**: Requerido para el uso de la API `HttpClient`.
2.  **Librería Gson**: Descargar el archivo `.jar` de Gson e incluirlo en el *Classpath* del proyecto.
    * *En IntelliJ IDEA:* Ve a `File` > `Project Structure` > `Modules` > `Dependencies`, haz clic en el ícono `+`, selecciona `JARs or directories` y localiza el archivo descargado.

## 💻 Ejecución

1.  Clona este repositorio en tu máquina local.
2.  Abre la carpeta del proyecto en tu IDE.
3.  Verifica que el archivo `Conversor.java` se encuentre dentro del directorio `src/`.
4.  Ejecuta el método `main` de la clase `Conversor`.

## 🏗️ Estructura de la Arquitectura

El flujo lógico del sistema opera bajo el siguiente esquema:
1.  **Captura de Datos**: El usuario ingresa la opción deseada y el monto.
2.  **Construcción de la URI**: Se concatena la URL base con el *API Key*, las divisas origen/destino y el monto.
3.  **Transacción HTTP**: Se despacha la petición `GET` mediante `HttpRequest` y se captura la `HttpResponse`.
4.  **Parseo JSON**: `JsonParser` extrae específicamente el nodo `conversion_result` validando el estado de la consulta.
5.  **Salida**: Volcado de datos formateados en la salida estándar de la consola.
