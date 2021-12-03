<p align="center">
  <h1 align="center">AxioWeb API</h1>
</p>

Base URL Dev: https://axioweb-real-estate.herokuapp.com
# Access

## Login 
Endpoit para iniciar sesion

### Headers
```
Path: /AxioWeb/user/login
Methos: POST
Headers: {
  Accept: "application/json",
  "Content-Type": "application/json"
}
```
### Body
```
{
  // @axioweb.com para empleados y @gmail.com para usuarios
  "email": "fernando@axioweb.com",
  "password": "romo"
}
```
### Response success
```
  Token
```

## Register
Endpoit para registrarse como usuario

### Headers
```
Path: /AxioWeb/user/register
Methos: POST
Headers: {
  Accept: "application/json",
  "Content-Type": "application/json"
}
```
### Body
```
{
  "username": "Fernando Romo",
  "email": "fernando@gmail.com",
  "password": "romo"
}
```
### Response success
```
  Token
```
# Admin

## Create user
Endpoint para crear un admin, employee o user

### Headers
```
Path: /AxioWeb/user/create
Methos: POST
Headers: {
  Accept: "application/json",
  "Content-Type": "application/json",
  "x-access-token": token
}
```
### Body
```
{
  // @axioweb.com para empleados y @gmail.com para usuarios
    "username": "Fernando Romo",
    "email": "fernando@axioweb.com",
    "password": "romo",
    "roles": ["employee"]
}
```
### Response success
```
{
    {
    "_id": "619fbef2b7b6a3717ef0bd95",
    "username": "Fernando Romo",
    "email": "fernando@axioweb.com",
    "roles": [
        "619c89cdfa94542c830143c0"
    ]
}
```

## Delete estate
Endpoint para eliminar un inmueble en especifico a traves del ID

### Headers
```
Path: /AxioWeb/estate/:id
Methos: DELETE
Headers: {
  Accept: "application/json",
  "Content-Type": "application/json",
  "x-access-token": token
}
```
### Response success
```
{
    "message": "Estate deleted successfully"
}
```
# Authorized Personal 

## Get user estates
Endpoit para obtener todos los inmuebles 

### Headers
```
Path: /AxioWeb/user_estates
Methos: GET
Headers: {
  Accept: "application/json",
  "Content-Type": "application/json",
  "x-access-token": token
}
```

### Response success
```
[
    {
        "details": {
            "terrain": "1,200",
            "preserved": "Excelente",
            "service_room": true,
            "rooms": 4,
            "floors": 2,
            "parking": 1,
            "construction": "1,850",
            "old_estate": "5",
            "bathrooms": "3",
            "maintenance": "0"
        },
        "location": {
            "type": "Point",
            "coordinates": [
                20.2742,
                -104.2697
            ]
        },
        "contact": {
            "username": "Fernando Romo",
            "email": "fernando@axioweb.com"
        },
        "_id": "619fbf3ab7b6a3717ef0bdab",
        "name": "Jardines del norte",
        "description": "Casa en jardines del norte",
        "price": "1000000",
        "estate_type": "DEPARTAMENT",
        "estate_status": "RENT",
        "status": "SALE",
        "imgs": [
            {
                "id_media": "AxioWeb/nda3hblpeqavnoksywpe",
                "media": "http://res.cloudinary.com/duytv65yt/image/upload/v1637859215/AxioWeb/nda3hblpeqavnoksywpe.jpg"
            },
            {
                "id_media": "AxioWeb/lahv7ijulizbjlbwcqz6",
                "media": "http://res.cloudinary.com/duytv65yt/image/upload/v1637859216/AxioWeb/lahv7ijulizbjlbwcqz6.jpg"
            }
        ],
        "areas": [
            "Bodega",
            "Park"
        ],
        "equipped": [
            "Cisterna"
        ],
        "createdAt": "2021-11-25T16:52:10.971Z",
        "updatedAt": "2021-11-25T16:54:59.130Z",
        "__v": 0
    },
    {
        "details": {
            "terrain": "1,253",
            "preserved": "Excelente",
            "service_room": true,
            "rooms": 4,
            "floors": 3,
            "parking": 2,
            "construction": "1,850",
            "old_estate": "11",
            "bathrooms": "6.5",
            "maintenance": "0"
        },
        "location": {
            "type": "Point",
            "coordinates": [
                20.2742,
                -104.2697
            ]
        },
        "contact": {
            "username": "Fernando Romo",
            "email": "fernando@axioweb.com"
        },
        "_id": "619fbf60b7b6a3717ef0bdb6",
        "name": "Jardines del sur",
        "description": "Casa en jardines del sur",
        "price": "1000000",
        "estate_type": "HOUSE",
        "estate_status": "SALE",
        "status": "SALE",
        "imgs": [
            {
                "id_media": "AxioWeb/u6slzrcg55mfylmy0ll0",
                "media": "http://res.cloudinary.com/duytv65yt/image/upload/v1637859167/AxioWeb/u6slzrcg55mfylmy0ll0.jpg"
            },
            {
                "id_media": "AxioWeb/yk2bqwbzqmuxh6qnsdsv",
                "media": "http://res.cloudinary.com/duytv65yt/image/upload/v1637859167/AxioWeb/yk2bqwbzqmuxh6qnsdsv.jpg"
            },
            {
                "id_media": "AxioWeb/zvwlkgx5oeft5bou9wez",
                "media": "http://res.cloudinary.com/duytv65yt/image/upload/v1637859167/AxioWeb/zvwlkgx5oeft5bou9wez.jpg"
            }
        ],
        "areas": [
            "Bodega"
        ],
        "equipped": [
            "Cisterna"
        ],
        "createdAt": "2021-11-25T16:52:48.173Z",
        "updatedAt": "2021-11-25T16:52:48.173Z",
        "__v": 0
    }
]
```

## Create estate
Endpoint para crear un inmueble

### Headers
```
Path: /AxioWeb/estate
Methos: POST
Headers: {
  Accept: "application/json",
  "Content-Type": "application/json",
  "x-access-token": token
}
```
### Body

```
/* Enviar un form-data y en "media" por tipo file y sube una imagen .jpg  */

"name": "Jardines del sur"
"description": "Casa en jardines del sur"
"price": "1000000"
"estate_type": "HOUSE"
"estate_status": "SALE"
"areas": "Bodega"
"equipped": "Cisterna"
"terrain": "1,253"
"preserved": "Excelente"
"service_room": "true"
"rooms": "4"
"floors": "3"
"parking": "2"
"construction": "1,850"
"old_estate": "11"
"bathrooms": "6.5"
"maintenance": "0"
"coordinates": "20.2742"
"coordinates": "-104.2697"
"media": Jardines 1.jpg
"media": Jardines 2.jpg
"media": Jardines 3.jpg
```
### Response success
```
{
    "message": "Estate created successfully"
}
```
## Update estate
Endpoint para actualizar un inmueble en especifico a traves del ID

### Headers
```
Path: /AxioWeb/estate/:id
Methos: PATCH
Headers: {
  Accept: "application/json",
  "Content-Type": "application/json",
  "x-access-token": token
}
```
### Body
```
/* Se maneja el mismo form-data que en el Create estate */
```
### Response success
```
{
    "message": "Estate updated successfully"
}
```
## Buy a estate
Enpoint para que el usuario pague por un inmueble

### Headers
```
Path: /AxioWeb/estate/:id
Methos: PUT
Headers: {
  Accept: "application/json",
  "Content-Type": "application/json",
  "x-access-token": token
}
```

### Response success
Si el inmueble sigue en venta
```
{
    "message": "Estate sold successfully"
}
```
Si el inmueble ya se vendio
```
{
    "message": "Estate for sale again"
}
```
# Public

## Get user estates
Endpoit para obtener todos los inmuebles 

### Headers
```
Path: /AxioWeb/public_estates
Methos: GET
Headers: {
  Accept: "application/json",
  "Content-Type": "application/json"
}
```

### Response success
```
[
    {
        "details": {
            "terrain": "1,200",
            "preserved": "Excelente",
            "service_room": true,
            "rooms": 4,
            "floors": 2,
            "parking": 1,
            "construction": "1,850",
            "old_estate": "5",
            "bathrooms": "3",
            "maintenance": "0"
        },
        "location": {
            "type": "Point",
            "coordinates": [
                20.2742,
                -104.2697
            ]
        },
        "contact": {
            "username": "Fernando Romo",
            "email": "fernando@axioweb.com"
        },
        "_id": "619fbf3ab7b6a3717ef0bdab",
        "name": "Jardines del norte",
        "description": "Casa en jardines del norte",
        "price": "1000000",
        "estate_type": "DEPARTAMENT",
        "estate_status": "RENT",
        "status": "SALE",
        "imgs": [
            {
                "id_media": "AxioWeb/nda3hblpeqavnoksywpe",
                "media": "http://res.cloudinary.com/duytv65yt/image/upload/v1637859215/AxioWeb/nda3hblpeqavnoksywpe.jpg"
            },
            {
                "id_media": "AxioWeb/lahv7ijulizbjlbwcqz6",
                "media": "http://res.cloudinary.com/duytv65yt/image/upload/v1637859216/AxioWeb/lahv7ijulizbjlbwcqz6.jpg"
            }
        ],
        "areas": [
            "Bodega",
            "Park"
        ],
        "equipped": [
            "Cisterna"
        ],
        "createdAt": "2021-11-25T16:52:10.971Z",
        "updatedAt": "2021-11-25T16:54:59.130Z",
        "__v": 0
    },
    {
        "details": {
            "terrain": "1,253",
            "preserved": "Excelente",
            "service_room": true,
            "rooms": 4,
            "floors": 3,
            "parking": 2,
            "construction": "1,850",
            "old_estate": "11",
            "bathrooms": "6.5",
            "maintenance": "0"
        },
        "location": {
            "type": "Point",
            "coordinates": [
                20.2742,
                -104.2697
            ]
        },
        "contact": {
            "username": "Fernando Romo",
            "email": "fernando@axioweb.com"
        },
        "_id": "619fbf60b7b6a3717ef0bdb6",
        "name": "Jardines del sur",
        "description": "Casa en jardines del sur",
        "price": "1000000",
        "estate_type": "HOUSE",
        "estate_status": "SALE",
        "status": "SALE",
        "imgs": [
            {
                "id_media": "AxioWeb/u6slzrcg55mfylmy0ll0",
                "media": "http://res.cloudinary.com/duytv65yt/image/upload/v1637859167/AxioWeb/u6slzrcg55mfylmy0ll0.jpg"
            },
            {
                "id_media": "AxioWeb/yk2bqwbzqmuxh6qnsdsv",
                "media": "http://res.cloudinary.com/duytv65yt/image/upload/v1637859167/AxioWeb/yk2bqwbzqmuxh6qnsdsv.jpg"
            },
            {
                "id_media": "AxioWeb/zvwlkgx5oeft5bou9wez",
                "media": "http://res.cloudinary.com/duytv65yt/image/upload/v1637859167/AxioWeb/zvwlkgx5oeft5bou9wez.jpg"
            }
        ],
        "areas": [
            "Bodega"
        ],
        "equipped": [
            "Cisterna"
        ],
        "createdAt": "2021-11-25T16:52:48.173Z",
        "updatedAt": "2021-11-25T16:52:48.173Z",
        "__v": 0
    }
    {
        "details": {
            "terrain": "1,253",
            "preserved": "Excelente",
            "service_room": true,
            "rooms": 4,
            "floors": 3,
            "parking": 2,
            "construction": "1,850",
            "old_estate": "11",
            "bathrooms": "6.5",
            "maintenance": "0"
        },
        "location": {
            "type": "Point",
            "coordinates": [
                20.2742,
                -104.2697
            ]
        },
        "contact": {
            "username": "Uriel Romo",
            "email": "uriel@axioweb.com"
        },
        "_id": "619fd7c8d90256d5add67baa",
        "name": "Jardines del sur",
        "description": "Casa en jardines del sur",
        "price": "1000000",
        "estate_type": "HOUSE",
        "estate_status": "SALE",
        "status": "SALE",
        "imgs": [],
        "areas": [
            "Bodega"
        ],
        "equipped": [
            "Cisterna"
        ],
        "createdAt": "2021-11-25T18:36:56.886Z",
        "updatedAt": "2021-11-25T18:36:56.886Z",
        "__v": 0
    }
]
```

## Get estate
Endpoint para obtener un inmueble en especifico a traves del ID
### Headers
```
Path: /AxioWeb/estate/:id
Methos: GET
Headers: {
  Accept: "application/json",
  "Content-Type": "application/json"
}
```
### Response success
```
{
    {
        "details": {
            "terrain": "1,253",
            "preserved": "Excelente",
            "service_room": true,
            "rooms": 4,
            "floors": 3,
            "parking": 2,
            "construction": "1,850",
            "old_estate": "11",
            "bathrooms": "6.5",
            "maintenance": "0"
        },
        "location": {
            "type": "Point",
            "coordinates": [
                20.2742,
                -104.2697
            ]
        },
        "contact": {
            "username": "Uriel Romo",
            "email": "uriel@axioweb.com"
        },
        "_id": "619fd7c8d90256d5add67baa",
        "name": "Jardines del sur",
        "description": "Casa en jardines del sur",
        "price": "1000000",
        "estate_type": "HOUSE",
        "estate_status": "SALE",
        "status": "SALE",
        "imgs": [],
        "areas": [
            "Bodega"
        ],
        "equipped": [
            "Cisterna"
        ],
        "createdAt": "2021-11-25T18:36:56.886Z",
        "updatedAt": "2021-11-25T18:36:56.886Z",
        "__v": 0
    }
}
```