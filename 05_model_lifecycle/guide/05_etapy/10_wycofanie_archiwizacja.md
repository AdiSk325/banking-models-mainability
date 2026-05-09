# Etap 5.10: Wycofanie i Archiwizacja

> **Część:** Model Lifecycle Guide — Rozdział 5 (Etapy Lifecycle)  
> **Status:** Draft  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](../MODEL_LIFECYCLE_GUIDE.md) | [← Poprzedni: Zmiana](./09_zarzadzanie_zmiana.md) | [Powrót do: Przegląd Lifecycle](../04_przeglad_cyklu_zycia.md)

---

## Cel Etapu

Bezpieczne i kontrolowane wycofanie modelu z produkcji, z właściwą archiwizacją wszystkich artefaktów i zachowaniem możliwości odtworzenia historycznych decyzji.

---

## Kto wykonuje

| Rola | Aktywność |
|------|-----------|
| **Model Owner** | Inicjacja wycofania, koordynacja |
| **MRM** | Zatwierdzenie, aktualizacja inwentarza |
| **IT / MLOps** | Techniczne wycofanie z produkcji |
| **Compliance** | Weryfikacja wymogów archiwizacyjnych |
| **Data Steward** | Archiwizacja danych |

---

## Kiedy Wycofać Model

<!-- PROMPT DLA AUTORA:
Opisz kryteria decyzji o wycofaniu modelu.
Jak wygląda decyzja o wycofaniu vs re-development?
Kto ma prawo zaproponować wycofanie?
-->

Model powinien być wycofany gdy:

- [ ] Zastępuje go nowy, zatwierdzony model
- [ ] Proces biznesowy, który obsługiwał, został zakończony lub zmieniony
- [ ] Model nie nadaje się do dalszego użycia (niemożliwa rekalibracja/re-development w sensownym czasie)
- [ ] Wyniki monitoringu trwale wykraczają poza akceptowalne progi, bez możliwości naprawy
- [ ] Zmiana regulacyjna wyklucza dalsze stosowanie metodologii
- [ ] Decyzja biznesowa o rezygnacji z obszaru, który model obsługiwał

---

## Proces Wycofania

1. **Inicjacja wycofania** — Model Owner lub MRM proponuje wycofanie
2. **Ocena wpływu** — analiza czy istnieje model zastępczy, jakie procesy zależą od modelu
3. **Plan przejścia** — jak procesy zostaną obsłużone po wycofaniu (zastępnik, fallback)
4. **Zatwierdzenie wycofania** — Model Owner + MRM sign-off
5. **Wycofanie techniczne** — IT/MLOps dezaktywuje model w produkcji
6. **Archiwizacja** — kompletna archiwizacja wszystkich artefaktów
7. **Aktualizacja Model Inventory** — zmiana statusu na "Retired"
8. **Komunikacja** — poinformowanie interesariuszy

---

## Co Archiwizować

<!-- PROMPT DLA AUTORA:
Opisz wymagania archiwizacyjne obowiązujące w organizacji.
Jakie są okresy retencji? Gdzie przechowywane są archiwa?
Jakie są wymogi regulacyjne dotyczące archiwizacji (RODO, KNF)?
-->

Archiwizacja musi obejmować:

| Element | Okres archiwizacji | Uwagi |
|---------|--------------------|-------|
| Kod modelu (wszystkie wersje) | [PLACEHOLDER: np. 7 lat] | Repozytorium Git z tagami |
| Parametry modelu (wagi, konfiguracja) | [PLACEHOLDER] | Model Registry |
| Model Development Document | [PLACEHOLDER] | Dokumentacja formalna |
| Validation Reports (wszystkie) | [PLACEHOLDER] | Ślad audytowy |
| Approval Records | [PLACEHOLDER] | Ślad audytowy |
| Change Log | [PLACEHOLDER] | Historia zmian |
| Monitoring Reports | [PLACEHOLDER: np. 5 lat] | Historia działania |
| Dane treningowe (snapshot) lub dokumentacja danych | [PLACEHOLDER] | RODO compliance |
| Retirement Record | Stale | Dokumentacja zamknięcia |

> ⚠️ **RODO:** Archiwizacja danych osobowych musi być zgodna z RODO — dane osobowe mogą wymagać anonimizacji lub usunięcia po upływie okresu retencji.

---

## Retirement Record — Minimalna Zawartość

Retirement Record musi zawierać:
- Identyfikator modelu (Model ID)
- Data wycofania
- Powód wycofania
- Model zastępujący (jeśli istnieje)
- Plan przejścia (jak procesy są obsługiwane po wycofaniu)
- Potwierdzenie archiwizacji artefaktów
- Model Owner i MRM sign-off
- Informacja dla audytu: gdzie przechowywane są archiwa

---

## Kryteria Wyjścia — Stage Gate 9

- [ ] Retirement Record kompletny i podpisany
- [ ] Model wycofany z infrastruktury produkcyjnej
- [ ] Artefakty zarchiwizowane
- [ ] Model Inventory zaktualizowany (status: "Retired")
- [ ] Model Owner + MRM sign-off

---

## Specyfika dla Modeli Regulacyjnych (Kategoria A)

<!-- PROMPT DLA AUTORA:
Opisz czy wycofanie modelu regulacyjnego wymaga notyfikacji nadzorcy.
Jak długo muszą być przechowywane archiwa modeli IRB?
-->

Dla modeli Kategorii A:
- Ocena czy wycofanie wymaga notyfikacji regulatora (EBC, KNF)
- Okres archiwizacji może być dłuższy niż standardowy — zgodnie z wymogami regulacyjnymi
- Zachowanie możliwości odtworzenia historycznych decyzji regulacyjnych przez wymagany okres

---

*Szablony: [Retirement Record Template](../../templates/), [Archive Checklist](../../templates/)*
