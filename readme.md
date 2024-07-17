## modelo vista controlador
modelos ---> estructuras de la base de datos
(1 modelo por cada colección de mi BBDD , 1 modelo para el estudiante y 1un modelo para los profes)
vistas---> interfaces graficas
rutas--> (routes express())
controladores-- > funciones de la logica del negocio (las funciones que se ejecutaran al entrar en un endpoint o ruta)

## Uso de la api 
- **Registro de usuario** para registrar un usuario es neceario enviar un objeto con la siguiente estructura, donde la contraseña debe tener letras numeros y una mayúscula
 ***https://proyecto-node-vercel.onrender.com/user/register***

  ```json
  {
    "name": "maricarmen" ,
    "email": "maricarmen@gmail.com" ,
    "password": "Maricarmen123"
  }
  ```
**fetch** La peticion al servidor quedara algo como lo siguiente:

```js
  fetch(' https://proyecto-node-vercel.onrender.com/user/register', {
      method: 'POST',
      body: JSON.stringify({
        name: 'dayana',
        email: 'dayana1239@gmail.com',
        password: 'Dayana123',
      }),
      headers: {
        'Content-Type': 'application/json',
      },
    })
```
  **respuesta**
  ```json
    {
      "success": true,
      "data": {
          "name": "dayana",
          "email": "dayana1234@gmail.com",
          "password": "$2b$10$ZCWXL7N967Q2O3NLa79tcuMwCmS3KMoHaDQ.o3sdQ2o6uME9QBK0C",
          "role": "user",
          "image": "",
          "_id": "6697feba3651cfc3ca3a8315",
          "__v": 0
      }
    }
  ```
- **Login de usuario** Para el login de usuario es necesario enviar un objeto con la siguiente estructura 
  ***https://proyecto-node-vercel.onrender.com/user/login***
  ```json
     {
        "email": "maricarmen@gmail.com" ,
        "password": "Maricarmen123"
     }
  ```
  
  **respuesta**
  ```json
    {
      "success": true,
      "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiZGF5YW5hIiwiZW1haWwiOiJkYXlhbmExMjM0QGdtYWlsLmNvbSIsIl9pZCI6IjY2OTdmZWJhMzY1MWNmYzNjYTNhODMxNSIsImlhdCI6MTcyMTIzNzIyMiwiZXhwIjoxNzIxMjQwODIyfQ.ZC0eg2_aBGaIbgh3YzwOE_xzzq1vsKqScox7P1M-TNw"
    }
  ```
- **Validar token** Para validar si el usuario esta logado, se debe hacer una petición a la siguiente ruta, enviando el token generado y si es corecto te devolvera una resùesta como la siguiente 
  ***https://proyecto-node-vercel.onrender.com/user/isLogin***
  
  **respuesta**
  ```json
  {
    "success": true,
    "token": "correct"
  }
  ```
