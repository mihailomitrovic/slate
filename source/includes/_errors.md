# Greške

Films API koristi naredne kodove za greške:

Kod za grešku | Značenje
---------- | -------
400 | Bad Request -- Nevalidan zahtev.
401 | Unauthorized -- Pogrešan API ključ.
403 | Forbidden -- Zahtevani objekat je vidljiv samo administratorima.
404 | Not Found -- Objekat nije pronađen.
405 | Method Not Allowed -- Pokušali ste da pristupite objektu nevalidnom metodom.
406 | Not Acceptable -- Zahtevate format koji nije JSON.
410 | Gone -- Zahtevani objekat je uklonjen sa našeg servera.
418 | Ja sam šoljica čaja.
429 | Too Many Requests -- Zahtevate previše objekata! Usporite!
500 | Internal Server Error -- Imamo problem sa serverom. Pokušajte kasnije.
503 | Service Unavailable -- Privremeno smo offline zbog radova. Pokušajte kasnije.
