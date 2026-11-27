# Inventory — Room, codelabs 1 y 2

Proyecto basado en los codelabs oficiales de Android Developers y en el [código de Google](https://github.com/google-developer-training/basic-android-kotlin-compose-training-inventory-app), con licencia Apache 2.0.

## Configuración

Kotlin 2.1.0, Jetpack Compose, Room 2.7.2 y KSP. Android 15: compileSdk 35 y targetSdk 35; mínimo API 24. Android Gradle Plugin 8.8.0, Gradle 8.12 y JDK 17 o 21.

## Codelab 1: conservar datos

[Guía de persistencia](https://developer.android.com/codelabs/basic-android-kotlin-compose-persisting-data-room?hl=es-419).

Entidad Item, ItemDao, InventoryDatabase y repositorio local. La pantalla Add Item registra nombre, precio y cantidad en `item_database`, tabla `items`.

## Codelab 2: leer y actualizar

[Guía de lectura y actualización](https://developer.android.com/codelabs/basic-android-kotlin-compose-update-data-room?hl=es-419).

- Lista de productos en LazyColumn, observada mediante Flow y StateFlow.
- Detalles del producto seleccionado.
- Sell descuenta una unidad y queda deshabilitado cuando no hay stock.
- Edit Item carga los valores existentes y guarda los cambios conservando el identificador.
- Save se deshabilita si un campo requerido está vacío.
- Delete pide confirmación y elimina el producto antes de regresar al inventario.

La base de datos de la primera parte se conserva: no se cambió el esquema ni el identificador de la aplicación.

## Ejecutar y probar

Abrir el proyecto en Android Studio, sincronizar Gradle y ejecutar `app` en el dispositivo conectado. En `app/src/androidTest/java/com/example/inventory/ItemDaoTest.kt` se incluyen las cinco pruebas instrumentadas del codelab: insertar, consultar todos, consultar uno, actualizar y eliminar. Utilizan una base de datos en memoria independiente del inventario del usuario.

Para ejecutarlas, abrir ItemDaoTest en Android Studio y ejecutar la clase en el dispositivo. También se pueden ejecutar con `./gradlew connectedDebugAndroidTest`.

## Historial de entregas

1. Inicial del codelab 1: proyecto de partida para Android 15.
2. Final del codelab 1: persistencia con Room.
3. Inicial del codelab 2: continuidad desde el final anterior y alcance de la segunda práctica.
4. Final del codelab 2: lista, detalles, venta, edición, eliminación y pruebas del DAO.

## Pruebas instrumentadas

Las cinco pruebas de ItemDaoTest se ejecutaron correctamente en el Motorola Edge 50 Fusion (Android 16, API 36), manteniendo compileSdk y targetSdk 35. Las pruebas utilizan Room en memoria. La ejecución instrumentada puede reinstalar la aplicación; los datos de ejemplo se volvieron a cargar para la demostración manual.

## Verificación manual en el Motorola

Se comprobó que la lista muestra los productos guardados, que los detalles cargan el producto seleccionado y que Edit Item precarga sus datos. El precio de Prueba se cambió de 3.50 a 4.00 y la cantidad de 2 a 1. Al vaciar el precio, Save se deshabilitó. Una venta dejó la cantidad en cero y deshabilitó Sell. Al confirmar Delete, Prueba desapareció de la lista.
