# Pronadji-Majstora-# Pronađi majstora

## Osnovna arhitektura sistema

Aplikacija „Pronađi majstora“ sastoji se od nekoliko glavnih delova:

- Frontend – korisnički interfejs aplikacije
- Backend – glavna logika aplikacije
- API – omogućava komunikaciju između frontenda i backenda
- Baza podataka – čuva podatke o korisnicima, majstorima, uslugama, zahtevima i ocenama
- Sistem za prijavu i bezbednost – omogućava registraciju, prijavu i kontrolu pristupa

## Povezanost delova sistema

Korisnik → Frontend → API → Backend → Baza podataka

Korisnik preko aplikacije šalje zahtev. Frontend prosleđuje zahtev preko API-ja do backenda. Backend obrađuje zahtev, pristupa bazi podataka i vraća rezultat korisniku.

## Dijagram arhitekture

```mermaid
flowchart LR
    U[Korisnik] --> F[Frontend]
    M[Majstor] --> F
    F --> A[API]
    A --> B[Backend]
    B --> DB[(Baza podataka)]

    B --> S[Pretraga i usluge]
    B --> R[Zahtevi i rezervacije]
    B --> O[Ocene i komentari]
    B --> AUTH[Prijava i bezbednost]

    S --> DB
    R --> DB
    O --> DB
    AUTH --> DB
