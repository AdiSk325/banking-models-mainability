# Etap 5.1: Inicjacja i Zgłoszenie Potrzeby Modelowej

> **Część:** Model Lifecycle Guide — Rozdział 5 (Etapy Lifecycle)  
> **Status:** Draft  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](../MODEL_LIFECYCLE_GUIDE.md) | [Poprzedni: Przegląd](../04_przeglad_cyklu_zycia.md) | [Następny: Dane →](./02_pozyskanie_danych.md)

---

## Cel Etapu

Formalne zgłoszenie potrzeby modelowej, wstępna ocena zasadności i ryzyka, przypisanie ról oraz uzyskanie zgody na rozpoczęcie prac rozwojowych.

---

## Kto wykonuje

| Rola | Aktywność |
|------|-----------|
| **Business Owner / Sponsor** | Inicjuje potrzebę, opisuje cel biznesowy |
| **Model Owner** | Przyjmuje ownership, formalnie sponsoruje projekt |
| **Data Scientist** | Uczestniczy w ocenie wykonalności, wstępna analiza danych |
| **Model Risk Management** | Weryfikacja klasyfikacji, akceptacja do rozpoczęcia |

---

## Wejścia (Inputs)

- Potrzeba biznesowa lub regulacyjna (nieformalne zgłoszenie)
- Obowiązujące regulacje lub zmiany regulacyjne
- Wyniki przeglądu istniejącego modelu (jeśli inicjacja to re-development)

---

## Główne Aktywności

<!-- PROMPT DLA AUTORA:
Opisz szczegółowo jak przebiega etap inicjacji w organizacji.
Jakie są formalne kroki? Jaki formularz? Kto jest zaangażowany?
Czy istnieje formalny rejestr inicjacji / pipeline modeli?
-->

1. **Opis potrzeby biznesowej** — Business Owner opisuje cel, problem do rozwiązania, oczekiwany wpływ
2. **Wstępna ocena wykonalności** — Data Scientist ocenia dostępność danych i wykonalność techniczną
3. **Wstępna klasyfikacja modelu** — MRM przypisuje Tier (patrz [Rozdział 3](../03_klasyfikacja_modeli.md))
4. **Przypisanie ról** — formalnie wskazywany Model Owner, Data Scientist lead
5. **Przygotowanie Model Concept Note** — dokument inicjacyjny (patrz szablon)
6. **Rejestracja wstępna w Model Inventory** — nadanie identyfikatora modelu
7. **Uzyskanie akceptacji Gate 1** — sign-off od Model Ownera i MRM

---

## Wymagane Artefakty

| Artefakt | Opis | Obowiązkowość |
|----------|------|---------------|
| **Model Concept Note** | Opis celu, zakresu, metodologii wstępnej, danych, ryzyk | ✅ Obowiązkowy |
| **Regulatory Mapping** | Mapowanie do regulacji (tylko Kategoria A) | ✅ Kategoria A |
| **Wstępna Ocena Ryzyka** | Wstępna klasyfikacja Tier i uzasadnienie | ✅ Obowiązkowy |
| **Model Inventory Entry (initial)** | Rejestracja z podstawowymi danymi | ✅ Obowiązkowy |
| **Approval Record (Gate 1)** | Podpis Model Ownera i MRM | ✅ Obowiązkowy |

---

## Kryteria Wejścia (Stage Gate 1 — Input)

- Potrzeba biznesowa jest zidentyfikowana i opisana
- Dostępność zasobów (DS, Data Owner) wstępnie potwierdzona

## Kryteria Wyjścia — Stage Gate 1

- [ ] Model Concept Note ukończony i zaakceptowany
- [ ] Tier przypisany przez MRM
- [ ] Model Owner formalnie wskazany
- [ ] Wstępna rejestracja w Model Inventory
- [ ] Akceptacja do rozpoczęcia prac (Model Owner + MRM sign-off)

---

## Specyfika według Kategorii Modelu

| Kategoria | Dodatkowe wymagania na etapie inicjacji |
|-----------|----------------------------------------|
| A — Regulacyjny | Regulatory Mapping Document jako obowiązkowy element Concept Note |
| B — Scorecard | Opis populacji docelowej i zmiennych wstępnie planowanych |
| C — Supervised ML | Wstępne określenie targetów, dostępności etykiet, horyzontu predykcji |
| D — Unsupervised | Uzasadnienie biznesowe "co model ma odkryć / umożliwić" |

---

## Najczęstsze Błędy na tym Etapie

<!-- PROMPT DLA AUTORA:
Uzupełnij o typowe problemy obserwowane w organizacji.
Przykłady: brak wyraźnego celu biznesowego, model owner wyznaczony "na papierze" bez zaangażowania, brak analizy dostępności danych.
-->

- ❌ Brak jasnego celu biznesowego — "zbudujemy model i zobaczymy co wyjdzie"
- ❌ Model Owner wskazany formalnie bez faktycznego zaangażowania
- ❌ Pominięcie MRM przy inicjacji i klasyfikacji
- ❌ Brak rejestracji w Model Inventory od początku procesu

---

*Szablony: [Model Concept Note Template](../../templates/), [Model Risk Assessment Form](../../templates/)*
