# Inventory — Persistencia con Room

Práctica del codelab [Cómo conservar datos con Room](https://developer.android.com/codelabs/basic-android-kotlin-compose-persisting-data-room?hl=es-419), basada en el [proyecto oficial de Google](https://github.com/google-developer-training/basic-android-kotlin-compose-training-inventory-app).

## Configuración

- Kotlin y Jetpack Compose.
- Android 15: compileSdk 35 y targetSdk 35; mínimo API 24.
- Room 2.7.2, KSP y corrutinas.
- Android Gradle Plugin 8.8.0 y Gradle 8.12.

## Funcionalidad de esta entrega

La pantalla Add Item permite registrar nombre, precio y cantidad. Save se habilita al completar los campos; al guardar se inserta el producto en la tabla `items` de `item_database` y se vuelve a Inventory.

Esta primera práctica conserva los datos, pero todavía no muestra los productos en la pantalla principal. La lista, edición y eliminación en la interfaz corresponden al siguiente codelab. Los métodos correspondientes del DAO y del repositorio quedan definidos.

## Ejecución y comprobación

1. Abrir el proyecto en Android Studio y sincronizar Gradle con JDK 17 o 21.
2. Seleccionar el Motorola conectado por USB y ejecutar `app`.
3. Presionar +, completar los tres campos y guardar.
4. Abrir View > Tool Windows > App Inspection > Database Inspector.
5. Seleccionar `com.example.inventory`, abrir `item_database` y consultar la tabla `items`.
6. Reiniciar la app y volver a consultar la tabla para comprobar la persistencia.

## Historial de la práctica

- **Inicial:** proyecto oficial de partida (`starter`) configurado para Android 15.
- **Final:** entidad, DAO, base de datos, repositorio e integración del guardado con la interfaz.

Se conserva la licencia Apache 2.0 del proyecto original.

## Codelab 2: lectura y actualización

Punto de partida: el commit final del primer codelab, con guardado en Room y Android 15 (SDK 35).

La segunda parte implementará la lista observable, los detalles, la venta de una unidad, la edición y la eliminación con confirmación. También incluirá las cinco pruebas instrumentadas de las operaciones del DAO indicadas en la guía.

Guía: https://developer.android.com/codelabs/basic-android-kotlin-compose-update-data-room?hl=es-419
