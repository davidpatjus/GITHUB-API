# Documentación del API de GitHub

¡Bienvenido a la documentación del API de GitHub! Esta guía proporciona detalles sobre cómo interactuar con nuestros endpoints para obtener información sobre usuarios y repositorios.

## Endpoints

### 1. Obtener Información del Usuario

- **Endpoint:** `/api/github/user/:username`
- **Método:** GET

#### Parámetros de Ruta:

- `:username` (string) - Nombre de usuario de GitHub para obtener información.

#### Parámetros de Consulta (Opcionales):

- `include_repos` (boolean) - Indica si se deben incluir detalles de los repositorios públicos del usuario. Por defecto es `false`.

#### Ejemplo:
/api/github/user/username?include_repos=true

Errores Posibles:
404 Not Found: El nombre de usuario proporcionado no existe.
400 Bad Request: El parámetro username no es válido.
500 Internal Server Error: Error del servidor al procesar la solicitud.


2. Obtener Repositorios del Usuario
Endpoint: /api/github/user/:username/repos
Método: GET
Parámetros de Ruta:
:username (string) - Nombre de usuario de GitHub para obtener los repositorios.
Parámetros de Consulta (Opcionales):
sort (string) - Criterio para ordenar los repositorios. Valores posibles: created, updated, pushed, full_name. Por defecto es full_name.
direction (string) - Dirección de ordenamiento. Valores posibles: asc, desc. Por defecto es asc.

Ejemplo:
/api/github/user/username/repos?sort=updated&direction=desc

Errores Posibles:
404 Not Found: El nombre de usuario proporcionado no existe.
400 Bad Request: El parámetro username no es válido.
500 Internal Server Error: Error del servidor al procesar la solicitud.

4. Obtener Detalles del Repositorio
Endpoint: /api/github/user/:username/repos/:repo
Método: GET
Parámetros de Ruta:
:username (string) - Nombre de usuario de GitHub.
:repo (string) - Nombre del repositorio.
Ejemplo:
/api/github/user/:username/repos/:repo

Errores Posibles:
404 Not Found: El repositorio especificado no existe.
400 Bad Request: Los parámetros username o repo no son válidos.
500 Internal Server Error: Error del servidor al procesar la solicitud.
