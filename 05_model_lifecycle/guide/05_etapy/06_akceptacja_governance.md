# Etap 5.6: Akceptacja i Governance

> **Część:** Model Lifecycle Guide — Rozdział 5 (Etapy Lifecycle)  
> **Status:** Draft  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](../MODEL_LIFECYCLE_GUIDE.md) | [← Poprzedni: Walidacja](./05_walidacja_niezalezna.md) | [Następny: Wdrożenie →](./07_wdrozenie.md)

---

## Cel Etapu

Formalna akceptacja modelu przez właściwy komitet lub organ decyzyjny. Etap ten zamyka ścieżkę pre-wdrożeniową i daje formalną zgodę na przejście do implementacji.

---

## Kto wykonuje

| Rola | Aktywność |
|------|-----------|
| **Model Owner** | Prezentacja modelu, wnioskowanie o akceptację |
| **[Komitet Akceptacji Modeli]** | Formalna akceptacja / odrzucenie |
| **MRM** | Opinia, przekazanie wyników walidacji |
| **Compliance** | Weryfikacja zgodności regulacyjnej (Kat. A) |
| **Data Scientist** | Wsparcie techniczne prezentacji jeśli potrzebne |

---

## Główne Aktywności

<!-- PROMPT DLA AUTORA:
Opisz strukturę komitetów akceptujących modele w organizacji.
Kto zasiada w komitecie? Jak często się zbiera?
Jakie dokumenty są prezentowane na komitecie?
-->

1. **Przygotowanie materiałów na komitet** — summary dla decydentów (non-technical)
2. **Przekazanie pakietu dokumentów** — MDD, Validation Report, Findings Register
3. **Prezentacja na komitecie** — Model Owner + walidator prezentują
4. **Deliberacje i decyzja** — akceptacja / akceptacja warunkowa / odrzucenie
5. **Dokumentacja decyzji** — Approval Record z datą, decydentami, warunkami
6. **Aktualizacja Model Inventory** — zmiana statusu modelu

---

## Dokumenty Wymagane do Komitetu

| Dokument | Od kogo |
|----------|---------|
| Executive Summary modelu (1-2 strony) | Model Owner |
| Model Development Document (finalny) | Data Scientist |
| Validation Report | Walidator |
| Findings Register + Plan Remediation | Walidator / Model Owner |
| Regulatory Compliance Opinion (Kat. A) | Compliance / MRM |

---

## Możliwe Decyzje Komitetu

| Decyzja | Opis | Następny krok |
|---------|------|---------------|
| **Akceptacja bezwarunkowa** | Model gotowy do wdrożenia | Przejście do Etap 5.7 |
| **Akceptacja warunkowa** | Model może być wdrożony po spełnieniu warunków | Etap 5.7 z tracking warunków |
| **Odroczenie** | Wymagane dodatkowe prace — określone działania | Powrót do Etap 5.4 lub 5.5 |
| **Odrzucenie** | Model nie spełnia wymagań — decyzja o re-developmencie | Model Owner decyduje o dalszym kierunku |

---

## Approval Record — Minimalna Zawartość

<!-- PROMPT DLA AUTORA:
Opisz format Approval Record stosowany w organizacji.
Co musi być zarejestrowane w ramach śladu audytowego?
-->

Approval Record musi zawierać:
- Identyfikator modelu (Model ID z Model Inventory)
- Data akceptacji
- Decydenci (imiona, stanowiska, podpisy lub równoważne)
- Decyzja (akceptacja / akceptacja warunkowa / odrzucenie)
- Warunki (jeśli akceptacja warunkowa)
- Termin remediation findings (jeśli dotyczy)
- Referencja do Validation Report

---

## Kryteria Wyjścia — Stage Gate 6

- [ ] Akceptacja komitetu udzielona (bezwarunkowa lub warunkowa)
- [ ] Approval Record podpisany
- [ ] Status modelu w Model Inventory zaktualizowany
- [ ] Warunki wdrożenia (jeśli warunkowe) udokumentowane

---

## Zarządzanie Odstępstwami (Exceptions)

<!-- PROMPT DLA AUTORA:
Opisz procedurę wyjątkową — kiedy dopuszczalne jest wdrożenie modelu bez pełnej ścieżki?
Jakie są warunki i kto może zatwierdzić?
-->

W wyjątkowych sytuacjach (np. nagła zmiana regulacyjna, awaria modelu produkcyjnego) możliwe jest przyspieszenie procesu akceptacji zgodnie z procedurą awaryjną:
- Wymagana akceptacja [PLACEHOLDER: właściwy organ] zamiast komitetu
- Retroaktywna walidacja i formalna akceptacja w terminie [PLACEHOLDER: N tygodni]
- Pełna dokumentacja podstaw decyzji o zastosowaniu procedury awaryjnej

---

*Szablony: [Approval Record Template](../../templates/), [Executive Summary Template](../../templates/)*
