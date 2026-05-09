# STD-005: Standard Inwentarza Modeli

> **Typ dokumentu:** Standard (Poziom 2)  
> **Status:** 🔄 Szkielet  
> **Powiązany rozdział przewodnika:** Etapy 2, 9, 12, 13

---

## Cel standardu

Standard określa wymagania dla centralnego inwentarza modeli — centralnego rejestru wszystkich modeli używanych lub rozwijanych w organizacji.

---

## 1. Obowiązek Rejestracji

> 🔴 **OBOWIĄZKOWE** — Każdy model musi być zarejestrowany w inwentarzu przed rozpoczęciem developmentu.  
> Brak wpisu w inwentarzu = model nieautoryzowany.

---

## 2. Minimalne Pola Wpisu w Inwentarzu

| Pole | Opis | Obowiązkowe? |
|---|---|---|
| ID modelu | Unikalny identyfikator | Tak |
| Nazwa modelu | Opisowa nazwa | Tak |
| Typ modelu | Regulacyjny / Supervised / Unsupervised / Inny | Tak |
| Tier | 1 / 2 / 3 | Tak |
| Status | In Development / Validation / Approved / Production / Retired | Tak |
| Model Owner | Imię/nazwisko i jednostka | Tak |
| Data Scientist / Developer | Imię/nazwisko | Tak |
| Validator | Imię/nazwisko / jednostka | Tak (Tier 1/2) |
| Data rejestracji | Data inicjacji | Tak |
| Data wdrożenia | Data pierwszego wdrożenia produkcyjnego | Tak (po wdrożeniu) |
| Data ostatniego przeglądu | Data ostatniego annual review | Tak |
| Data planowanego przeglądu | Następny zaplanowany review | Tak |
| Opis zastosowania | Skrótowy opis use case | Tak |
| Lokalizacja dokumentacji | Link do MDD | Tak |
| Lokalizacja kodu | Link do repozytorium Git | Tak |
| Otwarte findings | Liczba i najwyższa kategoria otwartych findings | Tak |
| Open exceptions | Liczba aktywnych wyjątków | Tak |

---

## 3. Stany Modelu w Inwentarzu

```
[Zarejestrowany] → [In Development] → [In Validation] → [Approved] → [Production]
                                                                           ↓
                                                                    [Under Review]
                                                                           ↓
                                                               [Production] lub [Retired]
```

---

## 4. Zasady Utrzymania Inwentarza

> ✍️ **[DO UZUPEŁNIENIA]** Opisać:
> - Kto odpowiada za aktualizację inwentarza
> - Jak często jest przeglądany
> - Jak usuwane są modele wycofane
> - Jak weryfikowana jest kompletność inwentarza

---

## Powiązania

- [Rozdział 4: Przegląd Cyklu Życia](../00_guide/04_przeglad_cyklu_zycia.md)
- [PROC-001: Procedura Inicjacji](../02_procedures/PROC-001_inicjacja.md)
