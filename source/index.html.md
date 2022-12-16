---
title: API rute

language_tabs: # must be one of https://git.io/vQNgJ
  - Postman

includes:
  - errors

meta:
  - name: opis
    content: Dokumentacija za Films API
---

# Korisnici

## Vrati korisnike

```Postman
GET http://example.com/api/users
```

> Naredba vraća podatke u JSON formatu:

```json
{
    "users": [
        {
            "id": 1,
            "name": "Mihailo",
            "email": "mihailo@gmail.com"
        },
        {
            "id": 2,
            "name": "Marko",
            "email": "marko@gmail.com"
        }
    ]
}
```

Ovaj endpoint vraća sve korisnike. Svi imaju pristup.

### HTTP zahtev

`GET http://example.com/api/users`

## Registracija

```Postman
POST http://example.com/api/register
```

> Naredba vraća podatke u JSON formatu:

```json
{
    "data": {
        "name": "Milan",
        "email": "milan@gmail.com",
        "updated_at": "2022-12-16T10:48:12.000000Z",
        "created_at": "2022-12-16T10:48:12.000000Z",
        "id": 3
    },
    "access_token": "3|lnn9nDz0nOk8lsPGFWbLogyPzviFHWOpKGc2F1cB",
    "token_type": "Bearer"
}
```

Ovaj endpoint registruje korisnika. Svi imaju pristup.

### HTTP zahtev

`POST http://example.com/api/register`

## Prijava

```Postman
POST http://example.com/api/login
```

> Naredba vraća podatke u JSON formatu:

```json
{
    "message": "Milan, welcome!",
    "access_token": "4|SDsSh4T6nXsM4tP4xwM5jr8PP16Nii82xt2UXY98",
    "token_type": "Bearer"
}
```

Ovaj endpoint prijavljuje korisnika. Svi imaju pristup.

### HTTP zahtev

`POST http://example.com/api/login`

## Profil

```Postman
GET http://example.com/api/profile
```

> Naredba vraća podatke u JSON formatu:

```json
{
    "id": 5,
    "name": "Milan",
    "email": "milan@gmail.com",
    "email_verified_at": null,
    "created_at": "2022-12-16T10:48:12.000000Z",
    "updated_at": "2022-12-16T10:48:12.000000Z"
}
```

Ovaj endpoint prikazuje profil prijavljenog korisnika. Samo autentifikovani korisnik ima pristup.

### HTTP zahtev

`GET http://example.com/api/profile`

## Odjava

```Postman
POST http://example.com/api/logout
```

> Naredba vraća podatke u JSON formatu:

```json
{
    "message": "You have successfully logged out and the token has been successfully deleted."
}
```

Ovaj endpoint odjavljuje korisnika. Samo autentifikovani korisnici imaju pristup.

### HTTP zahtev

`POST http://example.com/api/logout`

# Žanrovi

## Vrati žanrove

```Postman
GET http://example.com/api/genres
```

> Naredba vraća podatke u JSON formatu:

```json
{
    "genres": [
        {
            "id": 1,
            "name": "Adventure"
        },
        {
            "id": 2,
            "name": "Drama"
        },
        {
            "id": 3,
            "name": "Horror"
        }
    ]
}
```

Ovaj endpoint vraća sve žanrove. Svi imaju pristup.

### HTTP zahtev

`GET http://example.com/api/genres`

# Režiseri

## Vrati režisere

```Postman
GET http://example.com/api/directors
```

> Naredba vraća podatke u JSON formatu:

```json
{
    "directors": [
        {
            "id": 1,
            "first_name": "James",
            "last_name": "Cameron",
            "user": 2
        },
        {
            "id": 2,
            "first_name": "Ruben",
            "last_name": "Östlund",
            "user": 3
        }
    ]
}
```

Ovaj endpoint vraća sve režisere. Svi imaju pristup.

### HTTP zahtev

`GET http://example.com/api/directors`

## Vrati režisera

```Postman
GET http://example.com/api/directors/2
```

> Naredba vraća podatke u JSON formatu:

```json
{
    "director": {
        "id": 2,
        "first_name": "Ruben",
        "last_name": "Östlund",
        "user": 2
    }
}
```

Ovaj endpoint vraća konkretnog režisera. Svi imaju pristup.

### HTTP zahtev

`GET http://example.com/api/directors/<ID>`

### URL parametri

Parametar | Opis
--------- | -----------
ID | ID režisera koji treba da se vrati


## Sačuvaj režisera

```Postman
POST http://example.com/api/directors
```

> Naredba vraća podatke u JSON formatu:

```json
[
    "The director has been added successfully.",
    {
        "id": 3,
        "first_name": "Patty",
        "last_name": "Jenkins",
        "user": 1
    }
]
```

Ovaj endpoint čuva konkretnog režisera. Samo autentifikovani korisnici imaju pristup.

### HTTP zahtev

`POST http://example.com/api/directors`

## Ažuriraj režisera

```Postman
PUT http://example.com/api/directors/3
```

> Naredba vraća podatke u JSON formatu:

```json
[
    "The director has been updated successfully.",
    {
        "id": 3,
        "first_name": "James",
        "last_name": "Gunn",
        "user": 1
    }
]
```

Ovaj endpoint ažurira konkretnog režisera. Samo autentifikovani korisnici imaju pristup.

### HTTP Request

`PUT http://example.com/api/directors/<ID>`

### URL Parameters

Parametar | Opis
--------- | -----------
ID | ID režisera koji treba da se ažurira

## Obriši režisera

```Postman
DELETE http://example.com/api/directors/3
```

> Naredba vraća podatke u JSON formatu:

```json
[
    "The director has been deleted successfully."
]
```

Ovaj endpoint briše konkretnog režisera. Samo autentifikovani korisnici imaju pristup.

### HTTP zahtev

`DELETE http://example.com/api/directors/<ID>`

### URL parametri

Parametar | Opis
--------- | -----------
ID | ID režisera koji treba da se obriše

# Filmovi

## Vrati filmove

```Postman
GET http://example.com/api/films
```

> Naredba vraća podatke u JSON formatu:

```json
{
    "films": [
        {
            "id": 1,
            "year": "2022",
            "title": "Avatar: The Way of Water",
            "tagline": "Return to Pandora",
            "synopsis": "Set more than a decade after the events of the first film, learn the story of the Sully family (Jake, Neytiri, and their kids), the trouble that follows them, the lengths they go to keep each other safe, the battles they fight to stay alive, and the tragedies they endure.",
            "genre": 1,
            "director": 1,
            "user": 1
        },
        {
            "id": 2,
            "year": "2022",
            "title": "The Triangle of Sadness",
            "tagline": "Sans filtre",
            "synopsis": "A celebrity model couple are invited on a luxury cruise for the uber-rich, helmed by an unhinged captain. What first appeared Instagrammable ends catastrophically, leaving the survivors stranded on a desert island and fighting for survival."
            "genre": 2,
            "director": 2,
            "user": 1
        },
        {
            "id": 3,
            "year": "2017",
            "title": "The Square",
            "tagline": "The Square is a sanctuary of trust and caring",
            "synopsis": "A prestigious Stockholm museum's chief art curator finds himself in times of both professional and personal crisis as he attempts to set up a controversial new exhibit.",
            "genre": 2,
            "director": 2,
            "user": 1
        }
    ]
}
```

Ovaj endpoint vraća sve filmove. Svi imaju pristup.

### HTTP zahtev

`GET http://example.com/api/films`

## Vrati film

```Postman
GET http://example.com/api/films/2
```

> Naredba vraća podatke u JSON formatu:

```json
{
    "film": {
        "id": 2,
        "year": "2022",
        "title": "The Triangle of Sadness",
        "tagline": "Sans filtre",
        "synopsis": "A celebrity model couple are invited on a luxury cruise for the uber-rich, helmed by an unhinged captain. What first appeared Instagrammable ends catastrophically, leaving the survivors stranded on a desert island and fighting for survival."
        "genre": 2,
        "director": 2,
        "user": 1
    }
}
```

Ovaj endpoint vraća konkretan film. Svi imaju pristup.

### HTTP zahtev

`GET http://example.com/api/films/<ID>`

### URL parametri

Parametar | Opis
--------- | -----------
ID | ID filma koji treba da se vrati

## Vrati filmove režisera

```Postman
GET http://example.com/api/directors/2/films
```

> Naredba vraća podatke u JSON formatu:

```json
{
    "films": [
        {
            "id": 2,
            "year": "2022",
            "title": "The Triangle of Sadness",
            "tagline": "Sans filtre",
            "synopsis": "A celebrity model couple are invited on a luxury cruise for the uber-rich, helmed by an unhinged captain. What first appeared Instagrammable ends catastrophically, leaving the survivors stranded on a desert island and fighting for survival."
            "genre": 2,
            "director": 2,
            "user": 1
        },
        {
            "id": 3,
            "year": "2017",
            "title": "The Square",
            "tagline": "The Square is a sanctuary of trust and caring",
            "synopsis": "A prestigious Stockholm museum's chief art curator finds himself in times of both professional and personal crisis as he attempts to set up a controversial new exhibit.",
            "genre": 2,
            "director": 2,
            "user": 1
        }
    ]
}
```

Ovaj endpoint vraća sve filmove konkretnog režisera. Svi imaju pristup.

### HTTP zahtev

`GET http://example.com/api/directors/<ID>/films`

### URL parametri

Parametar | Opis
--------- | -----------
ID | ID režisera čiji filmovi treba da se vrate

## Vrati filmove žanra

```Postman
GET http://example.com/api/genres/1/films
```

> Naredba vraća podatke u JSON formatu:

```json
{
    "films": [
        {
            "id": 1,
            "year": "2022",
            "title": "Avatar: The Way of Water",
            "tagline": "Return to Pandora",
            "synopsis": "Set more than a decade after the events of the first film, learn the story of the Sully family (Jake, Neytiri, and their kids), the trouble that follows them, the lengths they go to keep each other safe, the battles they fight to stay alive, and the tragedies they endure.",
            "genre": 1,
            "director": 1,
            "user": 1
        }
    ]
}
```

Ovaj endpoint vraća sve filmove konkretnog žanra. Svi imaju pristup.

### HTTP zahtev

`GET http://example.com/api/genres/<ID>/films`

### URL parametri

Parametar | Opis
--------- | -----------
ID | ID žanra čiji filmovi treba da se vrate

## Sačuvaj film

```Postman
POST http://example.com/api/films
```

> Naredba vraća podatke u JSON formatu:

```json
[
    "The film has been added successfully.",
    {
        "id": 1,
        "year": "2014",
        "title": "The Tourist",
        "tagline": "The consequences in the fear and flight situation",
        "synopsis": "While holidaying in the French Alps, a Swedish family deals with acts of cowardliness as an avalanche breaks out.",
        "genre": 2,
        "director": 2,
        "user": 2
    }
]
```

Ovaj endpoint čuva konkretan film. Samo autentifikovani korisnici imaju pristup.

### HTTP zahtev

`POST http://example.com/api/films`

## Ažuriraj film

```Postman
PUT http://example.com/api/films/4
```

> Naredba vraća podatke u JSON formatu:

```json
[
    "The film has been updated successfully.",
    {
        "id": 1,
        "year": "2014",
        "title": "Force Majeure",
        "tagline": "The consequences in the fear and flight situation",
        "synopsis": "While holidaying in the French Alps, a Swedish family deals with acts of cowardliness as an avalanche breaks out.",
        "genre": 2,
        "director": 2,
        "user": 2
    }
]
```

Ovaj endpoint ažurira konkretan film. Samo autentifikovani korisnici imaju pristup.

### HTTP Request

`PUT http://example.com/api/films/<ID>`

### URL Parameters

Parametar | Opis
--------- | -----------
ID | ID filma koji treba da se ažurira

## Obriši film

```Postman
DELETE http://example.com/api/films/4
```

> Naredba vraća podatke u JSON formatu:

```json
[
    "The film has been deleted successfully."
]
```

Ovaj endpoint briše konkretan film. Samo autentifikovani korisnici imaju pristup.

### HTTP zahtev

`DELETE http://example.com/api/films/<ID>`

### URL parametri

Parametar | Opis
--------- | -----------
ID | ID filma koji treba da se obriše