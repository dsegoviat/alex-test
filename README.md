Tienes que desarrollar las siguientes aplicaciones:
 - Capitales de países (API REST) -> `capitals-api`
 - Buscador de capitales (Web application) -> `capitals-app`

Para `capitals-api` tienes que ser capaz de:
 - Listar todas las ciudades presentes en tu base de datos. `GET /countries`
  - Response: `200 OK`
  ```json
  {
      "countries": [
          "spain",
          "usa",
          "germany",
          "france"
      ]
  }
  ```
 - Obtener la capital de una ciudad. `GET /countries/{countryName}/capital`.
   - Si `countryName` existe -> Response: `200 OK`. En este caso, `countryName = spain` => `GET /countries/spain/capital`
    ```json
    {
        "capital": "madrid"
    }
    ```
    - Si no existe -> Response: `404 Not found`.
 - Introducir una ciudad en la base de datos. `POST /countries`
    - Body:
    ```json
    {
        "name": "spain",
        "capital": "madrid"
    }
    ```
    - Deberá retornar el status code dependiendo del resultado de la operación. Por ejemplo, si ya existía -> `409 Conflict`. Si no existía y se ha creado correctamente, qué código debería retornar? Haz que tu API use los status code correctos. Te dejo los principales escenarios:
    - Se ha creado correctamente.
    - No se ha creado porque ya existe (conflicto)
    - El usuario no ha introducido un país válido (e.g. falta el `name` o `capital`, esos fields son un numero en lugar de string...)
 - Borrar un país de tu API. `DELETE /countries/{countryName}`

Para `capitals-app` tendrás que llamar a tu propia API y poder hacer lo siguiente:
 - Listar todos los países
    - Si clicas en un país podrás ver su capital
 - Obtener la capital de un país introduciendo su nombre.
    - Si no se encuentra, mostrar un mensaje de error.
 - Crear y borrar países (con algún botón)


## Technology stack
Para la API -> [Spring boot](https://spring.io/projects/spring-boot)

Para la web app -> [Angular](https://angular.io/)
