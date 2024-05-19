# 24001118-synrgy7-ars-bcr-ch5
# 24001118-synrgy7-ars-bcr-ch5
## CHALLENGE 5 RESTFUL API FSW 2 ARSY MUHAMMAD IQBAL

### INSTRUCTION
1. Clone project into your local
2. Change directory to this project folder `cd 24001118-synrgy7-ars-bcr-ch5`
3. Use command `npm install` to install all packages
4. Next step use command `npm run compile` to compile TypeScript into JavaScript
5. Copy `.env.example` file to `.env` and fill up the correct value of your PostgreSQL connection!
6. Run command `npx knex migration:up` to create table via migration
7. Run command `npm run dev`

### ENDPOINT LIST

| API ENDPOINT    | METHOD   |     DESCRIPTION        |
|-----------------|----------|------------------------|
| `/cars`         |   `GET`  | Get All Data Cars      |
| `/cars/:id`     |   `GET`  | Get Data Cars By Id    |
| `/cars/create`  |  `POST`  | Post Data Cars         |
| `/cars/:id`     |   `PUT`  | Update Data Cars By Id |
| `/cars/:id`     | `DELETE` | Delete Data Cars By Id |

### EXAMPLE DATA
- **Show All Data Cars**
    - **Request** 
        - Endpoint : `/cars`
        - method : `GET`
    - **Response**
        - Json Response :
        ```json
    {
    "status": true,
    "message": "OK",
    "data": [
        {
            "id": 1,
            "name": "Toyota Innova Reborn",
            "year": "2024",
            "price": "Rp, 7000.0000",
            "image_url": "opokui",
            "startRent": "05/14/2024",
            "finishRent": "16/14/2024",
            "created_at": "2024-05-18T05:56:41.804Z",
            "updated_at": "2024-05-18T05:56:41.804Z"
        },
        {
            "id": 4,
            "name": "Kijang Kapsul",
            "year": "2000",
            "price": "Rp. 200000",
            "image_url": "http://res.cloudinary.com/dywme8e2k/image/upload/v1716111564/fsw/xqar7f5i5veqe4yuzvzj.png",
            "startRent": "05/14/2024",
            "finishRent": "05/14/2024",
            "created_at": "2024-05-19T09:39:23.592Z",
            "updated_at": "2024-05-19T09:39:23.592Z"
        },
        {
            "id": 5,
            "name": "Toyota Yaris",
            "year": "2000",
            "price": "Rp. 200000",
            "image_url": "http://res.cloudinary.com/dywme8e2k/image/upload/v1716121812/fsw/y8fw9sfrusz2twxzn78q.png",
            "startRent": "05/14/2024",
            "finishRent": "05/14/2024",
            "created_at": "2024-05-19T12:30:12.614Z",
            "updated_at": "2024-05-19T12:30:12.614Z"
        }
    ]
}
        ```
        - Status code : `200`

- **Show Data Cars By Id**
    - **Request** 
        - Endpoint : `/cars/:id`
        - Parameter: `:id`
        - method : `GET`
    - **Response**
        - Json Response :
        ```json
  {
      "status": true,
      "message": "OK",
      "data": {
          "id": 5,
          "name": "Toyota Yaris",
          "year": "2000",
          "price": "Rp. 200000",
          "image_url": "http://res.cloudinary.com/dywme8e2k/image/upload/v1716121812/fsw/y8fw9sfrusz2twxzn78q.png",
          "startRent": "05/14/2024",
          "finishRent": "05/14/2024",
          "created_at": "2024-05-19T12:30:12.614Z",
          "updated_at": "2024-05-19T12:30:12.614Z"
      }
  }
        ```
        - Status Code : `200`

- **Insert Data Cars**
    - **Request**
        - Endpoint : `/cars/create`
        - Body : `form-data`
        - Method : `POST`
        - Form Data :

        | Key         | Value                    |
        | ----------- | ------------------------ |
        | name        | Porche 911               |
        | year        | 2023                     |
        | price       | Rp. 20000000             |
        | image_url   | file: download.jpeg      |
        | startRent   | 19/4/2024                |
        | finishRent  | 20/4/2024                |
    - **Response**
        - Json Response :
        ```json
        {
    "status": true,
    "message": "Successfully created",
    "data": {
        "name": "Porche 911",
        "year": "2023",
        "price": "Rp. 20000000",
        "startRent": "19/4/2024",
        "finishRent": "20/4/2024",
        "image_url": "http://res.cloudinary.com/dywme8e2k/image/upload/v1716124035/fsw/uhxplchga7jpgqo13zzi.jpg",
        "id": 9
            }
        }
        ```
        - Status Code : `200`

- **Update Data Cars**
    - **Request**
        - Endpoint : `/cars/:id`
        - Parameter : `:id`
        - Body : `form-data`
        - Method : `PUT`
        - Form Data :

        | Key         | Value                    |
        | ----------- | ------------------------ |
        | name        | Lamborgini Aventador     |
        | year        | 2023                     |
        | price       | Rp. 100000               |
        | picture     | file: download.jpeg      |
        | start_rent  | 8/4/2024                 |
        | finish_rent | 20/4/2024                |
    - **Response**
        - Json Response :
        ```json
     {
        "status": true,
        "message": "Successfully update car",
        "data": {
            "name": "Lamborgini Aventador",
            "price": "Rp. 100000",
            "year": "2023",
            "startRent": "18/4/2024",
            "finishRent": "20/4/2024",
            "image_url": "http://res.cloudinary.com/dywme8e2k/image/upload/v1716125411/fsw/rnjaqnqdhauktfz3pk4b.jpg",
            "id": 5,
            "created_at": "2024-05-19T12:30:12.614Z",
            "updated_at": "2024-05-19T12:30:12.614Z"
          }
      }
        ```
        - Status Code : `200`

- **Delete Data Cars**
    - **Request**
        - Endpoint : `/cars/:id`
        - Parameter : `:id`
        - Method : `DELETE`
    - **Response**
        - Json Response :
        ```json
        {
    "status": true,
    "message": "Successfully deleted car",
    "data": [
        {
            "id": 1,
            "name": "Toyota Innova Reborn",
            "year": "2024",
            "price": "Rp, 7000.0000",
            "image_url": "opokui",
            "startRent": "05/14/2024",
            "finishRent": "16/14/2024",
            "created_at": "2024-05-18T05:56:41.804Z",
            "updated_at": "2024-05-18T05:56:41.804Z"
        },
        {
            "id": 4,
            "name": "Kijang Kapsul",
            "year": "2000",
            "price": "Rp. 200000",
            "image_url": "http://res.cloudinary.com/dywme8e2k/image/upload/v1716111564/fsw/xqar7f5i5veqe4yuzvzj.png",
            "startRent": "05/14/2024",
            "finishRent": "05/14/2024",
            "created_at": "2024-05-19T09:39:23.592Z",
            "updated_at": "2024-05-19T09:39:23.592Z"
        },
        {
            "id": 6,
            "name": "Toyota Alphard",
            "year": "2000",
            "price": "Rp. 200000",
            "image_url": "http://res.cloudinary.com/dywme8e2k/image/upload/v1716122540/fsw/ors3pyvmgj5ksjrpkvrh.png",
            "startRent": "05/14/2024",
            "finishRent": "05/14/2024",
            "created_at": "2024-05-19T12:42:20.315Z",
            "updated_at": "2024-05-19T12:42:20.315Z"
        },
        {
            "id": 8,
            "name": "Datsun Go",
            "year": "2000",
            "price": "Rp. 200000",
            "image_url": "http://res.cloudinary.com/dywme8e2k/image/upload/v1716122699/fsw/mvnht5kne00tmww2d63h.png",
            "startRent": "05/14/2024",
            "finishRent": "05/14/2024",
            "created_at": "2024-05-19T12:44:59.768Z",
            "updated_at": "2024-05-19T12:44:59.768Z"
        },
        {
            "id": 9,
            "name": "Porche 911",
            "year": "2023",
            "price": "Rp. 20000000",
            "image_url": "http://res.cloudinary.com/dywme8e2k/image/upload/v1716124035/fsw/uhxplchga7jpgqo13zzi.jpg",
            "startRent": "19/4/2024",
            "finishRent": "20/4/2024",
            "created_at": "2024-05-19T13:07:15.466Z",
            "updated_at": "2024-05-19T13:07:15.466Z"
        }
    ]
}
        ```
        - Status Code : `200`

### ERD (Entity Relationship Diagram)
![Untitled](https://github.com/amiqbal7/24001118-synrgy7-ars-bcr-ch5/assets/89888051/df94431f-067c-4965-97e8-54c511b694ac)
